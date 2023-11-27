
### 事务

````go
    //获取传话
	session, err := pubifs.IMongoDBS.Beginwork(me.dbName)
    if err != nil {
		return err
	} 
    //获取传话上下文
    sCTX, err := pubifs.IMongoDBS.GetWorkSessionContext(dbName, context.TODO(), session)
    if err != nil {
        return err
    } 
/*  
    arg := wizdeclare.MongoArgInsOne{}
    arg.DBName = "xxx"
    arg.Collection = "yyy"
    arg.SessionCtx = sCTX
    arg.Doc = bson.D{{Key: "aaa",Value: "v"}}
    opt := new(options.InsertOneOptions)
    arg.Opts =  []*options.InsertOneOptions{opt},
    pubifs.IMongoDBS.InsertOne(arg)
*/
    //事务中执行语句
    pubifs.IMongoDBS.InsertOne(wizdeclare.MongoArgInsOne{
		MongoArgBase:wizdeclare.MongoArgBase{DBName: "xxx",Collection:"yyy", SessionCtx: sCTX},
		Doc:bson.D{{Key: "aaa",Value: "v"}},
        Opts: []*options.InsertOneOptions{&options.InsertOneOptions{}},
	})
   ......
   //提交事务
   	
	err := pubifs.IMongoDBS.CommitWork(dbName,session)
	if err != nil{
        if err := pubifs.IMongoDBS.RollbackWork(dbName,session);err!=nil{
            return err
        } 
        return err
	}
	

````

### 批量事务执行

````go
//要执行的回调
func aaa(sCtx mongo.SessionContext) (any, error){
    pubifs.IMongoDBS.InsertOne(wizdeclare.MongoArgInsOne{
		MongoArgBase:wizdeclare.MongoArgBase{DBName: "xxx",Collection:"yyy", SessionCtx: sCTX},
		Doc:bson.D{{Key: "aaa",Value: "v"}},
        Opts: []*options.InsertOneOptions{&options.InsertOneOptions{}},
	})
}
funs := []func(sCtx mongo.SessionContext) (any, error){}
//注入切片
func = append(funs,aaa)
//内部自动开启事务相关会话，事务上下文。
_,err := pubifs.IMongoDBS.BulkExec(dbName,funs)
````



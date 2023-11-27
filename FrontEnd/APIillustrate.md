
### lang  

````text
作用： 更新国际化内容，国际化内容存放在_sys_i18n _sys_i18n_det表中,在
````







#### 传入参数

```json

{
    key:""
    data:[
       {
          lang : "zh-CN",                      
          value: ""
       }
    ]
}
```

* 参数说明：

|                属性名                | 数据类型 | 是否必须 |                                                                                                                   说明                                                                                                                    |
| :----------------------------------: | :------: | :------: | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
|                 key                  |  string  |    是    |                                                                                                                国际化key值                                                                                                                |
| <span style="color:#f80">data</span> |  array   |    是    |                                                                                                                 数据内容                                                                                                                  |
|                 lang                 |  string  |    是    | [zh-CN\|en-US]     国际语言标准，详见[国际化语言对照表](https://wenku.baidu.com/view/b24b3c42986648d7c1c708a1284ac850ad020490.html?_wkts_=1690253523843&bdQuery=%E5%9B%BD%E9%99%85%E5%8C%96%E8%AF%AD%E8%A8%80%E5%AF%B9%E7%85%A7%E8%A1%A8) |
|                value                 |  string  |    是    |                                                                                                           对应data[i].lang的值                                                                                                            |



#### 返回参数

```json
{
    "success":true,
    "msg":"200,BE,0,Successful operation",
    "data":""
}
```

* 参数说明  

| 属性名  | 数据类型 | 说明     |
| ------- | -------- | -------- |
| success | boolean  | 状态     |
| msg     | string   | 消息说明 |
| data    | any      | 返回数据 |

### setFunConf 功能配置

传入参数



???





### getPartData

#### 传入参数

````json
{
	"funName": "",//功能名
    "tableName":"", //表名或为空
    "dbType":"mysql",
    "pageNo":1,
    "pageSize":2,
	"lang": "zh-CN",
    "globalSearch": "",//全局模糊搜索
	"filter": {"fieldName1":1,"fieldName2":"2"},  //bson表达式
    "rule": {
		   "QBE": {
			     "funName": "",
			     "fieldName": ""
           },
           "statistics":[  //统计信息
                         {
                             "alais":"",   //返回的别名不能与查询字段同名
                             "pipeline":{} //一个bson管道表达式
                         }
         ], 
    },
	 "sort": [{
			"field": "title",
			"value": "asc",
			"weight": 0,
		}] 
}
````
参数说明：

|    属性名    | 数据类型 | 是否必须 |                       说明                       |
| :----------: | :------: | :------: | :----------------------------------------------: |
|   funName    |  string  |    是    |                      功能名                      |
|  tableName   |  string  |    是    |                    表名或为空                    |
|    dbType    |  string  |    是    |                  数据库                   |
|    pageNo    |  number  |    是    |                     第几页                    |
|   pageSize   |  number  |    是    |                     数据条数                    |
|     lang     |  string  |    是    |                  语言                  |
| globalSearch |  string  |    是    |                   全局模糊搜索                   |
|    filter    |   obj    |    是    |                    bson表达式                    |
|  fieldName1  |  number  |    是    |            对应filter的键值          |
|  fieldName2  |  number  |    是    |            对应filter的键值           |
|     rule     |   obj    |    是    |                                                  |
|     QBE      |   obj    |    是    |                    rule的键值,QBE查询                    |
|   funName    |  string  |    是    |                    QBE的键值                     |
|  fieldName   |  string  |    是    |                    QBE的键值                     |
|  statistics  |  array   |    是    |               rule的键值,统计信息                |
|    alais     |  string  |    是    | statistics[0]的键值,返回的别民不能与查询字段同名 |
|   pipeline   |   obj    |    是    |      statistics[0]的键值,一个bson管道表达式      |
|     sort     |  array   |    是    |                                                  |
|    field     |  string  |    是    |           sort[0]的键值           |
|    value     |  string  |    是    |            sort[0]的键值             |
|    weight    |  number  |    是    |              sort[0]的键值               |


#### 返回参数 

````json
{
  "success": true,
  "msg": "200,BE,0,Successful operation",
  "data":{
    "total": 5,
    "pageTotal": 5,
    "summaryInfo": {},
    "rows": [
   
    ]
  }
}
````

* 参数说明 

| 属性名        | 数据类型 | 说明       |
| ------------- | -------- | ---------- |
| success       | boolean  | 状态       |
| msg           | string   | 消息说明   |
| data          | object   | 数据       |
| _ total       | number   | 数据总条数 |
| _ pageTotal   | number   | 总页数     |
| _ summaryInfo | object   |            |
| _ rows        | array    | 行数据     |

#### 属性说明

* filter[逻辑命令]

  | 标识符 | 说明  |                                     语法                                     | 例子  |
  | :----: | :---: | :--------------------------------------------------------------------------: | :---: |
  |  $and  |  与   | { $and: [ { <expression1> }, { <expression2> } , ... , { <expressionN> } ] } |       |
  |  $or   |  或   |                { field: { $not: { <operator-expression> } } }                |       |
  |  $not  |  非   |  { $or: [ { <expression1> }, { <expression2> }, ... , { <expressionN> } ] }  |       |
  |  $nor  | 或非  |  { $nor: [ { <expression1> }, { <expression2> }, ...  { <expressionN> } ] }  |       |


* filter[比较命令]

  | 标识符 |   说明   |                           语法                           | 例子  |
  | :----: | :------: | :------------------------------------------------------: | :---: |
  |  $eq   |   等于   |                { field: { $eq: value } }                 |       |
  |  $gt   |   大于   |                { field: { $gt: value } }                 |       |
  |  $lt   |   小于   |                { field: { $lt: value } }                 |       |
  |  $ne   |  不等于  |                { field: { $ne: value } }                 |       |
  |  $gte  | 大于等于 |                { field: { $gte: value } }                |       |
  |  $lte  | 小于等于 |                { field: { $lte: value } }                |       |
  |  $in   |   包含   | { field: { $in: [<value1>, <value2>, ... <valueN> ] } }  |       |
  |  $nin  |  不包含  | { field: { $nin: [ <value1>, <value2> ... <valueN> ] } } |       |

* 过滤举例

  ````json
   {"fieldName1":1,"fieldName2":"2"}                                                             field1 = 1 AND fieldName = '2'
   {"fieldName1":{"$gt":1}}                                                                      fieldName1 > 1
   {"$and":[{"a":1},{"$or":[{"b":2},{"c":3}]}]}                                                  (a = 1) AND (b = 2 OR c = 3)
   {"nor":[{"a":1},{"b":{"$gte":8}}]}                                                            NOT((a = 1) OR (b >= 8))
   {"aaa":{"$in":[1,2,3]}}                                                                       aaa IN(1,2,3)
   {"aaa":{"$nin":[1,2,3]}}                                                                      aaa NOT IN(1,2,3)
  ````


* statistics 统计表达式

  ````tex
  平均值
  一个分组的平均值表达式
  {
         "$group":
           {
             "_id": "$item",
             "avgAmount": { "$avg": { "$multiply": [ "$price", "$quantity" ] } },
             "avgQuantity": { "$avg": "$quantity" }
           }
    }
    
   绝对值
   "$project": { "delta": { "$abs": { "$subtract": [ "$start", "$end" ] } } }
   最小值
   
    '$group': {'_id': '$name', 'minField': {'$min': '$field'}}
  ````

  


* 高级过滤规则[待定]

  * 条件符号

  * 、>、<、!=、<>、- 只限数据的栏位的通配表达方法。

    |  符号  |   含义   |                                              例子                                              |
    | :----: | :------: | :--------------------------------------------------------------------------------------------: |
    | 无符号 |   等于   |                                       9，搜索等于9的内容                                       |
    |   =    |   等于   |                                      =9，搜索等于9的内容                                       |
    |   >    |   大于   |                                      >9，搜索大于9的内容                                       |
    |   <    |   小于   |                                      <9，搜索小于9的内容                                       |
    |   !=   |  不等于  |                                     !=9，搜索不等于9的内容                                     |
    |   <>   |  不等于  |                                     <>9，搜索不等于9的内容                                     |
    |   :    |   范围   |                                   0-9，搜索大于0小于9的内容                                    |
    |   %    | 模糊查询 |   a%，搜索开头为a的内容，如abc。%a，搜索结尾为a的内容，如cba。%a%，搜索包含a的内容，如cbabc    |
    |   ?    | 模糊查询 | 同%。a?，搜索开头为a的内容，如abc。?a，搜索结尾为a的内容，如cba。?a?，搜索包含a的内容，如cbabc |
    |   \|   | 多个查询 |                                    a \| b搜索等于a或等于b的                                    |

  * 内转译符号

    | 符号 | 例子                                                     |
    | ---- | -------------------------------------------------------- |
    | \    | a\%，搜索等于“a%”的内容，而不认为是模糊查询开头为a的内容 |
    | `    | \`a%`，搜索等于“a%”的内容，而不认为是模糊查询开头        |  |

* 特殊条件表达式[待定]

  - md5
    1487509e878ff01e = is null
    3cbec5745f51eacf = is not null
    f3b524343c9438bc = is space
    82a4bf8bcd5f65e5 = is not space

* 传出数据

  * 成功

    ````json
    {
    	"success": true,
    	"total": 0,
    	"pageTotal": 0,
    	"rows": []
    }
    ````

* 参数说明 

  | 属性名        | 数据类型 | 说明       |
  | ------------- | -------- | ---------- |
  | success       | boolean  | 状态       |
  | total       | number   | 数据总条数 |
  | pageTotal   | number   | 总页数     |
  | rows        | array    | 行数据     |
    

  * 失败

    ````json
    {
    	"success": false,
    	"msg":""
    }
    ````
  * 参数说明 

  | 属性名        | 数据类型 | 说明       |
  | ------------- | -------- | ---------- |
  | success       | boolean  | 状态       |
  | msg       | string  | 消息说明       |

### baseGrid类参数

````json
{
    "tableName": "xxx",
    "dbType": "mysql", //mongo|mysql
     "rule":{},//全局策略
    "insertRecords": {
       
        "scope":{"xxx":xxx}, //排序时，给定的范围过滤条件条件 bson格式
        "data": [
                  {
                    //如果是关联表在相字段要插入相应关联ID值
                    rowData:[{"field": <fieldName>,"value": <value>}],
                    fileInfo:{}, //表示此行文件字段的处理
                    rule:{}, //行策略
                  }
                ]
    },
    "removeRecords": {
        rule:{},
        filter:{"$and":[{"id":{"$in":[1, 2, 3]}},{"xxx":1}]}
    },
    "updateRecords": {
                      data:[
                          {
                             filter:{"id":123},
                             fileInfo:{}, //表示此行文件字段的处理
                             rule:{}, //行策略
                             rowData:[{"field": <fieldName>,"value": <value>}]
                          }
                      ]
     }
       
}
````

 * 参数说明

| 属性名        | 数据类型 | 是否必须 | 说明                                                                                                     |
| ------------- | -------- | -------- | -------------------------------------------------------------------------------------------------------- |
| tablename     | string   | 是       |                            表名                                                                            |
| dbType        | string   | 是       | 数据库,可选mongo/mysql                                                                                |
| rule          | obj      | 是       | 全局策略                                                                                                 |
| insertRecords | obj      | 是       |             新增数据                                                                                             |
| scope         | obj      | 是       | 对应insertRecords的键值，排序时，给定的范围过滤条件 bson格式                                             |
| data          | array    | 是       | 对应insertRecords的键值                                                                                  |
| rowData       | array    | 是       | 对应data[0]的值，如果是关联表在相应字段要插入相应关联ID值，示例[{"field": <fieldName>,"value": <value>}] |
| fileInfo      | obj      | 是       | 对应data[0]的值，表示此行文件字段的处理                                                                  |
| rule          | obj      | 是       | 对应data[0]的值，行策略                                                                                  |
| removeRecords | obj      | 是       |                                                                                                          |
| rule          | obj      | 是       | 对应removeRecords的键值                                                                                  |
| filter        | obj      | 是       | 对应removeRecords的键值,默认{"$and":[{"id":{"$in":[1, 2, 3]}},{"xxx":1}]}                                |
| updateRecords | obj      | 是       |                                                                                                          |
| data          | array    | 是       | 对应updateRecords的键值                                                                                  |
| filter        | obj      | 是       | 对应data[0]的值，默认{"id":123}                                                                          |
| rowData       | array    | 是       | 对应data[0]的值，如果是关联表在相应字段要插入相应关联ID值，示例[{"field": <fieldName>,"value": <value>}] |
| fileInfo      | obj      | 是       | 对应data[0]的值，表示此行文件字段的处理                                                                  |
| rule          | obj      | 是       | 对应data[0]的值，行策略                                                                                  |


### CTD

#### 传入参数 

````json
{
    "tableName": "xxx",
    "dbType": "mysql", //mongo|mysql
     "rule":{},//全局策略
    "insertRecords": {
        "scope":{"xxx":xxx}, //排序时，给定的范围过滤条件条件 bson格式
        "data": [
                  {
                    rowData:[{"field": <fieldName>,"value": <value>}],
                    fileInfo:{}, //表示此行文件字段的处理
                    rule:{}, //行策略
                  }
                ]
    },
    "removeRecords": {
        rule:{},
        filter:{"$and":[{"id":{"$in":[1, 2, 3]}},{"xxx":1}]}
    },
    "updateRecords": {

                      data:[
                          {
                             filter:{"id":123},
                             fileInfo:{}, //表示此行文件字段的处理
                             rule:{}, //行策略
                             rowData:[{"field": <fieldName>,"value": <value>}]
                          }
                      ]
     }
       
}
````


* 参数说明

| 属性名        | 数据类型 | 是否必须 | 说明                                                                                                     |
| ------------- | -------- | -------- | -------------------------------------------------------------------------------------------------------- |
| tablename     | string   | 是       |            表名或                                                                                              |
| dbType        | string   | 是       | 数据库,可选mongo/mysql                                                                                |
| rule          | obj      | 是       | 全局策略                                                                                                 |
| insertRecords | obj      | 是       |                                                                                                          |
| scope         | obj      | 是       | 对应insertRecords的键值，排序时，给定的范围过滤条件 bson格式                                             |
| data          | array    | 是       | 对应insertRecords的键值                                                                                  |
| rowData       | array    | 是       | 对应data[0]的值，如果是关联表在相应字段要插入相应关联ID值，示例[{"field": <fieldName>,"value": <value>}] |
| fileInfo      | obj      | 是       | 对应data[0]的值，表示此行文件字段的处理                                                                  |
| rule          | obj      | 是       | 对应data[0]的值，行策略                                                                                  |
| removeRecords | obj      | 是       |                                                                                                          |
| rule          | obj      | 是       | 对应removeRecords的键值                                                                                  |
| filter        | obj      | 是       | 对应removeRecords的键值,默认{"$and":[{"id":{"$in":[1, 2, 3]}},{"xxx":1}]}                                |
| updateRecords | obj      | 是       |                                                                                                          |
| data          | array    | 是       | 对应updateRecords的键值                                                                                  |
| filter        | obj      | 是       | 对应data[0]的值，                                                                          |
| rowData       | array    | 是       | 对应data[0]的值，如果是关联表在相应字段要插入相应关联ID值，示例[{"field": <fieldName>,"value": <value>}] |
| fileInfo      | obj      | 是       | 对应data[0]的值，表示此行文件字段的处理                                                                  |
| rule          | obj      | 是       | 对应data[0]的值，行策略                                                                                  |

#### 参数说明

* scope 

  * 排序时的过滤条件，是mongo bson格式的jons表达式

  * 如果需要排序在新增或者更新时对\_sort\_给小数位的值触发自动排序。

* 插入排序

  ````tex
  insertRecords.scope <bsonExpr>
  1、表达式是一个bson表达式josn格式，如遇到长整型值需用字符串表达。如果为空则表示所有数据(如果数据量大会耗性能)。
  2、系统在插入新数据时每个表都有一个浮点类型的管理字段_sort_，常规情况下这个值都是整数。
  3、当要插入排序时以0.000001单位加减，后端检测到插入_sort_字段值小数位后会根据scope的过滤范围重新排序重写_sort_为整数。
  ````


#### 返回参数

````json
{
	"success": true,
	"msg": "200,BE,0,Successful operation",
	"detail": {
		"insIDs": ["307821439044550656"],
		"insQty": 1,
		"updQty": 0,
		"delQty": 0
	}
}
````

* 参数说明 

| 属性名        | 数据类型    | 说明     |
|------------|---------|--------|
| success    | boolean | 状态     |
| msg        | string  | 消息说明   |
| detail     | object  | 修改细节   |
| --  insIDs | array   | 新增数据ID |
|  -- insQty | number  | 新增数    |
|  -- updQty | number  | 更新数    |
|  -- delQty | number  | 删除数    |



### BPA

#### 接口描述  

单据的标准传参格式，head表示头部表单json，body表示表格json

#### 传入参数 

参数说明



````json
{
    "head": { 
                "tableName": "_sys_fun",
                "dbType":"mysql",                                    //mongo | mysql
                 rule:{},
                "insertRecords": {
                    rule:{},
                    fileInfo:{},
                    rowData:[{"field": "title","value": ""}]
                },
                "updateRecords": {
                    rule:{},
                    fileInfo:{},
                    filter:{},
                    rowData:[{"field": "title","value": "abcd"}]
                },
                "removeRecords": {
                    "filter":{"id":xx}, //bson with json
                    "rule":{}, //删除单头的规则
                    "mto": [{
                        "rule":{}， //删除 单身的规则 
                        "dbType":"" //单身数据库类型
                        "tableName": "t1",
                        "filter":{"billID":123} //删除 单身的条件
                    }]
                }
       
   	 },
    "body": {
        rule:{},
        data:[
            {
                "tableName": "",
                "dbType":"mysql", //mongo | mysql
                "insertRecords": {
                     //排序时，给定的范围过滤条件条件bson格式
                     // 当basepanel 单身新增时：是单身m2o 主单id的单身字段与值。
                     // 当basepanel 新增单据时，此处是单身的对应字段
                     "scope":{field:"xxx": value:xxx},
                     "data":[
                             {
                                 rule{},
                                 fileInfo:{},
                                   //如果是关联表在相字段要插入相应关联ID值
                                 rowData:[{ "field": "fieldName","value": <value>}],

                             }

                          ]
                   },
                   "updateRecords": {
                             
                              "data":[
                                         {
                                             rule{},
                                             filter:{},
                                             fileInfo:{},
                                             rowData:[{ "field": "fieldName","value": <value>}],

                                         }
                                    ]
                  },
                 "removeRecords":{
                    rule:{},
                    filter:{"id":{"$in":[1, 2, 3]}}, 
                },
    		}
			]
  		}
}
````

#### 参数说明

* head 单头数据
  * 在只操作单身时非必须属性。
  * 在操作单头时必须，如果有此属性会检查子属性合法性
    * tableName,dbType 是否有值
    * fileInfo是否存在
    * updateRecords,insertRecords,removeRecords 三选一

* body 单身数据
  * 在只操作单头时非必须属性。
  * 在操作单身时， 如果有此属性会检查子属性全法性。
    * tableName,dbType,mto
    * updateRecords,insertRecords,removeRecords 至少有一项操作



* 插入排序

  ````tex
  insertRecords.scope <bsonExpr>
  1、表达式是一个bson表达式josn格式，如遇到长整型值需用字符串表达。
  2、系统在插入新数据时每个表都有一个浮点类型的管理字段_sort_，常规情况下这个值都是整数。
  2、当要插入排序时以0.000001单位加减，后端检测到插入_sort_字段值小数位后会根据scope的过滤范围重新排序重写_sort_为整数。
  ````

#### 返回参数

````json
{
	"success": true,
	"msg": "200,BE,0,Successful operation",
	"detail": {
		"insIDs": ["307821439044550656"],
		"insQty": 1,
		"updQty": 0,
		"delQty": 0
	}
}
````
* 参数说明 

| 属性名        | 数据类型    | 说明     |
|------------|---------|--------|
| success    | boolean | 状态     |
| msg        | string  | 消息说明   |
| detail     | object  | 修改细节   |
| --  insIDs | array   | 新增数据ID |
|  -- insQty | number  | 新增数    |
|  -- updQty | number  | 更新数    |
|  -- delQty | number  | 删除数    |


#### 单据新增

- 在初始操作新增单头或新增单头和单身的处理逻辑。单头产生ID 对应 单身明细字段插入单身 。单身明细字段在mto对象中。
- 如果单头insertRecords不为空时触发【单身新增】处理逻辑。只处理单头或单身的insertRecerds数据，如单身insertRecords为空。则只新增单头。

#### 单据删除

- 单头removeRecord有数据时触发。先删除单身所有数据再删除单头数据。对象body数据无效

#### 其它

- 在单头insertRecerds和removeRecords为空的情况下，单头的updateRecords和单身所有跟ctd API同理

#### 排序

每次插入时会检查是否带小数的__sort__,自动处理。

#### 冲突异常处理

- 如单头insertRecords、removeRecords、updateRecords 只能三者其一有数据，否则会触发方向选择错误。

### treeGrid

#### 传入参数

````json
{
    "mode": "", //stepTree/flatTree
    "tableName": "",
    "fields": [],
    "reportPlanId": null, //报表的方案id
    "options": {
        "hasChild": "HASCHILD",
        "childField": "",
        "childValue": "",
        "isLazy": false
    },
    "filter": [
        {
            "field": "",
            "value": ""
        }
    ]
}
````

##### 说明

| 属性名       | 数据类型 | 是否必须 | 说明                              |
| ------------ | -------- | -------- | --------------------------------- |
| mode         | string   | 是       | 可选stepTree/flatTree             |
| tableName    | string   | 是       |   表名                               |
| fields       | array    | 是       |    字段组                               |
| reportPlanId | string   | 是       | 报表的方案id                      |
| options      | obj      | 是       |                                   |
| hasChild     | string   | 是       | 对应options的键值 |
| childField   | string   | 是       | 对应options的键值                 |
| childValue   | string   | 是       | 对应options的键值                 |
| isLazy       | boolean  | 是       | 对应options的键值，默认false      |
| filter       | array    | 是       |     过滤                              |
| field        | string   | 是       | 对应filter的键值                  |
| value        | string   | 是       | 对应filter的键值                  |

### gpfd 

#### 接口描述  
打印API，接口疑似换了

#### 传入参数

````json
{
  "rule": {},
  "sort": [],
  "filter": {},//mongo bson格式
  "lang": "zh-CN",
  "funName": "test1",
  "dbType": "mongo",
  "tableName": "test1",
  "fieldName": "_sys_fun_group_id",
    "sort": [{                      //非必须
			"field": "",
			"value": "asc",
			"weight": 0,
		}] 
}
````



#### 参数说明

| 属性名    | 数据类型 | 是否必须 | 说明                        |
| --------- | -------- | -------- | --------------------------- |
| rule      | obj      | 是       |                             |
| sort      | array    | 是       |                             |
| filter    | obj      | 是       | mongo bson格式              |
| lang      | string   | 是       | 语言               |
| funName   | string   | 是       |   功能名             |
| dbType    | string   | 是       | 数据库类型                |
| tableName | string   | 是       | 表名               |
| fieldName | string   | 是       | 字段名     |
| sort      | array    | 是       |       排序  ，非必须                    |
| field     | string   | 是       | 对应sort[0]的键值，字段名           |
| value     | string   | 是       | 对应sort[0]的键值,字段值 |
| weight    | number   | 是       | 对应sort[0]的键值    |


#### 返回参数 

````json
{
  "success": true,
  "msg": "200,BE,0,Successful operation",
  "total": 4,
  "pageTotal": 10,
    //如果指定字段有对应虚拟字段则全部返回
  "rows": [
    
  ]
}
````

* 参数说明 

| 属性名        | 数据类型    | 说明     |
|------------|---------|--------|
| success    | boolean | 状态     |
| msg        | string  | 消息说明   |
| total       | number   | 数据总条数 |
| pageTotal   | number   | 总页数     |
| rows   | array   | 行数据，如果指定字段有对应虚拟字段则全部返回     |

### expxls

#### 接口描述
导出接口，疑似新增fileName字段

#### 传入参数

````json
{
    "fields":[],
    "rule":{},
    "lang": "zh-CN",
    "dbType":"",
    "tableName":"",
    "funName":"",
    "globalSearch": "",
    "filter": {},
    "sort": [{
        "field": "",
        "value": "",
        "weight": 0
    }]
}
````

#### 参数说明

| 属性名       | 数据类型 | 是否必须 | 说明            |
| ------------ | -------- | -------- | --------------- |
| fields       | array    | 是       |                 |
| rule         | obj      | 是       |                 |
| lang         | string   | 是       | 默认"zh-CN"     |
| dbType       | string   | 是       |                 |
| tableName    | string   | 是       |     表名            |
| funName      | string   | 是       |                 |
| globalSearch | string   | 是       |                 |
| filter       | obj      | 是       |                 |
| sort         | array    | 是       |                 |
| field        | string   | 是       | 对应sort[0]的值 |
| value        | string   | 是       | 对应sort[0]的值 |
| weight       | number   | 是       | 对应sort[0]的值 |

#### 返回参数 

````json
{
  "success": true,
  "msg": "200,BE,0,Successful operation",
  "total": 4,
  "pageTotal": 10,
  "rows": [
  ]
}
````

| 属性名        | 数据类型    | 说明     |
|------------|---------|--------|
| success    | boolean | 状态     |
| msg        | string  | 消息说明   |
| total       | number   | 数据总条数 |
| pageTotal   | number   | 总页数     |
| rows   | array   | 行数据    |

### apiQuery



#### 传入参数

````json
{
	"funName": "",//功能名
    "tableName":"",//表名 
    "dbType":"mysql",
    "lang": "zh-CN", 
    "fields":["f1","f2"],
    "rule": {},
    "filter": {"fieldName1":1,"fieldName2":"2"},  //bson表达式
	 "sort": [{
			"field": "title",
			"value": "asc",
			"weight": 0,
		}] 
}
````



#### 参数说明

| 属性名     | 数据类型 | 是否必须 | 说明                         |
| ---------- | -------- | -------- | ---------------------------- |
| funName    | string   | 是       | 功能名                       |
| tableName  | string   | 是       | 表名                         |
| dbType     | string   | 是       | 默认"mysql"                  |
| lang       | string   | 是       | 默认"zh-CN"                  |
| fields     | array    | 是       | 默认["f1","f2"]              |
| rule       | obj      | 是       |                              |
| filter     | obj      | 是       | bson表达式                   |
| fieldName1 | string   | 是       | 默认'1'                      |
| fieldName2 | string   | 是       | 默认'2'                      |
| sort       | array    | 是       |                              |
| field      | string   | 是       | 对应sort[0]的值，默认"title" |
| value      | string   | 是       | 对应sort[0]的值 ,默认"asc"   |
| weight     | number   | 是       | 对应sort[0]的值 ,默认0       |

````json 
替换1.0中query.action
注意：
1、如果查询的功能或表需要权限控制，需要添加到系统功能。
2、如果需要复杂查询，需要在相应数据库【mongo|mysql|...】中加视图来体现.
````



#### 返回参数

````json
{
  "success": true,
  "msg": "200,BE,0,Successful operation",
  "total": 5,
  "pageTotal": 5,
  "summaryInfo": {},
  "rows": [
   //如果指定字段有对应虚拟字段则全布返回
  ]
}
````

### getToken

#### 传入参数

````json
{
    "userNo":"",
    "userPass":""
}
````

#### 参数说明

| 属性名   | 数据类型 | 是否必须 | 说明 |
| -------- | -------- | -------- | ---- |
| userNo   | string   | 是       |      |
| userPass | string   | 是       |      |

#### 返回参数



````json
{
  "success": true,
  "msg": "200,BE,0,Successful operation",
  "total": 4,
  "pageTotal": 10,
    //如果指定字段有对应虚拟字段则全布返回
  "rows": [
    {
        field:"",
        value:""
        virtualField:""
        virtualValue:""
    }
  ]
}
````

### Login

#### 传入参数

````json
{
    "userNo":"",
    "userPass":""
}
````

| 属性名   | 数据类型 | 是否必须 | 说明 |
| -------- | -------- | -------- | ---- |
| userNo   | string   | 是       |      |
| userPass | string   | 是       |      |

##### 参数说明

#### 返回参数

````json
{
	"msg": "200,BE,0,Successful operation",
	"success": true,
	"token": "",
	"userID": "216119610972307456",
	"userName": "admin",
	"userNo": "admin"
}
````


### upload

#### 传入参数

````json
{
  "funInfo": [
    {
      "funName": "quote_table",
      "fileName": "API.xlsx"
    }
  ],
  "lang": "zh-CN",
  "type": "import",
  "dataHandle": "insert",
  "option": "import",
  "mode": "strict"
}
````

| 属性名   | 数据类型 | 是否必须 | 说明 |
| -------- | -------- | -------- | ---- |
| userNo   | string   | 是       |      |
| userPass | string   | 是       |      |

##### 参数说明

#### 返回参数

````json
{
	"msg": "200,BE,0,Successful operation",
	"success": true,
	"token": "",
	"userID": "216119610972307456",
	"userName": "admin",
	"userNo": "admin"
}
````



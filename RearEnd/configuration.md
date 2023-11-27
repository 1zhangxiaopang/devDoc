
* 系统表配置
  
  在conf.go中map变量sysDBFuns配置系统中所有母数据库表名;
  
  ```js
  //是否系统表
  pubifs.Icofnig.IsSysTable(tableName string) bool 
  
  // 格式化系统表字串，如果非母数据库表则返回原表 
  pubifs.Iconfig.FmtSysTableStr(tableName) string
  ```

* 购买方配置
  
  在buyerInfo.go中配置map变量buyerInfoMap;在conf.go中buyerTitle中指定；

* 后端版本
  
   conf.go -> sysVersion

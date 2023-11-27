
````json
外部API采用两种登录方式,统一采用header验证方式

1、key 由系统管理员发放登录key.
   在请求头Header.Authorization增加value
   Authorization:Basic <key>
2、token
    在请求头Header.Authorization增加value
   Authorization:Bearer <token>
3、如果要采用token验证,通过key获取token
   get http://localhost:8080/api/gettoken?key=<key>
   返回：
      {
	"code": 200,
	"status": "OK",
	"message": "Successful operation",
	"data": {
		"userID": 420162251547213824, 
		"userNo": "guest",
		"userName": "guest",
		"dbName": "xcsys",
		"issuedAt": 1696899993,
		"expiresAt": 1696902873,
		"token": "..."
	}
}
   
````


####更改当前用户密码

* 格式：
  *\_\_resetPWD\_\_\`cmdID\`oldPWD\`newPWD#

* \*号表示命令开始，#号表示命令结束，\`反分号表示分隔符。

* \_\_resetPWD\_\_ 更改当前用户密码，前后加两个下划线。

* cmdID 表示产生唯一请求的编号，以便服务器返回消息中的对应。

* oldPWD 旧密码，不可明文，需前端密文传送

* newPWD 新密码，不可明文，需前端密文传送。

* **举例**
  *\_\_resetPWD\_\_\`1234567\`KK98XX\`UD89==#

* 成功返回
  
  ```json
  {"success":true,"cmdID":1234567,"msg":""｝
  ```

* 失败返回

```json
{"success":false,"cmdID":1234567,"msg":"error code"}
```

####GET API

* 格式：
  *\_\_get\_\_\`cmdID\`getName\`params#

* \*号表示命令开始，#号表示命令结束，\`反分号表示分隔符。

* \_\_resetPWD\_\_ 更改当前用户密码，前后加两个下划线。

* cmdID 表示产生唯一请求的编号，以便服务器返回消息中的对应。

* getName getAPI 调用名。

* params 参数。

* **举例**
  *\_\_get\_\_\`1234567\`testName\`{...}#

* 成功返回
  
  ```json
  {"success":true,"cmdID":1234567,"totle":100,"rows":[...]｝
  ```

* 失败返回

```json
{"success":false,"cmdID":1234567,"msg":"error code"}
```


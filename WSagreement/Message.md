
#### 发送消息

* 格式：
  *\_\_sendMsg\_\_\`cmdID\`toObj\`fromUserNo\`level\`message#

* \*号表示命令开始，#号表示命令结束，\`反分号表示分隔符。

* \_\_sendMsg\_\_ 发送消息，前后加两个下划线。

* cmdID 表示产生唯一请求的编号，以便服务器返回消息中的对应。

* toObj 接收对象,JSON格式:[用户编号|用户组编号|角色],用户编号可以是"\_\_AllUser\_\_",代表所有在线用户。

* fromUserNo  发送人。

* level 消息等级。消息等级详见->消息规范

* message内容。
  
   1·待办事项通知 ：{"type":"sysMsg","property":"pendingApprovalQty"}
   2·公告通知 :{"type":"sysMsg","property":"readMsgQty"}
   3·消息提示 :{"type":"sysMsg","property":"reminderQty"}

* **举例**

* **toObj**
  
  ```json
  {
    "userNos": ["admin", "jack"],  //用户编号
    "userGroupNos": ["DVL", "HR"], //用户组编号
    "roles": [{                    //角色
        "roleType": 0,
        "objId": 1
    }]
  }
  ```

*\_\_sendMsg\_\_\`1234567\`{"userNos":["admin","jack"],"userGroupNos":["DVL","HR"],"roles":[{"roleType":0,"objId":1}]}\`snow\`10\`hello#
 发送一个提示性消息给jack

 *\_\_sendMsg\_\_\`1234567\`{"userNos":["\_\_AllUser\_\_"],"userGroupNos":[],"roles":[]}\`snow\`10\`hello#
 发送一个提示性广播消。
 *__sendMsg__`1234567`{"userNos":[],"userGroupNos":[],"roles":[{"roleType":2,"objId":2}]}`ssj`10`hello#

* 成功返回
  
  ```json
  {"success":true,"cmdID":1234567｝
  ```

* 失败返回

```json
{"success":false,"cmdID":1234567,"msg":"error code"}
```

#### 接收发送消息（2.0）

```
接收
{"__message__":msgJSON}
msgJSON说明：
 1·待办事项通知
 {"type":"SYS_MSG","data":{"property":"pendingApprovalQty","count":1}}
 2·公告通知
 {"type":"SYS_MSG","data":{"property":"readMsgQty","count":1}}
 3·消息提示
 {"type":"SYS_MSG","data":{"property":"reminderQty","count":1}}
 4.更新token
 {"type":"REFRESH_TOKEN","data":{"token":"xxx"}}
 

 
 发送
{
"FromHubID":"ALL",
"FromUserNo":"admin",
UsersMsg: [{"ToUserNo":"xxx","Msg": xxx }]
}

 
 
 
 
```

#### 

* 格式：
  *\_\_getMsgTotal\_\_\`cmdID\`userNo\`params#

* \*号表示命令开始，#号表示命令结束，\`反分号表示分隔符。

* \_\_getMsgTotal\_\_ 更改当前用户密码，前后加两个下划线。

* cmdID 表示产生唯一请求的编号，以便服务器返回消息中的对应。

* userNo 用户名。

* params 参数。

* **举例**
  *\_\_getMsgTotal\_\_\`1234567\`jack\`{...}#

* 成功返回
  
  ```json
  {"success":true,"cmdID":1234567,"totle":100,"rows":[...]｝
  ```

* 失败返回

```json
{"success":false,"cmdID":1234567,"msg":"error code"}
```

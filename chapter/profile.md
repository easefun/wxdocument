#获取用户信息
* 功能：获取某个用户的信息
* URL： http://{网校域名}/api/user/用户的ID/get
* Content-Type： application/json（校验失败：text/html）
* HTTP请求方式: GET
* 请求参数

|参数名|	必选|	类型及范围|	说明|
|--|--|--|--|
|userId	|true|	string|	用户ID|
|timestamp|	true|	string|	当前的时间戳|
|sign|	true|	string|	签名|

* 注意事项
  * 返回错误列表

| 返回响应代码 | 说明     |
|----------- | -------- |
|400         | 非法时间戳 |
|400         |	找不到API|
|400         |	找不到用户|
|403         |	签名错误  |
|200         |	查询成功  |

* JSON示例
````
//普通用户
{"code": "200",
"status": "success",
"message": "",
"data":{ "lastLoginTime": ,
         "occupation": ,
         "gender": ,
         "mobile": ,
         "nickname": ,
         "createdTime": ,
         "avatar":}
}
````
`````
//教师用户
{"code": "200",
 "status": "success",
 "message": "",
 "data":{ "lastLoginTime": ,
          "occupation": ,
          "gender": ,
          "mobile": ,
          "nickname": ,
          "createdTime": ,
          "avatar": ,
          "courseList":[{"courseId": ,"title":}, {"courseId": ,"title":}
           ......
          ]
       }
}
``````
* 字段说明

|字段|	说明|
|---|----|
|code	|响应代码|
|status|	响应状态|
|message	|响应信息|
|data|	用户信息数据|
|data[n].lastLoginTime|	用户最后登陆时间(时间戳)|
|data[n].occupation	|用户职位|
|data[n].gender	|用户性别|
|data[n].mobile	|用户手机|
|data[n].nickname	|用户昵称|
|data[n].createdTime|	用户创建时间|
|data[n].avatar	|用户头像地址|
|data[n].courseList|	教师所教课程|
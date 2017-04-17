#密码修改
* 功能：修改用户基本信息
* URL：http://{网校域名}/api/user/用户ID/update-password
* Content-Type： application/json（校验失败：text/html）
* HTTP请求方式: POST
* 请求参数

|参数名|	必选|	类型及范围|	说明|
|--|--|--|--|
|userId|	true|	string|	用户ID|
|timestamp|	true|	long|	当前的时间戳|
|sign|	true|	string|	签名|
|password	|true|	string|	新密码(使用MD5加密)|

* 注意事项
	* 返回错误列表

| 返回响应代码 | 说明     |
|----------- | -------- |
|400|	非法时间戳|
|400|	找不到API|
|400	|找不到用户|
|400|	密码不能为空|
|400|	修改密码失败|
|403|	签名错误|
|200|	密码修改成功，通知短信发送成功|
|200|	密码修改成功，但是通知短信发送失败|

* JSON示例

````
//修改密码成功
{
  "code": "200",
  "status": "success",
  "message": "密码修改成功。",
  "data":null
}
````
````
//修改密码失败
{"code": "400",
"status": "error",
"message": "修改密码失败。",
"data":null
}
````

* 字段说明

|字段|	说明|
|---|----|
|code|	响应代码|
|status|	响应状态|
|message|	响应信息|
|data|	返回数据|
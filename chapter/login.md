#用户登录
* 功能：用户登录，将用户信息存在session中，密码错误3次，用户将被锁定一天。
* URL：http://{网校域名}/api/login
* Content-Type： application/json（校验失败：text/html）
* HTTP请求方式： POST
* 请求参数

|参数名|	必选|	类型及范围|	说明|
|--|--|--|--|
|timestamp|true|long|当前的时间戳|
|sign|true|string|签名|
|username|true|string|登录帐户|
|password|true|string|登录密码(使用MD5加密)|

* 注意事项
  * 返回错误列表

| 返回响应代码 | 说明     |
|----------- | -------- |
|400|	非法时间戳|
|400|	找不到API|
|400|	找不到用户|
|400|	密码错误|
|400|	输入帐户密码错误3次，用户被锁定一天|
|400|	用户已经被锁定|
|403|	签名错误|
|200|	登录成功|

* JSON示例

````
//登录成功
{
  "code": "200",
  "status": "success",
  "message": "登录成功",
  "data": "登录成功."
}
````
````
//登录失败
{
  "code": "400",
  "status": "error",
  "message": "密码错误。",
  "data": ""
}
````

* 字段说明

|字段|	说明|
|---|----|
|code|	响应代码|
|status|	响应状态|
|message|	响应信息|
|data|	返回数据|
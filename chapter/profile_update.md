#修改用户基本信息
* 功能：修改用户基本信息
* URL：http://{网校域名}/api/user/用户的ID/update
* HTTP请求方式： POST
* 响应数据类型: JSON
* 请求参数

|参数名|	必选|	类型及范围|	说明|
|--|--|--|--|
|userId|	true|	string|	用户ID|
|timestamp|	true|	long|	当前的时间戳|
|sign|	true|	string|签名|
|nickname	|true|	string|	用户昵称|
|avatar|	true|	string|	头像地址|
|gender	|true	|string|	性别，M(男)、F(女)、S(保密)|
|occupation	|true|	string	|职业|




* 注意事项
  * 返回错误列表

| 返回响应代码 | 说明     |
|----------- | -------- |
| 200 | 更新成功 |
| 400 |	更新失败 |
| 403 | 非法时间戳；找不到API；找不到用户；签名错误 |

* JSON示例

````
//修改信息成功
{
  "code": "200",
  "status": "success",
  "message": "",
  "data":null
}
````
````
//修改失败
{
  "code": "400",
  "status": "error",
  "message": "update failed.",
  "data": null
}
````

* 字段说明

|字段|	说明|
|---|----|
|code|	响应代码|
|status|	响应状态|
|message|	响应信息|
|data|	返回数据|

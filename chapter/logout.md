# 退出登录

* 功能：退出登录，删除用户的登录信息。
* URL：[http://{网校域名}/api/logout](http://{网校域名}/api/login)
* HTTP请求方式： POST
* 响应数据类型: JSON
* 请求参数

| 参数名 | 必选 | 类型及范围 | 说明 |
| --- | --- | --- | --- |
| timestamp | true | long | 当前的时间戳 |
| sign | true | string | 签名 |


* 注意事项
  * 返回错误列表

| 返回响应代码 | 说明 |
| --- | --- |
| 200 | 登录成功 |
| 400 |	退出出错 |
| 403 | 非法时间戳；找不到API；签名错误 |

* JSON示例

```
//登录成功
{
  "code":200,
  "status":"success",
  "message":"",
  "data":"sign out success"
}
```

```
//登录失败
{
  "code": "400",
  "status": "error",
  "message": "sign out error",
  "data": ""
}
```

* 字段说明

| 字段 | 说明 |
| --- | --- |
| code | 响应代码 |
| status | 响应状态 |
| message | 响应信息 |
| data | 返回数据 |

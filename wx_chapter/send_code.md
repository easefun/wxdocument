# 发送短信验证码

* 功能：发送短信验证码。
* URL：[https://{网校域名}/api/wx/code/send-code](https://{网校域名}/api/wx/code/send-code)
* Content-Type： application/json（校验失败：text/html）
* HTTP请求方式： GET/POST
* 请求参数

| 参数名 | 必选 | 类型及范围 | 说明 |
| --- | --- | --- | --- |
| mobile | true | string | 手机号 |
| sessionId | true | string | 会话ID |
| t | true | long | 短信签名接口返回的时间戳 |
| h | true | string | 短信签名接口返回的签名 [查看接口](code_sign.md)|

* 注意事项
  * 返回错误列表

| 返回响应代码 | 说明 |
| --- | --- |
| 400 |	会话ID错误 |
| 200 | 调用成功 |

* JSON示例

```
//调用成功
{
  code: 200,
  status: "success",
  message: "",
  data: "success"
}

```
```
//调用失败
{
  code: 400,
  status: "error",
  message: "blank mobile",
  data: ""
}

```

* 字段说明

| 字段 | 说明 |
| --- | --- |
| code | 响应代码 |
| status | 响应状态 |
| message | 响应信息 |
| data | 返回数据 |


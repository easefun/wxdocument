# 短信发送签名

* 功能：获取短信发送签名。
* URL：[https://{网校域名}/api/wx/code/code-sign](https://{网校域名}/api/wx/code/code-sign)
* HTTP请求方式： GET/POST
* 响应数据类型: JSON
* 请求参数

| 参数名 | 必选 | 类型及范围 | 说明 |
| --- | --- | --- | --- |
| sessionId | true | string | 会话ID |

* 注意事项
  * 返回错误列表

| 返回响应代码 | 说明 |
| --- | --- |
| 200 | 调用成功 |
| 400 |	会话ID错误 |

* JSON示例

```
//调用成功
{
  code: 200,
  status: "success",
  message: "",
  data: {
	t: 1492504404368,
	h: "b8f699a7258320370cee9689e0918792"
  } 
}
```

* 字段说明

| 字段 | 说明 |
| --- | --- |
| code | 响应代码 |
| status | 响应状态 |
| message | 响应信息 |
| data | 返回数据 |
| data.t | 时间戳，用于发送短信验证码接口 |
| data.h | 签名，用于发送短信验证码接口 | 


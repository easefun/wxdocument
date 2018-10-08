# 点播视频签名

* 功能：获取点播视频签名。
* URL：[https://{网校域名}/api/wx/video-sign/get](https://{网校域名}/api/wx/video-sign/get)
* HTTP请求方式： GET/POST
* 响应数据类型: JSON
* 请求参数

| 参数名 | 必选 | 类型及范围 | 说明 |
| --- | --- | --- | --- |
| sessionId | true | string | 会话ID |
| vid | true | string | 视频ID |

* 注意事项
  * 返回错误列表

| 返回响应代码 | 说明 |
| --- | --- |
| 200 | 调用成功 |
| 400 | 会话ID错误 |

* JSON示例

```
//调用成功
{
  code: 200,
  status: "success",
  message: "",
  data: {
	sign: b8f699a7258320370cee9689e0918792,
	ts: "1492504404368"
  } 
}

```
```
//调用失败
{
  code: 400,
  status: "error",
  message: "blank vid",
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
| data.sign | 签名 |
| data.ts | 时间戳 |

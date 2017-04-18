# 微信小程序-用户登录

* 功能：用户登录网校，并返回sessionId和openId。
* URL：[https://{网校域名}/api/wx/login](https://{网校域名}/api/wx/login)
* Content-Type： application/json（校验失败：text/html）
* HTTP请求方式： GET
* 请求参数

| 参数名 | 必选 | 类型及范围 | 说明 |
| --- | --- | --- | --- |
| code | true | string | 用户允许小程序登录后，微信回调内容会带上code，网校服务器接收code后换取openId和sessionKey |

* 注意事项
  * 返回错误列表

| 返回响应代码 | 说明 |
| --- | --- |
| 400 | 登录失败 |
| 200 | 登录成功 |

* JSON示例

```
//登录成功
{
  code: 200,
  status: "success",
  message: "",
  data: {
	openId: "od3H50g8EaFz8Z13v7dx3D41cCdY",
	sessionId: "ep4g07c210"
  }
}
```

```
//登录失败
{
  "code": "400",
  "status": "error",
  "message": "login error",
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
| data.openId | 微信用户ID |
| data.sessionId | 会话ID，调用部分接口需要该ID |


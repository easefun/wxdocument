# 预约课程

* 功能：预约某直播课程，直播前30分钟发送通知提醒。
* URL：[https://{网校域名}/api/wx/course-booking/add](https://{网校域名}/api/wx/course-booking/add)
* Content-Type： application/json（校验失败：text/html）
* HTTP请求方式： GET/POST
* 请求参数

| 参数名 | 必选 | 类型及范围 | 说明 |
| --- | --- | --- | --- |
| curriculumId | false | string | 课时ID |
| mobile | false | long | 手机号，非绑定手机号用户第一次预约必填 |
| code | false | string | 短信验证码，非绑定手机号第一次预约必填，点击这里访问发送验证码接口api/wx/code/code-sign |
| courseId | true | long | 课程ID |
| sessionId | true | string | 会话ID |

* 注意事项
  * 返回错误列表

| 返回响应代码 | 说明 |
| --- | --- |
| 400 |	会话ID错误 |
| 400 | 调用失败 |
| 200 | 调用成功 |

* JSON示例

```
//调用成功
{
  code: 200,
  status: "success",
  message: "",
  data: "true"
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


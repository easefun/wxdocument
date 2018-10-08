# 获取课程预约

* 功能：获取某课时预约状况。
* URL：[https://{网校域名}/api/wx/course-booking/status](https://{网校域名}/api/wx/course-booking/status)
* HTTP请求方式： GET
* 响应数据类型: JSON
* 请求参数

| 参数名 | 必选 | 类型及范围 | 说明 |
| --- | --- | --- | --- |
| courseId | true | long | 课程ID |
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
  data: "NOBOOKING-NOMOBILE"
}
```

* 字段说明

| 字段 | 说明 |
| --- | --- |
| code | 响应代码 |
| status | 响应状态 |
| message | 返回数据 |
| data | 课程预约状态；NOBOOKING-NOMOBILE 没预约(没绑定手机号)、NOBOOKING 没预约(已绑定手机号)、WAITING 等待通知、FINISHED 已经通知 |


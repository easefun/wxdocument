# 取消课程收藏

* 功能：取消课程收藏。
* URL：[https://{网校域名}/api/wx/favorite-courses/课程ID/del](https://{网校域名}/api/wx/favorite-courses/课程ID/del)
* Content-Type： application/json（校验失败：text/html）
* HTTP请求方式： GET/POST
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
  data: "true"
}

```

* 字段说明

| 字段 | 说明 |
| --- | --- |
| code | 响应代码 |
| status | 响应状态 |
| message | 响应信息 |
| data | 返回数据 |


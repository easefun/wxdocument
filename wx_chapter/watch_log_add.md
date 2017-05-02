# 添加观看记录

* 功能：添加观看课程记录。
* URL：[https://{网校域名}/api/wx/watch-log/add](https://{网校域名}/api/wx/watch-log/add)
* Content-Type： application/json（校验失败：text/html）
* HTTP请求方式： GET/POST
* 请求参数

| 参数名 | 必选 | 类型及范围 | 说明 |
| --- | --- | --- | --- |
| sessionId | true | string | 会话ID |
| curriculumId | false | string | 课时ID |
| courseId | true | long | 课程ID |

* 注意事项
  * 返回错误列表

| 返回响应代码 | 说明 |
| --- | --- |
| 200 | 调用成功 |
| 400 | 调用失败 |

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


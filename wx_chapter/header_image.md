# 首页头图

* 功能：获取网校头图列表。
* URL：[https://{网校域名}/api/wx/header-image/get](https://{网校域名}/api/wx/header-image/get)
* HTTP请求方式： GET/POST
* 响应数据类型: JSON
* 请求参数：无

* 注意事项
  * 返回错误列表

| 返回响应代码 | 说明 |
| --- | --- |
| 200 | 调用成功 |

* JSON示例

```
//调用成功
{
  code: 200,
  status: "success",
  message: "",
  data: [
  {
	id: "j1g1vr74",
	src: "https://res.wangxiaoyun.net/image/201704/ea5da79a9eb548998bddfed8a8f44a8f.jpg",
	href: "440",
	title: "直播视频长期存储",
	desc: "",
	ordered: 1,
	status: "Y",
	createdTime: "2017-04-13 14:55:20"
  }]
}
```

* 字段说明

| 字段 | 说明 |
| --- | --- |
| code | 响应代码 |
| status | 响应状态 |
| message | 响应信息 |
| data | 返回数据 |
| data.id | 头图ID |
| data.src | 头图链接 |
| data.href | 课程ID |
| data.title | 头图标题 |
| data.desc | 头图简介 |
| data.ordered | 排序序号，由小到大 |
| data.status | 状态，Y发布，N未发布 |
| data.createdTime | 创建时间 |

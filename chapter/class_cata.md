# 课程分类

* 功能： 获取整个网校的课程分类信息，返回结果以树型结构呈现
* URL： [http://{网校域名}/api/category/get-all](http://{网校域名}/api/category/get-all)
* Content-Type: application/json（校验失败：text/html）
* HTTP请求方式： GET/POST
* 请求参数

| 参数名 | 必选 | 类型及范围 | 说明 |
| --- | --- | --- | --- |
| timestamp | true | long | 当前时间戳 |
| sign | true | string | 签名 |

* 注意事项
  * 返回错误列表

| 返回响应代码 | 说明 |
| --- | --- |
| 400 | 非法时间戳 |
| 400 | 找不到API |
| 400 | 找不到用户 |
| 403 | 签名错误 |
| 200 | 查询成功 |

* JSON示例

```
{
  code: 200,
  status: "success",
  message: "",
  data: [
    {
      categoryId: 63,
      schoolId: "demo",
      parentId: 0,
      lft: 1,
      rgt: 6,
      name: "课程分类",
      description: "课程的默认分类",
      icon: null,
      createdTime: 1481685178000,
      lastModified: 1481685178000,
      depth: 0,
      courseCount: 28
    },
    {
      categoryId: 64,
      schoolId: "demo",
      parentId: 1,
      lft: 2,
      rgt: 5,
      name: "文科",
      description: "这里是文科",
      icon: "",
      createdTime: 1481685378000,
      lastModified: 1492142051000,
      depth: 1,
      courseCount: 0
    }
  ]
}
```

* 字段说明

| 字段 | 说明 |
| --- | --- |
| code | 响应代码 |
| status | 响应状态 |
| message | 响应信息 |
| data | 返回数据 |
| data\[index\].categoryId | 分类ID |




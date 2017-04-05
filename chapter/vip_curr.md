#VIP课时信息

* 功能：根据课程ID，返回所有直播公开课的课时信息
* URL： http://{网校域名}/api/curriculum/vip-curriculum
* Content-Type: application/json（校验失败：text/html）
* HTTP请求方式： GET/POST
* 请求参数

|参数名|	必选	|类型及范围|	说明|
|----|---|----|----|
|userId|	true|	string|	用户ID|
|timestamp|	true|	string|	当前的时间戳|
|sign|	true|	string|	签名|
|courseId	|true	|string|	课程ID|

* 注意事项
  * 返回错误列表

| 返回响应代码 | 说明     |
|----------- | -------- |
|400         | 非法时间戳 |
|400         |	找不到API|
|400         |	找不到用户|
|403         |	签名错误  |
|200         |	查询成功  |

JSON示例
操作结果返回json
````
//查询成功
{"code": "200",
"status": "success",
"message": "",
"data":{"vipLiveCurriculums":[{"curriculumType":"类别", "title":"章节名称或者课时名称" },
                              {"curriculumType":"类别", "title":"章节名称或者课时名称" },
                               ...
                              {"curriculumType":"类别", "title":"章节名称或者课时名称" }],
        "vipVodCurriculums":[{"curriculumType":"类别", "title":"章节名称或者课时名称" },
                              {"curriculumType":"类别", "title":"章节名称或者课时名称" },
                               ...
                              {"curriculumType":"类别", "title":"章节名称或者课时名称" }]
}
````

* 字段说明

|字段|	说明|
|---|----|
|code|	响应代码|
|status|	响应状态|
|message|	响应信息|
|data|	返回数据|
|data.vipLiveCurriculums|	vip直播课时|
|data.vipLiveCurriculums[index].curriculumType|	vip直播类别|
|data.vipLiveCurriculums[index].title|	vip直播章节或者课时名称，取决于类别|
|data.vipVodCurriculums|	vip点播课时|
|data.vipVodCurriculums[index].curriculumType|	vip点播类别|
|data.vipVodCurriculums[index].title|	vip点播章节或者课时名称，取决于类别|
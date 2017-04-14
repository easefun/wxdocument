#课程信息

* 功能：根据课程ID，返回相应课程的详细信息
* URL: http://{网校域名}/api/course/course-info
* Content-Type: application/json（校验失败：text/html）
* HTTP请求方式: GET/POST
* 请求参数

|参数名|	必选|	类型及范围|	说明|
|-----|----|------------|-----|
|timestamp|	true|	long|	当前的时间戳|
|sign|	true|	string|	签名|
|courseId|	true|	long|	课程ID|

* 注意事项
	* 返回错误列表

|返回响应代码	|说明|
|-----------|---|
|400|	非法时间戳|
|400|	找不到API|
|400|	找不到课程|
|403|	签名错误|
|200|	查询成功|

JSON示例
操作结果返回json
````
{"code": "200",
"status": "success",
"message": "",
"data":[{"title": "标题",
   "subtitle": "副标题",
   "categoryName": "分类名称",
   "keyword1": "标签",
   "keyword2": "标签",
   "keyword3": "标签",
   "coverImage": "课程封面图片路径",
   "price": "课程价格",
   "isFreeVip": "VIP会员是否免费",
   "studentCount": "在学人数",
   "objectives": "教学目标",
   "audiences": "目标学员",
   "requirements": "学习要求"},
  
  {"title": "标题",
   "subtitle": "副标题",
   "categoryName": "分类名称",
   "keyword1": "标签",
   "keyword2": "标签",
   "keyword3": "标签",
   "coverImage": "课程封面图片路径",
   "price": "课程价格",
   "isFreeVip": "VIP会员是否免费",
   "studentCount": "在学人数",
   "objectives": "教学目标",
   "audiences": "目标学员",
   "requirements": "学习要求"},
   .......
]
}
````

* 字段说明

|字段|	说明|
|----|------|
|code|	响应代码|
|status|	响应状态|
|message|	响应信息|
|data|	返回数据|

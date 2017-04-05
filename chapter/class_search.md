#课程搜索

* 功能：根据关键字，返回相应课程列表的详细信息
* URL： http://{网校域名}/api/course/search
* Content-Type: application/json（校验失败：text/html）
* HTTP请求方式： GET/POST
* 请求参数

|参数名|	必选|	类型及范围|	说明|
|-----|----|------------|-------|
|userId|	true|	string|	用户ID|
|timestamp|	true|	string|	当前的时间戳|
|sign	|true|	string	|签名|
|keyword|	true|	string	|关键字|
|start	|true|	string|	开始点|
|end|	true	|string|	结束点|

* 注意事项
	* 返回错误列表

|返回响应代码|	说明|
|----------|-------|
|400|	appId为空|
|400|	非法时间戳|
|400|	找不到API|
|400|	找不到用户|
|400|	传入参数错误|
|403|	签名错误|
|200|	查询成功|

JSON示例
````
//查询成功
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
|code	|响应代码|
|status|	响应状态|
|message|	响应信息|
|data|	返回数据|

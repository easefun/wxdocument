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
{
  code: 200,
  status: "success",
  message: "",
  data: {
	courseId: 76,
	courseType: "VIP",
	courseMeth: "LIVE",
	categoryId: 75,
	schoolId: "test",
	title: "语文一年级",
	subtitle: "语文一年级上学期",
	summary: "概要",
	keyword1: "语文",
	keyword2: "小学",
	keyword3: "",
	objectives: "教学目标",
	audiences: "目标学员",
	requirements: "",
	coverImage: "https://res.wangxiaoyun.net/image/287x180/201704/c0cf3f220c474d7bb19ef55719bea124.png",
	promoImage: null,
	promoVideoId: null,
	price: 0,
	validity: 0,
	isFree: "Y",
	isFreeVip: "Y",
	isRecommend: "N",
	recommendTime: 1478167919000,
	isBarrageEnabled: "Y",
	isTickerEnabled: "Y",
	tickerContent: "233",
	isRoyaltyEnabled: "N",
	channelId: 0,
	channelSecretkey: null,
	status: "published",
	userId: "iuhqvcn6",
	createdTime: 1475310831000,
	publishedTime: null,
	lastModified: 1492149794000,
	studentCount: 12,
	reviewCount: 0,
	ratingScore: 0,
	categoryName: "语文",
	teacherId: "iv38g5ck",
	teacherName: "gg",
	teacherAvatar: "https://res.wangxiaoyun.net/image/220x220//resources/images/avatars/28avatar.jpg",
	channelPasswd: "",
	description: "<p>课程介绍</p>"
  }
}
````

* 字段说明

|字段|	说明|
|----|------|
|code|	响应代码|
|status|	响应状态|
|message|	响应信息|
|data|	返回数据|

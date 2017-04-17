#学员课程

* 功能：根据用户ID查出在学课程，已经购买的课程和收藏的课程。
* URL：http://{网校域名}/api/course/get-courses
* Content-Type： application/json（校验失败：text/html）
* HTTP请求方式：GET/POST
* 请求参数

|参数名|	必选|	类型及范围|	说明|
|--|--|--|--|
|userId|	true|	string|	用户ID|
|timestamp|	true	|long|	当前的时间戳|
|sign	|true|	string|	签名|


* 注意事项
  * 返回错误列表

| 返回响应代码 | 说明     |
|----------- | -------- |
|400         | 非法时间戳 |
|400         |	找不到API|
|400         |	找不到用户|
|403         |	签名错误  |
|200         |	查询成功  |
* JSON示例

````
{
  code: 200,
  status: "success",
  message: "",
  data: {
    purchasedCourseList: [
      {
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
      tickerContent: "微网校",
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
      teacherAvatar: "https://res.wangxiaoyun.net/assets/images/avatars/10avatar.jpg",
      channelPasswd: "",
      description: "<p>课程介绍</p>"
      }
    ],
    learningCoursesList: [],
    favoriteCoursesList: []
    }
}

{"code": "200",
"status": "success",
"message": "",
"data":{"learningCourseList":[{课程信息的json},{...},....{...}]}, //在学课程的课程信息
       {"favoriteCourseList":[{课程信息的json},{...},....{...}]}, //喜爱的课程信息
       {"purchasedCourseList":[{课程信息的json},{...},....{...}]} //已购买的课程信息
}
`````
`````
//每一个课程json的信息包含
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
 "requirements": "学习要求"
}
`````
* 字段说明(其他字段信息请在json示例里查看)

|字段|	说明|
|---|----|
|code|	响应代码|
|status|	响应状态|
|message|	响应信息|
|data|	返回数据|
|data.learningCourseList|	在学课程|
|data.favoriteCourseList|	喜爱的课程|
|data.purchasedCourseList|	已购买的课程|
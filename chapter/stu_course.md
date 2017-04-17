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
    learningCoursesList: [...结构同上],
    favoriteCoursesList: [...结构同上]
    }
}

`````
* 字段说明(其他字段信息请在json示例里查看)

|字段|	说明|
|---|----|
|code|	响应代码|
|status|	响应状态|
|message|	响应信息|
|data|	返回数据|
|data|	返回数据|
|data.learningCourseList|	在学课程列表，内容结构同已购买的课程列表|
|data.favoriteCourseList|	喜爱的课程列表，内容结构同已购买的课程列表|
| data.purchasedCourseList|已购买的课程列表|
| data.purchasedCourseList\[index\].courseId | 课程ID |
| data.purchasedCourseList\[index\].courseType | 课程类型，OPEN_VOD（点播公开课）、OPEN_LIVE（直播公开课）、VIP（VIP课程） |
| data.purchasedCourseList\[index\].courseMeth | 上课方式，VOD（视频点播）、LIVE（视频直播）、VIP（VIP） |
| data.purchasedCourseList\[index\].categoryId | 分类ID |
| data.purchasedCourseList\[index\].schoolId | 网校ID |
| data.purchasedCourseList\[index\].title | 课程标题 |
| data.purchasedCourseList\[index\].subtitle | 课程子标题 |
| data.purchasedCourseList\[index\].summary | 课程概要 |
| data.purchasedCourseList\[index\].keyword1 | 课程关键词1 |
| data.purchasedCourseList\[index\].keyword2 | 课程关键词2 |
| data.purchasedCourseList\[index\].keyword3 | 课程关键词3 |
| data.purchasedCourseList\[index\].objectives | 教学目标 |
| data.purchasedCourseList\[index\].audiences | 目标学员 |
| data.purchasedCourseList\[index\].requirements | 学习要求 |
| data.purchasedCourseList\[index\].coverImage | 课程封面图 |
| data.purchasedCourseList\[index\].promoImage | 课程宣传图 |
| data.purchasedCourseList\[index\].promoVideoId | 课程宣传片视频ID |
| data.purchasedCourseList\[index\].price | 课程定价 |
| data.purchasedCourseList\[index\].validity | 学习有效期，单位：天 |
| data.purchasedCourseList\[index\].isFree | 是否免费，Y（免费）、N（收费） |
| data.purchasedCourseList\[index\].isFreeVip | 是否对VIP会员免费，Y（免费）、N（收费） |
| data.purchasedCourseList\[index\].isRecommend | 是否推荐，Y（推荐）、N（不是推荐） |
| data.purchasedCourseList\[index\].recommendTime | 推荐时间(时间戳) |
| data.purchasedCourseList\[index\].isBarrageEnabled | 是否开启弹幕，Y（开启）、N（关闭） |
| data.purchasedCourseList\[index\].isTickerEnabled | 是否开启跑马灯功能，Y（开启）、N（关闭） |
| data.purchasedCourseList\[index\].tickerContent | 跑马灯内容模板 |
| data.purchasedCourseList\[index\].isRoyaltyEnabled | 是否实施收入分成 |
| data.purchasedCourseList\[index\].channelId | 直播课程的频道ID |
| data.purchasedCourseList\[index\].channelSecretkey | 直播课程的SecretKey |
| data.purchasedCourseList\[index\].status | 课程状态 |
| data.purchasedCourseList\[index\].userId | 课程创建者用户Id |
| data.purchasedCourseList\[index\].createdTime | 课程创建时间 |
| data.purchasedCourseList\[index\].publishedTime | 课程发布时间(时间戳) |
| data.purchasedCourseList\[index\].lastModified | 课程最近修改时间(时间戳) |
| data.purchasedCourseList\[index\].studentCount | 学员总数 |
| data.purchasedCourseList\[index\].reviewCount | 评论数据 |
| data.purchasedCourseList\[index\].ratingScore | 平均评分 |
| data.purchasedCourseList\[index\].categoryName | 分类名称 |
| data.purchasedCourseList\[index\].teacherId | 主讲老师ID |
| data.purchasedCourseList\[index\].teacherName | 主讲老师名称 |
| data.purchasedCourseList\[index\].teacherAvatar | 主讲老师头像 |
| data.purchasedCourseList\[index\].channelPasswd | 直播频道号密码 |
| data.purchasedCourseList\[index\].description | 课程详情 |

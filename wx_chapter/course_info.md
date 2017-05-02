# 课程详细信息

* 功能：根据课程ID，返回相应课程的详细信息
* URL: http://{网校域名}/api/wx/course/course-info
* Content-Type: application/json（校验失败：text/html）
* HTTP请求方式： GET
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
| 400 | 会话ID错误 |

* JSON示例

```
//调用成功
{
  code: 200,
  status: "success",
  message: "",
  data: {
	course: 
	{
      courseId: 160,
      courseType: "OPEN_LIVE",
      courseMeth: "LIVE",
      categoryId: 63,
      schoolId: "test",
      title: "直播公开课",
      subtitle: "",
      summary: null,
      keyword1: "",
      keyword2: "",
      keyword3: "",
      objectives: null,
      audiences: null,
      requirements: null,
      coverImage: "https://res.wangxiaoyun.net/assets/images/default/course-large.png",
      promoImage: null,
      promoVideoId: null,
      price: 0,
      validity: 0,
      isFree: "Y",
      isFreeVip: "N",
      isRecommend: "N",
      recommendTime: null,
      isBarrageEnabled: "N",
      isTickerEnabled: "N",
      tickerContent: null,
      isRoyaltyEnabled: "N",
      channelId: 0,
      channelSecretkey: "9dVy3s16Vv",
      status: "published",
      userId: "iv9491le",
      createdTime: 1486278039000,
      publishedTime: null,
      lastModified: 1488794098000,
      studentCount: 209,
      reviewCount: 0,
      ratingScore: 0,
      categoryName: "课程分类",
      teacherId: "iv9321le",
      teacherName: "孙老师",
      teacherAvatar: "https://res.wangxiaoyun.net/assets/images/avatars/10avatar.jpg",
      channelPasswd: "",
      description: ""
    },
    liveStatus: "live",
	liveUserId: "edvf2fpec9"
  }
}

//调用失败
{
  code: 400,
  status: "error",
  message: "course not exist",
  data: ""
}
```

* 字段说明

| 字段 | 说明 |
| --- | --- |
| code | 响应代码 |
| status | 响应状态 |
| message | 响应信息 |
|data|  返回数据|
|data.liveStatus|  课程直播状态，live直播中, waiting未直播, end已结束, ready直播前30分钟|
|data.liveUserId|  直播用户ID|
|data.course| 课程详情 |
| data.course.courseId | 课程ID |
| data.course.courseType | 课程类型，OPEN_VOD（点播公开课）、OPEN_LIVE（直播公开课）、VIP（VIP课程） |
| data.course.courseMeth | 上课方式，VOD（视频点播）、LIVE（视频直播）、VIP（VIP） |
| data.course.categoryId | 分类ID |
| data.course.schoolId | 网校ID |
| data.course.title | 课程标题 |
| data.course.subtitle | 课程子标题 |
| data.course.summary | 课程概要 |
| data.course.keyword1 | 课程关键词1 |
| data.course.keyword2 | 课程关键词2 |
| data.course.keyword3 | 课程关键词3 |
| data.course.objectives | 教学目标 |
| data.course.audiences | 目标学员 |
| data.course.requirements | 学习要求 |
| data.course.coverImage | 课程封面图 |
| data.course.promoImage | 课程宣传图 |
| data.course.promoVideoId | 课程宣传片视频ID |
| data.course.price | 课程定价 |
| data.course.validity | 学习有效期，单位：天 |
| data.course.isFree | 是否免费，Y（免费）、N（收费） |
| data.course.isFreeVip | 是否对VIP会员免费，Y（免费）、N（收费） |
| data.course.isRecommend | 是否推荐，Y（推荐）、N（不是推荐） |
| data.course.recommendTime | 推荐时间(时间戳) |
| data.course.isBarrageEnabled | 是否开启弹幕，Y（开启）、N（关闭） |
| data.course.isTickerEnabled | 是否开启跑马灯功能，Y（开启）、N（关闭） |
| data.course.tickerContent | 跑马灯内容模板 |
| data.course.isRoyaltyEnabled | 是否实施收入分成 |
| data.course.channelId | 直播课程的频道ID |
| data.course.channelSecretkey | 直播课程的SecretKey |
| data.course.status | 课程状态 |
| data.course.userId | 课程创建者用户Id |
| data.course.createdTime | 课程创建时间 |
| data.course.publishedTime | 课程发布时间(时间戳) |
| data.course.lastModified | 课程最近修改时间(时间戳) |
| data.course.studentCount | 学员总数 |
| data.course.reviewCount | 评论数据 |
| data.course.ratingScore | 平均评分 |
| data.course.categoryName | 分类名称 |
| data.course.teacherId | 主讲老师ID |
| data.course.teacherName | 主讲老师名称 |
| data.course.teacherAvatar | 主讲老师头像 |
| data.course.channelPasswd | 直播频道号密码 |
| data.course.description | 课程详情 |


# 微信小程序-获取课程预约

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
| 400 | 调用失败 |
| 200 | 调用成功 |

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
      title: "paul直播公开课",
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
      channelSecretkey: "9dVyTsp6Vv",
      status: "published",
      userId: "iv9491le",
      createdTime: 1486278039000,
      publishedTime: null,
      lastModified: 1488794098000,
      studentCount: 209,
      reviewCount: 0,
      ratingScore: 0,
      categoryName: "课程分类",
      teacherId: "iv9491le",
      teacherName: "Lin",
      teacherAvatar: "https://res.wangxiaoyun.net/assets/images/avatars/10avatar.jpg",
      channelPasswd: "",
      description: null
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
| data | 课程预约状态；NOBOOKING-NOMOBILE 没预约(没绑定手机号)、NOBOOKING 没预约(已绑定手机号)、WAITING 等待通知、FINISHED 已经通知 |


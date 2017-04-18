# 微信小程序-获取最近观看课程列表

* 功能：获取最近观看课程列表。
* URL：[https://{网校域名}/api/wx/watch-log/get](https://{网校域名}/api/wx/watch-log/get)
* Content-Type： application/json（校验失败：text/html）
* HTTP请求方式： GET、POST
* 请求参数

| 参数名 | 必选 | 类型及范围 | 说明 |
| --- | --- | --- | --- |
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
  data: [
  {
	openId: "od3H50PtEaFz8Zv317dxsF41cCdY",
    courseId: 440,
    schoolId: "test",
    courseType: "OPEN_LIVE",
    courseTitle: "直播视频长期存储",
    coverImage: "http://res.wangxiaoyun.net/image/287x180/201703/f8b0d9cae5674112911a1eb3392e230e.png",
    curriculumId: "",
    curriculumTitle: "",
    watchTimeMills: 1492137337051,
    createdTime: 1492137337000,
    lastModified: 1492137337000,
    courseMeth: "LIVE",
    categoryId: 199,
    categoryName: "课程分类",
    courseSubtitle: null,
    promoImage: null,
    promoVideoId: null,
    isFree: "Y",
    isFreeVip: "N",
    isRecommend: "Y",
    studentCount: 15,
    reviewCount: 0,
    teacherId: "j0hj91ym",
    teacherName: "孙老师",
    teacherAvatar: "http://res.wangxiaoyun.net/image/220x220/201703/aacb188d382b4b4babf2cd817d991742.png"
  }]
}
```

* 字段说明

| 字段 | 说明 |
| --- | --- |
| code | 响应代码 |
| status | 响应状态 |
| message | 响应信息 |
| data | 响应内容 |
| data.openId | 微信用户ID |
| data.courseId | 课程ID |
| data.schoolId | 网校ID |
| data.courseType | 课程类型，OPEN_VOD（点播公开课）、OPEN_LIVE（直播公开课）、VIP（VIP课程） |
| data.courseTitle | 课程标题 |
| data.coverImage | 课程封面图 |
| data.curriculumId | 课时ID |
| data.curriculumTitle | 课程标题 |
| data.watchTimeMills | 观看时长 |
| data.createdTime | 添加时间(时间戳) |
| data.lastModified | 最近修改时间(时间戳) |
| data.courseMeth | 上课方式，VOD（视频点播）、LIVE（视频直播）、VIP（VIP） |
| data.categoryId | 分类ID |
| data.categoryName | 分类名称 |
| data.courseSubtitle | 课程子标题 |
| data.promoImage | 课程宣传图 |
| data.promoVideoId | 课程宣传片视频ID |
| data.isFree | 是否免费，Y（免费）、N（收费） |
| data.isFreeVip | 是否对VIP会员免费，Y（免费）、N（收费） |
| data.isRecommend | 是否推荐，Y（推荐）、N（不是推荐） |
| data.studentCount | 学员总数 |
| data.reviewCount | 评论数据 |
| data.teacherId | 主讲老师ID |
| data.teacherName | 主讲老师名称 |
| data.teacherAvatar | 主讲老师头像 |



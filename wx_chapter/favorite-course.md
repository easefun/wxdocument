# 微信小程序-获取收藏课程列表

* 功能：获取某课时预约状况。
* URL：[https://{网校域名}/api/wx/favorite-courses](https://{网校域名}/api/wx/favorite-courses)
* Content-Type： application/json（校验失败：text/html）
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
  data: [
  {
	courseId: 417,
	courseType: "OPEN_VOD",
	courseMeth: "VOD",
	categoryId: 199,
	schoolId: "demo",
	title: "视频采集卡使用方法",
	subtitle: null,
	summary: "",
	keyword1: null,
	keyword2: null,
	keyword3: null,
	objectives: null,
	audiences: null,
	requirements: null,
	coverImage: "http://res.wangxiaoyun.net/image/287x180/201703/b8e40512fd724a12b0918eb2691238c4.png",
	promoImage: null,
	promoVideoId: null,
	price: 0,
	validity: 0,
	isFree: "Y",
	isFreeVip: "N",
	isRecommend: "N",
	recommendTime: 1492480335000,
	isBarrageEnabled: "N",
	isTickerEnabled: "N",
	tickerContent: null,
	isRoyaltyEnabled: "N",
	channelId: 0,
	channelSecretkey: null,
	status: "published",
	userId: "j0h196ym",
	createdTime: 1490606307000,
	publishedTime: null,
	lastModified: 1492480335000,
	studentCount: 30,
	reviewCount: 0,
	ratingScore: 0,
	categoryName: "课程分类",
	teacherId: "j0hj96ym",
	teacherName: "孙老师",
	teacherAvatar: "https://res.wangxiaoyun.net/image/220x220/201703/aacb188d382b4b4babf2cd817d991742.png",
	channelPasswd: "",
	description: ""
  }]
}
```

* 字段说明

| 字段 | 说明 |
| --- | --- |
| code | 响应代码 |
| status | 响应状态 |
| message | 响应信息 |
|data[index]| 收藏课程列表 |
| data\[index\].courseId | 课程ID |
| data\[index\].courseType | 课程类型，OPEN_VOD（点播公开课）、OPEN_LIVE（直播公开课）、VIP（VIP课程） |
| data\[index\].courseMeth | 上课方式，VOD（视频点播）、LIVE（视频直播）、VIP（VIP） |
| data\[index\].categoryId | 分类ID |
| data\[index\].schoolId | 网校ID |
| data\[index\].title | 课程标题 |
| data\[index\].subtitle | 课程子标题 |
| data\[index\].summary | 课程概要 |
| data\[index\].keyword1 | 课程关键词1 |
| data\[index\].keyword2 | 课程关键词2 |
| data\[index\].keyword3 | 课程关键词3 |
| data\[index\].objectives | 教学目标 |
| data\[index\].audiences | 目标学员 |
| data\[index\].requirements | 学习要求 |
| data\[index\].coverImage | 课程封面图 |
| data\[index\].promoImage | 课程宣传图 |
| data\[index\].promoVideoId | 课程宣传片视频ID |
| data\[index\].price | 课程定价 |
| data\[index\].validity | 学习有效期，单位：天 |
| data\[index\].isFree | 是否免费，Y（免费）、N（收费） |
| data\[index\].isFreeVip | 是否对VIP会员免费，Y（免费）、N（收费） |
| data\[index\].isRecommend | 是否推荐，Y（推荐）、N（不是推荐） |
| data\[index\].recommendTime | 推荐时间(时间戳) |
| data\[index\].isBarrageEnabled | 是否开启弹幕，Y（开启）、N（关闭） |
| data\[index\].isTickerEnabled | 是否开启跑马灯功能，Y（开启）、N（关闭） |
| data\[index\].tickerContent | 跑马灯内容模板 |
| data\[index\].isRoyaltyEnabled | 是否实施收入分成 |
| data\[index\].channelId | 直播课程的频道ID |
| data\[index\].channelSecretkey | 直播课程的SecretKey |
| data\[index\].status | 课程状态 |
| data\[index\].userId | 课程创建者用户Id |
| data\[index\].createdTime | 课程创建时间 |
| data\[index\].publishedTime | 课程发布时间(时间戳) |
| data\[index\].lastModified | 课程最近修改时间(时间戳) |
| data\[index\].studentCount | 学员总数 |
| data\[index\].reviewCount | 评论数据 |
| data\[index\].ratingScore | 平均评分 |
| data\[index\].categoryName | 分类名称 |
| data\[index\].teacherId | 主讲老师ID |
| data\[index\].teacherName | 主讲老师名称 |
| data\[index\].teacherAvatar | 主讲老师头像 |
| data\[index\].channelPasswd | 直播频道号密码 |
| data\[index\].description | 课程详情 |

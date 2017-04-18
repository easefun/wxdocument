#课程信息

* 功能：根据课程ID，返回相应课程的详细信息
* URL: http://{网校域名}/api/wx/course/openCourses
* Content-Type: application/json（校验失败：text/html）
* HTTP请求方式: GET
* 请求参数： 无

|返回响应代码	|说明|
|-----------|---|
|200|	查询成功|

JSON示例
操作结果返回json
````
{
  code: 200,
  status: "success",
  message: "",
  data: {
  	openCourses: [
  	{
	  courseId: 31,
	  courseType: "OPEN_VOD",
	  courseMeth: "VOD",
	  categoryId: 3,
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
  	}],
	openLiveCourse: [
	{
	  curriculumId: "160iz564e8k",
	  curriculumType: "lecture",
	  courseId: 160,
	  schoolId: "test",
	  title: "公开直播课",
	  description: null,
	  ordered: 1,
	  startDate: 1492484437974,
	  startTime: "11:00",
	  endTime: "16:00",
	  duration: 300,
	  hasEndDate: "Y",
	  endDate: 1493222400000,
	  isRepeatWeek1: "Y",
	  isRepeatWeek2: "Y",
	  isRepeatWeek3: "Y",
	  isRepeatWeek4: "Y",
	  isRepeatWeek5: "Y",
	  isRepeatWeek6: "Y",
	  isRepeatWeek7: "Y",
	  hasFile: 0,
	  fileid: null,
	  filename: null,
	  filesize: 0,
	  fileurl: null,
	  hasPlayback: "N",
	  videoId: null,
	  videoDuration: 0,
	  status: "published",
	  createdTime: 1487054949000,
	  lastModified: 1492485637000,
	  startTs: 0,
	  endTs: 0,
	  isRepeat: "Y",
	  courseType: "OPEN_LIVE",
	  courseMeth: "LIVE",
	  courseTitle: "直播公开课",
	  courseSubtitle: "",
	  coverImage: "https://res.wangxiaoyun.net/assets/images/default/course-large.png",
	  promoImage: null,
	  promoVideoId: null,
	  studentCount: 209,
	  categoryId: 63,
	  categoryName: "课程分类",
	  teacherId: "iv94913e",
	  teacherName: "孙老师",
	  teacherAvatar: "https://res.wangxiaoyun.net/assets/images/avatars/10avatar.jpg",
	  liveStatus: "live",
	  hasPlaybackAsBoolean: false,
	  hasFileAsBoolean: false,
	  videoCoverImage: ""
	}]
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
|data[index].openCourses| 点播公开课列表 |
| data\[index\].openCourses.courseId | 课程ID |
| data\[index\].openCourses.courseType | 课程类型，OPEN_VOD（点播公开课）、OPEN_LIVE（直播公开课）、VIP（VIP课程） |
| data\[index\].openCourses.courseMeth | 上课方式，VOD（视频点播）、LIVE（视频直播）、VIP（VIP） |
| data\[index\].openCourses.categoryId | 分类ID |
| data\[index\].openCourses.schoolId | 网校ID |
| data\[index\].openCourses.title | 课程标题 |
| data\[index\].openCourses.subtitle | 课程子标题 |
| data\[index\].openCourses.summary | 课程概要 |
| data\[index\].openCourses.keyword1 | 课程关键词1 |
| data\[index\].openCourses.keyword2 | 课程关键词2 |
| data\[index\].openCourses.keyword3 | 课程关键词3 |
| data\[index\].openCourses.objectives | 教学目标 |
| data\[index\].openCourses.audiences | 目标学员 |
| data\[index\].openCourses.requirements | 学习要求 |
| data\[index\].openCourses.coverImage | 课程封面图 |
| data\[index\].openCourses.promoImage | 课程宣传图 |
| data\[index\].openCourses.promoVideoId | 课程宣传片视频ID |
| data\[index\].openCourses.price | 课程定价 |
| data\[index\].openCourses.validity | 学习有效期，单位：天 |
| data\[index\].openCourses.isFree | 是否免费，Y（免费）、N（收费） |
| data\[index\].openCourses.isFreeVip | 是否对VIP会员免费，Y（免费）、N（收费） |
| data\[index\].openCourses.isRecommend | 是否推荐，Y（推荐）、N（不是推荐） |
| data\[index\].openCourses.recommendTime | 推荐时间(时间戳) |
| data\[index\].openCourses.isBarrageEnabled | 是否开启弹幕，Y（开启）、N（关闭） |
| data\[index\].openCourses.isTickerEnabled | 是否开启跑马灯功能，Y（开启）、N（关闭） |
| data\[index\].openCourses.tickerContent | 跑马灯内容模板 |
| data\[index\].openCourses.isRoyaltyEnabled | 是否实施收入分成 |
| data\[index\].openCourses.channelId | 直播课程的频道ID |
| data\[index\].openCourses.channelSecretkey | 直播课程的SecretKey |
| data\[index\].openCourses.status | 课程状态 |
| data\[index\].openCourses.userId | 课程创建者用户Id |
| data\[index\].openCourses.createdTime | 课程创建时间 |
| data\[index\].openCourses.publishedTime | 课程发布时间(时间戳) |
| data\[index\].openCourses.lastModified | 课程最近修改时间(时间戳) |
| data\[index\].openCourses.studentCount | 学员总数 |
| data\[index\].openCourses.reviewCount | 评论数据 |
| data\[index\].openCourses.ratingScore | 平均评分 |
| data\[index\].openCourses.categoryName | 分类名称 |
| data\[index\].openCourses.teacherId | 主讲老师ID |
| data\[index\].openCourses.teacherName | 主讲老师名称 |
| data\[index\].openCourses.teacherAvatar | 主讲老师头像 |
| data\[index\].openCourses.channelPasswd | 直播频道号密码 |
| data\[index\].openCourses.description | 课程详情 |
|data[index].openLiveCourse| 直播公开课列表 |
|data[index].openLiveCourse.curriculumId|课时ID|
|data[index].openLiveCourse.curriculumType|课时类型，section（章节）、lecture（课时）|
|data[index].openLiveCourse.courseId|课程ID|
|data[index].openLiveCourse.schoolId|网校ID|
|data[index].openLiveCourse.title|课时标题|
|data[index].openLiveCourse.description|课时简介|
|data[index].openLiveCourse.ordered|排序序号，有小到大|
|data[index].openLiveCourse.startDate|开始日期(时间戳)，yyyy/MM/dd|
|data[index].openLiveCourse.startTime|开始时间，HH:mm|
|data[index].openLiveCourse.endTime|预计结束时间，HH:mm|
|data[index].openLiveCourse.duration|预计直播时长，单位：分钟|
|data[index].openLiveCourse.hasEndDate|是否永不结束|
|data[index].openLiveCourse.endDate|结束日期(时间戳)，yyyy/MM/dd|
|data[index].openLiveCourse.isRepeatWeek1|是否周一重复，Y（是）、N（否）|
|data[index].openLiveCourse.isRepeatWeek2|是否周二重复|
|data[index].openLiveCourse.isRepeatWeek3|是否周三重复|
|data[index].openLiveCourse.isRepeatWeek4|是否周四重复|
|data[index].openLiveCourse.isRepeatWeek5|是否周五重复|
|data[index].openLiveCourse.isRepeatWeek6|是否周六重复|
|data[index].openLiveCourse.isRepeatWeek7|是否周日重复|
|data[index].openLiveCourse.hasFile|是否有课时素材，0（没有）、1（有）|
|data[index].openLiveCourse.fileid|文件ID|
|data[index].openLiveCourse.filename|文件名|
|data[index].openLiveCourse.filesize|文件大小，单位：bytes|
|data[index].openLiveCourse.fileurl|下载链接|
|data[index].openLiveCourse.hasPlayback|是否有直播回放，Y（有）、N（没有）|
|data[index].openLiveCourse.videoId|直播回放的视频ID|
|data[index].openLiveCourse.videoDuration|视频播放时长，单位：秒|
|data[index].openLiveCourse.status|课时状态|
|data[index].openLiveCourse.createdTime|课时创建时间(时间戳)|
|data[index].openLiveCourse.lastModified|上次修改时间(时间戳)|
|data[index].openLiveCourse.startTs|开始时长(时间戳)，yyyy/MM/dd/HH:mm:ss|
|data[index].openLiveCourse.endTs|结束时间(时间戳)，yyyy/MM/dd/HH:mm:ss|
|data[index].openLiveCourse.isRepeat|是否每周重复|
|data[index].openLiveCourse.videoCoverImage|回放视频封面图|


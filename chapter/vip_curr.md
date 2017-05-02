#VIP课时信息

* 功能：根据课程ID，返回所有直播公开课的课时信息
* URL： http://{网校域名}/api/curriculum/vip-curriculum
* Content-Type: application/json（校验失败：text/html）
* HTTP请求方式： GET/POST
* 请求参数

|参数名|	必选	|类型及范围|	说明|
|----|---|----|----|
|timestamp|	true|	long|	当前的时间戳|
|sign|	true|	string|	签名|
|courseId	|true	|long|	课程ID|

* 注意事项
  * 返回错误列表

| 返回响应代码 | 说明     |
|----------- | -------- |
| 200 | 查询成功 |
| 403 | 非法时间戳；找不到API；签名错误 |


JSON示例
操作结果返回json
````
//查询成功
{
  code: 200,
  status: "success",
  message: "",
  data: {
	vipLiveCurriculums: [
  	{
	  curriculumId: "177izqk6n9o",
	  curriculumType: "lecture",
	  termId: "177izqk5nph",
	  courseId: 177,
	  schoolId: "test",
	  title: "vip课程",
	  description: null,
	  ordered: 1488348358,
	  startKey: "20170317/12:00",
	  startDate: 1489680000000,
	  startTime: "12:00",
	  endKey: "20170317/12:30",
	  endDate: 1489680000000,
	  endTime: "12:30",
	  duration: 30,
	  hasFile: 0,
	  fileid: null,
	  filename: null,
	  filesize: 0,
	  fileurl: null,
	  hasPlayback: "Y",
	  videoId: "sl81a4jjbxd339735d345592136ed8fa_s",
	  videoDuration: 2,
	  status: "published",
	  createdTime: 1488348358000,
	  lastModified: 1489555351000,
	  startTs: 1489723200000,
	  endTs: 1489725000000,
	  videoCoverImage: "http://img.videocc.net/uimage/s/sl8da4jjbx/a/sl8da4jjbxd339735d345592136ed8fa_1.jpg"
	}],
    vipVodCurriculums: [ 
	{
	  curriculumId: "177j1lrs9me",
	  curriculumType: "section",
	  courseId: 177,
	  schoolId: "test",
	  title: "章节一",
	  description: null,
	  ordered: 1,
	  status: "draft",
	  isFree: "N",
	  hasVideo: 0,
	  videoId: "",
	  videoDuration: 0,
	  hasFile: 0,
	  fileid: "",
	  filename: null,
	  filesize: 0,
	  fileurl: null,
	  createdTime: 1492412358000,
	  lastModified: 1492412358000,
	  videoCoverImage: ""
	}]
  }
}

````

* 字段说明

|字段|	说明|
|---|----|
|code|	响应代码|
|status|	响应状态|
|message|	响应信息|
|data|	返回数据|
|data.vipLiveCurriculums|VIP直播课时列表|
|data.vipLiveCurriculums\[index\].curriculumId|课时ID|
|data.vipLiveCurriculums\[index\].curriculumType|课时类型，section(章节)、lecture(课时)|
|data.vipLiveCurriculums\[index\].termId|所属班期ID|
|data.vipLiveCurriculums\[index\].courseId|直播课程ID|
|data.vipLiveCurriculums\[index\].schoolId|网校ID|
|data.vipLiveCurriculums\[index\].title|课时标题|
|data.vipLiveCurriculums\[index\].description|课时简介|
|data.vipLiveCurriculums\[index\].ordered|排序序号，由小到大|
|data.vipLiveCurriculums\[index\].startKey|开始时间，yyyyMMdd/HH:mm|
|data.vipLiveCurriculums\[index\].startDate|开始日期(时间戳)，yyyy/MM/dd|
|data.vipLiveCurriculums\[index\].startTime|开始时间，HH:mm|
|data.vipLiveCurriculums\[index\].endKey|预计结束日期，yyyyMMdd/HH:mm|
|data.vipLiveCurriculums\[index\].endDate|预计结束日期(时间戳），yyyy/MM/dd|
|data.vipLiveCurriculums\[index\].endTime|预计结束时间，HH:mm|
|data.vipLiveCurriculums\[index\].duration|预计直播时长，单位：分钟|
|data.vipLiveCurriculums\[index\].hasFile|是否有课时素材：0(没有)、1(有)|
|data.vipLiveCurriculums\[index\].fileid|文件ID|
|data.vipLiveCurriculums\[index\].filename|文件名|
|data.vipLiveCurriculums\[index\].filesize|文件大小，单位：bytes|
|data.vipLiveCurriculums\[index\].fileurl|下载链接|
|data.vipLiveCurriculums\[index\].hasPlayback|是否有直播回放，Y(有)、N(没有)|
|data.vipLiveCurriculums\[index\].videoId|直播回放的视频ID|
|data.vipLiveCurriculums\[index\].videoDuration|视频播放时长，单位：秒|
|data.vipLiveCurriculums\[index\].status|课时状态|
|data.vipLiveCurriculums\[index\].createdTime|课时创建时间(时间戳)|
|data.vipLiveCurriculums\[index\].lastModified|上次修改时间(时间戳)|
|data.vipLiveCurriculums\[index\].startTs|开始时长(时间戳)，yyyy/MM/dd/HH:mm:ss|
|data.vipLiveCurriculums\[index\].endTs|结束时间(时间戳)，yyyy/MM/dd/HH:mm:ss|
|data.vipLiveCurriculums\[index\].videoCoverImage|回放视频封面图|
|data.vipVodCurriculums|VIP点播课时列表|
|data.vipLiveCurriculums\[index\].curriculumId|课时ID|
|data.vipLiveCurriculums\[index\].curriculumType|课时类型，section(章节)、lecture(课时)|
|data.vipLiveCurriculums\[index\].courseId|直播课程ID|
|data.vipLiveCurriculums\[index\].schoolId|回放视频封面图|
|data.vipLiveCurriculums\[index\].title|课时标题|
|data.vipLiveCurriculums\[index\].description|课时简介|
|data.vipLiveCurriculums\[index\].ordered|排序序号，由小到大|
|data.vipLiveCurriculums\[index\].status|课时状态|
|data.vipLiveCurriculums\[index\].isFree|是否免费|
|data.vipLiveCurriculums\[index\].hasVideo|是否有课时素材：0(没有)、1(有)|
|data.vipLiveCurriculums\[index\].videoId|直播回放的视频ID|
|data.vipLiveCurriculums\[index\].videoDuration|视频播放时长，单位：秒|
|data.vipLiveCurriculums\[index\].hasFile|是否有课时素材：0(没有)、1(有)|
|data.vipLiveCurriculums\[index\].fileid|是否有课时素材：0(没有)、1(有)|
|data.vipLiveCurriculums\[index\].filename|文件名|
|data.vipLiveCurriculums\[index\].filesize|文件大小，单位：bytes|
|data.vipLiveCurriculums\[index\].fileurl|下载链接|
|data.vipLiveCurriculums\[index\].createdTime|课时创建时间(时间戳)|
|data.vipLiveCurriculums\[index\].lastModified|上次修改时间(时间戳)|
|data.vipLiveCurriculums\[index\].videoCoverImage|回放视频封面图|

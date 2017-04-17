#直播公开课课时信息
* 功能：根据课程ID，返回该直播公开课的所有课时信息
* URL： http://{网校域名}/api/curriculum/live-open-curriculum
* Content-Type： application/json（校验失败：text/html）
* HTTP请求方式：GET/POST
* 请求参数

|参数名|	必选|	类型及范围|	说明|
|----|----|----|----|
| timestamp | true | long | 当前的时间戳 |
| sign | true | string | 签名 |
| courseId | true | long | 课程ID |

* 注意事项
  * 返回错误列表

| 返回响应代码 | 说明     |
|----------- | -------- |
|400         | 非法时间戳 |
|400         |	找不到API|
|403         |	签名错误  |
|200         |	查询成功  |

* JSON示例
````
//查询成功
{
  code: 200,
  status: "success",
  message: "",
  data: [
	{
	  curriculumId: "174iz87rro7",
	  curriculumType: "lecture",
	  courseId: 174,
	  schoolId: "test",
	  title: "直播公开课",
	  description: null,
	  ordered: 1,
	  startDate: 1488988800000,
	  startTime: "17:04",
	  endTime: "22:04",
	  duration: 300,
	  hasEndDate: "Y",
	  endDate: 1488988800000,
	  isRepeatWeek1: "N",
	  isRepeatWeek2: "N",
	  isRepeatWeek3: "N",
	  isRepeatWeek4: "N",
	  isRepeatWeek5: "N",
	  isRepeatWeek6: "N",
	  isRepeatWeek7: "N",
	  hasFile: 0,
	  fileid: null,
	  filename: null,
	  filesize: 0,
	  fileurl: null,
	  hasPlayback: "N",
	  videoId: null,
	  videoDuration: 0,
	  status: "published",
	  createdTime: 1487239118000,
	  lastModified: 1489056470000,
	  startTs: 1489050240000,
	  endTs: 1489068240000,
	  isRepeat: "N",
	  videoCoverImage: ""
	}
  ]
}
````

* 字段说明

|字段|说明|
|---|---|
|code|	响应代码|
|status|	响应状态|
|message|	响应信息|
|data|	返回数据|
|data[index].curriculumId|课时ID|
|data[index].curriculumType|课时类型，section（章节）、lecture（课时）|
|data[index].courseId|课程ID|
|data[index].schoolId|网校ID|
|data[index].title|课时标题|
|data[index].description|课时简介|
|data[index].ordered|排序序号，有小到大|
|data[index].startDate|开始日期，yyyy/MM/dd|
|data[index].startTime|开始时间，HH:mm|
|data[index].endTime|预计结束时间，HH:mm|
|data[index].duration|预计直播时长，单位：分钟|
|data[index].hasEndDate|是否永不结束|
|data[index].endDate|结束日期，yyyy/MM/dd|
|data[index].isRepeatWeek1|是否周一重复，Y（是）、N（否）|
|data[index].isRepeatWeek2|是否周二重复|
|data[index].isRepeatWeek3|是否周三重复|
|data[index].isRepeatWeek4|是否周四重复|
|data[index].isRepeatWeek5|是否周五重复|
|data[index].isRepeatWeek6|是否周六重复|
|data[index].isRepeatWeek7|是否周日重复|
|data[index].hasFile|是否有课时素材，0（没有）、1（有）|
|data[index].fileid|文件ID|
|data[index].filename|文件名|
|data[index].filesize|文件大小，单位：bytes|
|data[index].fileurl|下载链接|
|data[index].hasPlayback|是否有直播回放，Y（有）、N（没有）|
|data[index].videoId|直播回放的视频ID|
|data[index].videoDuration|视频播放时长，单位：秒|
|data[index].status|课时状态|
|data[index].createdTime|课时创建时间|
|data[index].lastModified|上次修改时间|
|data[index].startTs|开始时长，yyyy/MM/dd/HH:mm:ss|
|data[index].endTs|结束时间，yyyy/MM/dd/HH:mm:ss||
|data[index].isRepeat|是否每周重复|
|data[index].videoCoverImage|回放视频封面图|

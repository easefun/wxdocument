#点播公开课课时信息
* 功能：根据课程ID，返回所有点播公开课的课时信息
* URL：http://{网校域名}/api/wx/curriculum/vod-open-curriculum
* Content-Type： application/json（校验失败：text/html）
* HTTP请求方式： GET/POST
* 请求参数

|参数名|	必选|	类型及范围|	说明|
|-----|----|------------|------|
| courseId|	true|	long|	课程ID|
| sessionId | true | string | 会话ID |

* 注意事项
  * 返回错误列表

| 返回响应代码 | 说明     |
|----------- | -------- |
|400         |	会话ID错误  |
|200         |	查询成功  |

JSON示例
操作结果返回json
````
//查询成功
{
  code: 200,
  status: "success",
  message: "",
  data: [
  {
	curriculumId: "176izhzhngf",
	curriculumType: "section",
	courseId: 176,
	schoolId: "test",
	title: "第一章",
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
	createdTime: 1487829871000,
	lastModified: 1487830322000,
	videoCoverImage: ""
  },
  {
	curriculumId: "176izhzipyz",
	curriculumType: "lecture",
	courseId: 176,
	schoolId: "test",
	title: "课时1",
	description: null,
	ordered: 2,
	status: "draft",
	isFree: "N",
	hasVideo: 1,
	videoId: "sl8da4jjbxe2a142a68695c377aa8aa4_s",
	videoDuration: 121,
	hasFile: 0,
	fileid: "",
	filename: null,
	filesize: 0,
	fileurl: null,
	createdTime: 1487829921000,
	lastModified: 1487829921000,
	videoCoverImage: "http://img.videocc.net/uimage/s/sl8da4jjbx/4/sl8da4jjbxe2a142a68695c377aa8aa4_1.jpg"
  }]
}
````

* 字段说明

|字段|	说明|
|---|----|
|code|	响应代码|
|status|	响应状态|
|message|	响应信息|
|data|	返回数据|
|data\[index\].curriculumId|课时ID|
|data\[index\].curriculumType|课时类型，section(章节)、lecture(课时)|
|data\[index\].courseId|课程ID|
|data\[index\].schoolId|网校ID|
|data\[index\].title|课时标题|
|data\[index\].description|课时简介|
|data\[index\].ordered|排序序号，由小到大|
|data\[index\].status|课时状态|
|data\[index\].isFree|允许免费试看，Y(允许)、N(不允许)|
|data\[index\].hasVideo|是否有视频,0(没有)、1(有)|
|data\[index\].videoId|视频ID|
|data\[index\].videoDuration|视频播放时长，单位：秒|
|data\[index\].hasFile|是否有课时素材，0(没有)、1(有)|
|data\[index\].fileid|文件ID|
|data\[index\].filename|文件名|
|data\[index\].filesize|文件大小，单位：bytes|
|data\[index\].fileurl|文件连接|
|data\[index\].createdTime|创建时间(时间戳)|
|data\[index\].lastModified|上传修改时间(时间戳)|
|data\[index\].videoCoverImage|视频封面图|
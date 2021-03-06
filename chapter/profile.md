#获取用户信息
* 功能：获取某用户个人信息
* URL： http://{网校域名}/api/user/用户ID/get
* HTTP请求方式: GET
* 响应数据类型: JSON
* 请求参数

|参数名|	必选|	类型及范围|	说明|
|--|--|--|--|
|userId	|true|	string|	用户ID|
|timestamp|	true|	long|	当前的时间戳|
|sign|	true|	string|	签名|

* 注意事项
  * 返回错误列表

| 返回响应代码 | 说明     |
|----------- | -------- |
| 200 | 查询成功 |
| 403 | 非法时间戳；找不到API；找不到用户；签名错误 |

* JSON示例
````
//普通用户
{
  code: 200,
  status: "success",
  message: "",
  data: {
	user: {
	  userId: "iv38g51n",
	  avatar: "https://res.wangxiaoyun.net/assets/images/default/avatar.png",
	  mobile: "13888888888",
	  nickName: "学员昵称",
	  gender: "S",
	  roleCodes: "student",
      roleNames: "学员",
	  createdTime: 1478230795000,
	  lastLoginTime: 1484104186000,
	  occupation: "",
	  isRecommend: "N",
	  courseList: [ ]
	}
  }
}
````
`````
//教师用户
{
  code: 200,
  status: "success",
  message: "",
  data: {
	user: {
	  userId: "iv9494le",
	  avatar: "https://res.wangxiaoyun.net/assets/images/avatars/10avatar.jpg",
	  mobile: "13777777777",
	  nickName: "教师昵称",
	  gender: "M",
	  createdTime: 1478586542000,
	  lastLoginTime: 1492399308000,
	  occupation: "",
	  roleCodes: "student,teacher",
	  roleNames: "学员,教师",
	  isRecommend: "N",
	  courseList: [
	    {
	  	  courseId: "1",
	  	  title: "英语音标从入门到精通",
	  	  status: "published"
	    }
	  ]
  	}
  }
}
``````
* 字段说明

|字段|	说明|
|---|----|
|code	|响应代码|
|status|	响应状态|
|message	|响应信息|
|data|	用户信息数据|
|data.user.userId	|用户ID|
|data.user.avatar	|用户头像链接|
|data.user.mobile	|用户手机号|
|data.user.nickname	|用户昵称|
|data.user.gender	|用户性别，M（男）、F（女）、S（保密）|
|data.user.createdTime|	用户创建时间|
|data.user.lastLoginTime|	用户最后登录时间(时间戳)|
|data.user.occupation	|用户 职位|
|data.user.roleCodes	|用户角色代码|
|data.user.roleNames	|用户角色|
|data.user.isRecommend	|是否为推荐老师，Y（是）、N（否）|
|data.user.courseList	|教师所教课程|
|data.user.courseList\[index\].courseId	|课程ID|
|data.user.courseList\[index\].title	|课程标题|
|data.user.courseList\[index\].status	|课程状态（草稿：draft，已发布：published，已隐藏：hidden，已删除：deleted）|
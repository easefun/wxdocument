#添加用户

* 功能：添加新用户，返回简单的用户信息
* URL： http://{网校域名}/api/user/add
* HTTP请求方式： POST
* 响应数据类型: JSON
* 请求参数

|参数名|	必选|	类型及范围|	说明|
|-----|----|------------|-------|
|timestamp|	true|	long|	当前的时间戳 |
|sign	|true|	string	|签名 |
|password|	true|	string	|密码（使用MD5加密后的密码）|
|mobile	|true|	string|手机号码（11位手机号）	|
|nickname|	true	|string|昵称（长度不能超过60个字符） |
|isAdmin|	false	|string|是否是管理员（‘Y’为是， ‘N’为否）默认为'N' |
|isTeacher|	false	|string|是否是教师（‘Y’为是， ‘N’为否）默认为'N' |

* 注意事项
	* 返回错误列表

|返回响应代码|	说明|
|----------|-------|
| 200 |	查询成功 |
| 400 |	传入参数错误 |
| 403 | 非法时间戳；找不到API；签名错误 |

JSON示例
````
// 添加成功
{
   "code":200,
   "status":"success",
   "message":"",
   "data":
      {
        "userId":"jk1z9kax",
        "nickname":"paul",
        "account":"13650957983",
        "schoolId":"demo"
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
| data.userId | 用户ID |
| data.nickname | 用户昵称 |
| data.account | 用户账号 |
| data.schoolId | 网校ID |


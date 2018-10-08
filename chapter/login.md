# 用户登录

* 功能：用户登录，将用户信息存在session中，密码错误3次，用户将被锁定一天。
* URL：[http://{网校域名}/api/login](http://{网校域名}/api/login)
* HTTP请求方式： POST
* 响应数据类型: JSON
* 请求参数

| 参数名 | 必选 | 类型及范围 | 说明 |
| --- | --- | --- | --- |
| timestamp | true | long | 当前的时间戳 |
| sign | true | string | 签名 |
| username | true | string | 登录帐户 |
| password | true | string | 登录密码\(使用MD5加密\) |

* 注意事项
  * 返回错误列表

| 返回响应代码 | 说明 |
| --- | --- |
| 200 | 登录成功 |
| 400 |	帐号或者密码不能为空；密码错误；输入帐户密码错误三次，用户将被锁定一天；用户已经被锁定；用户不存在 |
| 403 | 非法时间戳；找不到API；签名错误 |

* JSON示例

```
//登录成功
{
  "code":200,
  "status":"success",
  "message":"",
  "data":
    {
      "userId":"j176rhdo",
      "nickname":"宝宝",
      "account":"13650957972",
      "schoolId":"demo",
      "token":"9a1a40f2696fdde266813d0b7e6faa7b"
    }
}
```

```
//登录失败
{
  "code": "400",
  "status": "error",
  "message": "密码错误。",
  "data": ""
}
```

* 字段说明

| 字段 | 说明 |
| --- | --- |
| code | 响应代码 |
| status | 响应状态 |
| message | 响应信息 |
| data | 返回数据 |
| data.userId | 用户ID |
| data.nickname | 用户昵称 |
| data.account | 用户账号 |
| data.schoolId | 网校ID |
| data.token | 授权token |

* TOKEN使用说明
登录接口登录成功后，返回值会带有TOKEN(TOKEN的有效期为10分钟且只能使用一次)，获取TOKEN并与此前的apiKey做一次MD5：
sign = MD5(apiKey + token)
获得sign值后，GET请求下面地址：（页面会自动登录跳转）
http://网校域名/login/token?token=token&sign=sign

# API文档说明 

* 开发者使用网校API需要事先申请开通网校并获得开发者账号 [申请开通网校](http://www.wangxiaoyun.net/)

* 接口鉴权方式：每个接口除本身需要提交参数外，还要另外提交两个参数用于接口校验

  * 需要的参数：

    * timestamp 当前时间戳

    * sign 签名

  * sign的拼接规则：（secretKey为管理员后台保存的Key）
    * secretKey+参数名1+参数值1+参数名2+参数值2+secretKey进过md5加密并字母变为大写（如果参数对应的值为空，则不用计入sign）
    * 参数是用参数名称以字母表abc..来排列
    * 例如：访问某个api，secretKey是"key"，传递的参数有name=Tony，pwd=2，sex=,timestamp=1491362788262。\(sex的值是空的\) 则sign的值为"keynameTonypwd2timestamp1491362788262key"这一个字符串经过MD5加密之后将字母全部变为大写便可以得到sign。  

* 校验返回结果：
  * 校验成功则会自动进入请求的后台。
  * 校验失败返回的结果为\(Content-Type:text/html\)
    ```
    <html>
    <head>
        <title>Error report</title>
    </head>
    <body>
      <h1>HTTP Status 400 - invalid timestamp.</h1>

    </body>
    </html>
    ```
  * 校验失败的提示信息与相应代码：

| 返回响应代码 | 说明 |
| --- | --- |
| 400 | 非法时间戳 |
| 400 | 找不到API |
| 400 | 找不到用户 |
| 403 | 签名错误 |

* 由网校跳到第三方平台的接口，网校会带一个token到第三方系统，验证是否是在网校跳转。
  * secretKey：这里的secretKey是系统的第三方接入设置的key,参考上面的描述;
  * token的规则：json + "DEWX_FLAG" + MD5;
  * json: 这是一个存放当前登录用户的userId 和 userName的json;
  * "DEWX_FLAG": 这是一个分割字符;
  * MD5: 这个md5的生成规则是 secretKey + json + secretKey这个字符用md5加密转大写，用于对比。
  * token生成的代码如下：
           JSONObject jsonObject = new JSONObject();
           jsonObject.put("userId", (null != user) ? user.getUserId() : "");
           jsonObject.put("userName", (null != user) ? user.getNickname() : "");
     
           String paramBase64 = Base64Utils.encodeToString(jsonObject.toString().getBytes());
           String sign = apiKey + paramBase64 +apiKey;
           return URLEncoder.encode(paramBase64 + "DEWX_FLAG" + MD5Utils.getMD5String(sign).toUpperCase(),"UTF-8");
  
  * 可通过对paramBase64的Base64解密获得userId和userName，用于第三方系统使用; 
  * 可用secretKey + paramBase64 MD5加密判断是否来自网校。




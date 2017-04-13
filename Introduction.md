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




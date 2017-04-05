#说明文档

* 每个接口除本身需要提交参数外，还要另外提交两个参数用于接口校验：
	* 需要的参数：
		* 1.timestamp 当前时间戳
		* 2.sign 签名
	* sign的拼接规则：（secretKey为管理员后台保存的Key）
		* secretKey+参数名1+参数值1+参数名2+参数值2+secretKey进过md5加密并字母变为大写（如果参数对应的值为空，则不用计入sign）
		* 例如：访问某个api，secretKey是"key"，传递的参数有name=Tony，pwd=2，sex=，(sex的值是空的)则sign的值为"keynameTonypwd2key"这一个字符串经过MD5加密之后将字母全部变为大写便可以得到sign。  
* 校验返回结果：
	* 校验失败返回的结果为
	````
	<html>
	  <head>
	  <title>Apache Tomcat/7.0.59 - Error report</title>
	  </head>
	  <body>
	    <h1>HTTP Status 400 - invalid timestamp.</h1>
	    <HR size="1" noshade="noshade">
	    <p>
	       <b>type</b> Status report
	    </p>
	    <p>
	       <b>message</b> <u>invalid timestamp.</u>
	    </p>
	    <p>
	       <b>description</b> <u>The request sent by the client was
	           syntactically incorrect.</u>
	    </p>
	    <HR size="1" noshade="noshade">
	    <h3>Apache Tomcat/7.0.59</h3>
	  </body>
	 </html>
	````  
	* 校验失败的提示信息与相应代码：


		| 返回响应代码 | 说明     |
		|----------- | -------- |
		|400         | 非法时间戳 |
		|400         |	找不到API|
		|400         |	找不到用户|
		|403         |	签名错误  |


	* 校验成功则会自动进入请求的后台。
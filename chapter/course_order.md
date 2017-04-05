#课程订单
* 功能：获取课程订单，如果课程ID为空则返回该用户所有课程订单（返回课程订单的字段：订单名称，课程名称，订单生成时间，订单状态，订单支付时间，订单价格，支付方式）
* URL： http://{网校域名}/api/order/course-orders
* Content-Type： application/json（校验失败：text/html）
* HTTP请求方式: POST或者GET
* 请求参数

|参数名|	必选|	类型及范围|	说明|
|--|--|--|--|
|userId|	true|	string|	用户ID|
|timestamp|	true|	string|	当前的时间戳|
|sign|	true	|string	|签名|
|courseId	|false	|string	|课程ID|


* 注意事项
  * 返回错误列表

| 返回响应代码 | 说明     |
|----------- | -------- |
|400         | 非法时间戳 |
|400         |	找不到API|
|400         |	找不到用户|
|403         |	签名错误  |
|200         |	查询成功  |

* JSON示例
````
//查找成功
{"code": "200",
"status": "success",
"message": "",
"data":[{"tradeTitle": "订单名称", "title": "课程名称", "createTime": "订单生成时间",
         "status":"订单状态", "paidTime": "订单支付时间", "amount": "交付金额",
         "paymentType": "支付方式"},
         .............
        {"tradeTitle": "订单名称", "title": "课程名称", "createTime": "订单生成时间",
         "status":"订单状态", "paidTime": "订单支付时间", "amount": "交付金额",
         "paymentType": "支付方式"}
       ]
}
````

* 字段说明

|字段|	说明|
|---|----|
|code|	响应代码|
|status|	响应状态|
|message|	响应信息|
|data|	返回数据|
|data[n].tradeTitle|订单名称|
|data[n].title|课程名称|
|data[n].createTime|订单生成时间|
|data[n].status|订单状态|
|data[n].paidTime|订单支付时间|
|data[n].amount|交付金额|
|data[n].paymentType|支付方式|
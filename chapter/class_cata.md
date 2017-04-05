#课程分类

* getCategories
* 作用：获取整个网校的课程分类信息，返回结果以树型结构呈现
* URL
    http://api.wx.net/category/get-all
* 支持格式
    JSON 或 TEXT/HTML
* HTTP请求方式
    GET/POST
* 请求参数

| 参数名       | 必选  | 类型及范围 | 说明 |
| ----------- | ----- | -------- | -----|
| userId      | true  | string   |用户ID |
| appId       | true  | string   |appID |
| timestamp   | true  | string   |当前时间戳|
|sign         |true|string |签名|

* http请求头参数:

| 参数名	  | 必选	   | 类型及范围	| 说明 |
| ------- | ------ | ---------  |------|
|X-School|	false|	string|	网校ID|
|X-Domain|	false|	string|	网校域名|

* 注意事项
  * 返回错误列表

 | 返回响应代码|说明|
 |----|---|
 |400|	appId为空|
 |400|	非法时间戳|
 |400|	找不到API|
 |400|	找不到用户|
 |403|	签名错误|
 |200|	查询成功|
* 返回结果
 * 安全校验错误结果返回Text/Html

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

* JSON示例
  * 操作结果返回json

````
{"code": "200",
"status": "success",
"message": "",
"data":[{"categoryId": "分类ID",
          "name": "分类标题",
          "depth": "深度",
          "subCategory": [{"categoryId": "分类ID",
                             "name": "分类标题",
                             "depth": "深度",
                     "subCategory": [{...},{...}...{...}],
              ...
             "categoryId": "分类ID",
              "name": "分类标题",
              "depth": "深度",
              "subCategory": [{...},{...}...{...}]
                   }]
   },
   
   {"categoryId": "分类ID",
    "name": "分类标题",
    "depth": "深度",
   "subCategory": [{"categoryId": "分类ID",
               "name": "分类标题",
               "depth": "深度",
               "subCategory": [{...},{...}...{...}],
               ...
               "categoryId": "分类ID",
               "name": "分类标题",
               "depth": "深度",
               "subCategory": [{...},{...}...{...}]
                    }]
   }
   
   .......
  ]
}
`````

* 字段说明

|字段|说明|
|---|---|
|code|	响应代码|
|status|	响应状态|
|message|	响应信息|
|data|	返回数据|
|data[index].categoryId|	分类ID|
|data[index].name|	分类标题|
|data[index].depth|	深度|
|data[index].subCategory|	子分类|

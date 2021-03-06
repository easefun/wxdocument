#分页点播公开课课程列表
* 功能：分页返回点播公开课课程列表信息
* URL：http://{网校域名}/api/course/vod-open-courses
* HTTP请求方式： GET/POST
* 响应数据类型: JSON
* 请求参数

|参数名|	必选|	类型及范围|	说明|
|-----|----|------------|------|
|timestamp|	true|	long|	当前的时间戳|
|sign	|true|	string	|签名|
|page	|false|	int	|第几页，不传默认为1|
|pageSize	|false|	int	|每页显示数量，不传默认为6|


* 注意事项
  * 返回错误列表

| 返回响应代码 | 说明     |
|----------- | -------- |
| 200 | 查询成功 |
| 403 | 非法时间戳；找不到API；签名错误 |


JSON示例
操作结果返回json
````
//查询成功
{
  "code": 200,
  "status": "success",
  "message": "",
  "data": {
    "pageNumber": 1,
    "totalItems": 4,
    "contents": [
      {
        "courseId": 309,
        "courseType": "OPEN_VOD",
        "courseMeth": "VOD",
        "categoryId": 1,
        "schoolId": "test",
        "title": "如何用手机拍摄做直播",
        "subtitle": "459437593274183487vFDIAHF OIN OIA Hoighoiewn44e09jid发到手机哦大佛后",
        "summary": "2333333333333333easdgfhusaf",
        "keyword1": "",
        "keyword2": "",
        "keyword3": "",
        "objectives": null,
        "audiences": null,
        "requirements": null,
        "coverImage": "https://res.wangxiaoyun.net/thumbnail/287x180/201702/8873a96852a44769a8f8df9a1df60a30.png",
        "promoImage": null,
        "promoVideoId": null,
        "price": 0.00,
        "validity": 0,
        "isFree": "Y",
        "isFreeVip": "N",
        "isRecommend": "Y",
        "recommendTime": 1486973264000,
        "isBarrageEnabled": "N",
        "isTickerEnabled": "N",
        "tickerContent": null,
        "isRoyaltyEnabled": "N",
        "channelId": 0,
        "channelSecretkey": null,
        "status": "published",
        "userId": "iv8th0wc",
        "createdTime": 1486709506000,
        "publishedTime": null,
        "lastModified": 1510941607000,
        "studentCount": 497,
        "reviewCount": 2,
        "ratingScore": 4.50,
        "categoryName": "基础课",
        "teacherId": "iv8tth3a",
        "teacherName": "Lina",
        "teacherAvatar": "http://wx.qlogo.cn/mmhead/4M0MViahrTuFIgj36bRWFqrRk17ufc2x5OIo3BMYYCms/0",
        "channelPasswd": "",
        "playDuration": 5903,
        "videoView": 90,
        "flowSize": 0,
        "vodVideoView": 0,
        "description": "<p><br/></p><p><br/></p><p><br/></p><p style=\"text-align: center;\"><a href=\"http://test.dewx.net/course/309\" target=\"_blank\" style=\"box-sizing: border-box; text-decoration: none; color: rgb(33, 150, 243); font-family: \" microsoft=\"\" hiragino=\"\" sans=\"\" wenquanyi=\"\" micro=\"\" font-size:=\"\" white-space:=\"\" background-color:=\"\">如何用手机拍摄做直播</a></p><p><br/></p><p><br/></p><p style=\"text-align: center;\"><img src=\"//res.wangxiaoyun.net/image/201702/0c06fafeede54dba8566cd7fcd6cefe7.png\" title=\"201702/0c06fafeede54dba8566cd7fcd6cefe7.png\" alt=\"2.如何用手机拍摄做直播.png\"/></p>"
      },
      {
        "courseId": 308,
        "courseType": "OPEN_VOD",
        "courseMeth": "VOD",
        "categoryId": 1,
        "schoolId": "test",
        "title": "视频卡顿自查步骤",
        "subtitle": null,
        "summary": "",
        "keyword1": null,
        "keyword2": null,
        "keyword3": null,
        "objectives": null,
        "audiences": null,
        "requirements": null,
        "coverImage": "https://res.wangxiaoyun.net/thumbnail/287x180/201702/60f0d98eb666455eafe23d1f5a219211.png",
        "promoImage": null,
        "promoVideoId": null,
        "price": 0.00,
        "validity": 0,
        "isFree": "Y",
        "isFreeVip": "N",
        "isRecommend": "Y",
        "recommendTime": 1486973263000,
        "isBarrageEnabled": "N",
        "isTickerEnabled": "N",
        "tickerContent": null,
        "isRoyaltyEnabled": "N",
        "channelId": 0,
        "channelSecretkey": null,
        "status": "published",
        "userId": "iv8th0wc",
        "createdTime": 1486708686000,
        "publishedTime": null,
        "lastModified": 1510899922000,
        "studentCount": 268,
        "reviewCount": 3,
        "ratingScore": 4.67,
        "categoryName": "基础课",
        "teacherId": "iv8th0wc",
        "teacherName": "晓浓丸",
        "teacherAvatar": "https://test.wangxiaoyun.net/image/201708/4780222271944778ba6f43064631d548.jpg",
        "channelPasswd": "",
        "playDuration": 4596,
        "videoView": 53,
        "flowSize": 0,
        "vodVideoView": 0,
        "description": "<p><br/></p><p><br/></p><p><br/></p><p style=\"text-align: center;\"><a href=\"http://test.dewx.net/course/308\" target=\"_blank\" style=\"box-sizing: border-box; text-decoration: none; color: rgb(33, 150, 243); font-family: &quot;Microsoft Yahei&quot;, &quot;Hiragino Sans GB&quot;, &quot;WenQuanYi Micro Hei&quot;, sans-serif, arial; font-size: 18px; white-space: normal; background-color: rgb(255, 255, 255);\">视频卡顿自查步骤</a></p><p><br/></p><p><br/></p><p style=\"text-align: center;\"><img src=\"//res.wangxiaoyun.net/image/201702/78ed6e41a4cb49e385e9fb3b637dc934.png\" title=\"201702/78ed6e41a4cb49e385e9fb3b637dc934.png\" alt=\"1.视频卡顿自查步骤.png\"/></p>"
      },
      {
        "courseId": 313,
        "courseType": "OPEN_VOD",
        "courseMeth": "VOD",
        "categoryId": 1,
        "schoolId": "test",
        "title": "Polyv如何实现版权保护",
        "subtitle": null,
        "summary": "",
        "keyword1": null,
        "keyword2": null,
        "keyword3": null,
        "objectives": null,
        "audiences": null,
        "requirements": null,
        "coverImage": "https://res.wangxiaoyun.net/thumbnail/287x180/201702/5ed57094da0a4b69b93ed2fb3e43ef78.png",
        "promoImage": null,
        "promoVideoId": null,
        "price": 0.00,
        "validity": 0,
        "isFree": "Y",
        "isFreeVip": "N",
        "isRecommend": "Y",
        "recommendTime": 1486973228000,
        "isBarrageEnabled": "N",
        "isTickerEnabled": "N",
        "tickerContent": null,
        "isRoyaltyEnabled": "N",
        "channelId": 0,
        "channelSecretkey": null,
        "status": "published",
        "userId": "iv8th0wc",
        "createdTime": 1486710760000,
        "publishedTime": null,
        "lastModified": 1510855211000,
        "studentCount": 72,
        "reviewCount": 3,
        "ratingScore": 4.67,
        "categoryName": "基础课",
        "teacherId": "iv8th0wc",
        "teacherName": "晓浓丸",
        "teacherAvatar": "https://test.wangxiaoyun.net/image/201708/4780222271944778ba6f43064631d548.jpg",
        "channelPasswd": "",
        "playDuration": 3719,
        "videoView": 37,
        "flowSize": 0,
        "vodVideoView": 0,
        "description": "<p><br/></p><p><br/></p><p><br/></p><p style=\"text-align: center;\"><a href=\"http://test.dewx.net/course/313\" target=\"_blank\" style=\"box-sizing: border-box; text-decoration: none; color: rgb(33, 150, 243); font-family: &quot;Microsoft Yahei&quot;, &quot;Hiragino Sans GB&quot;, &quot;WenQuanYi Micro Hei&quot;, sans-serif, arial; font-size: 18px; white-space: normal; background-color: rgb(255, 255, 255);\">Polyv如何实现版权保护</a></p><p><br/></p><p><br/></p><p style=\"text-align: center;\"><img src=\"//res.wangxiaoyun.net/image/201702/90b8496f55ea419182865c7091d4ebb9.png\" title=\"201702/90b8496f55ea419182865c7091d4ebb9.png\" alt=\"6.Polyv如何实现版权保护.png\"/></p>"
      },
      {
        "courseId": 310,
        "courseType": "OPEN_VOD",
        "courseMeth": "VOD",
        "categoryId": 1,
        "schoolId": "test",
        "title": "保利威视产品介绍",
        "subtitle": null,
        "summary": "",
        "keyword1": null,
        "keyword2": null,
        "keyword3": null,
        "objectives": null,
        "audiences": null,
        "requirements": null,
        "coverImage": "https://res.wangxiaoyun.net/thumbnail/287x180/201702/6f755da9f9dd4bf08c200a3bba1c4b49.png",
        "promoImage": null,
        "promoVideoId": null,
        "price": 0.00,
        "validity": 0,
        "isFree": "Y",
        "isFreeVip": "N",
        "isRecommend": "Y",
        "recommendTime": 1486710648000,
        "isBarrageEnabled": "N",
        "isTickerEnabled": "N",
        "tickerContent": null,
        "isRoyaltyEnabled": "N",
        "channelId": 0,
        "channelSecretkey": null,
        "status": "published",
        "userId": "iv8th0wc",
        "createdTime": 1486710607000,
        "publishedTime": null,
        "lastModified": 1510855210000,
        "studentCount": 53,
        "reviewCount": 2,
        "ratingScore": 4.50,
        "categoryName": "基础课",
        "teacherId": "iv8th0wc",
        "teacherName": "晓浓丸",
        "teacherAvatar": "https://test.wangxiaoyun.net/image/201708/4780222271944778ba6f43064631d548.jpg",
        "channelPasswd": "",
        "playDuration": 4238,
        "videoView": 32,
        "flowSize": 0,
        "vodVideoView": 0,
        "description": "<p><br/></p><p><br/></p><p><br/></p><p style=\"text-align: center;\"><a href=\"http://test.dewx.net/course/310\" target=\"_blank\" style=\"box-sizing: border-box; text-decoration: none; color: rgb(33, 150, 243); font-family: &quot;Microsoft Yahei&quot;, &quot;Hiragino Sans GB&quot;, &quot;WenQuanYi Micro Hei&quot;, sans-serif, arial; font-size: 18px; white-space: normal; background-color: rgb(255, 255, 255);\">保利威视产品介绍</a></p><p><br/></p><p><br/></p><p style=\"text-align: center;\"><img src=\"//res.wangxiaoyun.net/image/201702/3aa6fc4e48bd4c4b973c3980c7a0864d.png\" title=\"201702/3aa6fc4e48bd4c4b973c3980c7a0864d.png\" alt=\"3.保利威视产品介绍.png\"/></p>"
      }
    ],
    "firstPage": true,
    "lastPage": true,
    "startRow": 1,
    "nextPageNumber": 1,
    "prePageNumber": 1,
    "totalPages": 1,
    "endRow": 4,
    "limit": 4,
    "offset": 0
  }
}
````

* 字段说明

|字段|	说明|
|---|----|
|code|	响应代码|
|status|	响应状态|
|message|	响应信息|
|data|	返回数据|
|data.pageNumber|当前第几页|
|data.totalItems|当前页共几个课程|
|data.firstPage|当前是否是第一页|
|data.lastPage|当前是否是最后一页|
|data.totalItems|当前页共几个课程|
|data.firstPage|当前是否是第一页|
|data.lastPage|当前是否是最后一页|
|data.startRow|当前页第一条记录在总结果集中的位置，序号从1开始|
|data.endRow|当前页最后一条记录在总结果集中的位置|
|data.nextPageNumber|下一页的页码|
|data.prePageNumber|上一页的页码|
|data.totalPages|课程总数量|
|data.offset|单次查询第一条记录在总结果集中的位置，序号从0开始|
|data.limit|单次查询数量| 
|data\[index\].courseId|课程ID|
|data\[index\].courseType|课程类型|
|data\[index\].courseMeth|讲课方式|
|data\[index\].categoryId|课程分类ID|
|data\[index\].schoolId|网校ID|
|data\[index\].title|课程名称|
|data\[index\].subtitle|子标题|
|data\[index\].summary|简介|
|data\[index\].keyword1|关键词1|
|data\[index\].keyword2|关键词2|
|data\[index\].keyword3|关键词3|
|data\[index\].objectives|教学目标|
|data\[index\].audiences|目标学员|
|data\[index\].requirements|学习要求|
|data\[index\].coverImage|课程封面图片|
|data\[index\].promoImage|竖向的首页宣传图片)|
|data\[index\].promoVideoId|课程宣传片的视频ID|
|data\[index\].price|课程价格|
|data\[index\].validity|学习有效期|
|data\[index\].isFree|是否为免费课程：Y/N|
|data\[index\].isFreeVip|此课程对VIP会员是否免费|
|data\[index\].isRecommend|是否推荐：Y/N|
|data\[index\].recommendTime|推荐时间|
|data\[index\].isTickerEnabled|是否开启跑马灯功能：Y/N|
|data\[index\].tickerContent|跑马灯内容模版|           
|data\[index\].isRoyaltyEnabled|是否实施收入分成|
|data\[index\].channelId|频道号|
|data\[index\].channelSecretkey|频道Secretkey|
|data\[index\].status|课程状态|
|data\[index\].userId|课程创建者ID|
|data\[index\].createdTime|创建时间|
|data\[index\].publishedTime|发布时间|
|data\[index\].lastModified|更新时间|
|data\[index\].studentCount|学生数，浏览数|
|data\[index\].reviewCount|评分数|
|data\[index\].ratingScore|评分平均数|
|data\[index\].categoryName|分类名称|
|data\[index\].teacherId|教师ID|
|data\[index\].teacherName|教师名称|
|data\[index\].teacherName|视频封面图|
|data\[index\].teacherAvatar|教师头像|
|data\[index\].channelPasswd|频道密码|
|data\[index\].playDuration|播放总分钟数|
|data\[index\].videoView|播放总次数|
|data\[index\].flowSize|播放总流量|
|data\[index\].vodVideoView|点播播放次数|
|data\[index\].description|课程详情|

# 获取最进观看的课程

* 功能： 获取网校最近一个月观看的课程，降序排序
* URL： [http://{网校域名}/api/course/recent-watch](http://{网校域名}/api/category/get-all)
* HTTP请求方式： GET/POST
* 响应数据类型: JSON
* 请求参数

| 参数名 | 必选 | 类型及范围 | 说明 |
| --- | --- | --- | --- |
| timestamp | true | long | 当前时间戳 |
| sign | true | string | 签名 |
| userId | true | string | 用户Id |

* 注意事项
  * 返回错误列表

| 返回响应代码 | 说明 |
| --- | --- |
| 403 | 非法时间戳；找不到API；签名错误；用户Id为空 |
| 200 | 查询成功 |

* JSON示例

```
{
    code: 200,
    status: "success",
    message: "",
    data: [
        {
        courseId: 1815,
        courseType: "VIP",
        categoryId: 76,
        schoolId: "test",
        title: "wefwefewf",
        subtitle: null,
        summary: null,
        coverImage: null,
        price: 0,
        validity: 0,
        isFree: "Y",
        isFreeVip: "N",
        status: "published",
        createdTime: 1516673530000,
        publishedTime: null,
        lastModified: 1557367217000,
        studentCount: 6,
        reviewCount: 0,
        ratingScore: 0,
        categoryName: "课程分类",
        teacherId: "iv9491le",
        teacherName: "Lin",
        teacherAvatar: "201704\56604837c70f467d8751cbca77e42613.jpg",
        studentNum: 5,
        description: null
        }
    ]
}
```

* 字段说明

| 字段 | 说明 |
| --- | --- |
| code | 响应代码 |
| status | 响应状态 |
| message | 响应信息 |
| data | 返回数据 |
| data\[index\].courseId | 课程ID |
| data\[index\].courseType | 课程类型，OPEN_VOD（点播公开课）、OPEN_LIVE（直播公开课）、VIP（VIP课程） |
| data\[index\].categoryId | 分类ID |
| data\[index\].schoolId | 网校ID |
| data\[index\].title | 课程标题 |
| data\[index\].subtitle | 课程子标题 |
| data\[index\].summary | 课程概要 |
| data\[index\].coverImage | 课程封面图 |
| data\[index\].price | 课程定价 |
| data\[index\].validity | 学习有效期，单位：天 |
| data\[index\].isFree | 是否免费，Y（免费）、N（收费） |
| data\[index\].isFreeVip | 是否对VIP会员免费，Y（免费）、N（收费） |
| data\[index\].status | 课程状态 draft（草稿）、published（已发布）、hidden（已隐藏）、deleted（已删除）|
| data\[index\].createdTime | 课程创建时间 |
| data\[index\].publishedTime | 课程发布时间(时间戳) |
| data\[index\].lastModified | 课程最近修改时间(时间戳) |
| data\[index\].studentCount | 学员总数 |
| data\[index\].reviewCount | 评论数据 |
| data\[index\].ratingScore | 平均评分 |
| data\[index\].categoryName | 分类名称 |
| data\[index\].teacherId | 主讲老师ID |
| data\[index\].teacherName | 主讲老师名称 |
| data\[index\].teacherAvatar | 主讲老师头像 |
| data\[index\].description | 课程详情 |

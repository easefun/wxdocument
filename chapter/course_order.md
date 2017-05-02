#课程订单
* 功能：获取课程订单，如果课程ID为空则返回该用户所有课程订单（返回课程订单的字段：订单名称，课程名称，订单生成时间，订单状态，订单支付时间，订单价格，支付方式）
* URL： http://{网校域名}/api/order/course-orders
* Content-Type： application/json（校验失败：text/html）
* HTTP请求方式: POST或者GET
* 请求参数

|参数名|	必选|	类型及范围|	说明|
|--|--|--|--|
| userId | true | string | 用户ID |
| timestamp | true | long | 当前的时间戳 |
| sign|true | string | 签名 |
| courseId | false | long	| 课程ID |


* 注意事项
  * 返回错误列表

| 返回响应代码 | 说明     |
|----------- | -------- |
| 200 |	查询成功 |
| 403 | 非法时间戳；找不到API；找不到用户；签名错误 |

* JSON示例
````
//查找成功
{
  code: 200,
  status: "success",
  message: "",
  data: [
	{
	  orderId: "F20170414154703504b8c",
	  schoolId: "test",
	  tradeTitle: "购买《语文一年级》",
	  tradeNote: null,
	  amount: 0,
	  payment: 0,
	  coupon: 0,
	  couponId: null,
	  userId: "iv9491le",
	  nickname: "2233尖峰",
	  courseId: 76,
	  courseType: "VIP",
	  courseMeth: "LIVE",
	  categoryId: 75,
	  categoryName: "语文",
	  title: "购买《语文一年级》",
	  summary: null,
	  coverImage: "https://res.wangxiaoyun.net/image/287x180/201704/c0cf3f220c474d7bb19ef55719bea124.png",
	  promoImage: null,
	  promoVideoId: null,
	  price: 0,
	  validity: 0,
	  isFree: "Y",
	  isFreeVip: "Y",
	  isRecommend: "N",
	  recommendTime: null,
	  isBarrageEnabled: "Y",
	  isTickerEnabled: "Y",
	  tickerContent: "微网校",
	  isRoyaltyEnabled: "N",
	  channelId: 0,
	  teacherId: null,
	  teacherName: null,
	  teacherAvatar: null,
	  paymentType: "MANUALLY",
	  status: "FINISH",
	  outTradeNo: "",
	  outTradeStatus: "",
	  createdTime: 1492156024000,
	  lastModified: 1492156024000,
	  paidTime: 1492156024000
	}
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
| data\[index\].orderId|订单ID|
| data\[index\].schoolId|网校ID|
| data\[index\].tradeTitle|交易标题|
| data\[index\].tradeNote|交易备注|
| data\[index\].amount|交易金额|
| data\[index\].payment| 交易金额 |
| data\[index\].coupon| 代金券金额 |
| data\[index\].couponId| 代金券ID |
| data\[index\].userId| 购买者ID |
| data\[index\].nickname| 购买者昵称 |
| data\[index\].courseId| 课程ID |
| data\[index\].courseType| 课程类型 |
| data\[index\].courseMeth| 上课方式 |
| data\[index\].categoryId| 分类ID |
| data\[index\].categoryName| 分类名称 |
| data\[index\].title| 课程标题 |
| data\[index\].summary| 课程概要 |
| data\[index\].coverImage| 课程封面图 |
| data\[index\].promoImage| 课程宣传图 |
| data\[index\].promoVideoId| 课程宣传片视频ID |
| data\[index\].price | 课程定价 |
| data\[index\].validity | 学习有效期，单位：天 |
| data\[index\].isFree | 是否免费，Y（免费）、N（收费） |
| data\[index\].isFreeVip | 是否对VIP会员免费，Y（免费）、N（收费） |
| data\[index\].isRecommend | 是否推荐，Y（推荐）、N（不是推荐） |
| data\[index\].price | 课程定价 |
| data\[index\].validity | 学习有效期，单位：天 |
| data\[index\].isFree | 是否免费，Y（免费）、N（收费） |
| data\[index\].isFreeVip | 是否对VIP会员免费，Y（免费）、N（收费） |
| data\[index\].isRecommend | 是否推荐，Y（推荐）、N（不是推荐） |
| data\[index\].recommendTime | 推荐时间 |
| data\[index\].isBarrageEnabled | 是否开启弹幕，Y（开启）、N（关闭） |
| data\[index\].isTickerEnabled | 是否开启跑马灯功能，Y（开启）、N（关闭） |
| data\[index\].tickerContent | 跑马灯内容模板 |
| data\[index\].isRoyaltyEnabled | 是否实施收入分成 |
| data\[index\].channelId | 直播课程的频道ID |
| data\[index\].teacherId | 主讲老师ID |
| data\[index\].teacherName | 主讲老师名称 |
| data\[index\].teacherAvatar | 主讲老师头像 |
| data\[index\].paymentType | 支付方式 |
| data\[index\].status| 订单状态 |
| data\[index\].outTradeNo | 外部支付交易号 |
| data\[index\].outTradeStatus | 外部支付交易状态 |
| data\[index\].createdTime | 订单创建时间(时间戳) |
| data\[index\].lastModified | 订单修改时间(时间戳) |
| data\[index\].paidTime | 订单支付时间(时间戳) |

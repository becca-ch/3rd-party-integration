## 订单同步接口
### 1.订单实时推送
#### 1.1 接口描述
> 实时推送订单信息到商户方，暂定付款成功或退款成功状态推送订单信息，或由双方进一步确认其它状态
#### 1.2 请求方式
> POST
#### 1.3 url
> 商户方提供访问地址，端口，路径，参数，返回值
#### 1.4 数据方向
> 系统方至商户方
#### 1.5 请求参数
| 参数名称 | 参数类型 | 是否必须 | 示例值 | 参数描述  |
| :---  |   :-------    |    :---   | :---        | :---        |
| tId   | 字符串     | 是            | 1002241501752197580   |订单唯一标识|
| realPay   | 整型     | 是    | 120   |实付款，单位:分(RMB)|
| receiverName   | 字符串    | 是    | 老王  | 收货人姓名|
| mobile   | 字符串     | 是    | 13800001111   | 分页数据，每页显示数据条数 |
| postFee   | 整型     | 是    | 150   | 运费，单位:分(RMB) |
| gprice   | 整型     | 是    | 1500   | 商品价格，单位:分(RMB) |
| gsc   | 字符串     | 是    | 10mg*100s   | 商品规格 |
| gcode   | 字符串     | 是    | 20058962   | 商品编码 |
| gnum   | 整形     | 是    | 1   | 购买数量 |
| discount   | 整形     | 否    | 1   | 优惠金额，单位:分(RMB) |
| paystyle   | 字符串     | 是    | wx   | 支付方式::</br>ali (支付宝) ，</br>wx (微信)，</br> bil(快钱)，</br> unionPay(银联)，</br> health_insurance（医保），</br>cash（现金） |
| poststyle   | 字符串     | 否    | 170   | 购买方式::</br>150：送货上门；</br>160：门店自提；</br>170：门店直购 |
| uid   | 字符串     | 否    | 120   | 门店编码 |
| storeUserMobile   | 字符串     | 否    | 13833334444   | 下单店员手机 |
| totalPay   | 整形     | 是    | 180   | 总金额(商品金额+运费)，单位:分(RMB) |
| totalFee   | 整形     | 否    | 180   | 商品金额，单位:分(RMB) |
| receicerAddress   | 字符串     | 是    | 北美市美帝路111号   | 收货人地址 |
| memberMobile   | 字符串     | 是    |  13833334444  | 收货人手机 |
| status   | 整形     | 是    | 1   | 订单状态::1：已付款（未退款），0：已退款 |
--------------------- 
#### 1.6 请求示例
 ``` 
{
  "msg": "订单查询成功",
  "code": 0,//0:成功，-1：失败
  "tradesList":
    {
      "realPay": 180,//实付款
      "receiverName": "老王",//收货人姓名
      "mobile": "13800001111",//收货人手机号码
      "postFee": 0,//运费
      "orderList": [//商品列表
        {
          "gprice": 100,//商品价格
          "gsc": "10mg*100s",//商品规格
          "gcode": "32301029",//商品编码
          "gnum": 1//购买数量
        }
      ],
      "discount": 0,//优惠金额
      "paystyle": "wx",//支付方式:ali (支付宝) ，wx (微信)， bil(快钱)， unionPay(银联)， health_insurance（医保），cash（现金）
      "poststyle": 170,//购买方式::150：送货上门；160：门店自提；170：门店直购
      "tId": 1002241501752197580,//订单编号
      "uid": "123",//门店编码
      "storeUserMobile":"13811112222",//下单店员手机
      "totalPay": 180,//商品金额+运费
      "totalFee": 180,//商品金额
      "receicerAddress": "",//收货地址
      "memberMobile": "13800001111",//会员手机号码
      "status": 1//订单状态：1：已付款（未退款），0：已退款
    },
}
```
#### 1.7 返回示例
* 对商户方暂无要求
#### 1.8 特殊说明
* storeUserMobile属性目前仅提供给100309
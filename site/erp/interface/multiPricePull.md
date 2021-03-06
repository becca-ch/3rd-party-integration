## 多价格同步接口
### 1.多价格定时同步
#### 1.1 接口描述
* 定时同步商户各门店价格，使得系统商城价格遵循特定门店价格。
* 常见场景：门店店员店内下单；店外下单分单。
* 目前暂定单次请求不超过2000条。
* 目前暂定同步频率为2小时/次。
* 有会员价格的，优先取会员价格，否则取门店零售价格。
* 如果对接了实时同步价格的接口，本接口不需要对接，以实时同步优先
#### 1.2 请求方式
> GET
#### 1.3 url
> /goods/multiPricePull
#### 1.4 数据方向
> ERP-->线上系统
#### 1.5 请求参数
> 无请求参数
#### 1.6 请求数据
 ``` 

```
#### 1.7 返回数据
```
| 参数名称 | 参数类型 | 是否必须 | 示例值 | 参数描述  |
| :---         |     :---      |     :--- | :--- | :--- |
| code   | 字符串     | 是    | 10000    | 请求状态值，10000:成功;20000:失败 |
| msg   | 字符串    | 是    | 成功    | 成功或失败消息 |
| siteId   | 字符串     | 是    | 100100   |商户ID|
| storeNumber   | 字符串     | 是    | 0010   |门店编码，仅支持单一门店|
| goodsCode   | 字符串    | 是    | 544744    | 商品编码 |
| storeGoodsPrice   | 整型    | 是    | 2022   | 门店商品现价，单位:分(RMB) |
| storeMemberPrice   | 整型    | 是    | 2022   | 门店商品会员现价，单位:分(RMB) |
| type   | 整型    | 是    | 10   | 价格体系类型::<br/> 10(总部基础价格)<br/>20(市级价)<br/>30(区级价)<br/>40(门店价) |
--------------------- 
```
#### 1.8 请求成功(更新价格成功)
```
"code": "10000",
"msg": "请求成功",
"data": {
  "goodsPrices":[
     {
	"storeNumber":"A316",//门店编码
	"goodsCode":"K1232313",//商品编码
	"storeGoodsPrice":"39.79"//门店价格；元为单位
	"storeMemberPrice":"39.79"//会员价格；元为单位
     },
     {
	"storeNumber":"A316",
	"goodsCode":"AC15220",
	"storeGoodsPrice":"39.79"//门店价格；元为单位
	"storeMemberPrice":"39.79"//会员价格；元为单位
     }
  ]
}
```
#### 1.9 请求成功(更新价格失败)
```
{
    "msg": "请求成功",
    "code": 10000
}
```
#### 1.10 请求成功(数据有误)
```
{
    "msg": "通讯异常，请稍后重试",
    "code": 20000
｝
```
#### 1.11 请求成功(数据有误)
```
{
    "msg": "需要修改的商品信息不能为空",
    "code": 20000
｝
```

## 盘点审批商品数据
### 1.提供盘点审批商品数据查询
#### 1.1 接口描述
* 线上系统后台审批完成后，ERP方从线上系统读取审批商品数据
* 如果批量传输，暂定单次传输不超过1000个商品
#### 1.2 请求方式
> GET
#### 1.3 触发条件
> 盘点单审批通知成功
#### 1.3 url
* ERP：
> /inventory/approvedGoods
#### 1.4 数据方向
> 线上系统-->ERP
#### 1.5 请求参数
| 参数名称 | 参数类型 | 是否必须 | 示例值 | 参数描述  |
| :---         |     :---      |     :--- | :--- | :--- |
| inventoryNo   | 字符串     | 是    | PD100190170003    | 盘点单号 |
| pageNum   | 整型     | 否    | 1    | 页码，默认:1 |
| storeNumber   | 字符串     | 是    | 1001    | 门店编号 |
--------------------- 
#### 1.6 返回参数
| 参数名称 | 参数类型 | 是否必须 | 示例值 | 参数描述  |
| :---         |     :---      |     :--- | :--- | :--- |
| code   | 字符串     | 是    | 10000    | 返回代码，10000(查询成功)，20000(查询失败) |
| msg   | 字符串    | 是    | 回传成功    | 返回消息描述 |
| inventoryNo   | 字符串     | 是    | PD100190170003    | 盘点单号 |
| unitNo   | 字符串    | 是    | 1192    | 门店编号 |
| goodsCode   | 字符串    | 是    | AW020785    | 商品编码 |
| accountQuatity   | 数值    | 是    | 2   | 账面库存数 |
| actualInventoryQuatity   | 数值    | 是    | 12    | 实际盘点数 |
| batchNumber   | 字符串    | 是    | AC321321    | 批号 |
| totalPage   | 数值    | 是    | 12    | 分页总页数 |
--------------------- 
#### 1.7 返回示例
 ``` 
 "code" : 10000,
 "msg" : "回传成功",
 "data": {
   "totalPage": 12,//总页数
   "inventoryNo": "PD100190170003",//盘点单号
   "goodsList": [
		{
		  "unitNo": "1192",
		  "goodsCode": "AW020785",//商品编码
		  "accountQuatity": "2",//账面库存数
		  "actualInventoryQuatity": "12",//实际盘点数
		  "batchNumber": "AC321321"//批号
		 },
		 {
		  "unitNo": "1192",
		  "goodsCode": "AW020786",//商品编码
		  "accountQuatity": "2",//账面库存数
		  "actualInventoryQuatity": "12",//实际盘点数
		   "batchNumber": "AC321321"//批号
		 }
		]
     }
```
#### 1.8 返回成功(未匹配到库存信息)
```
{
  "code": 10000,
  "data": {},
  "msg":"回传成功"
}
```
#### 1.9 请求失败
```
{
  "code": 20000,
  "data": {},
  "msg":"回传失败，无法匹配商品，商品编码：20056508"
}
```


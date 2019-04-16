## 第三方对接——接口方案
* [请求注册](https://github.com/bluesx/3rd-party-integration/blob/master/site/erp/interface/accessToken.md)
* [订单同步](#)
  + [订单推送](https://github.com/bluesx/3rd-party-integration/blob/master/site/erp/interface/orderPush.md)
  + ~~[订单查询](https://github.com/bluesx/3rd-party-integration/blob/master/site/erp/interface/orderList.md)~~
* [库存信息](#)
  + [实时库存--主动方式](https://github.com/bluesx/3rd-party-integration/blob/master/site/erp/interface/storage.md)
  + [实时库存--被动方式](#)
* [会员信息](#)
  + [会员积分交互](https://github.com/bluesx/3rd-party-integration/blob/master/site/erp/interface/memberPointsInteraction.md)
  + [会员信息推送](https://github.com/bluesx/3rd-party-integration/blob/master/site/erp/interface/userInfo.md)
  + [会员信息更新](https://github.com/bluesx/3rd-party-integration/blob/master/site/erp/interface/userUpdate.md)
  + [会员积分获取](#)
  + [会员积分消费查询](#)
* [商品基础信息维护--待定](#)
  + [实时单个商品信息推送](#)
  + [实时批量商品信息推送](#)
* [商品价格](#)
  + [初始化商品价格](https://github.com/bluesx/3rd-party-integration/blob/master/site/erp/interface/initializeGoodsPrices.md)
  + [定时同步商品价格](https://github.com/bluesx/3rd-party-integration/blob/master/site/erp/interface/multiPricePull.md)
  + [实时单个商品价格推送](https://github.com/bluesx/3rd-party-integration/blob/master/site/erp/interface/multiPricePushSingle.md)
  + [实时批量商品价格推送](https://github.com/bluesx/3rd-party-integration/blob/master/site/erp/interface/multiPricePushBatch.md)
* [盘点信息](#)
  + [盘点接口交互](https://github.com/bluesx/3rd-party-integration/blob/master/site/erp/interface/inventoryInteraction.md)
  + [盘点数据读取](https://github.com/bluesx/3rd-party-integration/blob/master/site/erp/interface/inventoryGoodsInfo.md)
  + ~~[获取实时库存](https://github.com/bluesx/3rd-party-integration/blob/master/site/erp/interface/inventoryStorage.md)~~
  + [盘点审批通知](https://github.com/bluesx/3rd-party-integration/blob/master/site/erp/interface/inventoryApprovedNotify.md)
  + ~~[盘点审批回传](https://github.com/bluesx/3rd-party-integration/blob/master/site/erp/interface/inventoryApproved.md)~~
  + [盘点审批查询](https://github.com/bluesx/3rd-party-integration/blob/master/site/erp/interface/inventoryApprovedGoods.md)
* [站点信息](#)
  + [实时开站--待定](https://github.com/bluesx/3rd-party-integration/blob/master/site/erp/interface/siteStartup.md)
## ~~第三方对接——数据库方案~~
* [订单同步](#)
  + [订单推送](https://github.com/bluesx/3rd-party-integration/blob/master/site/erp/database/orders_sync.md)
* [库存信息](#)
  + [实时库存](https://github.com/bluesx/3rd-party-integration/blob/master/site/erp/database/goods_stock.md)
* [会员信息](#)
  + [会员信息查询](https://github.com/bluesx/3rd-party-integration/blob/master/site/erp/database/user_info.md)
  + [会员信息更新](https://github.com/bluesx/3rd-party-integration/blob/master/site/erp/database/user_info.md)
* [商品价格](https://github.com/bluesx/3rd-party-integration/blob/master/site/erp/database/goods_multi_price.md)
* [盘点信息](#)
  + [盘点计划商品信息](https://github.com/bluesx/3rd-party-integration/blob/master/site/erp/database/inventory_goods_info.md)
  + [盘点审批回传商品](https://github.com/bluesx/3rd-party-integration/blob/master/site/erp/database/inventory_approve.md)
  + [实时查询门店品类](#)
  + [实时库存确定盈亏](#)

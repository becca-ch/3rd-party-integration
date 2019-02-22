## 系统部署基础设施

| 设施名称 | 功能 | 基本配置 | 数量 | 单价(台/月)  |是否可选  |
| :---  |   :-------    |    :---   | :---        | :---        |:---        |
| ecs-web   | 主服务web层     | 8核/8G/IO优化/3M | 2   |350 | |
| ecs-service   | 主服务service层     | 8核/8G/IO优化/3M  | 4   |350| |
| ecs-erp-web   | Erp服务web层     | 8核/8G/IO优化/3M | 2   |350| |
| ecs-erp-service   | Erp服务service层     | 8核/8G/IO优化/3M| 2   |350| |
| ecs-es   | 搜索服务     | 8核/8G/SSD/3M  | 3   |370| |
| oss   | 图片及文件服务     | 按量            | 1   | 300 | |
| mns   | 消息队列    | 按量            | 1   | 40 |  |
| LSB   | 负载均衡    | 按量            | 1   | 50 |  |
| redis   | 分布式缓存    | 按量            | 2   | 100 |  |
| 日志服务   | 日志搜集及搜索    | 按量            | 1   | 1000 |  |
| ECS-nginx(主、微、app)   | 反向代理    | 8核/8G/IO优化/3M            | 3   | 350 |  |
| RDS-mysql   | 关系数据库    | 8核/16G/ssd            | 1   | 2120 |  |
| ECS-jumpserver   | 跳板机    | 8核/8G/IO优化/3M            | 1   | 350 |  |
| SSL证书   | 通信加密证书    | 通配域名版本            | 1   | 约20000/年 |  |
---------------------

## 合计
350*2 + 350*4+350*2+350*2+370*3+300*1+40*1+50*1+100*2+1000*1+350*3+2120*1+350*1+20000/12=11386
减去可选合计：11386 – 350= 11036

## 重要说明
### 由于以下原因，独立部署的用户应该由我方协助注册账号及购买
* 1. 互联网云服务基础设施产品体系非常复杂，非专业用户极易选错
* 2. 除了基础配置本身，还涉及相应操作系统类型及版本的要求
* 3. 同一类型的基础设施下也有多个不同分支，比如LSB，我们通常会同时用到外部及内部LSB

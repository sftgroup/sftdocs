---
title: SFT

language_tabs:
  - ANY

search: true
---

# SFT

SFT-Solutions for tomorrow

SFT是主侧链机制的公链生态体系。主链主要提供数据存储以及调用功能，侧链则为较为复杂的合约运行提供支持。

SFT同样具备图灵完备以及以太虚拟机，为了方便合约开发者进行迁移，SFT同样支持Solidy语言进行合约编写以及跨链服务

SFT白皮书: [SFT白皮书](http://sftgroup.org/SFT_solutions_for_tomorrow.pdf "SFT白皮书")

SFT项目地址: [跳转](https://github.com/sftgroup/SFT "SFT项目地址")

11.21 SFT公链生态-加密社交工具树洞正式上线。

树洞生态中的SSC是SFT的侧链，其由加密社交圈＋知识社交＋社交电商三大体系组成，加密社交圈为用户提供圈子社区以及加密服务，作为平台流量数据的入口；社交电商-柠檬电商圈专业化社交电商团队化系统化运营，为用户提供品质商品服务，是生态流量的出口之一；知识社交生态为KOL意见领袖提供传递价值的平台，同时能够有效提升树洞整个加密社交体系的层次和内涵，提升用户的粘性。

树洞应用下载链接为: [点击跳转到树洞应用下载地址](https://h5.svcinsight.io/installation "树洞应用下载")

**扫码下载**

![树洞应用下载二维码](https://api.trochil.cn/sft/image/qrcode.png "二维码")

# _0基础一二三步接入区\_块\_链主网_

## 服务 Server

### 获取地址

>


```
```


> 请求返回示例

```javascript
{
  "code" : 200, # int
  "msg"  : "successed", # string
  "err"  : "null", # string
  "data" :
    {
      "address":"...ADDRESS...", #string
    },
}
```

#### http请求

`POST  路径参考: "\<WEBSITE/IP\>:\<PORT\>/api/get_NewAddress/"`

#### 请求参数

|名称       |描述     |类型     |必填 |样例         |取值范围|
|:----      |:--:     |:---:   |:--: |:--         |:-- |
|timestamp  |时间戳   |String  |Yes  |"1234554321" |---|
|user_id    |用户名   |String  |Yes  |"2020019428" |---|
|block      |主链名   |String  |Yes  |"Bitcoin"    |"Bitcoin"<br>"Ethereum"  |
|type       |类型     |String  |Yes  |"full"       |"full"|
|\_sign     |签名     |String  |Yes  |"mySign"     |---|

### 转账

>

```
```


> 请求返回示例

```javascript
{
  "code" : 200, # int
  "msg"  : "successed", # string
  "err"  : "null", # string
  "data" : "null", # string
}
```

#### http请求

`POST  路径参考: "\<WEBSITE/IP\>:\<PORT\>/api/transfer_Out/"`

#### 请求参数

|名称       |描述    |类型    |必填 |样例           |取值范围|
|:----      |:--:   |:---:   |:--: |:--           |:-- |
|timestamp  |时间戳  |String |Yes  |"1234554321"   |---|
|user_id    |用户名  |String |Yes  |"2020019428"   |---|
|block      |主链名  |String |Yes  |"Bitcoin"      |"Bitcoin"<br>"Ethereum"|
|coin_id    |货币名  |String |Yes  |"BTC"          |"BTC"<br>"ETHER"<br>"USDT"|
|order_id   |订单号  |String |Yes  |"..orderid.."  |---|
|type       |类型    |String |Yes  |"full"         |"full"|
|from       |发送者  |String |Yes  |"...from..."   |---|
|to         |接收者  |String |Yes  |"...to..."     |---|
|amount     |数额    |String |Yes  |"100.0"        |---|
|\_sign     |签名    |String |Yes  |"mySign"       |---|

## 回调 Callback

### 通知

>


```
```


> 请求返回示例

```javascript
 {
  "code" : 200, # int
  "msg"  : "successed", # string
  "err"  : "null", # string
  "data" : "null", # string
}
```

#### http请求

`POST  路径参考: "\<WEBSITE/IP\>:\<PORT\>/api/notification/"`

#### 请求参数

|名称       |描述   |类型   |必填  |样例         |取值范围|
|:----      |:--:  |:---:  |:--:  |:--         |:-- |
|timestamp  |时间戳 |String |Yes  |"1234554321" |---|
|status     |状态   |String |Yes  |"pending"    |"pending"<br>"confirmed"<br>"secured"<br>"cancelled"|
|block      |主链名 |String |Yes  |"Bitcoin"    |"Bitcoin"<br>"Ethereum"|
|coin_id    |货币名 |String |Yes  |"BTC"        |"BTC"<br>"ETHER"<br>"USDT"|
|app_id     |应用名 |String |Yes  |"Test_APP"   |(_用户自定义_)|
|order_id   |订单号 |String |Yes  |"..orderid.."|---|
|hash       |哈希值 |String |Yes  |"...hash..." |---|
|type       |类型   |String |Yes  |"Tx_In"      |"Tx_In"<br>"Tx_Out"|
|from       |发送者 |String |No   |"...from..." |---|
|to         |接收者 |String |Yes  |"...to..."   |---|
|amount     |数额   |String |Yes  |"100.0"      |---|
|\_sign     |签名   |String |Yes  |"mySign"     |---|

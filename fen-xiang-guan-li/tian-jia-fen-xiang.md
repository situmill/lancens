## 关于添加分享设备

* [创建一个分享设备给好友](#1增加设备分享)
* [重新分享设备给好友](#2app端重新分享设备给好友组名)

### 1.增加设备分享

* API接口:[https://weixin.lancens.com:6443/v1/api/device/app/share](https://weixin.lancens.com:6443/v1/api/device/app/share)
* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/device/app/share" -H  "accept: application/json" -H  "content-type: application/json" -H "token":"token" -d "{  \"duid\": \"string\",  \"suids\": [    null  ],  \"group_name\": \"string\",  \"starttime\": \"string\",  \"endtime\": \"string\",  \"per\": [    null  ],  \"status\": 0}"`
* 接口相关说明:单个设备uid 不能超过十个分享.选择需要分享的好友id\([查看用户已添加的好友获取好友ID](/../hao-you-guan-li/cha-kan-hao-you.html)\)  
  ,拼接数组格式进行分享,比如选择好友添加好友id为1,2,3  需按参数值数组格式, suids:\[1,2,3\] ,per权限也同理传\(注意字符串需要加双引号引起来,否则会报格式错误问题\)\["See\_video","Replay\_theater","Video\_intercom","Alarm\_push"\].

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(No device:没有设备\),\(Sharing upper limit:分享上限10个\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* | undefined XXX |
  | :--- |


  |  | 参数没有传XXX |
  | :--- | :--- |
  | XXX length error | XXX长度有误 |
  | XXX error | 验证XXX失败 |
  | XXX format error | XXX类型错误 |
  | 100XX,200XX,300XX | 数据库相关错误问题 |
  | XXX exist | XXX存在 |
  | no data error | 数据错误 |
  | paramer error | 代码中捕获到错误 |
* 数据格式:表1\(\*必传参数\)

### 表1

| duid:\* | string  \* 设备uid |
| :--- | :--- |
| suids:\* | \[\] description: \* 好友id\[52,50,51\] |
| group\_name:\* | string  \* 组名 |
| starttime:\* | string  \* 分享开始时间\(分钟0-1440\)默认0 |
| endtime:\* | string  \* 分享结束时间\(分钟0-1440\)默认1440 |
| per:\* | \[\] description: \* 权限功能\["See\_video","Replay\_theater","Video\_intercom","Alarm\_push"\] |
| status: | number 是否接收主设备分享的推送\(0或1,默认值为1 接收分享推送\) |

---

---

### 2.APP端重新分享设备给好友\(组名\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/group/XXX](https://weixin.lancens.com:6443/v1/api/device/share/group/XXX)
* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/device/share/group/XXX" -H  "accept: application/json" -H  "content-type: application/json" -H "token":"token" -d "{  \"group_name\": \"string\",  \"duid\": \"string\",  \"suids\": [    null  ],  \"starttime\": \"string\",  \"endtime\": \"string\",  \"per\": [    null  ],  \"status\": 0}"`
* 接口相关说明:根据XXX组名 ,重新分享组,分享不超过10个人,需要重新选择分享的好友id\([显示可以分享的好友获取好友ID](/../hao-you-guan-li/cha-kan-hao-you.html)\),拼接数组格式进行分享,比如选择好友添加好友id为1,2,3  需按参数值数组格式, suids:\[1,2,3,\] ,per权限也同理传\(注意字符串需要加双引号引起来,否则会报格式错误问题\)
  \* 
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* | undefined XXX |
  | :--- |


  |  | 参数没有传XXX |
  | :--- | :--- |
  | XXX length error | XXX长度有误 |
  | XXX error | 验证XXX失败 |
  | XXX format error | XXX类型错误 |
  | 100XX,200XX,300XX | 数据库相关错误问题 |
  | XXX exist | XXX存在 |
  | no data error | 数据错误 |
  | paramer error | 代码中捕获到错误 |
* 数据格式:表2\(必传参数\)

### 表2

| group\_name:\* | string \* 新组名 |
| :--- | :--- |
| duid:\* | string \* 设备uid |
| suids:\* | \[\] description: \* 好友id\[52,50,51\] |
| starttime:\* | string  \* 分享开始时间\(分钟\) |
| endtime:\* | string  \* 分享结束时间\(分钟\) |
| per:\* | \[\] description: \* 权限功能\["See\_video","Replay\_theater","Video\_intercom","Alarm\_push"\] |
| status: | number 是否接收主设备分享的推送\(0或1,默认值为1 接收分享推送\) |

---

---




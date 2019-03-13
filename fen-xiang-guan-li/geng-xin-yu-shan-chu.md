关于我的分享设备更新与删除

* [按序列号更新分享设备相关](#1app端为用户更新一个分享给好友的设备序列号)
* [更新分享设备的组名](#2app端更新一组组名组名)
* [按组名删除分享设备相关](#3app端删除用户分享给好友的设备组组名)
* 按序列号删除分享设备相关
* 按设备uid删除分享设备相关

### 1.APP端为用户更新一个分享给好友的设备\(序列号\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/app/share/XXX](https://weixin.lancens.com:6443/v1/api/device/app/share/XXX)
* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/device/app/share/XXX" -H  "accept: application/json" -H  "content-type: application/json" -H "token":"token" -d "{  \"group_name\": \"string\",  \"starttime\": \"string\",  \"endtime\": \"string\",  \"per\": [    null  ],  \"status\": 0}"`
* 接口相关说明:传序列号更新对应的分享设备信息\(权限,组名等\),,per权限需按格式\["See\_video","Replay\_theater","Video\_intercom","Alarm\_push"\] \(注意字符串需要加双引号,否则会报格式错误问题\)
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表1\(必传参数\)

### 表1

| group\_name:\* | string  \* 组名 |
| :--- | :--- |
| starttime:\* | string \* 分享开始时间\(分钟\) |
| endtime:\* | string \* 分享结束时间\(分钟\) |
| per:\* | \[...\] \* 权限功能\("See\_video","Replay\_theater","Video\_interco","Alarm\_push"\) |
| status: | number 是否接收主设备分享的推送\(0或1,默认值为1 接收分享推送\) |

---

---

### 2.APP端更新一组组名\(组名\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/app/XXX](https://weixin.lancens.com:6443/v1/api/device/share/app/XXX)
* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/device/share/app/XXX" -H  "accept: application/json" -H  "content-type: application/json" -H "token":"token" -d "{  \"group_name\": \"string\"}"`
* 接口相关说明:根据XXX旧组名 更新新组名,组名唯一不能重复
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

---

---

### 3.APP端删除用户分享给好友的设备组\(组名\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/delete/group/share/XXX](https://weixin.lancens.com:6443/v1/api/device/delete/group/share/XXX)
* 接口请求:`curl -X DELETE "https://weixin.lancens.com:6443/v1/api/device/delete/group/share/XXX" -H  "accept: application/json" -H "token":"token"`
* 接口相关说明:根据XXX组名删除用户分享给好友的设备组.删除后好友被分享的设备也删除,不会显示该分享设备
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

---

---

### 4.APP端删除用户分享给好友的设备组\(序列号\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/delete/app/share/XXX](https://weixin.lancens.com:6443/v1/api/device/delete/app/share/XXX)
* 接口请求:`curl -X DELETE "https://weixin.lancens.com:6443/v1/api/device/delete/app/share/XXX" -H  "accept: application/json" -H "token":"token"`
* 接口相关说明:根据XXX序列号删除用户分享给好友的设备组,删除后好友被分享的设备也删除,不会显示该分享设备
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

---

---

### 5.APP端删除用户分享给好友的设备组\(uid\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/delete/app/XXX/share](https://weixin.lancens.com:6443/v1/api/device/delete/app/XXX/share)
* 接口请求:`curl -X DELETE "https://weixin.lancens.com:6443/v1/api/device/delete/app/XXX/share" -H  "accept: application/json" -H "token":"token"`
* 接口相关说明:根据XXX设备uid删除用户分享给好友的设备组.删除后好友被分享的设备也删除,不会显示该分享设备
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)




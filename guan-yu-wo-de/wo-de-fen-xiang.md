## 关于我的分享设备

#### 分享设备需要满足:用户存在主设备和存在好友才可以分享.\(没有主设备需要[添加设备](http://developers.lancens.com:4000/she-bei-xiang-guan/wo-de-she-bei.html)才能分享\)

### 1.增加设备分享

* API接口:[https://weixin.lancens.com:6443/v1/api/device/app/share](https://weixin.lancens.com:6443/v1/api/device/app/share)
* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/device/app/share" -H  "accept: application/json" -H  "content-type: application/json" -H "token":"token" -d "{  \"duid\": \"string\",  \"suids\": [    null  ],  \"group_name\": \"string\",  \"starttime\": \"string\",  \"endtime\": \"string\",  \"per\": [    null  ],  \"status\": 0}"`
* 接口相关说明:单个设备uid 不能超过十个分享.选择需要分享的好友id\([我的好友8获取全部好友ID](/../guan-yu-wo-de/wo-de-hao-you.html)\),  
  ,拼接数组格式进行分享,比如选择好友添加好友id为1,2,3  需按参数值数组格式, suids:\[1,2,3\] ,per权限也同理传\(注意字符串需要加双引号引起来,否则会报格式错误问题\)\["See\_video","Replay\_theater","Video\_intercom","Alarm\_push"\].

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(No device:没有设备\),\(Sharing upper limit:分享上限10个\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

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

### 2.APP端根据设备uid查询分享设备相关信息\(uid\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/device?uid=XXX](https://weixin.lancens.com:6443/v1/api/device/share/device?uid=XXX)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/device/share/device?uid=XXX" -H  "accept: application/json" -H "token":"token"`
* 接口相关说明:suid 好友id, friendname好友名, realm 备注名 ,group\_name组名,starttime endtime 时间段, per权限 ,status 是否接收推送或历史记录  device 设备类型 ,XXX传uid
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表2\(返回数据\)

---

---

### 3.APP端根据设备uid查询分享设备相关信息\(组名\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/group?group=XXX](https://weixin.lancens.com:6443/v1/api/device/share/group?group=XXX)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/device/share/group?group=XXX" -H  "accept: application/json" -H "token":"token"`
* 接口相关说明:suid 好友id, friendname好友名, realm 备注名 ,group\_name组名,starttime endtime 时间段, per权限 ,status 是否接收分享设备的推送  device 设备类型 ,,XXX传组名group
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 返回数据:表2\(返回数据\)

### 表2

| suid: | string 好友id |
| :--- | :--- |
| friendname: | string 好友用户名 |
| realm: | string 好友昵称 |
| duid: | string 设备uid |
| starttime: | string 开始时间 |
| endtime: | string 结束时间 |
| per: | string 权限功能\("See\_video","Replay\_theater","Video\_intercom","Alarm\_push"\) |
| status: | number 是否接收主设备分享的推送\(0或1,默认值为1 接收分享推送\) |

---

---

### 4.APP端获取所有组名

* API接口:[https://weixin.lancens.com:6443/v1/api/device/app/group/share](https://weixin.lancens.com:6443/v1/api/device/app/group/share)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/device/app/group/share" -H  "accept: application/json"`
* 接口相关说明:获取用户分享的全部组名\(按组名显示分享组\)
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

---

---

### 5.APP端为用户更新一个分享给好友的设备\(序列号\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/app/share/XXX](https://weixin.lancens.com:6443/v1/api/device/app/share/XXX)
* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/device/app/share/XXX" -H  "accept: application/json" -H  "content-type: application/json" -H "token":"token" -d "{  \"group_name\": \"string\",  \"starttime\": \"string\",  \"endtime\": \"string\",  \"per\": [    null  ],  \"status\": 0}"`
* 接口相关说明:传序列号更新对应的分享设备信息\(权限,组名等\),,per权限需按格式\["See\_video","Replay\_theater","Video\_intercom","Alarm\_push"\] \(注意字符串需要加双引号,否则会报格式错误问题\)
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表3\(必传参数\)

### 表3

| group\_name:\* | string  \* 组名 |
| :--- | :--- |
| starttime:\* | string \* 分享开始时间\(分钟\) |
| endtime:\* | string \* 分享结束时间\(分钟\) |
| per:\* | \[...\] \* 权限功能\("See\_video","Replay\_theater","Video\_interco","Alarm\_push"\) |
| status: | number 是否接收主设备分享的推送\(0或1,默认值为1 接收分享推送\) |

---

---

### 6.APP端更新一组组名\(组名\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/app/XXX](https://weixin.lancens.com:6443/v1/api/device/share/app/XXX)
* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/device/share/app/XXX" -H  "accept: application/json" -H  "content-type: application/json" -H "token":"token" -d "{  \"group_name\": \"string\"}"`
* 接口相关说明:根据XXX旧组名 更新新组名,组名唯一不能重复
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

---

---

### 7.APP端重新分享设备给好友\(组名\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/group/XXX](https://weixin.lancens.com:6443/v1/api/device/share/group/XXX)
* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/device/share/group/XXX" -H  "accept: application/json" -H  "content-type: application/json" -H "token":"token" -d "{  \"group_name\": \"string\",  \"duid\": \"string\",  \"suids\": [    null  ],  \"starttime\": \"string\",  \"endtime\": \"string\",  \"per\": [    null  ],  \"status\": 0}"`
* 接口相关说明:根据XXX组名 ,重新分享组,分享不超过10个人,需要重新选择分享的好友id\([我的好友11获取除屏蔽的好友ID](/../guan-yu-wo-de/wo-de-hao-you.html)\),拼接数组格式进行分享,比如选择好友添加好友id为1,2,3  需按参数值数组格式, suids:\[1,2,3,\] ,per权限也同理传\(注意字符串需要加双引号引起来,否则会报格式错误问题\)
  \* 
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表4\(必传参数\)

### 表4

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

### 8.APP端删除用户分享给好友的设备组\(组名\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/delete/group/share/XXX](https://weixin.lancens.com:6443/v1/api/device/delete/group/share/XXX)
* 接口请求:`curl -X DELETE "https://weixin.lancens.com:6443/v1/api/device/delete/group/share/XXX" -H  "accept: application/json" -H "token":"token"`
* 接口相关说明:根据XXX组名删除用户分享给好友的设备组.删除后好友被分享的设备也删除,不会显示该分享设备
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

---

---

### 9.APP端删除用户分享给好友的设备组\(序列号\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/delete/app/share/XXX](https://weixin.lancens.com:6443/v1/api/device/delete/app/share/XXX)
* 接口请求:`curl -X DELETE "https://weixin.lancens.com:6443/v1/api/device/delete/app/share/XXX" -H  "accept: application/json" -H "token":"token"`
* 接口相关说明:根据XXX序列号删除用户分享给好友的设备组,删除后好友被分享的设备也删除,不会显示该分享设备
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

---

---

### 10.APP端删除用户分享给好友的设备组\(uid\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/delete/app/XXX/share](https://weixin.lancens.com:6443/v1/api/device/delete/app/XXX/share)
* 接口请求:`curl -X DELETE "https://weixin.lancens.com:6443/v1/api/device/delete/app/XXX/share" -H  "accept: application/json" -H "token":"token"`
* 接口相关说明:根据XXX设备uid删除用户分享给好友的设备组.删除后好友被分享的设备也删除,不会显示该分享设备
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)




## 我的好友相关

### 添加好友流程:先查询好友,再请求添加好友,对方通过申请才可以添加成功.

### 1.查找是否存在好友\(查询好友\)

* API接口:[https://weixin.lancens.com:6443/v1/api/selecte/share/friend?name=XXX](https://weixin.lancens.com:6443/v1/api/selecte/share/friend?name=XXX)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/selecte/share/friend?name=XXX" -H  "accept: application/json" -H "token":"token"`
* 参数说明:通过XXX手机号，邮箱，用户名查询用户是否存在.
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](http://developer.lancens.com:4000/deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(use myself:不能添加自己\)\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表1\(返回数据\)

### 表1

| suid: | number 好友id |
| :--- | :--- |
| friendname: | string 好友用户名 |
| phone: | string 手机号码 |
| mail: | string 邮箱 |
| realm: | string 昵称 |

---

---

### 2.申请添加好友，先添加到好友申请表中

* API接口:[https://weixin.lancens.com:6443/v1/api/add/share/friend](https://weixin.lancens.com:6443/v1/api/add/share/friend)
* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/add/share/friend" -H  "accept: application/json" -H  "content-type: application/json" -H "token":"token" -d "{ \"suid\": \"string\",  \"status\": 0}"`
* 参数说明:suid为好友id,status默认1
* 接口说明:申请添加好友后,好友将收到添加好友的推送,type=200为好友消息推送
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](http://developer.lancens.com:4000/deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(cannot add :不能添加自己\),\(suid error:好友不存在\),\(friend exist :已经是好友不能重复加\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表2\(必传参数\)

### 表2

| suid:\* | int好友id |
| :--- | :--- |
| status: | number 状态 |

---

---

### 3.查看用户主动申请添加好友,没有同意的好友列表\(主动\)

* API接口:[https://weixin.lancens.com:6443/v1/api/add/share/friend](https://weixin.lancens.com:6443/v1/api/add/share/friend)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/add/share/friend" -H  "accept: application/json" -H "token":"token"`

* 接口说明:显示用户申请添加好友，好友没有同意的列表\(显示未同意的好友列表\)

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](http://developer.lancens.com:4000/deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表3\(返回数据\)

---

---

### 4.查看用户被好友申请添加的好友的列表\(被动\)

* API接口:[https://weixin.lancens.com:6443/v1/api/add/friend/share](https://weixin.lancens.com:6443/v1/api/add/friend/share)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/add/friend/share" -H  "accept: application/json" -H "token":"token"`

* 接口说明:查看好友申请后  用户没有同意加好友的列表\(接收到好友的申请列表\)

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](http://developer.lancens.com:4000/deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表3\(返回数据\)

### 表3

| uid: | string 用户id |
| :--- | :--- |
| suid: | string 好友id |
| friendname: | string 好友用户名 |
| username: | string 自己用户名 |
| status: | number 状态 |

### 5.删除用户账号中一个主动临时添加好友申请\(主动\)

* API接口:[https://weixin.lancens.com:6443/v1/api/add/share/friend/XXX](https://weixin.lancens.com:6443/v1/api/add/share/friend/XXX)
* 接口请求:`curl -X DELETE "https://weixin.lancens.com:6443/v1/api/add/share/friend/XXX" -H  "accept: application/json" -H "token":"token"`

* 接口说明:XXX为序列号,用户取消添加好友的申请

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](http://developer.lancens.com:4000/deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

---

---

### 6.删除用户账号中一个被动临时添加好友申请\(被动\)

* API接口:[https://weixin.lancens.com:6443/v1/api/add/friend/XXX/friend](https://weixin.lancens.com:6443/v1/api/add/friend/XXX/friend)
* 接口请求:`curl -X DELETE "https://weixin.lancens.com:6443/v1/api/add/friend/XXX/friend" -H  "accept: application/json" -H "token":"token"`

* 接口说明:XXX为序列号,取消好友的好友申请,用户拒接添加此好友

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](http://developer.lancens.com:4000/deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

---

---

### 7.添加好友到好友表中\(需申请才能添加成功\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/friend](https://weixin.lancens.com:6443/v1/api/device/share/friend)
* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/device/share/friend" -H  "accept: application/json" -H  "content-type: application/json" -H "token":"token" -d "{  \"uid\": \"string\",  \"suid\": \"string\",  \"status\": 0}"`
* 参数说明:此处的uuid为用户ID**非设备uid**.suid为好友id,status默认0
* 接口说明:申请添加好友到临时好友表中后,才可以调用此接口添加好友到好友列表
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](http://developer.lancens.com:4000/deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表2

---

---

### 8.查看用户已添加的好友列表

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/friend](https://weixin.lancens.com:6443/v1/api/device/share/friend)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/device/share/friend" -H  "accept: application/json" -H "token":"token"`

* 接口说明:返回的好友列表按顺序排序

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](http://developer.lancens.com:4000/deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表4\(返回数据\)

### 表4

| id: | int id |
| :--- | :--- |
| uid: | string 用户id |
| suid: | string 好友id |
| friendname: | string 好友用户名 |
| realm: | string 好友昵称 |
| status: | number 状态 |

---

---

### 9.更新帐号中一个好友昵称信息\(传序列ID,非好友ID\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/friend/XXX](https://weixin.lancens.com:6443/v1/api/device/share/friend/XXX)
* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/device/share/friend/XXX" -H  "accept: application/json" -H  "content-type: application/json" -H "token":"token" -d "{  \"realm\": \"string\"}"`

* 接口说明:XXX为序列号,realm为好友的备注名\(1-32\)

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](http://developer.lancens.com:4000/deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

---

---

### 10.删除用户帐号中一个好友\(序列号\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/friend/XXX](https://weixin.lancens.com:6443/v1/api/device/share/friend/XXX)
* 接口请求:`curl -X DELETE "https://weixin.lancens.com:6443/v1/api/device/share/friend/XXX" -H  "accept: application/json" -H "token":"token"`

* 接口说明:XXX为序列号,删除好友成功后,彼此的好友信息都删除,彼此间分享的设备也都会删除.

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](http://developer.lancens.com:4000/deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

---

---

---

### 11.通过设备UID屏蔽分享过的好友\(显示可以分享的好友列表\)

* API接口:[https://weixin.lancens.com:6443/v1/api/shield/share/friend?uid=XXX](https://weixin.lancens.com:6443/v1/api/shield/share/friend?uid=XXX)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/shield/share/friend?uid=XXX" -H  "accept: application/json" -H "token":"token"`

* 接口说明:通过设备uid来屏蔽好友，按顺序显示可以分享的好友列表

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](http://developer.lancens.com:4000/deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表4




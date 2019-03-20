## 更新与删除好友相关

* [更新好友昵称](#1更新帐号中一个好友昵称信息传序列id非好友id)
* [删除申请添加好友\(取消添加好友\)](#2删除用户账号中一个主动临时添加好友申请主动取消添加好友)
* [删除来自好友的添加申请\(拒绝添加好友\)](#3删除用户账号中一个被动临时添加好友申请拒绝被添加好友)
* [删除正常好友](#4删除用户帐号中一个好友序列号)

### 1.更新帐号中一个好友昵称信息\(传序列ID,非好友ID\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/friend/XXX](https://weixin.lancens.com:6443/v1/api/device/share/friend/XXX)
* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/device/share/friend/XXX" -H  "accept: application/json" -H  "content-type: application/json" -H "token":"token" -d "{  \"realm\": \"string\"}"`

* 接口说明:XXX为序列号,realm为好友的备注名\(1-32\)

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

|  undefined XXX | 参数没有传XXX |
| :--- | :--- |
| no token | header请求头没有传token |
| XXX length error | XXX长度有误 |
| XXX error | 验证XXX失败 |
| XXX format error | XXX类型错误 |
| 100XX,200XX,300XX | 数据库相关错误问题 |
| invalid token | 无效的token令牌 |
| XXX exist | XXX存在 |
| username or password error | 账号密码不匹配 |
| no data error | 数据错误 |
| paramer error | 代码中捕获到错误 |

---

---

### 2.删除用户账号中一个主动临时添加好友申请\(主动取消添加好友\)

* API接口:[https://weixin.lancens.com:6443/v1/api/add/share/friend/XXX](https://weixin.lancens.com:6443/v1/api/add/share/friend/XXX)
* 接口请求:`curl -X DELETE "https://weixin.lancens.com:6443/v1/api/add/share/friend/XXX" -H  "accept: application/json" -H "token":"token"`

* 接口说明:XXX为序列号,用户主动_**取消添加好友**_.

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

|  undefined XXX | 参数没有传XXX |
| :--- | :--- |
| no token | header请求头没有传token |
| XXX length error | XXX长度有误 |
| XXX error | 验证XXX失败 |
| XXX format error | XXX类型错误 |
| 100XX,200XX,300XX | 数据库相关错误问题 |
| invalid token | 无效的token令牌 |
| XXX exist | XXX存在 |
| username or password error | 账号密码不匹配 |
| no data error | 数据错误 |
| paramer error | 代码中捕获到错误 |

---

---

### 3.删除用户账号中一个被动临时添加好友申请\(拒绝被添加好友\)

* API接口:[https://weixin.lancens.com:6443/v1/api/add/friend/XXX/friend](https://weixin.lancens.com:6443/v1/api/add/friend/XXX/friend)
* 接口请求:`curl -X DELETE "https://weixin.lancens.com:6443/v1/api/add/friend/XXX/friend" -H  "accept: application/json" -H "token":"token"`

* 接口说明:XXX为序列号,用户_**拒绝被添加好友**_

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

|  undefined XXX | 参数没有传XXX |
| :--- | :--- |
| no token | header请求头没有传token |
| XXX length error | XXX长度有误 |
| XXX error | 验证XXX失败 |
| XXX format error | XXX类型错误 |
| 100XX,200XX,300XX | 数据库相关错误问题 |
| invalid token | 无效的token令牌 |
| XXX exist | XXX存在 |
| username or password error | 账号密码不匹配 |
| no data error | 数据错误 |
| paramer error | 代码中捕获到错误 |

---

---

### 4.删除用户帐号中一个好友\(序列号\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/friend/XXX](https://weixin.lancens.com:6443/v1/api/device/share/friend/XXX)
* 接口请求:`curl -X DELETE "https://weixin.lancens.com:6443/v1/api/device/share/friend/XXX" -H  "accept: application/json" -H "token":"token"`

* 接口说明:XXX为序列号,删除好友成功后,彼此的好友信息都删除,彼此间分享的设备也都会删除.

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

|  undefined XXX | 参数没有传XXX |
| :--- | :--- |
| no token | header请求头没有传token |
| XXX length error | XXX长度有误 |
| XXX error | 验证XXX失败 |
| XXX format error | XXX类型错误 |
| 100XX,200XX,300XX | 数据库相关错误问题 |
| invalid token | 无效的token令牌 |
| XXX exist | XXX存在 |
| username or password error | 账号密码不匹配 |
| no data error | 数据错误 |
| paramer error | 代码中捕获到错误 |

---

---




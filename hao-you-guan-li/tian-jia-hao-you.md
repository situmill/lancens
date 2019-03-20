## 添加好友相关

### 添加好友简单流程:先查询到好友,再申请添加该好友,申请后等待好友对方同意,同意则添加成功,不同意则添加失败,需要再次查询再次申请.

### 1.查找是否存在好友\(查询好友\)

* API接口:[https://weixin.lancens.com:6443/v1/api/selecte/share/friend?name=XXX](https://weixin.lancens.com:6443/v1/api/selecte/share/friend?name=XXX)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/selecte/share/friend?name=XXX" -H  "accept: application/json" -H "token":"token"`
* 参数说明:通过XXX手机号，邮箱，用户名查询用户是否存在.
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(use myself:不能添加自己\)\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

| undefined XXX |
| :--- |


|  | 参数没有传XXX |
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
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(cannot add :不能添加自己\),\(suid error:好友不存在\),\(friend exist :已经是好友不能重复加\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

| undefined XXX |
| :--- |


|  | 参数没有传XXX |
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

* 数据格式:表2\(必传参数\)

### 表2

| suid:\* | int好友id |
| :--- | :--- |
| status: | number 状态 |

---

### 3.添加好友到好友表中\(需申请才能添加成功\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/friend](https://weixin.lancens.com:6443/v1/api/device/share/friend)
* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/device/share/friend" -H  "accept: application/json" -H  "content-type: application/json" -H "token":"token" -d "{  \"uid\": \"string\",  \"suid\": \"string\",  \"status\": 0}"`
* 参数说明:此处的uuid为用户ID**非设备uid**.suid为好友id,status默认0
* 接口说明:申请添加好友到临时好友表中后,APP端好友列表有_**好友申请**_才可以调用此接口添加好友到好友列表
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

| undefined XXX |
| :--- |


|  | 参数没有传XXX |
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

* 数据格式:表2

### 




## 关于更新用户资料的操作接口：

* [更新用户昵称](#1更新账号相关昵称信息)
* [更新用户名](#2修改用户名修改登录用户名)
* [更新用户邮箱](#3修改用户新邮箱)

### 1.更新账号相关昵称信息

* API接口:[https://weixin.lancens.com:6443/v1/api/user](https://weixin.lancens.com:6443/v1/api/user)

* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/user" -H  "accept: application/json" -H  "content-type: application/json" -H "token":"token" -d "{  \"realm\": \"string\"}"`

* 参数说明:realm\(1-32\),修改用户昵称.

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

| undefined XXX | 参数没有传XXX |
| :--- | :--- |
| no token | header请求头没有传token |
| XXX length error | XXX长度有误 |
| XXX error | 验证XXX失败 |
| XXX format error | XXX类型错误 |
| 100XX,200XX,300XX | 数据库相关错误问题 |
| invalid token | 无效的token令牌 |
| XXX exist | XXX存在 |
| no data error | 数据错误 |
| paramer error | 代码中捕获到错误 |

---

---

### 2.修改用户名\(修改登录用户名\)

* API接口:[https://weixin.lancens.com:6443/v1/api/user/username](https://weixin.lancens.com:6443/v1/api/user/username)

* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/user/username" -H  "accept: application/json" -H  "content-type: application/json" -H "token":"token" -d "{  \"username\": \"string\"}"`

* 参数说明:username\(6-32\)不能纯数字,修改用户名

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

| undefined XXX | 参数没有传XXX |
| :--- | :--- |
| no token | header请求头没有传token |
| XXX length error | XXX长度有误 |
| XXX error | 验证XXX失败 |
| XXX format error | XXX类型错误 |
| 100XX,200XX,300XX | 数据库相关错误问题 |
| invalid token | 无效的token令牌 |
| XXX exist | XXX存在 |
| no data error | 数据错误 |
| paramer error | 代码中捕获到错误 |

---

---

### 3.修改用户新邮箱

#### 修改新邮箱需要3步,第一步;更新用户表中的code,第二步发送code到新邮箱\(服务器处理\),邮箱获取code更新绑定新邮箱解绑旧邮箱

#### a.发送验证码到新邮箱,用于绑定新的邮箱\(修改为新邮箱\)

* API接口:[https://weixin.lancens.com:6443/v1/api/user/emailcode/email](https://weixin.lancens.com:6443/v1/api/user/emailcode/email)

* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/user/emailcode/email" -H  "accept: application/json" -H  "content-type: application/json" -H "token":"token" -d "{  \"email\": \"string\"}"`

* 参数说明:appname:APP名称用于显示邮件出处\(默认空\),language:邮件的语言\(默认en\),

* 接口说明:请求此接口后会给用户邮箱发送一封邮件,获取到正确的验证码才可以修改邮箱

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

#### b.获取发送到新邮箱的验证码来修改新的邮箱地址\(通过新邮箱的验证码,修改为新邮箱\)

* API接口:[https://weixin.lancens.com:6443/v1/api/user/emails](https://weixin.lancens.com:6443/v1/api/user/emails)

* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/user/emails" -H  "accept: application/json" -H  "content-type: application/json" -H "token":"token" -d "{  \"code\": \"string\",  \"email\": \"string\"}"`

* 参数说明:code为正确的邮箱验证码,email为该code对应的新邮箱地址.

* 接口说明:调用此接口会解绑原来的邮箱,绑定新邮箱.

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

| undefined XXX | 参数没有传XXX |
| :--- | :--- |
| no token | header请求头没有传token |
| XXX length error | XXX长度有误 |
| XXX error | 验证XXX失败 |
| XXX format error | XXX类型错误 |
| 100XX,200XX,300XX | 数据库相关错误问题 |
| invalid token | 无效的token令牌 |
| XXX exist | XXX存在 |
| no data error | 数据错误 |
| paramer error | 代码中捕获到错误 |

* 数据格式:表1\(\*必传参数\)

### 表1

| code:\* | string\* 邮箱收到的验证码 |
| :--- | :--- |
| email:\* | string\* 新电子邮箱 |

### 




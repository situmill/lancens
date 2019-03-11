## 修改密码相关接口

### 1.通过旧密码修改密码

* API接口:[https://weixin.lancens.com:6443/v1/api/user/password](https://weixin.lancens.com:6443/v1/api/user/password)

* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/user/password" -H  "accept: application/json" -H  "content-type: application/json" -H "token":"token"  -d "{  \"password\": \"string\",  \"oldpassword\": \"string\"}"`

* 接口相关说明:密码长度\(8-16\).

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(oldpassword error:旧密码错误\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表1\(\*必传参数\)

### 表1

| password:\* | string\* 用户密码 |
| :--- | :--- |
| oldpassword:\* | string 用户旧密码 |

---

---

### 2.手机号修改密码

#### 手机号修好密码,首先调用重置手机密码接口发送验证码,获取验证码后再调用手机修改密码接口.

##### 1.发送手机重置用户密码验证码

* API接口:[https://weixin.lancens.com:6443/v1/api/phone/retrieve](https://weixin.lancens.com:6443/v1/api/phone/retrieve)

* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/phone/retrieve" -H  "accept: application/json" -H  "content-type: application/json"  -d "{  \"phone\": \"string\"}"`

* 接口相关说明:手机验证码有效期5分钟,手机号目前支持国内.手机号必须存在才可以发送验证码.

##### 2.通过手机验证码重置用户密码

* API接口:[https://weixin.lancens.com:6443/v1/api/phone/retrieve](https://weixin.lancens.com:6443/v1/api/phone/retrieve)

* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/phone/retrieve" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"password\": \"string\",  \"phone\": \"string\",  \"code\": \"string\"}"`

* 接口相关说明:密码\(8-16\),code为手机号收到的6位数验证码.手机号必须对应code才可以修改成功.

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表2\(必传参数\)

### 表2

| password:\* | string\* 重置的新密码 |
| :--- | :--- |
| phone:\* | string\* 重置密码的手机号 |
| code:\* | string\* 重置密码手机对应的code验证码 |

---

---

### 3.邮箱修改密码

##### 1.发送邮箱重置用户密码验证码

* API接口:[https://weixin.lancens.com:6443/v1/api/user/passwordcode/email](https://weixin.lancens.com:6443/v1/api/user/passwordcode/email)

* 请求上面接口后,服务端会调用API接口:[https://weixin.lancens.com:6443/v1/api/mail2](https://weixin.lancens.com:6443/v1/api/user/passwordcode/email) \(服务端自动调用\).

* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/user/passwordcode/email" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"email\": \"string\"}"`

* 接口相关说明:正确邮箱格式,appname\(app名称默认空\),language邮件的语言格式默认英文.

##### 2.通过邮箱验证码，重置用户密码

* API接口:[https://weixin.lancens.com:6443/v1/api/user/email/reset/password](https://weixin.lancens.com:6443/v1/api/user/email/reset/password)

* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/user/email/reset/password" -H  "accept: application/json" -H  "content-type: application/json"  -d "{  \"password\": \"string\",  \"code\": \"string\",  \"email\": \"string\"}"`

* 接口相关说明:密码\(8-16\),code为手机号收到的6位数验证码.

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表3\(必传参数\)

### 表3

| password:\* | string\* 用户密码 |
| :--- | :--- |
| code:\* | string\* 验证码 |
| email:\* | string\* 电子邮件信息 |




## 邮箱注册相关接口

### 邮箱注册账号需要先调用发送邮箱验证码接口,获取到6位数验证码后,才能调用注册.

### 1.发送邮箱注册验证码

* API接口:[https://weixin.lancens.com:6443/v1/api/email/register](https://weixin.lancens.com:6443/v1/api/email/register)

* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/email/register?email=XXX" -H  "accept: application/json"`

* 接口相关说明：正确邮箱格式，appname\(app名称默认空\)，language邮件的语言格式默认英文。发送邮件6位数验证码

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(XXX length error: XXX长度有误\),\(XXX format error: XXX类型错误\),\(send error: 发送邮件错误\),\(10001,10021,10031, :数据库相关错误问题\),\(XXX exist: XXX存在\),\(being used :邮箱已被注册\),\(paramer error : 代码中捕获到错误\)

---

---

### 2.邮箱注册

* API接口:[https://weixin.lancens.com:6443/v1/api/email/register](https://weixin.lancens.com:6443/v1/api/email/register)

* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/email/register" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"password\": \"string\",  \"email\": \"string\",  \"apikey\": \"string\",  \"code\": \"string\"}"`

* 接口相关说明:账号名默认 em\_XXXX\(20位\),密码\(8-16\),apikey为lancens提供默认为lancens相关,code为邮箱收到的6位数验证码.

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(not applying: 验证码不匹配邮箱\),\(10001,10021,10031, 10041:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表1\(\*必须参数\)

### 表1

| password:**\*** | string\* 登录所使用账号对应正确的密码,由大小写字母及特殊字符"\_!@\#$%^&\*\(\)+-="组成,最大长度16个字节,最小长度8个字节 |
| :--- | :--- |
| email:**\*** | string\* 邮件地址,最大长度40个字节 |
| apikey:**\*** | string\* 由服务商提供,由小写字母组成,长度为32个字节 |
| code:**\*** | string\* 从注册邮件获取到的验码,由6位组成 |




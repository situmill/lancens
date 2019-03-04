## 邮箱注册相关接口：

邮箱注册账号需要先调用发送邮箱验证码接口，获取到6位数验证码后，才能调用注册。

### 1.发送邮箱注册验证码

* API接口：[https://weixin.lancens.com:6443/v1/api/email/register](https://weixin.lancens.com:6443/v1/api/email/register)

* 接口请求：`curl -X GET "https://weixin.lancens.com:6443/v1/api/email/register?email=XXX" -H  "accept: application/json"`

* 接口相关说明：正确邮箱格式，appname\(app名称默认空\)，language邮件的语言格式默认英文。

### 2.邮箱注册：

* API接口：https://weixin.lancens.com:6443/v1/api/email/register

* 接口请求：`curl -X POST "https://weixin.lancens.com:6443/v1/api/phone/register" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"password\": \"string\",  \"phone\": \"string\",  \"apikey\": \"string\",  \"code\": \"string\"}"`

* 接口相关说明，账号名默认 mp\_XXXX\(20位\)，密码\(8-16\)，apikey由lancens提供参数。code为手机号收到的6位数验证码




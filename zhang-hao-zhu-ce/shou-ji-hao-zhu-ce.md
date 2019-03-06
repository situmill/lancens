## 手机号注册相关接口

### 手机号注册账号需要先调用发送手机验证码接口,获取到6位数验证码后,才能调用注册.

### 1.发送手机注册验证码

* API接口:[https://weixin.lancens.com:6443/v1/api/phone/register](https://weixin.lancens.com:6443/v1/api/phone/register)

* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/phone/register" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"phone\": \"string\"}"`

* 接口相关说明：手机验证码有效期5分钟，手机号目前支持国内。

---

---

### 2.手机号注册

* API接口:[https://weixin.lancens.com:6443/v1/api/phone/register](https://weixin.lancens.com:6443/v1/api/phone/register)

* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/phone/register" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"password\": \"string\",  \"phone\": \"string\",  \"apikey\": \"string\",  \"code\": \"string\"}"`

* 接口相关说明,账号名默认 mp\_XXXX\(20位\),密码\(8-16\),apikey由lancens提供参数默认为lancens相关,code为手机号收到的6位数验证码.

* 数据格式:表1

表1

| description: | 手机号码注册新用户所使用信息 |
| :--- | :--- |
| password: | string\* 登录所使用账号对应正确的密码,由大小写字母及特殊字符"\_!@\#$%^&\*\(\)+-="组成,最大长度16个字节,最小长度8个字节 |
| phone: | string\* 手机号码最大长度20个字节,最小长度6个字节 |
| apikey: | string\* 由服务商提供,由小写字母组成,长度为32个字节 |
| code: | string\* 从手机获取到的验证码,由6位数字组成 |




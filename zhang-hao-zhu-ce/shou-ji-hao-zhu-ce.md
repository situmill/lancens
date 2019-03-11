## 手机号注册相关接口

### 手机号注册账号需要先调用发送手机验证码接口,获取到6位数验证码后,才能调用注册.

### 1.发送手机注册验证码

* API接口:[https://weixin.lancens.com:6443/v1/api/phone/register](https://weixin.lancens.com:6443/v1/api/phone/register)

* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/phone/register" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"phone\": \"string\"}"`

* 接口相关说明：必传手机号码,收到的手机验证码有效期5分钟，手机号目前支持国内。不能注册已存在得手机号

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(10001,10021 :数据库相关错误问题\),\(XXX exist: XXX存在\),\(no data error :数据错误\),\(paramer error : 代码中捕获到错误\)

---

---

### 2.手机号注册

* API接口:[https://weixin.lancens.com:6443/v1/api/phone/register](https://weixin.lancens.com:6443/v1/api/phone/register)

* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/phone/register" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"password\": \"string\",  \"phone\": \"string\",  \"apikey\": \"string\",  \"code\": \"string\"}"`

* 接口相关说明,密码\(8-16\),code为手机号收到的6位数验证码.手机号注册成功后账号名默认 mp\_XXXX\(20位\),apikey由lancens提供参数必须传入正确才可以完成注册.

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(10001,10021,10031, :数据库相关错误问题\),\(XXX exist: XXX存在\),\(no data error :数据错误\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表1\(\*为必传参数\)

### 表1

| password:**\*** | string\* 登录所使用账号对应正确的密码,由大小写字母及特殊字符"\_!@\#$%^&\*\(\)+-="组成,最大长度16个字节,最小长度8个字节 |
| :--- | :--- |
| phone:**\*** | string\* 手机号码最大长度20个字节,最小长度6个字节 |
| apikey:**\*** | string\* 由服务商提供,由小写字母组成,长度为32个字节 |
| code:**\*** | string\* 从手机获取到的验证码,由6位数字组成 |




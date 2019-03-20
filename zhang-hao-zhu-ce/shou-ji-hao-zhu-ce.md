## 手机号注册相关接口

* [区分国内短信还是国际短信,获取开通的国家区号列表\(默认国内\)](#1获取开通的国家区号列表)

* [调用发送手机验证码接口,获取到6位数验证码](#2发送手机注册验证码)

* [通过手机号与对应验证码完成注册.](#3手机号注册)

### 1.获取开通手机号短信的国家区号列表

* API接口:[https://weixin.lancens.com:6443/v1/api/area/code](https://weixin.lancens.com:6443/v1/api/area/code)

* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/area/code?language=en" -H  "accept: application/json"`

* 接口相关说明：需要传入language获取国家名显示的语言\(默认为en\),根据语言显示 国家名与国家区号\(**获取area\_code**\).

* 相关错误代码解析:\(10001,10008 :数据库相关错误问题\),\(no data error :数据错误\),\(paramer error : 代码中捕获到错误\)

* | undefined XXX | 参数没有传XXX |
  | :--- | :--- |
  | XXX length error | XXX长度有误 |
  | XXX error | 验证XXX失败 |
  | XXX format error | XXX类型错误 |
  | 10001,10081 | 数据库相关错误问题 |
  | XXX exist | XXX存在 |
  | no data error | 数据错误 |
  | paramer error | 代码中捕获到错误 |
* 数据格式:表1\(返回数据\)

#### 表1

| global\_id: | integer\($int64\) 序列id |
| :--- | :--- |
| area\_name: | string 国家名\(默认英文\) |
| area\_code: | int 国家对应区号\(不要带+号\) |

---

---

### 2.发送手机注册验证码

* API接口:[https://weixin.lancens.com:6443/v1/api/phone/register](https://weixin.lancens.com:6443/v1/api/phone/register)

* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/phone/register" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"phone\": \"string\" ,  \"area_code\": 0}"`

* 接口相关说明：必传手机号码,收到的手机验证码有效期5分钟，手机号目前支持国内短信。不能注册已注册使用的手机号.

* **area\_code**为[开通的国际短息国家区号](#1获取开通手机号短信的国家区号列表)\(默认为国内86\)

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(10001,10021 :数据库相关错误问题\),\(XXX exist: XXX存在\),\(no data error :数据错误\),\(paramer error : 代码中捕获到错误\)

* | undefined XXX | 参数没有传XXX |
  | :--- | :--- |
  | XXX length error | XXX长度有误 |
  | XXX error | 验证XXX失败 |
  | XXX format error | XXX类型错误 |
  | 10001,10021,10081 | 数据库相关错误问题 |
  | XXX exist | XXX存在 |
  | no data error | 数据错误 |
  | paramer error | 代码中捕获到错误 |

---

---

### 3.手机号注册

* API接口:[https://weixin.lancens.com:6443/v1/api/phone/register](https://weixin.lancens.com:6443/v1/api/phone/register)

* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/phone/register" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"password\": \"string\",  \"phone\": \"string\",  \"apikey\": \"string\",  \"code\": \"string\"}"`

* 接口相关说明,密码\(8-16\),code为手机号收到的6位数验证码.手机号注册成功后账号名默认 mp\_XXXX\(20位\),apikey由lancens提供参数必须传入正确才可以完成注册.默认邮箱为空

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(10001,10021,10031, :数据库相关错误问题\),\(XXX exist: XXX存在\),\(no data error :数据错误\),\(paramer error : 代码中捕获到错误\)

* | undefind XXX | 参数没有传XXX |
  | :--- | :--- |
  | XXX length error | XXX长度有误 |
  | XXX error | 验证XXX失败 |
  | XXX format error | XXX类型错误 |
  | 100XX,200XX,300XX | 数据库相关错误问题 |
  | XXX exist | XXX存在 |
  | no data error | 数据错误 |
  | paramer error | 代码中捕获到错误 |
* 数据格式:表2\(\*为必传参数\)

### 表2

| password:**\*** | string\* 登录所使用账号对应正确的密码,由大小写字母及特殊字符"\_!@\#$%^&\*\(\)+-="组成,最大长度16个字节,最小长度8个字节 |
| :--- | :--- |
| phone:**\*** | string\* 手机号码最大长度20个字节,最小长度6个字节 |
| apikey:**\*** | string\* 由服务商提供,由小写字母组成,长度为32个字节 |
| code:**\*** | string\* 从手机获取到的验证码,由6位数字组成 |




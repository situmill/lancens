## 用户名注册相关接口

### 1.用户名注册接口

* API接口:[https://weixin.lancens.com:6443/v1/api/user](https://weixin.lancens.com:6443/v1/api/user)

* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/user" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"username\": \"string\",  \"password\": \"string\",  \"realm\": \"string\",  \"email\": \"string\",  \"phone\": \"string\",  \"apikey\": \"string\",  \"code\": \"string\"}"`

* 数据格式:表1\(\*为必传参数\)

### 表1

| username:\* | string\* 登录所使用账号,由大小写字母及特殊字符"\_"组成,非纯数字,最大长度32个字节,最小长度6个字节 |
| :--- | :--- |
| password:\* | string\* 登录所使用账号对应正确的密码,由大小写字母及特殊字符"\_!@\#$%^&\*\(\)+-="组成,最大长度16个字节,最小长度8个字节 |
| realm:\* | string\* 最大长度32个字节,最小长度1个字节 |
| email:\* | string\* 邮件地址,最大长度40个字节 |
| phone:\* | string\* 电话号码,最大长度20个字节 |
| apikey:\* | string 由服务商提供,由小写字母组成,长度为32个字节 |
| code:\* | string\* 从手机获取到的验码,由6个数字组成 |

---

---

### 2.用户名注册接口说明

* 重要参数:username（用户名6-32位）,password（8-16）,phone（6-20）,email（6-40）,realm（1-32）,          apikey（32）,code（6）

* username用户名不能纯数字,apikey为lancens提供默认为lancens相关,code满足6位即可,成功返回201.

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(database XXX :数据库相关错误问题\),\(XXX exist: XXX存在\),\(no data error :数据错误\),\(paramer error : 代码中捕获到错误\)




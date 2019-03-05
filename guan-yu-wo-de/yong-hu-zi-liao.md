## 关于用户资料的操作接口：

### 1.获取用户的基本资料

* API接口:[https://weixin.lancens.com:6443/v1/api/user](https://weixin.lancens.com:6443/v1/api/user)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/user" -H  "accept: application/json"`
* 返回数据:表1
* 表1

| description: | 用户账号信息 |
| :--- | :--- |
| id: | integer\($int64\) 账号id |
| username: | string 登录所使用账号,由大小写字母及特殊字符"\_"组成,最大长度32个字节,最小长度2个字节 |
| realm | string 账号的昵称,格式1-32位字节 |
| email: | string 邮件地址,最大长度64个字节 |
| phone: | string 电话号码,最大长度20个字节 |

---

---

### 2.更新账号相关昵称信息

* API接口:[https://weixin.lancens.com:6443/v1/api/user](https://weixin.lancens.com:6443/v1/api/user)

* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/user" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"realm\": \"string\"}"`

* 参数说明:realm\(1-32\)

---

---

### 3.修改用户名\(修改登录用户名\)

* API接口:[https://weixin.lancens.com:6443/v1/api/user/username](https://weixin.lancens.com:6443/v1/api/user/username)

* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/user/username" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"username\": \"string\"}"`

* 参数说明:username\(6-32\)不能纯数字

---

---

4.修改新邮箱


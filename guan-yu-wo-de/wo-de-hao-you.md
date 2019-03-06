## 我的好友相关

### 添加好友流程:先查询好友,再请求添加好友,对方通过申请才可以添加成功.

### 1.查找是否存在好友\(查询好友\)

* API接口:[https://weixin.lancens.com:6443/v1/api/selecte/share/friend?name=XXX](https://weixin.lancens.com:6443/v1/api/selecte/share/friend?name=XXX)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/selecte/share/friend?name=XXX" -H  "accept: application/json"`
* 参数说明:通过XXX手机号，邮箱，用户名查询用户是否存在.
* 返回数据:表1

* 表1

| suid: | number 好友id |
| :--- | :--- |
| friendname: | string 好友用户名 |
| phone: | string 手机号码 |
| mail: | string 邮箱 |
| realm: | string 昵称 |

### 2.申请添加好友，先添加到好友申请表中

* API接口:[https://weixin.lancens.com:6443/v1/api/add/share/friend](https://weixin.lancens.com:6443/v1/api/add/share/friend)
* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/add/share/friend" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"uid\": \"string\",  \"suid\": \"string\",  \"status\": 0}"`
* 参数说明:此处的uuid为用户ID**非设备uid**.suid为好友id,status默认1
* 数据格式:表2

* 表1




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

---

---

### 2.申请添加好友，先添加到好友申请表中

* API接口:[https://weixin.lancens.com:6443/v1/api/add/share/friend](https://weixin.lancens.com:6443/v1/api/add/share/friend)
* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/add/share/friend" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"uid\": \"string\",  \"suid\": \"string\",  \"status\": 0}"`
* 参数说明:此处的uuid为用户ID**非设备uid**.suid为好友id,status默认1
* 接口说明:申请添加好友后,好友将收到添加好友的推送type=200为好友消息推送
* 数据格式:表2

* 表2

| uid: | int用户id |
| :--- | :--- |
| suid: | int好友id |
| status: | number 状态 |

---

---

### 3.查看用户主动申请添加好友,没有同意的好友列表\(主动\)

* API接口:[https://weixin.lancens.com:6443/v1/api/add/share/friend](https://weixin.lancens.com:6443/v1/api/add/share/friend)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/add/share/friend" -H  "accept: application/json"`

* 接口说明:显示用户申请添加好友，好友没有同意的列表

* 数据格式:表3

---

---

### 4.查看用户被好友申请添加的好友的列表\(被动\)

* API接口:[https://weixin.lancens.com:6443/v1/api/add/friend/share](https://weixin.lancens.com:6443/v1/api/add/friend/share)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/add/friend/share" -H  "accept: application/json"`

* 接口说明:查看好友申请后  用户没有同意加好友的列表

* 数据格式:表3

表3

| uid: | string 用户id |
| :--- | :--- |
| suid: | string 好友id |
| friendname: | string 好友用户名 |
| username: | string 自己用户名 |
| status: | number 状态 |

### 5.添加好友到好友表中\(需申请才能添加成功\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/friend](https://weixin.lancens.com:6443/v1/api/device/share/friend)
* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/device/share/friend" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"uid\": \"string\",  \"suid\": \"string\",  \"status\": 0}"`
* 参数说明:此处的uuid为用户ID**非设备uid**.suid为好友id,status默认0
* 接口说明:申请添加好友到临时好友表中后,才可以调用此接口添加好友到好友列表
* 返回数据:表2




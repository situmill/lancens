# 设备相关：

### 观看视频,转接视频,设备时区,设备上下线

### 1.根据uid获取播放的token,\(获取观看视频token，判断设备属于自己还是来自分享\)

* API接口:[https://weixin.lancens.com:6443/v1/api/user/device/all/XXX/token](https://weixin.lancens.com:6443/v1/api/user/device/all/XXX/token)

* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/user/device/all/XXX/token" -H  "accept: application/json"`

* 接口相关说明:通过uid 返回观看视频的token 与 asc,self\(自己\),other\(其他人\) starttime endtime per

* 参数说明:表1

* 表1

| message: | string 返回success为成功 |
| :--- | :--- |
| asc: | string self为自己设备,other为来自分享设备 |
| token: | string 观看token |
| starttime: | string 为分享设备时才有开始时间 |
| endtime: | string 为分享设备时才有结束时间 |
| per: | string 为分享设备时才有权限 |

---

---

### 2.APP端查看分享设备转接token

* API接口:[https://weixin.lancens.com:6443/v1/api/device/app/transfer?duid=XXX&suid=YYY](https://weixin.lancens.com:6443/v1/api/device/app/transfer?duid=XXX&suid=YYY)

* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/device/app/transfer?duid=XXX&suid=YYY" -H  "accept: application/json"`

* 接口相关说明:XXX参数为设备uid,YYY为好友id

* 参数说明:表2

* 表2

| id: | integer\($int64\) id |
| :--- | :--- |
| duid: | string 用户设备uid |
| suid: | string suid为好友id,uid为自己ID |
| transfertoken: | string 转接token |
| time: | string 转接时间\(分钟\) |
| status: | number 状态 |

---

---

### 3.APP端生成分享设备转接token\(type=100为推送分享转接\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/app/transfer](https://weixin.lancens.com:6443/v1/api/device/app/transfer)

* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/device/app/transfer" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"duid\": \"string\",  \"suid\": \"string\",  \"status\": 0}"`

* 接口相关说明:转接根据分享时设置的时间来决定是否转接,根据语言显示中英文 转接为响铃推送,duid转接设备uid,suid好友id,status默认是0

* 备注说明:转接好友在线会推送响铃给好友,不在线的话不会接收到该次响铃转接.转接后可以观看,对讲等

---

---

### 4.APP端修改设备的时区\(uid\)

* API接口:[https://weixin.lancens.com:6443/v1/api/user/time/zone](https://weixin.lancens.com:6443/v1/api/user/time/zone)
* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/user/time/zone" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"uid\": \"string\",\"synchro\": \"int\",\"time_zone\": \"string\"}"`
* 参数相关说明:uid设备的uid,synchro是否自动同步时区1开启0不开启,time\_zone 时区,默认480
* 接口相关说明:更新时区表和设备表,方便记录设备上次设备的时区.

---

---

### 5.APP端查看设备时区

* API接口:[https://weixin.lancens.com:6443/v1/api/user/time/zone](https://weixin.lancens.com:6443/v1/api/user/time/zone)

* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/user/time/zone?uid=XXX" -H  "accept: application/json"`

* 接口相关说明:XXX参数为设备uid,数据返回time\_zone设备时区.

---

---

### 6.APP端查看设备最后一次上下线状态

* API接口:[https://weixin.lancens.com:6443/v1/api/user/time/zone](https://weixin.lancens.com:6443/v1/api/user/time/zone)

* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/user/time/zone?uid=XXX" -H  "accept: application/json"`

* 接口相关说明:XXX参数为设备uid,数据返回time\_zone设备时区.




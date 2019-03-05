## 关于我的分享设备

### 1.APP端获取所有主动分享给好友的设备列表

* API接口:[https://weixin.lancens.com:6443/v1/api/device/app/share](https://weixin.lancens.com:6443/v1/api/device/app/share)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/device/app/share" -H  "accept: application/json"`

* 返回数据:表2

---

---

### 2.APP端获取所有被动分享给好友的设备列表

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/app](https://weixin.lancens.com:6443/v1/api/device/share/app)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/device/share/app" -H  "accept: application/json"`

* 返回数据:表2

* 表2

| img: | string 分享设备缩略图 |
| :--- | :--- |
| endtime: | string 分享结束时间\(分钟\) |
| group\_name: | string 组名 |
| remarkname: | string 分享设备备注 |
| duid: | string 用户设备uid |
| starttime: | string 分享开始时间\(分钟\) |
| status: | number 是否接收主设备分享的推送\(0或1,默认值为1 接收分享推送\) |
| id: | integer\($int64\) id |
| per: | string 权限功能\("See\_video","Replay\_theater"，"Video\_intercom"，"Alarm\_push"\) |
| suid: | string suid为好友id\(分享人的id\) |

---

---

### 3.APP端分享权限是否接收推送\(uid\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/name/XXX](https://weixin.lancens.com:6443/v1/api/device/share/name/XXX)
* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/device/share/name/XXX" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"remarkname\": \"string\"}"`
* 接口相关说明:根据XXXuid 更新remarkname\(1-32\)设备的备注名称

---

---

### 4.APP端分享权限是否接收推送\(uid\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/per/XXX](https://weixin.lancens.com:6443/v1/api/device/share/per/XXX)
* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/device/share/per/XXX" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"status\": 0}"`
* 接口相关说明:根据XXXuid 更新分享设备表 status 是否开启接收主设备推送 \(1接收0不接收\)默认接收推送\)

---

---

### 5.APP端删除来自好友的分享设备\(uid\)

* API接口:[https://weixin.lancens.com:6443/v1/api/app/device/share/XXX](https://weixin.lancens.com:6443/v1/api/app/device/share/XXX)
* 接口请求:`curl -X DELETE "https://weixin.lancens.com:6443/v1/api/app/device/share/XXX" -H  "accept: application/json"`
* 接口相关说明:根据XXXuid 删除来自好友的分享设备,退出分享.

### 




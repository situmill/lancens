## 设备会触发门铃事件,PR活动检测事件,门锁事件

### 1.获取当前用户所有设备的历史事件信息\(传多个参数\)

* API接口:[https://weixin.lancens.com:6443/v1/api/user/deviceses/event\_record?page=XXX&page\_number=YYY](https://weixin.lancens.com:6443/v1/api/user/deviceses/event_record?page=XXX&page_number=YYY)
* 请求接口:`curl -X GET "https://weixin.lancens.com:6443/v1/api/user/deviceses/event_record?page=XXX&page_number=YYY" -H  "accept: application/json"`
* 接口说明:XXX为页数,YYY为页显示的条数 ,比如\(0,50\) 按50条一页显示.
* 返回数据:表1

---

---

### 2.获取设备事件信息\(只传页数\)

* API接口:[https://weixin.lancens.com:6443/v1/api/user/deviceses/event\_record?page=XXX&page\_number=YYY](https://weixin.lancens.com:6443/v1/api/user/deviceses/event_record?page=XXX&page_number=YYY)
* 请求接口:`curl -X GET "https://weixin.lancens.com:6443/v1/api/user/deviceses/event_record?page=XXX&page_number=YYY" -H  "accept: application/json"`
* 接口说明:XXX为页数,YYY为页显示的条数 ,比如\(0,50\) 按50条一页显示.
* 返回数据:表1

* 表1

| description: | 设备事件记录 |
| :--- | :--- |
| img: | string 经过base64加密，使用需要base64解密 |
| width: | number 图片的宽度\(默认为0\) |
| height: | number 图片的高度\(默认为0\) |
| endtime: | number 视频录像结束的时间\(时间戳 默认无为0\) |
| time: | string 事件发生时间 |
| event\_guid: | string 事件id |
| starttime: | number 视频录像开始的时间\(时间戳 默认无为0\) |
| uid: | string 设备uid |
| video\_status: | number 是否有视频录像\(1为有，默认0 为无\) |
| type: | string 设备事件类型\(0人体感应，1门铃呼叫，2指纹开锁，3密码开锁，4低电压，5门锁\)，其他\[type=100为推送分享转接,type=200为推送添加好友信息,type=20为设备下线通知，type=21为设备上线通知\] |
| id: | integer\($int64\) 事件序列id |




## 关于我的分享设备:

### 1.增加设备分享:

* API接口:[https://weixin.lancens.com:6443/v1/api/device/app/share](https://weixin.lancens.com:6443/v1/api/device/app/share)
* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/device/app/share" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"duid\": \"string\",  \"suids\": [    null  ],  \"group_name\": \"string\",  \"starttime\": \"string\",  \"endtime\": \"string\",  \"per\": [    null  ],  \"status\": 0}"`
* 接口相关说明:单个设备uid 不能超过十个分享.
* 参数说明:

| duid: | string 设备uid |
| :--- | :--- |
| suids: | \[\] description:好友id\[52,50,51\] |
| group\_name: | string 组名 |
| starttime: | string 分享开始时间\(分钟0-1440\) |
| endtime: | string 分享结束时间\(分钟0-1440\) |
| per: | \[\] description:权限功能\["See\_video","Replay\_theater","Video\_intercom","Alarm\_push"\] |
| status: | number 是否接收主设备分享的推送\(0或1,默认值为1 接收分享推送\) |




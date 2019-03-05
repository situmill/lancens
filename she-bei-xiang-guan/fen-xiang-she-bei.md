## 关于我的分享设备:

### 1.增加设备分享:

* API接口:[https://weixin.lancens.com:6443/v1/api/device/app/share](https://weixin.lancens.com:6443/v1/api/device/app/share)
* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/device/app/share" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"duid\": \"string\",  \"suids\": [    null  ],  \"group_name\": \"string\",  \"starttime\": \"string\",  \"endtime\": \"string\",  \"per\": [    null  ],  \"status\": 0}"`
* 接口相关说明:push 主设备是否接收推送,ispush是否接收来主设备离线的推送\(默认接收1\),name\(1-32\),查找时区time\_zone 是否有记录。有就使用上次记录，没有就默认服务器时区480,并更新时区相应的表,synchro是否自动更新时区\(为1自动更新时区为0不自动,int类型\)可选参数，默认开启1,当前连的wifi\(可选参数，默认为空\),device类型\(区分UI,做适配用,可选参数，默认为空\)
* 参数说明:

| duid: | string 设备uid |
| :--- | :--- |
| suids: | \[\] description:好友id\[52,50,51\] |
| group\_name: | string 组名 |
| starttime: | string 分享开始时间\(分钟0-1440\) |
| endtime: | string 分享结束时间\(分钟0-1440\) |
| per: | \[\] description:权限功能\["See\_video","Replay\_theater","Video\_intercom","Alarm\_push"\] |
| status: | number 是否接收主设备分享的推送\(0或1,默认值为1 接收分享推送\) |




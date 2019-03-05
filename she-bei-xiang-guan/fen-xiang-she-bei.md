## 关于我的分享设备

### 1.增加设备分享:

* API接口:[https://weixin.lancens.com:6443/v1/api/device/app/share](https://weixin.lancens.com:6443/v1/api/device/app/share)
* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/device/app/share" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"duid\": \"string\",  \"suids\": [    null  ],  \"group_name\": \"string\",  \"starttime\": \"string\",  \"endtime\": \"string\",  \"per\": [    null  ],  \"status\": 0}"`
* 接口相关说明:单个设备uid 不能超过十个分享.
* 参数说明:表1
* 表1

| duid: | string 设备uid |
| :--- | :--- |
| suids: | \[\] description:好友id\[52,50,51\] |
| group\_name: | string 组名 |
| starttime: | string 分享开始时间\(分钟0-1440\) |
| endtime: | string 分享结束时间\(分钟0-1440\) |
| per: | \[\] description:权限功能\["See\_video","Replay\_theater","Video\_intercom","Alarm\_push"\] |
| status: | number 是否接收主设备分享的推送\(0或1,默认值为1 接收分享推送\) |

### 2.APP端获取所有主动分享给好友的设备列表

* API接口:[https://weixin.lancens.com:6443/v1/api/device/app/share](https://weixin.lancens.com:6443/v1/api/device/app/share)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/device/app/share" -H  "accept: application/json"`

* 返回数据:表2

### 3.APP端获取所有被动分享给好友的设备列表

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

### 4.APP端根据设备uid查询分享设备相关信息\(UID\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/device?uid=XXX](https://weixin.lancens.com:6443/v1/api/device/share/device?uid=XXX)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/device/share/device?uid=XXX" -H  "accept: application/json"`
* 接口相关说明:suid 好友id friendname好友名 realm 备注名 group\_name组名,starttime endtime per权限 status 是否接收推送或历史记录  device 设备类型 
* 返回数据:表3

### 5.APP端根据设备uid查询分享设备相关信息\(组名\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/group?group=XXX](https://weixin.lancens.com:6443/v1/api/device/share/group?group=XXX)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/device/share/group?group=XXX" -H  "accept: application/json"`
* 接口相关说明:suid 好友id friendname好友名 realm 备注名 group\_name组名,starttime endtime per权限 status 是否接收推送或历史记录  device 设备类型 
* 返回数据:表3
* 表3



| suid: | string 好友id |
| :--- | :--- |
| friendname: | string 好友用户名 |
| realm: | string 好友昵称 |
| duid: | string 设备uid |
| starttime: | string 开始时间 |
| endtime: | string 结束时间 |
| per: | string 权限功能\("See\_video","Replay\_theater","Video\_intercom","Alarm\_push"\) |
| status: | number 是否接收主设备分享的推送\(0或1,默认值为1 接收分享推送\) |




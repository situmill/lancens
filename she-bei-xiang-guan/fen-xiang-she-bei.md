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

### 4.APP端根据设备uid查询分享设备相关信息\(uid\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/device?uid=XXX](https://weixin.lancens.com:6443/v1/api/device/share/device?uid=XXX)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/device/share/device?uid=XXX" -H  "accept: application/json"`
* 接口相关说明:suid 好友id friendname好友名 realm 备注名 group\_name组名,starttime endtime per权限 status 是否接收推送或历史记录  device 设备类型 ,XXX传uid
* 返回数据:表3

### 5.APP端根据设备uid查询分享设备相关信息\(组名\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/group?group=XXX](https://weixin.lancens.com:6443/v1/api/device/share/group?group=XXX)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/device/share/group?group=XXX" -H  "accept: application/json"`
* 接口相关说明:suid 好友id friendname好友名 realm 备注名 group\_name组名,starttime endtime per权限 status 是否接收推送或历史记录  device 设备类型 ,XXX传组名group
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

### 6.APP端获取所有组名

* API接口:[https://weixin.lancens.com:6443/v1/api/device/app/group/share](https://weixin.lancens.com:6443/v1/api/device/app/group/share)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/device/app/group/share" -H  "accept: application/json"`
* 接口相关说明:获取用户分享的全部组名

### 7.APP端为用户更新一个分享给好友的设备\(序列号\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/app/share/XXX](https://weixin.lancens.com:6443/v1/api/device/app/share/XXX)
* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/device/app/share/XXX" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"group_name\": \"string\",  \"starttime\": \"string\",  \"endtime\": \"string\",  \"per\": [    null  ],  \"status\": 0}"`
* 接口相关说明:传序列号更新对应的分享设备信息（权限,名字等）
* 参数说明:表4
* 表4

| group\_name: | string 组名 |
| :--- | :--- |
| starttime: | string 分享开始时间\(分钟\) |
| endtime: | string 分享结束时间\(分钟\) |
| per: | \[...\] |
| status: | number 是否接收主设备分享的推送\(0或1,默认值为1 接收分享推送\) |

### 8.APP端更新一组组名\(组名\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/app/XXX](https://weixin.lancens.com:6443/v1/api/device/share/app/XXX)
* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/device/share/app/XXX" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"group_name\": \"string\"}"`
* 接口相关说明:根据XXX旧组名 更新新组名

### 9.APP端更新设备的备注名\(uid\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/name/XXX](https://weixin.lancens.com:6443/v1/api/device/share/name/XXX)
* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/device/share/name/XXX" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"remarkname\": \"string\"}"`
* 接口相关说明:根据XXXuid 更新备注名 ,remarkname\(1-32\)

### 10.APP端分享权限是否接收推送\(uid\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/per/XXX](https://weixin.lancens.com:6443/v1/api/device/share/per/XXX)
* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/device/share/per/XXX" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"status\": 0}"`
* 接口相关说明:根据XXXuid 更新分享设备表 status 是否开启接收主设备推送 \(1接收0不接收\)默认接收推送\)

### 11.APP端重新分享设备给好友\(组名\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/group/XXX](https://weixin.lancens.com:6443/v1/api/device/share/group/XXX)
* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/device/share/group/XXX" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"group_name\": \"string\",  \"duid\": \"string\",  \"suids\": [    null  ],  \"starttime\": \"string\",  \"endtime\": \"string\",  \"per\": [    null  ],  \"status\": 0}"`
* 接口相关说明:根据XXX组名 删除某组好友分组分享,重新新建一个好友分享组,分享不超过10个人
* 数据格式:表5
* 表5

| group\_name: | string 新组名 |
| :--- | :--- |
| duid: | string 设备uid |
| suids: | \[\] description:好友id\[52,50,51\] |
| starttime: | string 分享开始时间\(分钟\) |
| endtime: | string 分享结束时间\(分钟\) |
| per: | \[\] description:权限功能\["See\_video","Replay\_theater","Video\_intercom","Alarm\_push"\] |
| status: | number 是否接收主设备分享的推送\(0或1,默认值为1 接收分享推送\) |

### 12.APP端删除来自好友的分享设备\(uid\)

* API接口:[https://weixin.lancens.com:6443/v1/api/app/device/share/XXX](https://weixin.lancens.com:6443/v1/api/app/device/share/XXX)
* 接口请求:`curl -X DELETE "https://weixin.lancens.com:6443/v1/api/app/device/share/XXX" -H  "accept: application/json"`
* 接口相关说明:根据XXXuid 删除来自好友的分享设备,退出分享.

### 13.APP端删除来自好友的分享设备\(uid\)

* API接口:[https://weixin.lancens.com:6443/v1/api/app/device/share/XXX](https://weixin.lancens.com:6443/v1/api/app/device/share/XXX)
* 接口请求:`curl -X DELETE "https://weixin.lancens.com:6443/v1/api/app/device/share/XXX" -H  "accept: application/json"`
* 接口相关说明:根据XXXuid 删除来自好友的分享设备,退出分享.




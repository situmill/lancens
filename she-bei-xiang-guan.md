# 设备相关：

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

### 3.APP端查看分享设备转接token

* API接口:[https://weixin.lancens.com:6443/v1/api/device/app/transfer?duid=XXX&suid=YYY](https://weixin.lancens.com:6443/v1/api/device/app/transfer?duid=XXX&suid=YYY)

* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/device/app/transfer?duid=XXX&suid=YYY" -H  "accept: application/json"`

* 接口相关说明:XXX参数为设备uid,YYY为好友id

* 参数说明:表2

* 



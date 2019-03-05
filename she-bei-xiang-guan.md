# 设备相关：

### 1.我的设备

### 2，分享设备

根据uid获取播放的token,\(使用此集成接口，一次性获取token，判断设备属于自己还是来自分享\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/app/share](https://weixin.lancens.com:6443/v1/api/device/app/share)

* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/device/app/share" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"duid\": \"string\",  \"suids\": [    null  ],  \"group_name\": \"string\",  \"starttime\": \"string\",  \"endtime\": \"string\",  \"per\": [    null  ],  \"status\": 0}"`
* 接口相关说明:单个设备uid 不能超过十个分享.
* 参数说明:表1
* 



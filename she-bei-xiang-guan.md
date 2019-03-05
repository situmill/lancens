# 设备相关：

### 1.我的设备

### 2，分享设备

根据uid获取播放的token,\(使用此集成接口，一次性获取token，判断设备属于自己还是来自分享\)

* API接口:https://weixin.lancens.com:6443/v1/api/user/device/all/XXX/token

* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/user/device/all/XXX/token" -H  "accept: application/json"`

* 接口相关说明:通过uid 返回观看视频的token 与 asc,self\(自己\),other\(其他人\) starttime endtime per
* 参数说明:表1
* 



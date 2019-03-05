关于我的设备:

1.增加设备:

* API接口:[https://weixin.lancens.com:6443/v1/api/user/device](https://weixin.lancens.com:6443/v1/api/user/device)
* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/user/device" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"uid\": \"string\",  \"name\": \"string\",  \"push\": 0,  \"ispush\": 0,  \"wifi\": \"string\",  \"synchro\": 0,  \"time_zone\": \"string\",  \"device\": \"string\"}"`
* 接口相关说明:push 主设备是否接收推送,ispush是否接收来主设备离线的推送\(默认接收1\),name\(1-32\),查找时区time\_zone 是否有记录。有就使用上次记录，没有就默认服务器时区480,并更新时区相应的表,synchro是否自动更新时区\(为1自动更新时区为0不自动,int类型\)可选参数，默认开启1,当前连的wifi\(可选参数，默认为空\)




* ## 关于我的设备:

### 1.增加设备:

* API接口:[https://weixin.lancens.com:6443/v1/api/user/device](https://weixin.lancens.com:6443/v1/api/user/device)
* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/user/device" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"uid\": \"string\",  \"name\": \"string\",  \"push\": 0,  \"ispush\": 0,  \"wifi\": \"string\",  \"synchro\": 0,  \"time_zone\": \"string\",  \"device\": \"string\"}"`
* 接口相关说明:push 主设备是否接收推送,ispush是否接收来主设备离线的推送\(默认接收1\),name\(1-32\),查找时区time\_zone 是否有记录。有就使用上次记录，没有就默认服务器时区480,并更新时区相应的表,synchro是否自动更新时区\(为1自动更新时区为0不自动,int类型\)可选参数，默认开启1,当前连的wifi\(可选参数，默认为空\),device类型\(区分UI,做适配用,可选参数，默认为空\)

### 2.获取用户所有设备:

* API接口:[https://weixin.lancens.com:6443/v1/api/user/device](https://weixin.lancens.com:6443/v1/api/user/device)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/user/device" -H  "accept: application/json"`
* 返回参数如下表格1:

### 3.获取用户单个设备\(序列号\):

* API接口:[https://weixin.lancens.com:6443/v1/api/user/device/XXX](https://weixin.lancens.com:6443/v1/api/user/device/XXX)
* 接口请求:curl -X GET "[https://weixin.lancens.com:6443/v1/api/user/device/XXX](https://weixin.lancens.com:6443/v1/api/user/device/XXX)" -H  "accept: application/json"
* 参数说明:XXX参数为序列号,int整型.
* 返回参数表1:
* 表1如下

| id: | integer\($int64\) 设备id |
| :--- | :--- |
| uid: | string 由大写字母组成,固定长度20个字节 |
| name: | string 由除英文特殊字符“~\`!@\#$%^&\*\(\)\_+-={}\|\[\]\:";&lt;&gt;?,./‘”组成,最大长度32个字节,最小长度1个字节 |
| push: | number 是否接收推送信息（1开启 0关闭）（必传） |
| ispush: | number 是否接收设备掉线通知\(0未开启1开启\)可选参数，默认开启1 |
| wifi: | string 当前连的wifi，默认添加时为空\(选填参数，默认为空\) |
| synchro: | number 是否自动更新时区\(为1自动更新时区为0不自动,int类型\)可选参数，默认开启1 |
| time\_zone: | string 时区\(默认为东八区\(480\)\)可选参数 |

### 4.更新用户一台设备\(序列号\):

* API接口:https://weixin.lancens.com:6443/v1/api/user/device/0
* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/user/device/0" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"name\": \"string\",  \"push\": 0,  \"ispush\": 0}"`
* 参数说明:XXX参数为序列号,int整型,




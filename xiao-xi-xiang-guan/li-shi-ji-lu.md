## 设备会触发门铃事件,PR活动检测事件,门锁事件

1.获取当前用户所有设备的历史事件信息\(传多个参数\)新

* API接口:[https://weixin.lancens.com:6443/v1/api/user/deviceses/event\_record?page=XXX&page\_number=YYY](https://weixin.lancens.com:6443/v1/api/user/deviceses/event_record?page=XXX&page_number=YYY)
* 请求接口:`curl -X GET "https://weixin.lancens.com:6443/v1/api/user/deviceses/event_record?page=XXX&page_number=YYY" -H  "accept: application/json"`
* 接口说明:XXX为页数,YYY为页显示的条数 ,比如\(0,50\) 按50条一页显示




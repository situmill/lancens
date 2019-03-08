## 设备触发门铃事件,PR活动检测事件,门锁事件,手机APP将收到推送并可以查看对应的事件的信息.

### 1.获取当前用户所有设备的历史事件信息\(传多个参数\)

* API接口:[https://weixin.lancens.com:6443/v1/api/user/deviceses/event\_record?page=XXX&page\_number=YYY](https://weixin.lancens.com:6443/v1/api/user/deviceses/event_record?page=XXX&page_number=YYY)
* 请求接口:`curl -X GET "https://weixin.lancens.com:6443/v1/api/user/deviceses/event_record?page=XXX&page_number=YYY" -H  "accept: application/json" -H "token":"token"`
* 接口说明:XXX为页数,YYY为页显示的条数 ,比如\(0,20\) 按20条一页显示.
* 参数说明:img保存的是base64格式,需要解码后才能显示正确图片地址.
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](http://developer.lancens.com:4000/deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表1\(返回数据\)

---

---

### 2.获取当前用户下某设备的历史事件信息\(传uid多个参数\)

* API接口:[https://weixin.lancens.com:6443/v1/api/user/event\_record/ZZZ/devicees?page=XXX&page\_number=YYY](https://weixin.lancens.com:6443/v1/api/user/event_record/ZZZ/devicees?page=XXX&page_number=YYY)
* 请求接口:`curl -X GET "https://weixin.lancens.com:6443/v1/api/user/event_record/ZZZ/devicees?page=XXX&page_number=YYY" -H  "accept: application/json" -H "token":"token"`
* 接口说明:XXX为页数,YYY为页显示的条数,ZZZ为设备uid ,比如\(0,20\) 按20条一页显示.
* 参数说明:img保存的是base64格式,需要解码后才能显示正确图片地址
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](http://developer.lancens.com:4000/deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表1\(返回数据\)

### 表1

| img: | string 经过base64加密，使用需要base64解密 |
| :--- | :--- |
| width: | number 图片的宽度\(默认为0\) |
| height: | number 图片的高度\(默认为0\) |
| endtime: | number 视频录像结束的时间\(时间戳 默认无为0\) |
| time: | string 事件发生时间 |
| event\_guid: | string 事件id |
| starttime: | number 视频录像开始的时间\(时间戳 默认无为0\) |
| uid: | string 设备uid |
| video\_status: | number 是否有视频录像\(1为有，默认0 为无\) |
| type: | string 设备事件类型\(0人体感应，1门铃呼叫，2指纹开锁，3密码开锁，4低电压，5门锁\)，其他\[type=100为推送分享转接,type=200为推送添加好友信息,type=20为设备下线通知，type=21为设备上线通知\] |
| id: | integer\($int64\) 事件序列id |




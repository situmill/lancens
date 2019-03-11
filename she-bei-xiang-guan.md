# 设备相关：

#### 摘要:所有的API接口都需要在header请求头里面传入访问令牌token.

#### 设备相关操作:观看视频,转接视频,设备时区,设备上下线.设备触发事件,根据分享好友的权限等.

### 1.根据uid获取播放的token,\(获取观看视频token，判断设备属于自己还是来自分享\)

* API接口:[https://weixin.lancens.com:6443/v1/api/user/device/all/XXX/token](https://weixin.lancens.com:6443/v1/api/user/device/all/XXX/token)

* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/user/device/all/XXX/token" -H  "accept: application/json" -H "token":"token"`

* 接口相关说明:通过uid 返回观看视频的token 与 asc,self\(自己\),other\(其他人\) starttime ,endtime ,per\(时间段与权限\)

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](http://developer.lancens.com:4000/deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表1\(返回数据\)

### 表1

| message: | string 返回success为成功 |
| :--- | :--- |
| asc: | string self为自己设备,other为来自分享设备 |
| token: | string 观看token |
| starttime: | string 为分享设备时才有开始时间 |
| endtime: | string 为分享设备时才有结束时间 |
| per: | string 为分享设备时才有权限 |

---

---

### 2.APP端查看分享设备转接token

* API接口:[https://weixin.lancens.com:6443/v1/api/device/app/transfer?duid=XXX&suid=YYY](https://weixin.lancens.com:6443/v1/api/device/app/transfer?duid=XXX&suid=YYY)

* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/device/app/transfer?duid=XXX&suid=YYY" -H  "accept: application/json" -H "token":"token"`

* 接口相关说明:XXX参数为设备uid,YYY为好友id,只能转接被[分享的好友](http://developer.lancens.com:4000/guan-yu-wo-de/wo-de-fen-xiang.html)

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](http://developer.lancens.com:4000/deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表2\(返回数据\)

### 表2

| duid: | string 用户设备uid |
| :--- | :--- |
| suid: | string suid为好友id,uid为自己ID |
| transfertoken: | string 转接token |
| time: | string 转接时间\(分钟\) |
| status: | number 状态 |

---

---

### 3.APP端生成分享设备转接token\(type=100为推送分享转接\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/app/transfer](https://weixin.lancens.com:6443/v1/api/device/app/transfer)

* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/device/app/transfer" -H  "accept: application/json" -H  "content-type: application/json" -H "token":"token" -d "{  \"duid\": \"string\",  \"suid\": \"string\",  \"status\": 0}"`

* 接口相关说明:转接根据分享时设置的时间来决定是否转接,根据语言显示默认en 转接为响铃推送,duid转接设备uid,suid好友id,status默认是0,只能转接被[分享的好友](http://developer.lancens.com:4000/guan-yu-wo-de/wo-de-hao-you.html)

* 备注说明:转接好友在线会推送响铃给好友.转接后可以观看,对讲等.

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](http://developer.lancens.com:4000/deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表3\(\*必传参数\)

### 表3

| duid:\* | string \* 设备uid |
| :--- | :--- |
| suid:\* | string \* 好友id |
| status: | number 状态 |

---

---

### 4.APP端修改设备的时区\(uid\)

* API接口:[https://weixin.lancens.com:6443/v1/api/user/time/zone](https://weixin.lancens.com:6443/v1/api/user/time/zone)
* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/user/time/zone" -H  "accept: application/json" -H  "content-type: application/json" -H "token":"token"  -d "{  \"uid\": \"string\",\"synchro\": \"int\",\"time_zone\": \"string\"}"`
* 参数相关说明:uid设备的uid,synchro是否自动同步时区1开启0不开启,time\_zone 时区,默认480
* 接口相关说明:更新时区表和设备表,方便记录设备最后一次更新的时区.
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](http://developer.lancens.com:4000/deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表4\(必传参数\)

#### 表4

| uid:\* | string  \* 用户设备uid |
| :--- | :--- |
| synchro:\* | int  \* 是否自动同步 |
| time\_zone:\* | string  \* 时区值默认480 |

---

---

### 5.APP端查看设备时区

* API接口:[https://weixin.lancens.com:6443/v1/api/user/time/zone](https://weixin.lancens.com:6443/v1/api/user/time/zone)

* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/user/time/zone?uid=XXX" -H  "accept: application/json"`

* 接口相关说明:XXX参数为设备uid,数据返回time\_zone设备时区.

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

---

---

### 6.APP端查看设备最后一次上下线状态

* API接口:[https://weixin.lancens.com:6443/v1/api/device/online](https://weixin.lancens.com:6443/v1/api/device/online)

* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/device/online?uid=XXX" -H  "accept: application/json"`

* 接口相关说明:XXX参数为设备uid,只返回最近一条记录的状态.

* 返回数据说明:online\_type=21为设备上线，online\_type=20为设备下线,actual\_time为触发时间

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)




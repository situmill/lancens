## 关于我的设备:

### 1.增加设备:

* API接口:[https://weixin.lancens.com:6443/v1/api/user/device](https://weixin.lancens.com:6443/v1/api/user/device)
* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/user/device" -H  "accept: application/json" -H  "content-type: application/json" -H "token":"token"  -d "{  \"uid\": \"string\",  \"name\": \"string\",  \"push\": 0,  \"ispush\": 0,  \"wifi\": \"string\",  \"synchro\": 0,  \"time_zone\": \"string\",  \"device\": \"string\"}"`
* 接口相关说明:push 主设备是否接收推送,ispush是否接收来主设备离线的推送\(默认接收1\),name\(1-32\),查找时区time\_zone 是否有记录。有就使用上次记录，没有就默认服务器时区480,并更新时区相应的表,synchro是否自动更新时区\(为1自动更新时区为0不自动,int类型\)可选参数，默认开启1,当前连的wifi\(可选参数，默认为空\),device类型\(区分UI,做适配用,可选参数，默认为空\)
* 添加设备有限制,用户主设备不能超过20个.超过也会添加失败.
* 请求接口中  \(  -H "token":"token" \) 中 token 为[ 用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(add limited 添加设备超过限制20\),\(added to myself 该设备自己已添加\),\(added to others 该设备其他用户已添加\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表1\(\*必传参数\)

### 表1

| uid:\* | string  \*  由大写字母组成,固定长度20个字节 |
| :--- | :--- |
| name:\* | string \*  由除英文特殊字符“~\`!@\#$%^&\*\(\)\_+-={}\|\[\]\:";&lt;&gt;?,./‘”组成,最大长度32个字节,最小长度1个字节 |
| push:\* | number \* 是否接收推送信息\(int类型\)（1开启 0关闭）（必传） |
| ispush: | number 是否接收设备掉线推送通知\(没有传该字段默认为1开启,int类型\)可选参数，默认开启1 |
| wifi: | string 当前连的wifi，默认添加时为空\(可选参数，默认为空\) |
| synchro: | number 是否自动更新时区\(为1自动更新时区为0不自动,int类型\)可选参数，默认开启1 |
| time\_zone: | string 时区\(默认为东八区\(480\)\)可选参数 |
| device: | string 类型\(区分UI,做适配用,可选参数，默认为空\) |

---

---

### 2.获取用户所有设备:

* API接口:[https://weixin.lancens.com:6443/v1/api/user/device](https://weixin.lancens.com:6443/v1/api/user/device)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/user/device" -H  "accept: application/json" -H "token":"token"`
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表2

---

---

### 3.获取用户单个设备\(序列号\):

* API接口:[https://weixin.lancens.com:6443/v1/api/user/device/XXX](https://weixin.lancens.com:6443/v1/api/user/device/XXX)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/user/device/XXX" -H "accept: application/json" -H "token":"token"`
* 参数说明:XXX参数为序列号,int整型.
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表2\(返回数据\)

### 表2

| id: | integer\($int64\) 设备id |
| :--- | :--- |
| uid: | string 由大写字母组成,固定长度20个字节 |
| name: | string 由除英文特殊字符“~\`!@\#$%^&\*\(\)\_+-={}\|\[\]\:";&lt;&gt;?,./‘”组成,最大长度32个字节,最小长度1个字节 |
| push: | number 是否接收推送信息（1开启 0关闭）（必传） |
| ispush: | number 是否接收设备掉线通知\(0未开启1开启\)可选参数，默认开启1 |
| wifi: | string 当前连的wifi，默认添加时为空\(选填参数，默认为空\) |
| synchro: | number 是否自动更新时区\(为1自动更新时区为0不自动,int类型\)可选参数，默认开启1 |
| time\_zone: | string 时区\(默认为东八区\(480\)\)可选参数 |
| device | string 类型\(区分UI,做适配用,可选参数，默认为空\) |

---

---

### 4.更新用户一台设备\(序列号\):

* API接口:[https://weixin.lancens.com:6443/v1/api/user/device/XXX](https://weixin.lancens.com:6443/v1/api/user/device/XXX)
* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/user/device/XXX" -H  "accept: application/json" -H  "content-type: application/json" -H "token":"token" -d "{  \"name\": \"string\",  \"push\": 0,  \"ispush\": 0}"`
* 参数说明:XXX参数为序列号,int整型,更新name设备名，:push 主设备是否接收推送,ispush是否接收来主设备离线的推送\(默认接收1\)
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表3\(必传参数\)

### 表3

| name:\* | string  \* 由除英文特殊字符“~\`!@\#$%^&\*\(\)\_+-={}\|\[\]\:";&lt;&gt;?,./‘”组成,最大长度32个字节,最小长度1个字节 |
| :--- | :--- |
| push:\* | number \* 是否接收推送信息\(0未开启,1为开启,int类型\) |
| ispush: | number 是否接收设备掉线推送通知\(0未开启,1为开启,int类型\) |

---

---

### 5.删除用户一台设备\(序列号\):

* API接口:[https://weixin.lancens.com:6443/v1/api/user/device/XXX](https://weixin.lancens.com:6443/v1/api/user/device/XXX)
* 接口请求:`curl -X DELETE "https://weixin.lancens.com:6443/v1/api/user/device/XXX" -H  "accept: application/json" -H "token":"token"`
* 参数说明:XXX参数为序列号,int整型,删除设备后,分享好友的设备也会被清除。
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

---

---

### 6.删除用户一台设备\(UID\):

* API接口:[https://weixin.lancens.com:6443/v1/api/user/XXX/device](https://weixin.lancens.com:6443/v1/api/user/XXX/device)
* 接口请求:`curl -X DELETE "https://weixin.lancens.com:6443/v1/api/user/XXX/device" -H  "accept: application/json" -H "token":"token"`
* 参数说明:XXX参数为设备uid,20位.删除设备后,分享好友的设备也会被清除
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

---

---

---

### 7.查询主设备已分享了多少个用户\(传设备UID\)

* API接口:[https://weixin.lancens.com:6443/v1/api/user/device/share/total?uid=XXX](https://weixin.lancens.com:6443/v1/api/user/device/share/total?uid=XXX)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/user/device/share/total?uid=XXX" -H  "accept: application/json" -H  "token: token"`
* 参数说明:XXX参数为设备uid,20位.返回参数uid与对应已分享的总数
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表4\(返回数据\)

#### 表4

| uid: | string 设备的uid,固定长度20个字节 |
| :--- | :--- |
| total: | number 该主设备已分享的人数 |




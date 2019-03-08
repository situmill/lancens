登陆成功后需要为用户增加手机推送令牌,推送令牌操作接口如下:

#### 1.用户手机**响铃推送**令牌相关接口:

* ### 查询手机响铃推送令牌

  \* API接口:[https://weixin.lancens.com:6443/v1/api/user/token](https://weixin.lancens.com:6443/v1/api/user/token)

  \* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/user/token" -H  "accept: application/json"  -H "token":"token"`

        \*t

* \* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(10001, 10051:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

  \*数据格式:表1\(返回数据格式\)

* ### 表1

| id: | integer\($int64\) Userid |
| :--- | :--- |
| push\_token: | string  手机推送令牌 |
| language: | string  手机语言 |
| dev: | integer\($int64\) 版本值\(0,1\)，默认是0,\(可以不传\) |
| bundleid: | string 包名,默认为公司包名,\(必须传\) |
| os: | string 手机系统\(选传，使用手机系统推送，目前支持，小米，华为，FCM\) |
| os\_token: | string 手机系统推送token\(选传，使用手机系统推送所需要使用的token，目前支持，小米，华为，FCM\) |
| push\_platform: | string 安卓推送平台\(选传，使用安卓手机系统所需要的推送平台，目前支持，小米，华为，FCM\) |

* ### 更新手机响铃推送令牌\(序列号\)

  \*API接口:[https://weixin.lancens.com:6443/v1/api/user/token/XXX](https://weixin.lancens.com:6443/v1/api/user/token/XXX)

  \*接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/user/token/XXX" -H "accept: application/json" -H "content-type: application/json" -H "token":"token"  -d "{ \"push\_token\": \"string\", \"language\": \"string\"}"`

  \*接口说明:XXX为序列号,更新响铃推送令牌push\_token（64） 与语言language（2-11）

  \*请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](http://developer.lancens.com:4000/deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

  \* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(10001, 10051:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

  \*数据格式:表2\(\*必传参数\)

### 表2

| push\_token:\* | string\* 手机推送令牌 |
| :--- | :--- |
| language:\* | string\* 手机语言 |

* ### 删除一条手机响铃推送令牌\(序列号\)

  \*API接口:[https://weixin.lancens.com:6443/v1/api/user/token/XXX](https://weixin.lancens.com:6443/v1/api/user/token/XXX)

  \*接口请求:`curl -X DELETE "https://weixin.lancens.com:6443/v1/api/user/token/XXX" -H  "accept: application/json" -H "token":"token"`

  \*接口说明:XXX为序列号.

  \*请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](http://developer.lancens.com:4000/deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

  \*相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(10001, 10051:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

---

---

#### 2.用户手机**消息推送**令牌相关接口:

* ### 查询手机**消息**推送令牌

  \*API接口:[https://weixin.lancens.com:6443/v1/api/user/message/token](https://weixin.lancens.com:6443/v1/api/user/message/token)

  \*接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/user/message/token" -H  "accept: application/json" -H "token":"token"`

  \*请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](http://developer.lancens.com:4000/deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

  \*相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(10001, 10051:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

  \* 数据格式:表3\\(返回数据\\)

### 表3

| id: | integer\($int64\) Userid |
| :--- | :--- |
| push\_token: | string  手机推送令牌 |
| language: | string  手机语言 |
| dev: | integer\($int64\) 版本值\(0,1\)，默认是0,\(可以不传\) |
| bundleid: | string 包名,默认为公司包名,\(必须传\) |
| os: | string 手机系统\(选传，使用手机系统推送，目前支持，小米，华为，FCM\) |
| os\_token: | string 手机系统推送token\(选传，使用手机系统推送所需要使用的token，目前支持，小米，华为，FCM\) |
| push\_platform: | string 安卓推送平台\(选传，使用安卓手机系统所需要的推送平台，目前支持，小米，华为，FCM\) |

* ### 更新手机**消息**推送令牌\(序列号\)

  \*API接口:[https://weixin.lancens.com:6443/v1/api/user/message/token/XXX](https://weixin.lancens.com:6443/v1/api/user/message/token/XXX)

  \*接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/user/message/token/XXX" -H  "accept: application/json" -H  "content-type: application/json" -H "token":"token" -d "{  \"push_token\": \"string\",  \"language\": \"string\"}"`

  \*接口说明:XXX为序列号,更新消息推送令牌push\_token（64） 与语言language（2-11）

  \*请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](http://developer.lancens.com:4000/deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

  \*相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(10001, 10051:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

  \*数据格式:表4\(\*必传参数\)

### 表4

| push\_token:\* | string\* 手机推送令牌 |
| :--- | :--- |
| language:\* | string\* 手机语言 |

* ### 删除一条手机**消息**推送令牌\(序列号\)

  \*API接口:[https://weixin.lancens.com:6443/v1/api/user/message/token/XXX](https://weixin.lancens.com:6443/v1/api/user/message/token/XXX)

  \*接口请求:`curl -X DELETE "https://weixin.lancens.com:6443/v1/api/user/message/token/XXX" -H  "accept: application/json" -H "token":"token"`

  \*接口说明:XXX为序列号

  \*请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](http://developer.lancens.com:4000/deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

  \*相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(10001, 10051:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)




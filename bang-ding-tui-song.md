```
登陆后还需要为用户增加手机推送令牌
```

#### 1.增加用户手机**响铃推送**令牌:

* API接口:[https://weixin.lancens.com:6443/v1/api/user/token](https://weixin.lancens.com:6443/v1/api/user/token)

* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/user/token" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"push_token\": \"string\",  \"language\": \"string\", \"dev\": 0,  \"bundleid\": \"string\",  \"os\": \"string\",  \"os_token\": \"string\",  \"push_platform\": \"string\"}"`

* 相关重要参数:token,bundleid,os,push\_platform,os\_token,dev

* 参数说明:push\_token是响铃推送的令牌,bundleid是服务器配置的证书包名,os是安卓手机型号\(Huawei,Xiaomi等\),os\_token是安卓手机型号对应的推送token,push\_platform安卓系统推送的平台\(HUAWEI,XIAOMI等\),dev是ios开发版0/发布版1

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(10001, 10051:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

| undefined XXX |
| :--- |


|  | 参数没有传XXX |
| :--- | :--- |
| no token | header请求头没有传token |
| XXX length error | XXX长度有误 |
| XXX error | 验证XXX失败 |
| XXX format error | XXX类型错误 |
| 100XX,200XX,300XX | 数据库相关错误问题 |
| invalid token | 无效的token令牌 |
| XXX exist | XXX存在 |
| username or password error | 账号密码不匹配 |
| no data error | 数据错误 |
| paramer error | 代码中捕获到错误 |

* 数据格式:表1\(\*必须参数\)

---

---

#### 2.增加用户手机**消息推送**令牌:

* API接口:[https://weixin.lancens.com:6443/v1/api/user/message/token](https://weixin.lancens.com:6443/v1/api/user/message/token)

* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/user/message/token" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"push_token\": \"string\",  \"language\": \"string\", \"dev\": 0,  \"bundleid\": \"string\",  \"os\": \"string\",  \"os_token\": \"string\",  \"push_platform\": \"string\"}"`

* 相关重要参数:push\_token,bundleid,os,push\_platform,os\_token,dev

* 参数说明:push\_token是消息推送的令牌,bundleid是服务器配置的证书包名,os是安卓手机型号\(Huawei,Xiaomi等\),os\_token是安卓手机型号对应的推送token,push\_platform安卓系统推送的平台\(HUAWEI,XIAOMI等\),dev是ios开发版0/发布版1

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(10001, 10051:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

| undefined XXX |
| :--- |


|  | 参数没有传XXX |
| :--- | :--- |
| no token | header请求头没有传token |
| XXX length error | XXX长度有误 |
| XXX error | 验证XXX失败 |
| XXX format error | XXX类型错误 |
| 100XX,200XX,300XX | 数据库相关错误问题 |
| invalid token | 无效的token令牌 |
| XXX exist | XXX存在 |
| username or password error | 账号密码不匹配 |
| no data error | 数据错误 |
| paramer error | 代码中捕获到错误 |

* 数据格式:表1\(\*必须参数\)

### 表1

| push\_token:\* | string\* 手机推送令牌 |
| :--- | :--- |
| language:\* | string\* 手机语言 |
| dev: | integer\($int64\) ios版本值\(0为发布版,1为开发版本\)，默认是0,\(\) |
| bundleid: | string 包名,默认为lancens包名 |
| os: | string 手机系统\(选传默认空，使用手机系统推送，目前支持，小米，华为，OPPO等\) |
| os\_token: | string 手机系统推送token\(选传默认空，使用手机系统推送所需要使用的token，目前支持，小米，华为，OPPO等\) |
| push\_platform: | string 安卓推送平台\(选传默认空，使用安卓手机系统所需要的推送平台，目前支持，小米，华为，FCM\) |

---

---

#### 

### 3.查询手机响铃推送令牌

* API接口:[https://weixin.lancens.com:6443/v1/api/user/token](https://weixin.lancens.com:6443/v1/api/user/token)

*  接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/user/token" -H  "accept: application/json"  -H "token":"token"`

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(10001, 10051:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)
* 数据格式:表2\(返回数据\)

| undefined XXX |
| :--- |


|  | 参数没有传XXX |
| :--- | :--- |
| no token | header请求头没有传token |
| XXX length error | XXX长度有误 |
| XXX error | 验证XXX失败 |
| XXX format error | XXX类型错误 |
| 100XX,200XX,300XX | 数据库相关错误问题 |
| invalid token | 无效的token令牌 |
| XXX exist | XXX存在 |
| username or password error | 账号密码不匹配 |
| no data error | 数据错误 |
| paramer error | 代码中捕获到错误 |

 

### 表2

| id: | integer\($int64\) Userid |
| :--- | :--- |
| push\_token: | string  手机推送令牌 |
| language: | string  手机语言 |
| dev: | integer\($int64\) 版本值\(0,1\) |
| bundleid: | string 包名,默认为公司包名 |
| os: | string 手机系统\(选传，使用手机系统推送，目前支持，小米，华为，OPPO等\) |
| os\_token: | string 手机系统推送token\(选传，使用手机系统推送所需要使用的token，目前支持，小米，华为，OPPO等\) |
| push\_platform: | string 安卓推送平台\(选传，使用安卓手机系统所需要的推送平台，目前支持，小米，华为，OPPO等\) |

---

---

### 4.更新手机响铃推送令牌\(序列号\)

* API接口:[https://weixin.lancens.com:6443/v1/api/user/token/XXX](https://weixin.lancens.com:6443/v1/api/user/token/XXX)

* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/user/token/XXX" -H "accept: application/json" -H "content-type: application/json" -H "token":"token"  -d "{ \"push\_token\": \"string\", \"language\": \"string\"}"`

* 接口说明:XXX为序列号,更新响铃推送令牌push\_token（64） 与语言language（2-11）

* 请求接口中  \(  -H "token":"token" \) 中 token 为[ 用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(10001, 10051:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)undefined XXX

* 数据格式:表3\*必传参数\)

### 表3

| push\_token:\* | string\* 手机推送令牌 |
| :--- | :--- |
| language:\* | string\* 手机语言 |

---

---

### 5.删除一条手机响铃推送令牌\(序列号\)

* API接口:[https://weixin.lancens.com:6443/v1/api/user/token/XXX](https://weixin.lancens.com:6443/v1/api/user/token/XXX)

* 接口请求:`curl -X DELETE "https://weixin.lancens.com:6443/v1/api/user/token/XXX" -H  "accept: application/json" -H "token":"token"`

* 接口说明:XXX为序列号.

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(10001, 10051:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

---

---

### 6.用户查询手机消息推送令牌:

* API接口:[https://weixin.lancens.com:6443/v1/api/user/message/token](https://weixin.lancens.com:6443/v1/api/user/message/token)

* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/user/message/token" -H  "accept: application/json" -H "token":"token"`

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(10001, 10051:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)undefined XXX
* 数据格式:表4\(返回数据格式\)

### 表4

| id: | integer\($int64\) Userid |
| :--- | :--- |
| push\_token: | string  手机推送令牌 |
| language: | string  手机语言 |
| dev: | integer\($int64\) 版本值\(0,1\) |
| bundleid: | string 包名,默认为公司包名 |
| os: | string 手机系统\(选传，使用手机系统推送，目前支持，小米，华为，OPPO等\) |
| os\_token: | string 手机系统推送token\(选传，使用手机系统推送所需要使用的token，目前支持，小米，华为，OPPO等\) |
| push\_platform: | string 安卓推送平台\(选传，使用安卓手机系统所需要的推送平台，目前支持，小米，华为，OPPO等\) |

---

### 7.更新手机**消息**推送令牌\(序列号\)

* API接口:[https://weixin.lancens.com:6443/v1/api/user/message/token/XXX](https://weixin.lancens.com:6443/v1/api/user/message/token/XXX)

* 接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/user/message/token/XXX" -H  "accept: application/json" -H  "content-type: application/json" -H "token":"token" -d "{  \"push_token\": \"string\",  \"language\": \"string\"}"`

* 接口说明:XXX为序列号,更新消息推送令牌push\_token（64） 与语言language（2-11）

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(10001, 10051:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)undefined XXX
* 数据格式:表5\(\*必传参数\)



### 表5

| push\_token:\* | string\* 手机推送令牌 |
| :--- | :--- |
| language:\* | string\* 手机语言 |

---

---

### 8.删除一条手机**消息**推送令牌\(序列号\)

\*API接口:[https://weixin.lancens.com:6443/v1/api/user/message/token/XXX](https://weixin.lancens.com:6443/v1/api/user/message/token/XXX)

\*接口请求:`curl -X DELETE "https://weixin.lancens.com:6443/v1/api/user/message/token/XXX" -H  "accept: application/json" -H "token":"token"`

\*接口说明:XXX为序列号

\*请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

\*相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(10001, 10051:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)




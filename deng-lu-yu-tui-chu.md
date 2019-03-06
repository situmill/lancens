### 用户通过用户名或第三方实现登录,登陆后返回数据格式:

`{`

`"id": id,`

`"token": token,`

`"reflash_key": reflash_key,`

`"time": reflash_time`

`}`

### 登录成功获取数据后,APP需要保存返回的token用户令牌,API接口的调用都需要用此token来获取方可操作.

### 登陆后需要为用户增加手机推送令牌

#### 1.增加用户手机**响铃推送**令牌:

* API接口:[https://weixin.lancens.com:6443/v1/api/user/token](https://weixin.lancens.com:6443/v1/api/user/token)

* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/user/token" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"push_token\": \"string\",  \"language\": \"string\",  \"id\": 0,  \"dev\": 0,  \"bundleid\": \"string\",  \"os\": \"string\",  \"os_token\": \"string\",  \"push_platform\": \"string\"}"`

* 相关重要参数:token,bundleid,os,push\_platform,os\_token,dev

* 参数说明:push\_token是响铃推送的令牌,bundleid是服务器配置的证书包名,os是安卓手机型号\(Huawei,Xiaomi等\),os\_token是安卓手机型号对应的推送token,push\_platform安卓系统推送的平台\(HUAWEI,XIAOMI等\),dev是ios开发版0/发布版1

* 数据格式:表1

表1

---

---

#### 2.增加用户手机**消息推送**令牌:

* API接口:[https://weixin.lancens.com:6443/v1/api/user/message/token](https://weixin.lancens.com:6443/v1/api/user/message/token)

* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/user/message/token" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"push_token\": \"string\",  \"language\": \"string\",  \"id\": 0,  \"dev\": 0,  \"bundleid\": \"string\",  \"os\": \"string\",  \"os_token\": \"string\",  \"push_platform\": \"string\"}"`

* 相关重要参数:token,bundleid,os,push\_platform,os\_token,dev

* 参数说明:push\_token是响铃推送的令牌,bundleid是服务器配置的证书包名,os是安卓手机型号\(Huawei,Xiaomi等\),os\_token是安卓手机型号对应的推送token,push\_platform安卓系统推送的平台\(HUAWEI,XIAOMI等\),dev是ios开发版0/发布版1

* 数据格式:表1

表1

| push\_token: | string\* 手机推送令牌 |
| :--- | :--- |
| language: | string\* 手机语言 |
| id: | integer\($int64\) Userid |
| dev: | integer\($int64\) ios版本值\(0为发布版,1为开发版本\)，默认是0,\(\) |
| bundleid: | string 包名,默认为公司包名,\(\) |
| os: | string 手机系统\(选传，使用手机系统推送，目前支持，小米，华为，FCM\) |
| os\_token: | string 手机系统推送token\(选传，使用手机系统推送所需要使用的token，目前支持，小米，华为，FCM\) |
| push\_platform: | string 安卓推送平台\(选传，使用安卓手机系统所需要的推送平台，目前支持，小米，华为，FCM\) |




### 登陆成功后需要为用户增加手机推送令牌,推送令牌操作接口如下:

#### 1.用户手机**响铃推送**令牌相关接口:

* ### 查询手机响铃推送令牌

  \* API接口:[https://weixin.lancens.com:6443/v1/api/user/token](https://weixin.lancens.com:6443/v1/api/user/token)

  \* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/user/token" -H  "accept: application/json"`

  \* 返回数据表1:

  \*表1

| id: | integer\($int64\) Userid |
| :--- | :--- |
| push\_token: | string\* 手机推送令牌 |
| language: | string\* 手机语言 |
| dev: | integer\($int64\) 版本值\(0,1\)，默认是0,\(可以不传\) |
| bundleid: | string 包名,默认为公司包名,\(必须传\) |
| os: | string 手机系统\(选传，使用手机系统推送，目前支持，小米，华为，FCM\) |
| os\_token: | string 手机系统推送token\(选传，使用手机系统推送所需要使用的token，目前支持，小米，华为，FCM\) |
| push\_platform: | string 安卓推送平台\(选传，使用安卓手机系统所需要的推送平台，目前支持，小米，华为，FCM\) |

* ### 更新手机响铃推送令牌\(序列号\)

  \*API接口:[https://weixin.lancens.com:6443/v1/api/user/token/XXX](https://weixin.lancens.com:6443/v1/api/user/token/XXX)

  \*接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/user/token/XXX" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"push\_token\": \"string\",  \"language\": \"string\",  \"id\": 0,  \"dev\": 0,  \"bundleid\": \"string\",  \"os\": \"string\",  \"os\_token\": \"string\",  \"push\_platform\": \"string\"}"`

  \*接口说明:XXX为序列号,更新响铃推送令牌push\_token（64） 与语言language（2-11）

  \*接口数据:表2

  \*表2

| push\_token: | string\* 手机推送令牌 |
| :--- | :--- |
| language: | string\* 手机语言 |
| id: | integer\($int64\) Userid |
| dev: | integer\($int64\) ios版本值\(0为发布版,1为开发版本\)，默认是0,\(\) |
| bundleid: | string 包名,默认为公司包名,\(\) |
| os: | string 手机系统\(选传，使用手机系统推送，目前支持，小米，华为，FCM\) |
| os\_token: | string 手机系统推送token\(选传，使用手机系统推送所需要使用的token，目前支持，小米，华为，FCM\) |
| push\_platform: | string 安卓推送平台\(选传，使用安卓手机系统所需要的推送平台，目前支持，小米，华为，FCM\) |

* ### 删除一条手机响铃推送令牌\(序列号\)

  \*API接口:[https://weixin.lancens.com:6443/v1/api/user/token/XXX](https://weixin.lancens.com:6443/v1/api/user/token/XXX)

  \*接口请求:`curl -X DELETE "https://weixin.lancens.com:6443/v1/api/user/token/0" -H  "accept: application/json"`

  \*接口说明:XXX为序列号.

* ### 清除手机响铃推送令牌

  \*API接口:[https://weixin.lancens.com:6443/v1/api/user/token](https://weixin.lancens.com:6443/v1/api/user/token)

  \*接口请求:`curl -X DELETE "https://weixin.lancens.com:6443/v1/api/user/token" -H  "accept: application/json"`

#### 2.用户手机**消息推送**令牌相关接口:

* ### 查询手机**消息**推送令牌

  \*API接口:[https://weixin.lancens.com:6443/v1/api/user/message/token](https://weixin.lancens.com:6443/v1/api/user/message/token)

  \*接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/user/message/token" -H  "accept: application/json"`

  \*返回数据表:表3

  \*表3



* 更新手机**消息**推送令牌\(序列号\)  
  \*API接口:[https://weixin.lancens.com:6443/v1/api/user/token/XXX](https://weixin.lancens.com:6443/v1/api/user/token/XXX)

  \*接口请求:`curl -X PUT "https://weixin.lancens.com:6443/v1/api/user/token/XXX" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"push\_token\": \"string\",  \"language\": \"string\",  \"id\": 0,  \"dev\": 0,  \"bundleid\": \"string\",  \"os\": \"string\",  \"os\_token\": \"string\",  \"push\_platform\": \"string\"}"`

  \*接口说明:XXX为序列号,更新响铃推送令牌push\_token（64） 与语言language（2-11）

  \*接口数据:表2

  \*表2

  | push\_token: | string\* 手机推送令牌 |
  | :--- | :--- |
  | language: | string\* 手机语言 |
  | id: | integer\($int64\) Userid |
  | dev: | integer\($int64\) ios版本值\(0为发布版,1为开发版本\)，默认是0,\(\) |
  | bundleid: | string 包名,默认为公司包名,\(\) |
  | os: | string 手机系统\(选传，使用手机系统推送，目前支持，小米，华为，FCM\) |
  | os\_token: | string 手机系统推送token\(选传，使用手机系统推送所需要使用的token，目前支持，小米，华为，FCM\) |
  | push\_platform: | string 安卓推送平台\(选传，使用安卓手机系统所需要的推送平台，目前支持，小米，华为，FCM\) |

* 删除一条手机**消息**推送令牌\(序列号\)

  \*API接口:[https://weixin.lancens.com:6443/v1/api/user/token/XXX](https://weixin.lancens.com:6443/v1/api/user/token/XXX)

  \*接口请求:`curl -X DELETE "https://weixin.lancens.com:6443/v1/api/user/token/0" -H  "accept: application/json"`

  \*接口说明:XXX为序列号

* ### 清除手机**消息**推送令牌

  \*API接口:[https://weixin.lancens.com:6443/v1/api/user/token](https://weixin.lancens.com:6443/v1/api/user/token)

  \*接口请求:`curl -X DELETE "https://weixin.lancens.com:6443/v1/api/user/token" -H  "accept: application/json"`




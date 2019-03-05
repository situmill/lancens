### 登陆成功后需要为用户增加手机推送令牌,推送令牌操作接口如下:

#### 1.用户手机**响铃推送**令牌相关接口:

* 查询手机响铃推送令牌

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

#### 2.用户手机**消息推送**令牌相关接口:

* API接口:[https://weixin.lancens.com:6443/v1/api/user/message/token](https://weixin.lancens.com:6443/v1/api/user/message/token)

* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/user/message/token" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"push_token\": \"string\",  \"language\": \"string\",  \"id\": 0,  \"dev\": 0,  \"bundleid\": \"string\",  \"os\": \"string\",  \"os_token\": \"string\",  \"push_platform\": \"string\"}"`

* 相关重要参数:token,bundleid,os,push\_platform,os\_token,dev

* 参数说明:push\_token是响铃推送的令牌,bundleid是服务器配置的证书包名,os是安卓手机型号\(Huawei,Xiaomi等\),os\_token是安卓手机型号对应的推送token,push\_platform安卓系统推送的平台\(HUAWEI,XIAOMI等\),dev是ios开发版0/发布版1




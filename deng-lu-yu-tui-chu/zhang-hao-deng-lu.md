### 登陆成功后需要为用户增加手机推送令牌,推送令牌操作接口如下:

#### 1.用户手机**响铃推送**令牌相关接口:



#### 2.用户手机**消息推送**令牌相关接口:

* API接口:[https://weixin.lancens.com:6443/v1/api/user/message/token](https://weixin.lancens.com:6443/v1/api/user/message/token)

* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/user/message/token" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"push_token\": \"string\",  \"language\": \"string\",  \"id\": 0,  \"dev\": 0,  \"bundleid\": \"string\",  \"os\": \"string\",  \"os_token\": \"string\",  \"push_platform\": \"string\"}"`

* 相关重要参数:token,bundleid,os,push\_platform,os\_token,dev

* 参数说明:push\_token是响铃推送的令牌,bundleid是服务器配置的证书包名,os是安卓手机型号\(Huawei,Xiaomi等\),os\_token是安卓手机型号对应的推送token,push\_platform安卓系统推送的平台\(HUAWEI,XIAOMI等\),dev是ios开发版0/发布版1




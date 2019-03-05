### 用户通过用户名或第三方实现登录，登陆后返回数据格式：

`{`

`"id": id,`

`"token": token,`

`"reflash_key": reflash_key,`

`"time": reflash_time`

`}`

登录成功获取数据后，通过返回的token用户令牌，可以查询用户的资料和增加推送令牌

1.增加用户响铃推送令牌：

* API接口:[https://weixin.lancens.com:6443/v1/api/user/token](https://weixin.lancens.com:6443/v1/api/user/token)

* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/user/token" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"push_token\": \"string\",  \"language\": \"string\",  \"id\": 0,  \"dev\": 0,  \"bundleid\": \"string\",  \"os\": \"string\",  \"os_token\": \"string\",  \"push_platform\": \"string\"}"`

* 相关重要参数:token,bundleid,os,push\_platform,os\_token

* 参数说明:bundleid是服务器配置的证书,os是手机型号\(Huawei,Xiaomi等\),os\_token手机型号对应的推送token,push\_platform推送的平台\(HUAWEI,XIAOMI等\)




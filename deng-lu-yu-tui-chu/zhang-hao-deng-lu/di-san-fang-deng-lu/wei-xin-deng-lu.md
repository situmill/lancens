## 第三方微信登录相关接口：

摘要:第三方微信登录需要微信方授权，授权成功后再新建一个账号与微信方绑定账号。实现登录

### 1.第三方微信登录接口

* API接口：[https://weixin.lancens.com:6443/v1/api/user/weixin/app/login](https://weixin.lancens.com:6443/v1/api/user/weixin/app/login)

* 接口请求：`curl -X POST "https://weixin.lancens.com:6443/v1/api/user/weixin/app/login" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"access_token\": \"string\",  \"openid\": \"string\"}"`

### 2.第三方微信登录接口说明：

* 重要参数：access\_token\(&lt;60\)，openid\(28\)

* 微信授权接口：[https://api.weixin.qq.com/sns/userinfo?access\_token=XXX&openid=XXX](https://api.weixin.qq.com/sns/userinfo?access_token=XXX&openid=XXX)

* 调用此接口，授权成功后会返回字段unionid ，openid 。

* 成功返回201，此处返回的_**token**_值为用户令牌，**所有接口**都要传入才能获取用户信息。返回数据格式:

```
{
"id":0,
"token":"string",
"reflash_key":"string",
"time":0
}
```

* 相关错误代码解析：\(undefined XXX :参数没有传XXX\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(database XXX :数据库相关错误问题\),\(no data error :数据错误\),\(paramer error : 代码中捕获到错误\)




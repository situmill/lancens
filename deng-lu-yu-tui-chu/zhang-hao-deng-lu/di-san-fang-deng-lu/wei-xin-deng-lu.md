## 第三方微信登录相关接口：

摘要:第三方微信登录需要微信方授权，授权成功后再新建一个账号与微信方绑定账号。实现登录

### 1.第三方微信登录接口

* API接口：[https://weixin.lancens.com:6443/v1/api/user/weixin/app/login](https://weixin.lancens.com:6443/v1/api/user/weixin/app/login)

* 接口请求：`curl -X POST "https://weixin.lancens.com:6443/v1/api/user/weixin/app/login" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"access_token\": \"string\",  \"openid\": \"string\"}"`

### 2.第三方微信登录接口说明：

* 重要参数：access\_token\(6-32\)，openid\(28\)，reflash\_key\(token令牌有效期默认一个月时间戳\)

* username可以为用户名，手机号或邮箱，三者都可以登录。

* 调用此接口，会删除用户的响铃和消息推送令牌并重新在redis中生成用户登录令牌token。

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




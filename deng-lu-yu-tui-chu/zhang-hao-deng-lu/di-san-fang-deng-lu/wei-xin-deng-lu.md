## 第三方微信登录相关接口：

摘要:第三方微信登录需要微信方授权，授权成功后再新建一个账号与微信方绑定账号。实现登录

### 1.第三方微信登录接口

* API接口：[https://weixin.lancens.com:6443/v1/api/user/weixin/app/login](https://weixin.lancens.com:6443/v1/api/user/weixin/app/login)

* 接口请求：`curl -X POST "https://weixin.lancens.com:6443/v1/api/user/weixin/app/login" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"access_token\": \"string\",  \"openid\": \"string\"}"`

### 2.第三方微信登录接口说明：

* 重要参数：access\_token\(&lt;60\)，openid\(28\)

* 微信授权接口：[https://api.weixin.qq.com/sns/userinfo?access\_token=XXX&openid=XXX](https://api.weixin.qq.com/sns/userinfo?access_token=XXX&openid=XXX)

* 调用此接口，授权成功后会返回字段unionid ，openid ，通过查询微信绑定表,判断是否绑定用户。

* 若绑定用户则直接登录绑定的账号。返回数据格式:

  ```
  {
  "id":0,
  "token":"string",
  "reflash_key":"string",
  "time":0
  }
  ```

* 若未绑定用户则新建一个用户，默认用户名wx\_XXX\(20\)，密码随机10位。服务器先调用API：[https://weixin.lancens.com/v1/api/user/wx/app](https://weixin.lancens.com/v1/api/user/wx/app) 生成新的账号，再调用API接口： [https://weixin.lancens.com/v1/api/user/login](https://weixin.lancens.com/v1/api/user/login)  模拟用户登录，最后再调API:[https://weixin.lancens.com/v1/api/user/weixin/app](https://weixin.lancens.com/v1/api/user/weixin/app) 成功后新增记录绑定到微信表中，加上微信账号对应记录，下次就直接可以登录不需要新建账号

```
{
"id":0,
"token":"string",
"reflash_key":"string",
"time":0
}
```

* 相关错误代码解析：\(undefined XXX :参数没有传XXX\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(database XXX :数据库相关错误问题\),\(no data error :数据错误\),\(paramer error : 代码中捕获到错误\)




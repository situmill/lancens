## 第三方微信登录相关接口

#### 摘要:第三方微信登录需要微信方授权,授权成功后服务器再新建一个账号与微信方绑定账号,实现登录.

### 1.第三方微信登录接口

* API接口:[https://weixin.lancens.com:6443/v1/api/user/weixin/app/login](https://weixin.lancens.com:6443/v1/api/user/weixin/app/login)

* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/user/weixin/app/login" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"access_token\": \"string\",  \"openid\": \"string\"}"`

* 数据格式:表1\(必传参数\)

### 表1

| apikey: | 选传参数,由lancens提供32位,默认为lancens对应的apikey |
| :--- | :--- |
| access\_token:\* | string\* 微信token |
| openid:\* | string\* 微信openid |

---

---

### 2.第三方微信登录接口说明

* 重要参数:app端只需跟微信方授权后,调用上面API接口传相应的参数\(access\_token,openid\)即可,服务端会自动处理登录关联.

* 服务器自动调用微信查询接口:[https://api.weixin.qq.com/sns/userinfo?access\_token=XXX&openid=XXX](https://api.weixin.qq.com/sns/userinfo?access_token=XXX&openid=XXX)

* 调用此接口，查询成功后会返回字段unionid ,openid ,通过unionid查询微信绑定表,判断是否绑定用户.

* 若微信表中已绑定用户则直接登录绑定的账号.返回对应信息.

* 若未绑定用户则新建一个用户,默认用户名wx\_XXX\(20\),密码随机10位,apikey默认为lancens对应的32位值,服务器先调用API:[https://weixin.lancens.com/v1/api/user/wx/app](https://weixin.lancens.com/v1/api/user/wx/app) 生成新的账号,再调用API接口: [https://weixin.lancens.com/v1/api/user/login](https://weixin.lancens.com/v1/api/user/login)  模拟用户登录,最后再调API:[https://weixin.lancens.com/v1/api/user/weixin/app](https://weixin.lancens.com/v1/api/user/weixin/app) 成功后新增记录绑定到微信表中,下次无需再建账号.

* 成功返回201,此处返回的_**token**_值为用户令牌,**所有接口**都要获取token传入header中才能获取信息,time\(token令牌有效期默认一个月时间戳\).然后APP需要[绑定手机推送令牌](/../bang-ding-tui-song.html)

* 登录成功后返回数据格式:

```
    {
      "id":0,
      "token":"string",
      "reflash_key":"string",
      "time":0
    }
```

* 相关错误代码解析:相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(10001, 10051:数据库相关错误问题\),\(no data error:服务器数据异常\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

|  undefined XXX | 参数没有传XXX |
| :--- | :--- |
| XXX length error | XXX长度有误 |
| XXX error | 验证XXX失败 |
| XXX format error | XXX类型错误 |
| 100XX,200XX,300XX | 数据库相关错误问题 |
| XXX exist | XXX存在 |
| username or password error | 账号密码不匹配 |
| no data error | 数据错误 |
| paramer error | 代码中捕获到错误 |




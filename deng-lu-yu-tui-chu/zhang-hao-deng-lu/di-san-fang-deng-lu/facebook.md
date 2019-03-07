## Facebook登录相关接口

摘要:Facebook登录需要Facebook方授权,授权成功后再新建一个账号与Facebook方绑定账号,实现登录.

### 1.Facebook登录接口

* API接口:[https://weixin.lancens.com:6443/v1/api/user/facebook/app/login](https://weixin.lancens.com:6443/v1/api/user/facebook/app/login)

* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/user/facebook/app/login" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"access_token\": \"string\"}"`

* 接口数据:表1\(\*位必传参数\)

### 表1

| apikey: | 选传参数,由lancens提供,默认为lancens对应32位值 |
| :--- | :--- |
| access\_token:\* | string\* Facebook token |

---

---

### 2.Facebook登录接口说明

* 重要参数:access\_token.facebook授权的令牌

* Facebook授权接口:[http://www.plug2v.com:8088/v1/api/user/facebook/app/login?access\_token=XXX](http://www.plug2v.com:8088/v1/api/user/facebook/app/login?access_token=XXX)

* 调用此接口，授权成功后会返回字段id ,通过查询Facebook绑定表,判断是否绑定用户.

* 若Facebook表中已绑定用户则直接登录绑定的账号.

* 若未绑定用户则新建一个用户,默认用户名fb\_XXX\(20\),密码随机10位,服务器先调用API:[https://weixin.lancens.com/v1/api/user/wx/app](https://weixin.lancens.com/v1/api/user/wx/app) 生成新的账号,再调用API接口: [https://weixin.lancens.com/v1/api/user/login](https://weixin.lancens.com/v1/api/user/login)  模拟用户登录,最后再新增记录绑定到Facebook表中,下次无需再建账号.

* 登录成功后返回数据格式:

```
    {
      "id":0,
      "token":"string",
      "reflash_key":"string",
      "time":0
    }
```

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(database XXX :数据库相关错误问题\),\(no data error :数据错误\),\(paramer error : 代码中捕获到错误\).




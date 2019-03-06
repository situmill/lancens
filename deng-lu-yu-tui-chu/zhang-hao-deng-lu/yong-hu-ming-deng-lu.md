## 用户账号登录相关接口

### 1.用户账号登录接口

* API接口:[https://weixin.lancens.com:6443/v1/api/user/login](https://weixin.lancens.com:6443/v1/api/user/login)

* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/user/login" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"username\": \"string\",  \"password\": \"string\"}"`

* 数据格式:表1

表1

| description: | 管理员或普通用户登录所使用的信息 |
| :--- | :--- |
| username: | string\* 登录所使用账号,由大小写字母及特殊字符"\_"组成,最大长度32个字节,最小长度6个字节 |
| password: | string\* 登录所使用账号对应正确的密码,由大小写字母及特殊字符"\_!@\#$%^&\*\(\)+-="组成,最大长度16个字节,最小长度8个字节 |

---

---

### 2.用户账号登录接口说明

* 重要参数:username\(6-32\),password\(8-16\),reflash\_key\(token令牌有效期默认一个月时间戳\).

* username可以为用户名,手机号或邮箱,三者都可以登录.

* 调用此接口,会删除用户的响铃和消息推送令牌并重新在redis中生成用户登录令牌token.

* 成功返回201,此处返回的_**token**_值为用户令牌,**所有接口**都要传入才能获取用户信息,返回数据格式:

```
    {
      "id":0,
      "token":"string",
      "reflash_key":"string",
      "time":0
    }
```

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(database XXX :数据库相关错误问题\),\(no data error :数据错误\),\(paramer error : 代码中捕获到错误\)




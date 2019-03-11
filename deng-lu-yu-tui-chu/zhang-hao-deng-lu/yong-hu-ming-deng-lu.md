## 用户账号登录相关接口

### 1.用户名登录接口

* API接口:[https://weixin.lancens.com:6443/v1/api/user/login](https://weixin.lancens.com:6443/v1/api/user/login)

* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/user/login" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"username\": \"string\",  \"password\": \"string\"}"`

* 数据格式:表1\(\*必传参数\)

### 表1

| username:\* | string\* 登录所使用账号,由大小写字母及特殊字符"\_"组成,最大长度32个字节,最小长度6个字节 |
| :--- | :--- |
| password:\* | string\* 登录所使用账号对应正确的密码,由大小写字母及特殊字符"\_!@\#$%^&\*\(\)+-="组成,最大长度16个字节,最小长度8个字节 |

---

---

### 2.用户名登录接口说明

* 重要参数:username\(6-32\),password\(8-16\)

* username为用户名,手机号或邮箱,三者都可以登录.

* 成功返回201,此处返回的_**token**_值为用户令牌,**所有接口**都要获取token传入header才能获取信息,time\(token令牌有效期默认一个月时间戳\).然后APP需要[绑定手机推送令牌](http://developer.lancens.com:4000/deng-lu-yu-tui-chu.html).

* 返回数据格式:

```
    {
      "id":0,
      "token":"string",
      "reflash_key":"string",
      "time":0
    }
```

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(username or password error:账号密码不匹配\),\(10001, 10051:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)




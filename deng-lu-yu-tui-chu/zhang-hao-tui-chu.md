## 用户账号退出相关接口

### 注:退出账号需要清除用户访问令牌token,清除推送令牌.

### 1.用户账号退出接口

* API接口:[https://weixin.lancens.com:6443/v1/api/user/logout](https://weixin.lancens.com:6443/v1/api/user/logout)

* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/user/logout" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"username\": \"string\",  \"token\": \"string\"}"`

* 重要参数:用户名username\(6-32\).token用户访问令牌,此接口的参数传body请求体里面.

* 调用此接口,会删除用户的响铃和消息推送令牌并清除用户登录令牌token.

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 10051:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表1\(\*为必传参数\)

### 表1

| username\* | string \*用户名 |
| :--- | :--- |
| token:\* | string\*登录令牌 |

---

---

### 2.用户账号退出后清除推送令牌

### a.清除手机响铃推送令牌 {#清除手机响铃推送令牌}

\*API接口:[https://weixin.lancens.com:6443/v1/api/user/token](https://weixin.lancens.com:6443/v1/api/user/token)

\*接口请求:`curl -X DELETE "https://weixin.lancens.com:6443/v1/api/user/token" -H "accept: application/json" -H "token":"token"`

\*请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

\*相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(10001, 10051:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

---

### b.清除手机**消息**推送令牌 {#清除手机消息推送令牌}

\*API接口:[https://weixin.lancens.com:6443/v1/api/user/message/token](https://weixin.lancens.com:6443/v1/api/user/message/token)

\*接口请求:`curl -X DELETE "https://weixin.lancens.com:6443/v1/api/user/message/token" -H "accept: application/json" -H "token":"token"`

\*请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

\*相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(10001, 10051:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)


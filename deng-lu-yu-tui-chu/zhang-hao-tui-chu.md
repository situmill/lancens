## 用户账号退出相关接口

### 1.用户账号退出接口

* API接口:[https://weixin.lancens.com:6443/v1/api/user/logout](https://weixin.lancens.com:6443/v1/api/user/logout)

* 接口请求:`curl -X POST "https://weixin.lancens.com:6443/v1/api/user/logout" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"username\": \"string\",  \"token\": \"string\"}"`

### 2.用户账号退出接口说明

* 重要参数:用户名username\(6-32\).

* 调用此接口,会删除用户的响铃和消息推送令牌并清除redis中的用户登录令牌token.

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(database XXX :数据库相关错误问题\),\(no data error :数据错误\),\(paramer error : 代码中捕获到错误\).




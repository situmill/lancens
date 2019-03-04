## 用户账号登录相关接口：

### 1.用户账号登录接口

* API接口：[https://weixin.lancens.com:6443/v1/api/user/login](https://weixin.lancens.com:6443/v1/api/user/login)

* 接口请求：`curl -X POST "https://weixin.lancens.com:6443/v1/api/user/login" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"username\": \"string\",  \"password\": \"string\"}"`

### 2.用户账号登录接口说明：

* 重要参数：username\(6-32\)，password\(8-16\)，

* 调用此接口，会删除用户的响铃和消息推送令牌并清除redis中的用户登录令牌token。

* 相关错误代码解析：\(undefined XXX :参数没有传XXX\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(database XXX :数据库相关错误问题\),\(no data error :数据错误\),\(paramer error : 代码中捕获到错误\)




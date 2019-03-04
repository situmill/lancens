## 手机号注册相关接口：

手机号注册账号需要先调用发送手机验证码接口，获取到6位数验证码后，才能调用注册。

### 1.发送手机注册验证码

* API接口:

* 
* ### 2.用户名注册接口说明：
* 重要参数:username（用户名6-32位），password（8-16），phone（6-20），email（6-40），realm（1-32），          apikey（32）.code（6）

* username用户名不能纯数字，apikey由lancens提供参数。code满足6位即可，成功返回201

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(database XXX :数据库相关错误问题\),\(XXX exist: XXX存在\),\(no data error :数据错误\),\(paramer error : 代码中捕获到错误\)




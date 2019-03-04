## 用户名注册相关接口：

### 1.用户名注册接口

`接口:curl -X POST "https://weixin.lancens.com:6443/v1/api/user" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"username\": \"string\",  \"password\": \"string\",  \"realm\": \"string\",  \"email\": \"string\",  \"phone\": \"string\",  \"apikey\": \"string\",  \"code\": \"string\"}"`

### 2.用户名注册接口说明：

* 重要参数:username（用户名6-32位），password（8-16），phone（6-20），email（6-40），realm（1-32），          apikey（32）.code（6）

* username用户名不能纯数字，apikey由lancens提供参数。code满足6位即可，成功返回201

* 相关错误代码解析:\(undefined username 参数没有传用户名\),\(undefined password 没有传密码\),\(undefined realm 没有传昵称\),\(undefined email 没有传邮箱\),\(undefined phone 没有传手机号\),\(undefined apikey 没有传apikey\),\(undefined code 没有传code\),\(username length error 用户长度1-32\),\(username error 验证用户名失败\),\(password length\(8-16\) 密码长度8-16位\),\(realm length error 昵称长度1-32\),\(email length error 邮箱1-40\),\(email format error 邮箱类型错误\),\(token length error token长度不是32位\),\(phone length error 手机长度6-32\),\(apikey length error api不是32位\),\(database error SQL操作错误\),\(user exist 用户名存在\),\(email exist 邮箱存在\),\(database user error 数据库添加用户错误\),\(database vcard error 数据库添加用户卡片错误\),\(database token error 数据库添加token错误\),\(no data error 数据错误\),\(paramer error try中捕获到错误\)

###### 




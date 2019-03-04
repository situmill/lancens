## 用户名注册相关接口：

### 1.用户名注册接口

`接口:curl -X POST "https://weixin.lancens.com:6443/v1/api/user" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"username\": \"string\",  \"password\": \"string\",  \"realm\": \"string\",  \"email\": \"string\",  \"phone\": \"string\",  \"apikey\": \"string\",  \"code\": \"string\"}"`

### 2.用户名注册接口说明：

* 重要参数:username（用户名6-32位），password（8-16），phone（6-20），email（6-40），realm（1-32），          apikey（32）.code（6）

* username用户名不能纯数字，apikey由lancens提供参数。code满足6位即可，成功返回201

###### 




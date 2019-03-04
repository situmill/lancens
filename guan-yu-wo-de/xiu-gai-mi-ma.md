## 修改密码相关接口：

### 1.通过旧密码修改密码

* API接口：[https://weixin.lancens.com:6443/v1/api/phone/register](https://weixin.lancens.com:6443/v1/api/user/password)

* 接口请求：`curl -X PUT "https://weixin.lancens.com:6443/v1/api/user/password" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"password\": \"string\",  \"oldpassword\": \"string\"}"`

* 接口相关说明：密码长度\(8-16\)。

### 2.手机号修改密码：

#### 手机号修好密码，首先调用重置手机密码接口发送验证码，获取验证码后再调用手机修改密码接口

##### 1.发送手机重置用户密码验证码

* API接口：[https://weixin.lancens.com:6443/v1/api/phone/register](https://weixin.lancens.com:6443/v1/api/user/password)

* 接口请求：`curl -X PUT "https://weixin.lancens.com:6443/v1/api/user/password" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"password\": \"string\",  \"oldpassword\": \"string\"}"`

* 接口相关说明：密码长度\(8-16\)。

##### 2.通过手机验证码，重置用户密码

* API接口：[https://weixin.lancens.com:6443/v1/api/phone/register](https://weixin.lancens.com:6443/v1/api/user/password)

* 接口请求：`curl -X PUT "https://weixin.lancens.com:6443/v1/api/user/password" -H  "accept: application/json" -H  "content-type: application/json" -d "{  \"password\": \"string\",  \"oldpassword\": \"string\"}"`

* 接口相关说明：密码长度\(8-16\)。




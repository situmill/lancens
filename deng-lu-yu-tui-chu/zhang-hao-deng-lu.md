### 用户通过用户名或第三方实现登录，登陆后返回数据格式：

`{`

`"id": id,`

`"token": token,`

`"reflash_key": reflash_key,`

`"time": reflash_time`

`}`

登录成功获取数据后，通过返回的token用户令牌，可以查询用户的资料和增加推送令牌


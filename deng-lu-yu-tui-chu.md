### 用户通过用户名或第三方实现登录,登陆后统一返回数据格式:

`{`

`"id": id,`

`"token": token,`

`"reflash_key": reflash_key,`

`"time": reflash_time`

`}`

### 登录成功获取数据后,APP需要保存返回的用户访问令牌token\(所有的API接口都需要在header请求头里面传入访问令牌token\).

### 登陆后还需要为用户增加手机推送令牌

#### 简单流程图:

![](/assets/denglu01.png)






### 第三方注册与登录:

### 实现第三方登录的功能首先要明白oauth2.0的认证原理,通过授权获取第三方的access\_token令牌，完成相关认证后,如果数据库存在相关账号绑定信息,则直接可以登录,如果数据库没有存在绑定信息\(第一次登录授权\),则会新建一个账号与数据库绑定用户关系,下次就可以直接实现登录.

1.[微信登录](http://developer.lancens.com:4000/deng-lu-yu-tui-chu/zhang-hao-deng-lu/di-san-fang-deng-lu/wei-xin-deng-lu.html):

2.[Facebook登录](http://developer.lancens.com:4000/deng-lu-yu-tui-chu/zhang-hao-deng-lu/di-san-fang-deng-lu/facebook.html):


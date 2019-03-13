## 我的好友相关

### 显示好友列表有三种:

* [自己申请添加的好友列表\(需要等待好友同意\)](#chakan1)
* [来自好友请求添加成为好友的列表\(需要自己同意后成为好友\)](/chakan2)
* [已添加成功的好友列表](/chakan3)

### 1.&lt;h3 id="chakan1"&gt;查看用户主动申请添加好友,没有同意的好友列表\(主动\)&lt;/div&gt;

* API接口:[https://weixin.lancens.com:6443/v1/api/add/share/friend](https://weixin.lancens.com:6443/v1/api/add/share/friend)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/add/share/friend" -H  "accept: application/json" -H "token":"token"`

* 接口说明:申请添加好友，好友没有同意的列表,此处APP显示_**等待对方验证**_\(当好友同意后,添加则成功\)

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表1\(返回数据\)

---

---

### 2.&lt;h3 id="chakan2"&gt;查看用户被好友申请添加的好友的列表\(被动\)&lt;/div&gt;

* API接口:[https://weixin.lancens.com:6443/v1/api/add/friend/share](https://weixin.lancens.com:6443/v1/api/add/friend/share)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/add/friend/share" -H  "accept: application/json" -H "token":"token"`

* 接口说明:接收到好友的申请,此处APP显示_**好友申请**_\(只需同意请求,即可成为好友\)

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表1\(返回数据\)

#### 表1

| uid: | string 用户id |
| :--- | :--- |
| suid: | string 好友id |
| friendname: | string 好友用户名 |
| username: | string 自己用户名 |
| status: | number 状态 |

---

---

### 3.&lt;h3 id="chakan3"&gt;查看用户已添加的好友&lt;/h3&gt;

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/friend](https://weixin.lancens.com:6443/v1/api/device/share/friend)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/device/share/friend" -H  "accept: application/json" -H "token":"token"`

* 接口说明:返回的好友列表按顺序排序

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表2\(返回数据\)

---

---

### 4.通过设备UID屏蔽分享过的好友\(显示可以分享的好友列表\)

* API接口:[https://weixin.lancens.com:6443/v1/api/shield/share/friend?uid=XXX](https://weixin.lancens.com:6443/v1/api/shield/share/friend?uid=XXX)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/shield/share/friend?uid=XXX" -H  "accept: application/json" -H "token":"token"`

* 接口说明:通过设备uid来屏蔽好友，按顺序显示可以分享的好友列表

* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* 数据格式:表2\(返回数据\)

#### 表2

| id: | int 序列id |
| :--- | :--- |
| uid: | string 用户id |
| suid: | string 好友id |
| friendname: | string 好友用户名 |
| realm: | string 好友昵称 |
| status: | number 状态 |




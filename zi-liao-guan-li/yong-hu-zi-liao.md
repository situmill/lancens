## 关于用户资料的操作接口：

### 1.获取用户的基本资料

* API接口:[https://weixin.lancens.com:6443/v1/api/user](https://weixin.lancens.com:6443/v1/api/user)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/user" -H  "accept: application/json" -H "token":"token"`
* 数据说明:返回用户名,昵称,手机号,邮箱信息.
* 请求接口中  \(  -H "token":"token" \) 中 token 为 [用户登录时的token](/../deng-lu-yu-tui-chu.html),用作唯一访问令牌,API接口都需要传到header中

* 相关错误代码解析:\(undefined XXX :参数没有传XXX\),\(no token:header请求头没有传token\),\(XXX length error: XXX长度有误\),\(XXX error: 验证XXX失败\),\(XXX format error: XXX类型错误\),\(invalid token:无效的token令牌\),\(no data error:服务器数据异常\),\(10001, 20001,30001,40001,50001,80001:数据库相关错误问题\),\(XXX exist: XXX存在\),\(paramer error : 代码中捕获到错误\)

* | undefined XXX |
  | :--- |


  |  | 参数没有传XXX |
  | :--- | :--- |
  | XXX length error | XXX长度有误 |
  | XXX error | 验证XXX失败 |
  | XXX format error | XXX类型错误 |
  | 100XX,200XX,300XX | 数据库相关错误问题 |
  | XXX exist | XXX存在 |
  | no data error | 数据错误 |
  | paramer error | 代码中捕获到错误 |
* 数据格式:表1\(返回数据\)

### 表1

| id: | integer\($int64\) 账号id |
| :--- | :--- |
| username: | string 登录所使用账号,由大小写字母及特殊字符"\_"组成,最大长度32个字节,最小长度2个字节 |
| realm | string 账号的昵称,格式1-32位字节 |
| email: | string 邮件地址,最大长度64个字节 |
| phone: | string 电话号码,最大长度20个字节 |

### 




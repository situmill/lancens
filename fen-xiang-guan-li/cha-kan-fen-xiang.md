## 关于我的分享设备

* [按设备uid查询分享设备相关列表](#1app端根据设备uid查询分享设备相关信息uid)
* [按组名查询分享设备相关列表](#2app端根据设备uid查询分享设备相关信息组名)
* [获取全部组名列表](#3app端获取所有组名)

### 1.APP端根据设备uid查询分享设备相关信息\(uid\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/device?uid=XXX](https://weixin.lancens.com:6443/v1/api/device/share/device?uid=XXX)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/device/share/device?uid=XXX" -H  "accept: application/json" -H "token":"token"`
* 接口相关说明:suid 好友id, friendname好友名, realm 备注名 ,group\_name组名,starttime endtime 时间段, per权限 ,status 是否接收推送或历史记录  device 设备类型 ,XXX传uid
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

---

---

### 2.APP端根据设备uid查询分享设备相关信息\(组名\)

* API接口:[https://weixin.lancens.com:6443/v1/api/device/share/group?group=XXX](https://weixin.lancens.com:6443/v1/api/device/share/group?group=XXX)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/device/share/group?group=XXX" -H  "accept: application/json" -H "token":"token"`
* 接口相关说明:suid 好友id, friendname好友名, realm 备注名 ,group\_name组名,starttime endtime 时间段, per权限 ,status 是否接收分享设备的推送  device 设备类型 ,,XXX传组名group
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
* 返回数据:表1\(返回数据\)

### 表1

| suid: | string 好友id |
| :--- | :--- |
| friendname: | string 好友用户名 |
| realm: | string 好友昵称 |
| duid: | string 设备uid |
| starttime: | string 开始时间 |
| endtime: | string 结束时间 |
| per: | string 权限功能\("See\_video","Replay\_theater","Video\_intercom","Alarm\_push"\) |
| status: | number 是否接收主设备分享的推送\(0或1,默认值为1 接收分享推送\) |

---

---

### 3.APP端获取所有组名

* API接口:[https://weixin.lancens.com:6443/v1/api/device/app/group/share](https://weixin.lancens.com:6443/v1/api/device/app/group/share)
* 接口请求:`curl -X GET "https://weixin.lancens.com:6443/v1/api/device/app/group/share" -H  "accept: application/json"`
* 接口相关说明:获取用户分享的全部组名\(按组名显示分享组\)
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

---

---




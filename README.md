# 叮叮智能API说明书

### 关于叮叮智能APP相关API接口调用与说明.

#### 1.用户登录叮叮智能APP.没有账号需要注册账号.

* [用户名注册](/../zhang-hao-zhu-ce/yong-hu-ming-zhu-ce.html)

* [手机号注册](/../zhang-hao-zhu-ce/shou-ji-hao-zhu-ce.html)

* [邮箱注册](/../zhang-hao-zhu-ce/you-xiang-zhu-ce.html)

* [第三方注册登录](/../deng-lu-yu-tui-chu/zhang-hao-deng-lu/di-san-fang-deng-lu.html)

#### 2.登录APP成功

* 需要获取用户的访问令牌token这个很重要\(所有的API接口都需要在header请求头里面传入访问令牌token\),

* 还需要[绑定推送](/../deng-lu-yu-tui-chu.html).\(响铃推送与消息推送\)

#### 3.登录验证通过后,进入APP设备页面.显示自己的设备或好友分享的设备

* [自己主设备](/../she-bei-xiang-guan/wo-de-she-bei.html):进入播放页面有录像.拍照,对讲,开锁,转接等功能,进入编辑页面可以修改设备名,重新配网,设置活动检测,开启关闭下线通知,时区设置,删除设备等操作

* [来自分享的设备](/../she-bei-xiang-guan/fen-xiang-she-bei.html):分享的设备根据权限显示功能,只能修改名称和删除分享或关闭分享设备的推送

#### 4.消息页面:

* [历史记录](/../xiao-xi-xiang-guan/li-shi-ji-lu.html):主要是显示设备触发的事件:门铃呼叫,活动报警,电量低报警,门锁事件.目前限制为保留15天的历史记录且单个设备不超过300张图片。

#### 5.好友管理:

* [添加好友](/../hao-you-guan-li/tian-jia-hao-you.html):通过查找好友,申请添加好友,等待对方同意后,成为好友才可以分享设备

* [查看好友](/../hao-you-guan-li/cha-kan-hao-you.html):获取好友的基本信息\(用户名,昵称,好友ID\)

* [更新或删除好友](/../hao-you-guan-li/geng-xin-yu-shan-chu.html):更新好友的备注名,好友删除后,彼此分享的设备也会都自动清除.

#### 6.分享管理:

* [添加分享](/../fen-xiang-guan-li/tian-jia-fen-xiang.html):绑定主设备才可以分享给好友,单个设备分享暂不能超过10人,分享可设置分享时段,分享权限\(视频观看,事件记录,视频对讲,报警推送\),分享后,好友在设备列表就可以看到此设备.也可以重新生成分享组..

* [查看分享](/../fen-xiang-guan-li/cha-kan-fen-xiang.html):查看分享组,可以查看分享好友的成员与分享设备权限、时间段.

* [更新或删除分享](/../fen-xiang-guan-li/geng-xin-yu-shan-chu.html):更新分享组组名,删除分享组,对应分享组中的好友也可解除分享,解除分享不影响好友关系的存在.

#### 7.资料管理:

* [用户资料](/../zi-liao-guan-li/yong-hu-zi-liao.html):获取用户的基本资料.手机邮箱等

* [更新信息](/../zi-liao-guan-li/geng-xin-zi-liao.html):更新昵称、用户名、邮箱等

* [修改密码](/../zi-liao-guan-li/xiu-gai-mi-ma.html):通过旧密码、手机号或邮箱修改用户密码

#### 8.[退出登录](/../deng-lu-yu-tui-chu/zhang-hao-tui-chu.html),账号退出后,清除推送令牌和用户访问令牌token\(之前的token也随之失效\)

#### 简单流程图：

![](/assets/TIM截图20190306161312.png)


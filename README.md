# 叮叮智能API说明书

### 关于叮叮智能APP相关API接口调用与说明.

#### 1.用户登录叮叮智能APP.没有账号需要注册账号.

* [用户名注册](http://developer.lancens.com:4000/zhang-hao-zhu-ce/yong-hu-ming-zhu-ce.html)
* [手机号注册](http://developer.lancens.com:4000/zhang-hao-zhu-ce/shou-ji-hao-zhu-ce.html)
* [邮箱注册](http://developer.lancens.com:4000/zhang-hao-zhu-ce/you-xiang-zhu-ce.html)
* [第三方注册登录](http://developer.lancens.com:4000/deng-lu-yu-tui-chu/zhang-hao-deng-lu/di-san-fang-deng-lu.html)

#### 2.登录APP成功后,需要获取用户的访问令牌token这个很重要,还需要绑定推送.\(所有的API接口都需要在header请求头里面传入访问令牌token\)

#### 3.登录验证通过后,进入APP设备页面.显示[自己的设备](http://developer.lancens.com:4000/she-bei-xiang-guan/wo-de-she-bei.html)或好友[分享的设备](http://developer.lancens.com:4000/she-bei-xiang-guan/fen-xiang-she-bei.html),可以对设备进行相关的操作.

* 点击视频播放,进入播放页面有录像.拍照,对讲,开锁,转接等功能\(分享的设备根据权限显示功能\)
* 点击编辑设备,进入编辑页面可以修改设备名,重新配网,设置活动检测,开启关闭下线通知,时区设置,删除设备等操作\(分享的设备只能修改名称和删除分享或关闭分享设备的推送\)

#### 4.[消息页面](http://developer.lancens.com:4000/xiao-xi-xiang-guan.html):

* [消息选项](http://developer.lancens.com:4000/xiao-xi-xiang-guan/li-shi-ji-lu.html):主要是显示设备触发的事件:门铃呼叫,活动报警,电量低报警,门锁事件.
* 本地选项:主要是保存视频的拍照,录像\(可本地删除\)

#### 5.[我的页面](http://developer.lancens.com:4000/guan-yu-wo-de.html):

* [好友](http://developer.lancens.com:4000/guan-yu-wo-de/wo-de-hao-you.html):通过查找好友,申请添加好友,成为好友后才可以分享设备给好友.好友关系解除后,彼此分享的设备也解除关系.
* [分享](http://developer.lancens.com:4000/guan-yu-wo-de/wo-de-fen-xiang.html):绑定主设备才可以分享给好友,单个设备分享暂不能超过10人,分享可设置分享时段,分享权限\(视频观看,事件记录,视频对讲,报警推送\),分享后,好友设备列表就可以看到此设备.也可解除分享,解除分享不影响好友关系的存在.
* [资料](http://developer.lancens.com:4000/guan-yu-wo-de/yong-hu-zi-liao.html):可修改用户名\(不能纯数字\),[修改密码,邮箱](http://developer.lancens.com:4000/guan-yu-wo-de/xiu-gai-mi-ma.html).

#### 6.[退出登录](http://developer.lancens.com:4000/deng-lu-yu-tui-chu/zhang-hao-tui-chu.html),账号退出后,[清除推送令牌](http://developer.lancens.com:4000/deng-lu-yu-tui-chu/zhang-hao-tui-chu.html)和用户访问令牌token\(之前的token也随之失效\)

#### 简单流程图：

![](/assets/TIM截图20190306161312.png)


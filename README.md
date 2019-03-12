# 叮叮智能API说明书

### 关于叮叮智能APP相关API接口调用与说明.

#### 1.用户登录叮叮智能APP.没有账号需要注册账号.

* [用户名注册](/../zhang-hao-zhu-ce/yong-hu-ming-zhu-ce.html)
* [手机号注册](/../zhang-hao-zhu-ce/shou-ji-hao-zhu-ce.html)
* [邮箱注册](/../zhang-hao-zhu-ce/you-xiang-zhu-ce.html)
* [第三方注册登录](/../deng-lu-yu-tui-chu/zhang-hao-deng-lu/di-san-fang-deng-lu.html)

#### 2.登录APP成功后,需要获取用户的访问令牌token这个很重要,还需要绑定推送.\(所有的API接口都需要在header请求头里面传入访问令牌token\)

#### 3.登录验证通过后,进入APP设备页面.显示[自己的设备](/../she-bei-xiang-guan/wo-de-she-bei.html)或好友[分享的设备](/../she-bei-xiang-guan/fen-xiang-she-bei.html),可以对设备进行相关的操作.

* 点击视频播放,进入播放页面有录像.拍照,对讲,开锁,转接等功能\(分享的设备根据权限显示功能\)
* 点击编辑设备,进入编辑页面可以修改设备名,重新配网,设置活动检测,开启关闭下线通知,时区设置,删除设备等操作\(分享的设备只能修改名称和删除分享或关闭分享设备的推送\)

#### 4.[消息页面](/../xiao-xi-xiang-guan.html):

* 历史记录:主要是显示设备触发的事件:门铃呼叫,活动报警,电量低报警,门锁事件.
* 本地选项:主要是保存视频的拍照,录像\(可本地删除\)

#### 5.[好友管理](/../hao-you-guan-li.html):

* 添加好友:通过查找好友,申请添加好友,对方同意后,成为好友才可以分享设备.添加好友目前没有上限限制
* 删除好友:好友删除后,对应彼此分享的设备也会清除.

#### 6.[分享管理](/../fen-xiang-guan-li.html):

* 新增分享:绑定主设备才可以分享给好友,单个设备分享暂不能超过10人,分享可设置分享时段,分享权限\(视频观看,事件记录,视频对讲,报警推送\),分享后,好友在设备列表就可以看到此设备.
* 重新分享:重新分享组,可以重新设置设备权限与分享时间段.
* 删除分享:删除分享组,对应分享组中的好友也可解除分享,解除分享不影响好友关系的存在.

#### 7.[资料管理](/../zi-liao-guan-li.html):

* 用户资料:获取用户的基本资料.手机邮箱等
* 更新信息:更新昵称、用户名、邮箱、密码等

#### 8.[退出登录](/../deng-lu-yu-tui-chu/zhang-hao-tui-chu.html),账号退出后,清除推送令牌和用户访问令牌token\(之前的token也随之失效\)

#### 简单流程图：

![](/assets/TIM截图20190306161312.png)


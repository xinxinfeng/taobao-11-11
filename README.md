# 关于吾爱被删帖
* 就因为贴子加了个招收测试志愿者Q群的一段话，于是被管理直接删贴扣了所有吾爱币，连个警告也没有
* 罢了罢了，让人寒心，不会在吾爱发帖了

# 新增京东双11自动化任务功能
更新最新版本后，可同时执行淘宝+京东+支付宝自动脚本，按需勾选即可

# 淘宝+京东双十一活动脚本
## 支持淘宝\支付宝\京东双11任务自动执行
### 淘宝
* 支持自动【签到】
* 支持自动【领取奖励】
* 支持自动做【去完成】类任务
* 支持自动做【去浏览】类任务
* 支持自动做【去搜索】类任务
* 支持自动做【去观看】类任务
* 支持自动【拍猫猫】（可自定义次数）

### 支付宝
* 支持自动【签到】
* 支持自动做【逛一逛】类任务

### 京东
* 支持自动【签到】
* 支持【全民营业】活动自动赚金币

## 更新日志
### V 2.2.2   ——2020.10.26 21:28
* 新增调速功能，可自由选择调节脚本的操作间隔，旧手机的福音
* 优化京东活动分享任务的识别跳过机制
* 修复淘宝活动进入直播任务会划走无法获得奖励的问题
* 拍猫猫可选次数增加可拍300次

### V 2.1.0   ——2020.10.25 18:05
* 优化模拟点击算法，加入按住时长维度，每次短按屏幕时长随机化，更加接近真人操作
* 新增京东自动签到功能
* 修复京东脚本会卡在商圈活动的问题
* 控件未点击成功时，自动循环再点击，提高点击成功率
* 优化操作时间间隔

### V 2.0.2   ——2020.10.25 15:56
* 修复偶发性未点进任务内页，会在任务首页滑动的问题
* 修复偶发性退出到京东首页，导致脚本提前结束的问题
* 优化京东打开活动页逻辑

### V 2.0.1   ——2020.10.25 15:19
* 修复部分机型进入京东活动页会卡住的问题

### V 2.0.0   ——2020.10.25 14:15
* 新增京东双11全民营业活动自动化任务

### V 1.4.2   ——2020.10.25 00:12
* 拍猫猫小BUG修复

### V 1.4.1   ——2020.10.24 23:44
* 修复无障碍开关判定偶发错误的问题

### V 1.4.0   ——2020.10.24 23:04
* 优化任务执行模式，可选择性勾选淘宝赚喵币、淘宝拍猫猫、支付宝赚喵币任务
* 新增淘宝自动拍猫功能，可自由选择拍猫次数
* 新增自动做【去观看】类任务功能
* 优化等待逻辑，提升控件识别能力
* 优化代码规范及注释，方便学习

### V 1.3.2   ——2020.10.24 00:57
* 新增淘宝活动页自动签到功能

### V 1.3.1   ——2020.10.24 00:46
* 新增支付宝自动签到功能

### V 1.3.0   ——2020.10.23 18:11
* 新增支付宝自动化任务功能

### V 1.2.0   ——2020.10.23 11:24
* 修复进入打开淘宝特价版任务会卡住的问题

### V 1.1.1   ——2020.10.22 12:29
* 优化打开活动页方式，运行脚本可自动打开活动页

### V 1.1.0   ——2020.10.22 11:02
* 新增仿真滑屏动作，避开脚本检测

## 2020年10月24日22:58测试（没root），完全正常，可以获得全额奖励
一定要使用低版本淘宝（V5.7及以下），关掉淘宝的自动更新

有用户说原本能有奖励的，过了一两天之后没奖励了，是因为淘宝自动更新啦

大部分模拟器运行淘宝都会无法获取奖励（开不开脚本都一样），不建议使用模拟器

吾爱有用户说root环境下开了EDXP的话必制裁，建议可以关掉尝试下

详情可见吾爱链接：https://www.52pojie.cn/thread-1289644-1-1.html

## 创作说明
看了很多网上传的双十一脚本的源码，大多都**采用find控件再click这种触发事件**的方式

感觉还是有些问题的，因为**整个脚本并没有直接去点击屏幕**（在开发者模式是抓不到点击状态的）

而且。。。这些脚本所有动作的时间间隔都是**固定不变**的，整个脚本流程会**生硬许多**，**很容易被检测到**。

作为一个**PHPer**，也懂点auto.js，所以就自己写了个双十一的脚本。。。

这个脚本**完全模拟人工点击操作**，没有采用直接触发控件事件的方式。

而是找到控件的坐标范围，再在这个范围生成随机数**随机模拟点击**。

滑屏操作也并非机器式直线滑屏，**通过算法模拟真人滑屏（会有曲率），并有线性的速度（滑动过程先快后慢）**，感兴趣的可以在开发者工具看一下滑屏曲线

另外呢，**所有操作的时间间隔也加入了随机数**，不会固定一个间隔，所以应该能比较好地避开风控检测

目前来说，**多账号多手机亲测可用，可获全额奖励**

## 重要说明
* 高版本淘宝有**制裁规则**，会监控auto.js等脚本app进程，**奖励会变得特别低**
* 亲测淘宝V9.5.7版不会监控进程，可以获得全额奖励，推荐使用此版本
* [淘宝9.5.7下载](https://www.wandoujia.com/apps/32267/history_v278)

## 脚本说明
* 此脚本可自动做淘宝双十一的超级星秀猫任务，完全解放双手
* 市面上其他脚本都是直接触发控件，并没有真正去点击屏幕，容易被判定作弊
* 此脚本完全模拟人工点击（包括滑屏操作），所有操作均加入随机数，在脚本算法层面有效提升过风控几率

## 使用说明
* **安卓设备**（无需root）安装Auto.js，APP下导入js脚本
* 开启无障碍服务并授权给Auto.js
* Auto.js APP下导入js脚本，运行即可
* [auto.js-4.1.0下载](https://share.weiyun.com/5a9g8ys)
* 仍不了解怎么使用的，建议度娘一下

## 下载链接
* 手机进GitHub不好下载脚本的，可以进网盘下载
* V2.1.0版
下载:https://wws.lanzous.com/irXIQhqds7g 密码:f2bx

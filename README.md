# super-liver
安卓全平台保活  android keep running  demo可体验测试保活效果

## 什么是安卓保活

在我们使用app过程中，系统出于体验和性能上的考虑，在以下情况会回收app

- 用户关闭app
- app在退到后台一段时间或者重启手机

app一旦被系统回收后无法主动提示(消息通知,弹窗等方式)用户再次打开app。

安卓保活指的是以上情况中通过技术方法避免app被回收或者被回收后可以自动重新拉起。

## 保活的重要性和难点

保活一直是产品开发者关注的重要话题，添加保活后开发者可以通过系统消息,弹窗等各种方式引导用户再次打开app，从而直接提升产品曝光和收入。

保活一直是技术难题，安卓平台不断升级提高保活技术门槛导致大多数开发者面对安卓繁杂的系统和机型深感有心无力，同时保活作为各公司核心技术点导致市面上没有任何项目可供参考使用。

## super-live介绍

super-live作者一直从事android安全和底层开发工作，先后在360和微信从事相关工作，对应用保活有深入认识理解。super-live目前是市场上唯一系统提供保活解决方案的sdk且价格便宜，为开发者专注业务开发保驾护航。

super-live针对不同机型不同系统版本采用13种保活技术保证app存活，对android全版本有效,有以下特点

- 拒绝应用强杀
- 拒绝后台任务栏清理杀死
- 拒绝清除缓存杀死
- 开机自启动
- 第一次安装立即静默自启动
- 后台禁止休眠，拒绝进程冻结
- 不依赖权限的后台弹框，成功率 90 %
- 从Linux角度进行处理的保活方案，无需root
- 0权限申请

## super-live适用产品场景

super-live适用于工具app，游戏app，内容类(小说漫画音乐视频直播)app，社交app。以上是super-live普遍适用的产品场景，其他通过消息通知/弹窗唤醒用户的产品均适合接入使用

## 如何测试app被杀后保活效果(建议使用不同安卓版本测试)

```bash
# 先forcestop(系统回收进程)
adb shell am force-stop 包名

# 查看app是否继续存活
adb shell ps -ef |grep 包名
```

其中 com.miqt.demo是demo app包名，将其替换为需要测试的app包名。如果force-stop进程消失则说明app无法在系统回收后拉起。根据我们测试结果，市场上98%以上app无法在android9及以上保活


## 联系

vx : huolinmufeng

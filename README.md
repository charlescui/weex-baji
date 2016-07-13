# 电视直播节目单

## 编译说明

* 下载[WEEX](https://github.com/alibaba/weex)项目
* COPY到 [WEEX](https://github.com/alibaba/weex)的`examples`目录
* 在examples目录的 [index.we](https://github.com/alibaba/weex/blob/dev/examples/index.we)文件中, 添加如下内容`{name: 'Baji/index', title: '吧唧'},` 到 `data.items`

## 使用说明

0. 频道列表
	1. 当前APP支持哪些频道信息
0. 正在直播
	1. 当前时间各个频道正在直播的节目信息，以及该频道最新视频截图
2. 今日节目
	3. 当前频道今天的直播节目清单

## APP截图

> 频道/正在直播/今日节目的演示截图

<img src="https://raw.githubusercontent.com/charlescui/weex-baji/master/images/channels.jpg" width="160" /><img src="https://raw.githubusercontent.com/charlescui/weex-baji/master/images/playing.jpg" width="160" /><img src="https://raw.githubusercontent.com/charlescui/weex-baji/master/images/today.jpg" width="160" />

# 关于Weex

之前我一直在关注ReactiveNative的开发，机缘巧合，四月份我同事跟我提起阿里做了一个Weex，不久要开源了，我就一直持续关注至今。

真正动手用起来是在6月底，也就是Weex开源前的那一周，加入了开发者聊天群，申请了github仓库的权限，于是第一次看到了Weex的项目代码，很兴奋的跃跃欲试。

先是看文档，当时官方有两套文档：
- 一套是英文的，比较完整：
	- http://alibaba.github.io/weex/doc/tutorial.html
- 一套是中文的，比较细致：
	- https://github.com/weexteam/article/issues

一边看文档了解weex文件结构，了解各种组件，了解页面加载机制，以及很重要的内置的几个Module。
一边用项目提供的[example](https://github.com/alibaba/weex/tree/dev/examples)和[WeexOne](https://github.com/dodola/WeexOne)。
一边在交流群里请教问题和回答问题。

通过不断的修改Example来验证自己对Weex的理解，也得益于Weex框架友好的代码结构设计，一两天时间就可以把Example里面介绍的大多数用法掌握。

这个例子我陆陆续续花了4天时间完成，因为平时工作任务很重，每天少许时间调研Weex，真正投入到该例子开发中的时间应该是1.5人日。开发效率高，代码结构清晰，部署方便，支持丰富的JS库引入，语法层面用的都是熟悉的知识，这的确是Weex非常值得表扬的地方。

做完这个例子后，我在公司内部做了一次分享，跟研发有关的各种岗位的同学都参加了，大家几乎都是第一次看到Weex。但在分享过程中，每讲到一处，大家都有一种恍然领悟的感觉，仿佛在表达：“哦对，我也觉得该这么写”。一路讲下来，水到渠成，大家没有任何陌生感。平时在用ReactiveNative的同学对两者做了对比，认为还是Weex上手更快，比RN更贴近我们熟悉的前端开发。

对Weex熟悉的越多，我在工程上的思考也就越多，我认为有了Weex后，移动端团队的结构可以按这种方式组建：
- 原岗位的Android和iOS同学
	- 继续原生代码编程，负责Native底层的桥接工作，给UI组件提供底层能力支持。
		- Android和iOS的生态环境已经非常完善，我们已经在用的各种服务和SDK不能丢弃，这些Native代码需要桥接到UI组件
- 前端同学
	- 使用Weex按照熟悉的HTML\JS\CSS继续实现UI层

这样的话前端同学就成了真正意义上的大前端，主攻交互，往体验、往实现细节上深造。

Weex目前也有很多不足不成熟的地方，短时间内还不敢用于正式项目。我在开发过程中遇到很多问题，有BUG，也有功能缺失，举几个我觉得比较重要的功能相关的例子：
- 还没有好的调试工具
- iOS的Pod还不支持
- 页面切换方式不丰富，比如还没有一个页面从下到上出现的效果，就是iOS的presentViewController方法。
- 没有考虑到Android盒子的适配，包括：
	- 遥控器按上下左右的时候，需要有光标移动效果和组件获取光标焦点支持。

这些问题我已反馈给Weex维护团队，相信随着时间的推移，问题会越来越少，体验越来越好。

总体来说，Weex的出现让我很兴奋，它设计的对工程师非常友善。相信会有很多人来一起壮大Weex社群，也期望阿里集团能给Weex团队更多的支持，让他们更专注的把Weex做好，让业界乃至世界刮目相看。

---------

我写的这个例子叫："电视直播节目单"，原名叫"吧唧"，取自我之前做过的一个App："[吧唧TV](https://appsto.re/cn/zS45-.i)".

这个例子里使用了一个我做的直播流实时抽帧接口，该接口使用的云存储是按调用次数收费的，请大家不要爬取。如果真的需要可以联系我：cuizheng.hz#qq.com

# 领航人

# 目标

了解[react | 秋风的笔记 (qiufeng.blue)](https://www.qiufeng.blue/react/)网站的实现。——？

网络建站 ——？

小程序 ——？

# 教程

[JavaScript - 学习 Web 开发 | MDN (mozilla.org)](https://developer.mozilla.org/zh-CN/docs/learn/JavaScript)

B站-尚硅谷-javascript视频教程

# 优秀纯JS应用

[分享](https://juejin.cn/post/7181812894579818556)33个js游戏案例~😜 - 掘金 (juejin.cn)

# 概述

1995年诞生，最初主要处理网页中的前端验证，比如用户名长度、密码长度、邮箱格式等。而现在网页中的动态效果，都离不开JS。

不同的浏览器都需要实现JS/ECMAScript标准，才能支持javascript。其中chrome的v8引擎是最快的。

ECMAScript + DOM + BOM

document.write()

console.log()

var

# javascript

# 需要掌握

**知识点**

![](RackMultipart20230701-1-8o2qhv_html_86b60a64edbefd4b.png)

基础知识点：变量、[数组](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/First_steps/Arrays)、函数、判断、赋值运算等操作

关键知识点: [DOM](https://developer.mozilla.org/zh-CN/docs/Web/API/Document_Object_Model)、[事件](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Building_blocks/Events)、API、[canvas](https://developer.mozilla.org/zh-CN/docs/Web/API/Canvas_API)

特色：

1. 动态类型。声明变量时不需要指定变量类型（Number,String,Boolean,Array,Object）

**核心概念：**

事件循环：

JavaScript 有一个基于 **事件循环** 的并发模型，事件循环负责执行代码、收集和处理事件以及执行队列中的子任务。这个模型与其他语言中的模型截然不同，比如 C 和 Java。

![](RackMultipart20230701-1-8o2qhv_html_1d0680fdfbdd480e.png)

"执行至完成"：每一个消息完整地执行后，其他消息才会被执行。

添加消息：在浏览器里，每当一个事件发生并且有一个事件监听器绑定在该事件上时，一个消息就会被添加进消息队列。

永不阻塞：JavaScript 的事件循环模型与许多其他语言不同的一个非常有趣的特性是，它永不阻塞。处理 I/O 通常通过事件和回调来执行

## [文档对象模型](https://developer.mozilla.org/zh-CN/docs/Web/API/Document_Object_Model)DOM

[Document - Web API 接口参考 | MDN (mozilla.org)](https://developer.mozilla.org/zh-CN/docs/Web/API/Document)

## 事件

[事件参考](https://developer.mozilla.org/zh-CN/docs/Web/Events)| MDN (mozilla.org)

## API

分为第三方API和浏览器内置API。

**浏览器**  **API**  内建于 web 浏览器中，它们可以将数据从周边计算机环境中筛选出来，还可以做实用的复杂工作。例如：

- [文档对象模型](https://developer.mozilla.org/zh-CN/docs/Web/API/Document_Object_Model)API（DOM（Document Object Model）API） 能通过创建、移除和修改 HTML，为页面动态应用新样式等手段来操作 HTML 和 CSS。比如当某个页面出现了一个弹窗，或者显示了一些新内容（像上文小 demo 中看到那样），这就是 DOM 在运行。
- [地理位置](https://developer.mozilla.org/zh-CN/docs/Web/API/Geolocation)API（Geolocation API） 获取地理信息。这就是为什么 [谷歌地图](https://www.google.cn/maps) 可以找到你的位置，而且标示在地图上。
- [画布（](https://developer.mozilla.org/zh-CN/docs/Web/API/Canvas_API)Canvas） 和 [WebGL](https://developer.mozilla.org/zh-CN/docs/Web/API/WebGL_API) API 可以创建生动的 2D 和 3D 图像。人们正运用这些 web 技术制作令人惊叹的作品。参见 [Chrome Experiments](https://www.chromeexperiments.com/webgl) 以及 [webglsamples](https://webglsamples.org/)。
- 诸如 [HTMLMediaElement](https://developer.mozilla.org/zh-CN/docs/Web/API/HTMLMediaElement) 和 [WebRTC](https://developer.mozilla.org/zh-CN/docs/Web/API/WebRTC_API) 等 [影音类](https://developer.mozilla.org/zh-CN/docs/Web/Guide/Audio_and_video_delivery)[API](https://developer.mozilla.org/zh-CN/docs/Web/Guide/Audio_and_video_delivery) 让你可以利用多媒体做一些非常有趣的事，比如在网页中直接播放音乐和影片，或用自己的网络摄像头获取录像，然后在其他人的电脑上展示（试用简易版 [截图](http://chrisdavidmills.github.io/snapshot/)[demo](http://chrisdavidmills.github.io/snapshot/) 以理解这个概念）。

**第三方**  **API**  并没有默认嵌入浏览器中，一般要从网上取得它们的代码和信息。比如：

- [Twitter API](https://dev.twitter.com/overview/documentation)、[新浪微博](https://open.weibo.com/)[API](https://open.weibo.com/) 可以在网站上展示最新推文之类。
- [谷歌地图](https://developers.google.com/maps/)API、[高德地图](https://lbs.amap.com/)[API](https://lbs.amap.com/) 可以在网站嵌入定制的地图等等。
- [Web API 接口参考 | MDN (mozilla.org)](https://developer.mozilla.org/zh-CN/docs/Web/API)

## 框架

Vue、react、angular、


# js升级
## TypeScript

TypeScript 是javaScript的超集，2010年诞生于微软，在js的基础上，扩展js，引入类型概念，解决js不适用于大型项目的问题。

为什么出现，解决了什么问题？：

1. 易出问题，暴露到用户那里。

2. 难以维护。不适合开发大型项目。

3. js不报错。比如let 和函数入出参不声明变量类型，后续运算可能会出问题。

需要安装node.js, ts编译器。

支持es新特性。

丰富的配置选项tsconfig.json（es版本，类型支持程度）。

安装、快速入门、

### 快速入门

[5分钟上手TypeScript · TypeScript中文网 · TypeScript——JavaScript的超集 (tslang.cn)](https://www.tslang.cn/docs/handbook/typescript-in-5-minutes.html)

安装: node.js, ts编译器

编译：

tsc greeter.ts

tsc greeter.ts -w //监视模式，只针对一个文件

tsc //编译所有ts文件，需要配置文件

变量类型、

| 常规类型string, Boolean, number |
 |
| --- | --- |
| 字面量 | let a: 'hello' | 'world' |
| any | 没有指定变量类型和变量值时，默认是any。可以赋值给任意类型的变量。比较严重。 |
| unknown | 安全的any。let a:unknown; 只能嚯嚯自己。let b: string;b = a as string; 或b = \<string\>a指定a的类型为string，即可赋值给string类型的变量。typeof a; 查看a的变量类型。 |
| void | undefined |
| never | 报错时使用在函数返回值中。throw new Error(); |
| object | let b:{name:string};let a: (x,y,[proName:string]:any)let c: (a,b)=\>number;
 |
| array | let a:string[];let b: Array[any]; |
| tuple | [string,number] |
| enum | enum gender{Man;Female;} |

## 服务端js node.js

流行的服务器端 web 语言包括：PHP、Python、Ruby、ASP.NET 以及...... JavaScript！JavaScript 也可用作服务器端语言，比如现在流行的 Node.js 环境，你可以在我们的 [动态网页](https://developer.mozilla.org/zh-CN/docs/Learn/Server-side)[- 服务器端编程](https://developer.mozilla.org/zh-CN/docs/Learn/Server-side) 主题中找到更多关于服务器端 JavaScript 的知识。

### 创始人故事

创始人：Ryan Dahl

大学学习数学相关专业，毕业后用Ruby on Rails在南美旅行并做网站开发，为一个滑雪板公司制作网站。多个开源项目参与者，现在是Google Brain团队的软件工程师，主要负责深度学习的有关项目。

2009年，29岁创立node.js并向大家宣讲。

创始人观点：不过我认为 **Node**  **不是构建大型**  **Web**  **服务器的最佳选择** ，我会建议 **使用**  **Go** 来实现。老实说，这也是我离开 Node 的原因。因为我意识到：原来 Node 并不是最好的服务器端语言。我觉得 **Node**  **真的发光点是用在客户端。例如：一些小服务器开发或开发服务器的实时流量服务，** Node 是正确选择。但是如果构建一个大规模分布式DNS服务器，我不会选择 Node 的。

### 学习node.js

[Download | Node.js (nodejs.org)](https://nodejs.org/en/download)

[尚硅谷](https://www.bilibili.com/video/BV1gM411W7ex/?spm_id_from=333.337.search-card.all.click)2023版Node.js零基础视频教程，nodejs新手到高手\_哔哩哔哩\_bilibili

![](RackMultipart20230701-1-8o2qhv_html_86b60a64edbefd4b.png) ![](RackMultipart20230701-1-8o2qhv_html_425b362c4b376215.png)

Node.js是开源的、跨平台的、支持运行javaScript的运行环境，是基于事件循环实现的异步I/O框架。可以用来做服务器、工具类应用（Webpack、vite、babel用来提高开发效率）、用来开发桌面端应用（vscode, postman,-\>electron）

npm是Node.js默认的、用JavaScript编写的软件包管理系统。

运行：node hello.js

主要功能:作为一个服务器语言，需要能够接收网络请求、上传下载文件、进行逻辑处理/数据计算。

特征：前后端语言一致、高性能（实时、高并发）

普遍概念：函数式、原型链继承

核心概念：事件循环、回调函数嵌套、

Buffer: 缓冲区。内存固定的数据缓冲区。

[Node.js 入门到干活，10 个优质项目就够了！ - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/88452684#:~:text=1.Node.js%20%E5%9F%BA%E7%A1%80%E8%AF%BE%E7%A8%8B%20%E4%BB%8E%20Node.js%20%E7%9A%84%E5%9F%BA%E6%9C%AC%E6%A6%82%E5%BF%B5%E5%85%A5%E6%89%8B%EF%BC%8C%E5%87%BD%E6%95%B0%E3%80%81%E4%BA%8B%E4%BB%B6%E3%80%81%E6%A8%A1%E5%9D%97%EF%BC%8C%E7%94%B1%E6%B5%85%E5%85%A5%E6%B7%B1%EF%BC%8C%E6%9C%80%E7%BB%88%E5%88%B0%E4%BD%BF%E7%94%A8,web%20%E6%A1%86%E6%9E%B6%EF%BC%8C%E8%AE%A9%E4%BD%A0%E7%86%9F%E7%BB%83%E6%8E%8C%E6%8F%A1%20Node.js%20%E7%9A%84%E5%9F%BA%E6%9C%AC%E7%BC%96%E7%A8%8B%E3%80%82%202.Node.js%E4%B8%8A%E4%BC%A0%E6%96%87%E4%BB%B6%E5%AE%9E%E4%BE%8B)

[基本模块](https://www.liaoxuefeng.com/wiki/1022910821149312/1023025732384672)- 廖雪峰的官方网站 (liaoxuefeng.com)

learn by doing

**关键字：**

关键字async和await

**核心概念：**

事件循环：

**对象：**

唯一的全局 **对象** global: global.console,global.process.

process也是Node.js提供的一个对象，它代表当前Node.js进程。通过process对象可以拿到许多有用信息：

api: process.cwd() 查看当前路径

process.chdir('d:')更换工作路径

process.nextTick(function(){})等到下次事件循环执行此次函数

// 程序即将退出时的回调函数:

process.on('exit', function (code) {

console.log('about to exit with code: ' + code);

});

process.argv[2] 入参

[Promise](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Promise) 是一个对象，它代表了一个异步操作的最终完成或者失败，解决了经典的回调嵌套地狱问题。在事件循环完成之后调用，支持链式调用。

const promise = createAudioFileAsync(audioSettings);

promise.then(successCallback, failureCallback);

**内置模块：**

文件系统处理模块fs：

负责读写文件。同时提供了异步和同步的方法。

流模块stream

web http模块http:

从头处理TCP连接，解析HTTP这些工作实际上已经由Node.js自带的http模块完成了。应用程序并不直接和HTTP协议打交道，而是操作http模块提供的request和response对象。

通用加密和哈希算法crypto

常见web框架、自动化构建工具、ORM框架、测试框架：

express-\>koa, webpack, orm2、expresso、unit.js

[koa入门 - 廖雪峰的官方网站 (liaoxuefeng.com)](https://www.liaoxuefeng.com/wiki/1022910821149312/1099752344192192)

javascript由事件驱动执行的单线程模型。


### node.js升级

## 优秀的三维引擎 Three.js

## 问题

1. var 和 let的区别与联系

var可以多次声明，ie11之后才支持let。所以推荐使用let，但如果要支持ie11之前的版本，就需要使用var。

[如何存储你需要的信息 — 变量](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/First_steps/Variables)- 学习 Web 开发 | MDN (mozilla.org)

[https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/let](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/let)

1.
---
title: Improving compatibility using WebRTC adapter.js
slug: Web/API/WebRTC_API/adapter.js
---
{{WebRTCSidebar}}

虽然 WebRTC [规范](http://www.w3.org/TR/webrtc/)已经相对健全稳固了，但是并不是所有的浏览器都实现了它所有的功能。除此之外。有些浏览器需要在一些或者所有的 WebRTC API 上添加前缀才能正常使用。尽管你可以自己写代码解决这种问题，但是还有一个比较简单的方法。WebRTC 组织在 github 上提供了一个 [WebRTC 适配器](https://github.com/webrtc/adapter/)（WebRTC adapter）来解决在不同浏览器上实现 WebRTC 的兼容性问题。这个适配器是一个 JavaScript 垫片，它可以让你根据 WebRTC 规范描述的那样去写代码，在所有支持 WebRTC 的浏览器中不用去写前缀或者其他兼容性解决方法。

> **备注：** 由于 WebRTC 和支持的浏览器中的 API 的功能和命名在不断变动，推荐使用这个适配器。

这个 adapter（适配器）是基于 BSD 开源协议的。

## adapter.js 是干什么的

对于每个支持 WebRTC 的浏览器的各个版本，adapter.js 添加必要的 polyfills（填充），使用没有前缀的 API，以及使用一些修改让浏览器可以运行根据 WebRTC 规范写的代码。

举个例子，在火狐浏览器版本号 38 之前，adapter 增加了{{domxref("RTCPeerConnection.urls")}}属性；火狐浏览器并不原生的支持这个属性直到 38 版本，然而在谷歌浏览器中如果 API 不支持{{jsxref("Promise")}} 就添加支持。这只是一些例子；当然还有其他措施来实现这种统一 API。

WebRTC adapter 现在支持火狐、谷歌、和 Edge 浏览器

## 使用 adapter.js

要使用 adapter.js，你需要在使用 WebRTC APIs 的每个页面都引入 adapter.js ：

1. 从 GitHub 上下载一个最新[adapter.js](https://github.com/webrtc/adapter/tree/master/release)的副本。
2. 在你的网站文件目录里添加这个文件（比如在放在 scripts 目录下）。
3. 在你的项目里包含这个文件：\<script src="adapter.js">\</script>
4. 写代码，按照 WebRTC APIs 规范去写，知道你的代码应该在所有浏览器上工作。
5. 注意，即使有一个像这样优秀的 adapter 并不意味着你不需要在不同的浏览器上测试代码（以及在同一个浏览器中的不同版本）。

## 相关链接

- [The WebRTC adapter project on GitHub](https://github.com/webrtc/adapter)
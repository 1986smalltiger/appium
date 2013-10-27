# Appium

> Appium is an open source, cross-platform test automation tool for native, hybrid and mobile web apps.
Appium是一个支持原生,混合和移动web apps的开源的跨平台测试框架工具

[![NPM version](https://badge.fury.io/js/appium.png)](https://npmjs.org/package/appium)
[![Build Status](https://api.travis-ci.org/appium/appium.png?branch=master)](https://travis-ci.org/appium/appium)

## Supported Platforms
## 支持平台

* iOS
* Android
* FirefoxOS

## 为什么选择appium ?

1. You don't have to recompile your app or modify it in any way, due
   to use of standard automation APIs on all platforms.
1. 你不需要以任何方式重新编译或者修改你的app,就可以在所有的平台上使用标准的自动化APIs

2. 你可以用你喜欢的开发工具使用任何 [WebDriver](https://code.google.com/p/selenium/wiki/JsonWireProtocol) 兼容的语言来编写测试用例.比如
Java, [Objective-C](https://github.com/appium/selenium-objective-c),
   JavaScript with Node.js (in both [callback](https://github.com/admc/wd) and [yield-based](https://github.com/jlipps/yiewd) flavours),
   PHP, Python, [Ruby](https://github.com/appium/ruby_lib), C#, Clojure, 或者 Perl 
   可以使用标准的Selenium WebDriver API和特定语言的客户端库.
   
3. 你可以使用任何测试框架.

依托  [WebDriver](https://code.google.com/p/selenium/wiki/JsonWireProtocol) 意味着你可以押宝在一个已经成为事实上标准的独立,自由和开放的协议.而不会被限制在任何的专利中


如果在没有使用Appium的情况,你使用了Apple的UIAutomation库就只能通过Javascript,并且只能通过Instruments application插桩应用来运行你的测试.
同样的,在Google的UiAutomator体系下,你只能用Java写你的测试案例.
Appium最终开启了跨平台原生移动自动化的可能.

## 依赖

Your environment needs to be setup for the particular mobile platforms that you
want to run tests on. See below for particular platform requirements.
你的环境需要配置好运行测试相关的特定移动平台,下面列出相关的依赖平台

If you want to run Appium via an `npm install`, hack with or contribute to Appium, you will need
[node.js and npm](http://nodejs.org) 0.8 or greater (`brew install node`).
如果你想通过`npm install`来运行appium, 为Appium研究和贡献力量.你需要[node.js and npm](http://nodejs.org) 0.8 或者更高版本 (`brew install node`).

### IOS依赖

* Mac OS X 10.7 or higher, 10.8.4 recommended
* XCode &gt;= 4.6.3
* Apple Developer Tools (iPhone simulator SDK, command line tools)
* [Ensure you read our documentation on setting yourself up for iOS testing!](https://github.com/appium/appium/blob/master/docs/running-on-osx.md#ios)

### android依赖

* [Android SDK](http://developer.android.com) API &gt;= 17 (Additional features require 18)
* Appium支持OS X上的Android, Linux和Windows上的beta支持.确保你通过如下的指示来配置你需要运行测试的不同系统的环境
  * [linux](https://github.com/appium/appium/blob/master/docs/running-on-linux.md) 
  * [osx](https://github.com/appium/appium/blob/master/docs/running-on-osx.md#android)
  * [windows](https://github.com/appium/appium/blob/master/docs/running-on-windows.md)

### FirefoxOS Requirements

* [Firefox OS Simulator](https://developer.mozilla.org/en/docs/Tools/Firefox_OS_Simulator)

## 快速开始
启动Appium server,并运行用你喜欢的 [WebDriver](https://code.google.com/p/selenium/wiki/JsonWireProtocol) 兼容的语言编写的测试用例.
你可以用node.js或者下面的应用程序来运行Appium

### 使用Node.js

    $ npm install -g appium
    $ appium &

### 使用app

* [下载 Appium app](https://github.com/appium/appium/releases)
* 运行它! 

## Writing Tests for Appium
## 为Appium编写测试

我们支持 [Selenium WebDriver JSON Wire Protocol](https://github.com/appium/appium/wiki/JSON-Wire-Protocol:-Supported-Methods) 的一个子集
首先还需要指定特定移动平台相关的 [desired capabilities](https://github.com/appium/appium/blob/master/docs/caps.md) 来通过appium运行你的测试


You find elements by using a subset of [WebDriver](https://code.google.com/p/selenium/wiki/JsonWireProtocol)'s element-finding strategies.
See [finding elements](https://github.com/appium/appium/blob/master/docs/finding-elements.md) for detailed information.
你可以通过 [WebDriver](https://code.google.com/p/selenium/wiki/JsonWireProtocol) 的元素定位策略的一个子集来定位元素
更多信息请参考 [finding elements](https://github.com/appium/appium/blob/master/docs/finding-elements.md) 


We also have several extensions to the JSON Wire Protocol for [automating
mobile gestures](https://github.com/appium/appium/blob/master/docs/gestures.md)
like tap, flick, and swipe.
我们也对 JSON Wire Protocol for [automating mobile gestures](https://github.com/appium/appium/blob/master/docs/gestures.md) 做了一些扩展以支持像 tap, flick, 和 swipe 这样的动作(松开,按压,滑动)

You can also automate web views in hybrid apps! See the [hybrid app
guide](https://github.com/appium/appium/blob/master/docs/hybrid.md)
你也可以在混合模式下自动化你的用HTML5构建的Web页面 [hybrid app
guide](https://github.com/appium/appium/blob/master/docs/hybrid.md)

This repository contains [many examples of tests in a variety of different languages](https://github.com/appium/appium/tree/master/sample-code/examples/node)!
这个代码地址包含了 [很多不同语言的测试例子](https://github.com/appium/appium/tree/master/sample-code/examples/node)!



For the full list of Appium doc pages, visit [this directory](https://github.com/appium/appium/blob/master/docs/).
想了解全部的Appium的文档页面,请访问 [这个目录](https://github.com/appium/appium/blob/master/docs/).

## How It Works
## 工作原理

Appium drives various native automation frameworks and provides an API based on
Selenium's [WebDriver JSON wire protocol](https://code.google.com/p/selenium/wiki/JsonWireProtocol).
Appium通过多种原生自动化框架来提供基于Selenium的 [WebDriver JSON wire protocol](https://code.google.com/p/selenium/wiki/JsonWireProtocol) api

Appium drives Apple's UIAutomation library for iOS support, which is based on 
[Dan Cuellar's](http://github.com/penguinho) work on iOS Auto.
Appium驱动Apple的UIAutomation库提供IOS支持. UIAutomation基于[Dan Cuellar's](http://github.com/penguinho)

Android support uses the UiAutomator framework for newer platforms and
[Selendroid](http://github.com/DominikDary/selendroid) for older Android platforms.
Android支持上, 在新版本的Android使用了Uiautomator框架,老版本的android上使用了
[Selendroid](http://github.com/DominikDary/selendroid) 

FirefoxOS support leverages [Marionette](https://developer.mozilla.org/en-US/docs/Marionette),
an automation driver that is compatible with WebDriver and is used to automate
Gecko-based platforms.
FirefoxOS也支持,不过暂不翻译了.因为暂时用不到


## Contributing
## 如何贡献
Please take a look at our [contribution documentation](https://github.com/appium/appium/blob/master/CONTRIBUTING.md)
for instructions on how to build, test and run Appium from source.
可以看下我们的文档  [contribution documentation](https://github.com/appium/appium/blob/master/CONTRIBUTING.md) 
以了解如何从源代码中进行编译,测试和运行


## Project Credits & Inspiration

[Credits](https://github.com/appium/appium/blob/master/docs/credits.md)

## Mailing List
## 邮件列表

声明和公告经常放到讨论组 [Discussion Group](https://groups.google.com/d/forum/appium-discuss), 需要注册

## Troubleshooting
## 问题定位

我们增加了一个 [问题定位指南](https://github.com/appium/appium/blob/master/docs/troubleshooting.md).
Please have a look here first if you run into any problems. It contains instructions for checking a lot
of common errors and how to get in touch with the community if you're stumped.
如果你遇到一些问题,请看下这个问的那个.它包含了一些常见的错误说明,以及在无法解决的情况如何和社区联系

## Using Robots
## 使用Robots

Using Appium with [Tapster](https://github.com/hugs/tapsterbot) and other robots is possible, 
check out the [Appium Robots](https://github.com/appium/robots) project!
可以使用appium的一些robots扩展.或者其他的robots.想了解更多可以看看 [Appium Robots](https://github.com/appium/robots)

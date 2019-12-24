suloki的官方网站是 http://www.suloki.com/
suloki的头条文章是 https://www.toutiao.com/a6751207017316090372/
版本：1.9.0.1
suloki URC软件是完全依据上述资料文章的URC软件架构理论建立的软件，软件功能如下：
1，支持分布式架构：URC框架软件可以配置为URC服务和业务服务2种角色，从而构成以客户端-业务服务-URC服务的三层分布式系统架构；
2，支持插件式开发：开发人员只要用dll/so库的形式完成业务功能的开发，URC框架软件会完成自动加载，大大降低代码量和开发难度；
3，框架内置线程池：插件dll/so库不需要创建线程，一般不需要考虑异步，开发人员更多的是关注业务实现；
4，框架内置通讯机制：URC框架软件内部实现了业务服务-URC服务，业务服务-业务服务之间的通讯机制；
5，支持的URC资源：URC框架软件目前支持本地对象资源，本地和远程nosql资源，远程sql查询（这个将来会资源化）；
6，使用proto buffer作为序列化协议：URC框架软件使用proto buffer作为序列化协议，比xml和json效率高，比自定义数据结构的通用性和灵活信号要好；
7，统一插件模块接口：URC框架软件对插件模块接口进行了统一的定义，有利于开发和测试；
8，框架支持丰富的组件：URC框架软件包含了配置，日志，单键，无锁队列，id管理器，线程池，双分派，应用状态机等内部组件，帮助开发者；
9，跨平台：URC框架软件目前支持windows和linux；
10，依赖较少：URC框架软件完全用c++实现，主要依赖boost，loki和protobuf，mysql connector和websocketpp并不是必须的。
	URC软件未来规划功能如下：
1，增加消息队列资源；
2，sql数据资源化；
3，增加资源订阅；
4，资源变化推送；
5，服务高可用；
6，资源高可用；
7，服务自动部署升级；
8，日志分析；
9，基于URC的视频系统；
...

目录：
depend：依赖的开源软件
lib：suloki基础库和机出框架；
lib/suloki_interface.h：suloki的接口文件；
prj：基于lib的项目；
prj/suloki_framework：suloki软件框架项目；
prj/suloki_urc：suloki urc软件项目；
prj/suloki_urc/testclient：客户端
prj/suloki_urc/testserverdll：服务插件例子；
prj/suloki_urc/testserverdll/testmainmodule：服务插件源码；
prj/suloki_urc/urcserver：urc服务例子；
prj/suloki_urc/urcserver/urchandler：urc服务源码；
proto：proto buffer定义。

windows下例子的执行：
先安装vs2013_vcredist_x64；
启动prj/suloki_urc/urcserver/suloki_framework，config将suloki_framework配置成一个urc服务；
启动prj/suloki_urc/testserverdll/suloki_framework，config将suloki_framework配置成一个业务服务；
用谷歌浏览器打开prj/suloki_urc/testclient/test.html，点击网页按钮，网页经通过web socket协议与业务服务交互；
从而构成客户端-业务服务-URC服务的三层体系。

# Netty 项目


Netty 是一个**异步事件驱动型网络应用框架**，用于快速开发可维护、高性能的协议服务端与客户端。

## 相关链接
* [官方网站](https://netty.io/)
* [下载页面](https://netty.io/downloads.html)
* [技术文档](https://netty.io/wiki/)
* [Twitter @netty_project](https://twitter.com/netty_project)
* [官方 Discord 社区](https://discord.gg/q4aQ2XjaCa)

## 构建方式
有关构建与开发 Netty 的详细信息，请查阅[开发者指南](https://netty.io/wiki/developer-guide.html)。本页面仅提供基础说明。

构建 Netty 需要如下环境：
* 最新稳定版 [OpenJDK 8](https://adoptium.net/)
* 最新稳定版 [Apache Maven](https://maven.apache.org/)
* 如果你使用 Linux 或 MacOS 系统，需要安装[额外开发依赖包](https://netty.io/wiki/native-transports.html)，用于编译本地原生传输库。

> 注意：以上是**编译阶段**的环境要求。运行基于 Netty 的应用，Netty3.x 仅需要 JDK5；Netty4.0+/4.1+ 仅需要 JDK6。

## 分支说明
各个版本的开发代码存放于对应命名的分支，分支命名格式为 `<主版本号>.<次版本号>`。
例如：3.9 版本开发代码位于 [`3.9` 分支](https://github.com/netty/netty/tree/3.9)，4.1 版本开发代码位于 [`4.1` 分支](https://github.com/netty/netty/tree/4.1)。

## 在 JDK9 及以上版本中使用
Netty 可以作为一组**自动模块**，用于 JDK9+ 的模块化 Java 应用。
模块名采用反向域名风格，受历史原因影响，模块名来源于子项目名称，而非根包名。模块列表如下：

 * `io.netty.all`
 * `io.netty.buffer`
 * `io.netty.codec`
 * `io.netty.codec.dns`
 * `io.netty.codec.haproxy`
 * `io.netty.codec.http`
 * `io.netty.codec.http2`
 * `io.netty.codec.memcache`
 * `io.netty.codec.redis`
 * `io.netty.codec.smtp`
 * `io.netty.codec.socks`
 * `io.netty.codec.stomp`
 * `io.netty.codec.xml`
 * `io.netty.common`
 * `io.netty.handler`
 * `io.netty.handler.proxy`
 * `io.netty.resolver`
 * `io.netty.resolver.dns`
 * `io.netty.transport`
 * `io.netty.transport.epoll`（省略 native，native 是 Java 保留关键字）
 * `io.netty.transport.kqueue`（省略 native，native 是 Java 保留关键字）
 * `io.netty.transport.unix.common`（省略 native，native 是 Java 保留关键字）
 * `io.netty.transport.rxtx`
 * `io.netty.transport.sctp`
 * `io.netty.transport.udt`

自动模块不支持声明依赖关系，因此你需要在 `module‑info` 文件中手动逐个列出所有用到的 Netty 模块。

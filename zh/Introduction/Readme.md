---
sidebar: auto
---

# 什么是 LLStack ？

LLStack 全称是 “Linux LiteSpeed Stack”，即在 Linux 上安装 LiteSpeed + PHP + MySQL/MariaDB（可选）的高性能 Web 运行环境，特别适合运行 PHP 程序。

# LiteSpeed 介绍

LiteSpeed 即 LiteSpeed Web Server（简称 LSWS），是一款企业级商用 Web 服务软件，可以完美的 Apache HTTPD 兼容体验，.htaccess 规则可以直接兼容而不像 Nginx 需要重写，并兼容常用的mod扩展。得益于基于事件的架构优势，静态内容比Apache Httpd 快 5 倍 ，动态内容更是快 40 倍，HTTPS 访问快 3 倍并可以应用硬件加速器。

同时作为商业 Web 服务软件，也率先研究并落地最新的 Web 技术，在 HTTP/2 和 HTTP/3（QUIC） 上均是第一个应用的 Web 服务软件，可以直接无缝使用 Brotli、LSCahe 等新特性而无需像 Nginx 一样需要额外配置非官方的扩展并担心 API 兼容性问题。

## LiteSpeed 特性

### 更高性能

LiteSpeed Web Server使用事件驱动的体系结构，Apache是基于流程的。LiteSpeed Web Server及其事件驱动架构，可为几乎没有进程的所有连接提供服务，从而节省资源。

### 更加安全

同时 LiteSpeed 也支持 mod_Security，可以轻松实现基础的 WAF 能力，在没有极高的防御需求的时候仅使用 LiteSpeed 则无需额外购买高昂的商业WAF。 同时针对一些 CC 和 DDOS 攻击，LiteSpeed 也有做好优化和应对策略，可以降低攻击造成的影响。

### 开箱即用

相比 Nginx、Apache 安装一些高性能扩展，如 PageSpeed，Brotli，或者和 Varnish 这样的内存级 Web 加速软件，一些协议的支持上如TLS 1.3、QUIC，搭配都需要一定的经验以及复杂的配置，而这些特性在 LiteSpeed 上都是开箱即用的。

### 可视化后台

不同于 Nginx、Apache HTTPD 黑底白字的配置文件，LiteSpeed 即可以通过编辑配置文件操作也可以通过可视化控制台进行操作，降低操作门槛。

### Apache 兼容

不仅仅是兼容 Apache HTTPD 的特性和扩展，LiteSpeed 可以直接读取 Apache HTTPD 配置文件并转化，并且在不停机条件下直接从 Apache HTTPD 上完成无缝迁移。

**更多特性和 LiteSpeed 介绍请看：**  [LiteSpeed 介绍页](/zh/LiteSpeed/)

## 关于免费策略

**重要**

LiteSpeed Web Server 作为一款商业 Web 服务软件，其实是收费的，也正是因为商业化才可以做到那么高性能和高效的软件升级和维护。

不同于早前 LiteSpeed 限制最高400并发的免费策略，目前 LiteSpeed 的策略是：


::: danger 策略
LSWS 本身最大占用 1核心 CPU，服务器物理内存最大不超过 2G。   即可使用免费许可证。
:::

所以推荐的配置是： 1核心2G内存的云服务器。 

### 那么低的配置可以运行网站吗？

完全可以，绝大部分网站2G内存完全可以使用，优化得当的情况下日 1W PV 的 WordPress 完全不是问题。

许可证只是限制 LSWS 本身安装的服务器在不超过2G内存的服务器上。 对于一些流量较高的网站建议仅将 LiteSpeed Web Server 和 PHP 运行在本地服务器上。 MySQL、Redis 等软件完全可以放在同内网的其他服务器上。相关静态文件则可以托管在CDN或者对象存储上降低负载压力。

# 为什么需要 LLStack?

手动编译安装需要输入大量命令，且有可能会中途出错，往往会导致环境搭建两三天，结果写网站的热度却早已被磨光了。
同时对于新手来说，想要成功搭建建站环境特别是一个快速、安全的网站，颇费周折，需要大量的学习成本。

# LLStack 的优点

1. 完美支持 RHEL 系操作系统，如 RHEL、CentOS、CloudLinux、OracleLinux、AmazonLinux、AliLinux、Euler 等操作系统。
2. 均采用成熟的RPM包安装，而非自编译，安装更快速且升级更便捷
3. 支持多PHP版本，PHP 5.4~7.3，也可以通过编译方式安装 PHP4.4，5.2，5.3
4. 教程丰富，LLStack 将会不断丰富最佳实践
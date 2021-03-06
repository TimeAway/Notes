### LNMP 与 LAMP

两者均是一套完整的网站服务系统，唯一的区别就是 Web 服务器不同。

#### 1. LAMP

LAMP 全称是 Linux + Apache + MySQL + PHP。

LAMP 使用的是 Apache 作为 Web 服务器，Apache是世界是用排名第一的Web服务器软件，其几乎可以在所有
广泛使用的计算机平台上运营，由于其跨平台和安全性被广泛使用，是最流行的Web服务端软件之一。

**Apache 的特点**

- Apache 是 LAMP 架构最核心的 Web Server，开源、稳定、模块丰富是 Apache 的优势。但 Apache 的缺点是有些臃肿，内存和 CPU 开销大，性能上有损耗，不如一些轻量级的 Web 服务器（譬如：Nginx、Tengine等）高效，轻量级的 Web 服务器对于静态文件的响应能力来说远高于 Apache 服务器。

- Apache 做为 Web Server 是负载 PHP 的最佳选择，如果流量很大的话，可以采用 Nginx 来负载非 PHP 的 Web 请求。Nginx 是一个高性能的 HTTP 和反向代理服务器，Nginx 以其稳定、丰富功能集、示例配置文件和低系统资源的消耗而闻名。Nginx 现能支持 PHP 和 FastCGI，也支持负载均衡和容错，可和 Apache 配合使用，是轻量级的 HTTP 服务器的首选。

- Web 服务器缓存也有多种方案，Apache 提供了自己的缓存模块，也可以使用外加的 Squid 模块进行缓存，这两种方式均可有效提高 Apache 的访问响应能力。Squid Cache 是一个 Web 缓存服务器，支持高效缓存，可作为网页服务器的前置 cache 服务器缓存相关请求以提高 Web 服务器速度。把 Squid 放在 Apache 的前端来缓存 Web 服务器生成动态内容，而 Web 应用程序只需要适当地设置页面实效时间即可。如访问量巨大，则可考虑使用 memcache 作为分布式缓存。

- PHP 的加速可使用 eAccelerator 加速器，eAccelerator 是一个自由开放源码的 PHP 加速器。它会优化动态内容缓存，提高 PHP 脚本缓存性能，使 PHP 脚本在编译状态下，对服务器的开销几乎完全消除。它还可对脚本起优化作用，以加快其执行效率。 使 PHP 程序代码执效率可提高 1-10 倍。

#### 2. LNMP 

全称是 Linux + Nginx + MySQL + PHP （国外喜欢简称为LEMP，搜英文资料需要搜LEMP）。

LNMP 使用的是 Nginx，Nginx是一款高性能额 Http 和反向代理服务器，也是一个 AMAP/POP3/SMTP 服务器。

**Nginx 的特点**

Nginx 性能稳定、功能丰富、运维简单、处理静态文件速度快且消耗系统资源极少。

- 相比 Apache，用 Nginx 作为 Web 服务器：使用资源更少，支持更多并发连接，效率更高。

- 作为负载均衡服务器：Nginx 既可在内部直接支持 Rails 和 PHP，也可支持作为 HTTP 代理服务器对外进行服务。Nginx 用 C 编写而成， 不论是系统资源开销还是 CPU 使用效率都比 Perlbal 要好的多。

- 作为邮件代理服务器：Nginx 同时也是一款非常优秀的邮件代理服务器（最早开发这个产品的目的之一，是作为邮件代理服务器）。

- 反向代理可以根据url将请求转向于不同用途的集群，比如图片请求，转向图片服务器集群；视频请求，转身视频服务器集群。nginx是一款轻量级的web服务器/反向代理服务器/电子邮件代理服务器，安装非常简单，配置文件也很简洁（还支持 perl 语法）。Nginx 支持平滑加载新配置，还能够在不间断服务的情况下进行软件版本升级。


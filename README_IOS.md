# IOS使用指南

### 因为shadowrockt在国区被屏蔽，同时美区需要$3.99，所以选择直接安装

## 安装指南

1. 下载pp助手

2. 搜索shadowrockt

3. 连接手机安装

## 使用指南

有了 Shadowrocket 之后就可以开搞了，以下是 Shadowrocket 的正式教程。

打开 Shadowrocket，下方选项卡有四个标签，这里将分标签讲解 Shadowrocket 的功能。

主页
--

[![](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/10/1834630758.png)](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/10/1834630758.png)

### 未连接

emmmmmm，这个开关应该不用讲吧……  
第一次连接的时候会弹出是否允许创建V*N连接的窗口，允许，然后按个指纹/输个密码即可。

### 全局路由

有4个选项：

*   **配置（推荐）**  
    如果你没有自己改变过配置文件的话，那么这个选项就相当于“绕过局域网及大陆”
*   **代理**  
    即全局代理
*   **直连**  
    直连，不主动代理任何流量。可以用于“自己的手机不想翻*，但是想把代理共享给同一局域网内需要翻*的设备”的情况  
    基本是不会用到的
*   **场景**  
    根据下方 设置-场景 中的设置，在自己设定的情况下连接代理时会无视首页中的“全局路由”和“服务器”设置而使用你事先规定好的设置。

下面“设置”中的两个设置项就不多做介绍了，属于那种“萌新基本用不上，要用的人自然会用”的功能。

### 添加节点

#### 自动添加

*   **点击链接添加**  
    根据你 SSR 商提供的 SSR 链接，在 Safari 中打开时会自动跳转到 Shadowrocket 中进行添加。
*   **扫码添加**  
    如果你的 SSR 商有提供节点配置二维码的话，点击左上角的扫一扫。

#### 手动添加

点击右上角的“+”，进入配置添加界面，点击类型，然后选择“ShadowsocksR”，接着填入 SSR 商提供的节点信息，然后完成即可。

以下是目前（2017-10-12） Shadowrocket 支持的代理协议：

[![](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/10/1439935001.png)](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/10/1439935001.png)

#### 通过订阅添加（推荐）

如果你的 SSR 商有提供SSR订阅链接的话，那是最好的。  
跟手动添加的方法一样，但是类型选择“Subscribe”，然后填入订阅地址，然后完成即可。

### 选择节点

*   点击一个节点，前面出现了一个小橙点即代表你选中了这个节点。
*   点击“选择节点”右侧的“···”可以进入批量删除、排序模式。
*   左滑一个节点，可以进行3种操作：
    
    [![](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/10/1097017550.png)](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/10/1097017550.png)
    
    *   复制  
        复制出一份完全相同的配置供你修改（备注会自动重命名）
    *   二维码  
        展示这个服务器配置的二维码以供分享
    *   删除  
        节点：mmp
*   左滑一个订阅，也有3种操作：
    
    [![](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/10/1199973708.png)](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/10/1199973708.png)
    
    *   更新  
        更新订阅
    *   二维码  
        展示这个订阅的链接的二维码
    *   删除  
        订阅：mmp
*   点击一个配置右侧的“i”，可以编辑这个配置。

！！！进阶警告！！！
----------

以上即为 Shadowrocket 的基础使用说明，下面的是进阶功能使用教程。这部分比较复杂，但是是 Shadowrocket 的强大之处，不想折腾的萌新可以直接跳过，有兴趣的可以看看。

配置
--

[![](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/10/3926746023.png)](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/10/3926746023.png)

前三项没什么好说的。

### 测试规则

用于测试你当前选择的配置文件，输入域名或IP之后回车便会返回这个域名或IP所应用的那条规则，用于测试规则正确性。

### 本地文件

此处列出了本机上所有的配置文件。  
默认会有`default.conf`配置文件，这个规则为 GFWList + 绕过大陆 + 常用广告域名屏蔽 + 绕过国内常见域名。  
点击以后会弹出二级菜单：

[![](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/10/3991188116.png)](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/10/3991188116.png)

下面只讲几个重要的：

*   **编辑配置**  
    下面会详细讲。
*   **编辑纯文本**  
    以纯文本方式编辑配置，萌新不需理会，点进去大概会觉得是天书（。  
    语法较为简单，如果了解各个设置的工作方式（下面详细讲），那么这个纯文本看一看就知道什么是什么了，大概。  
    这个主要是方便大佬们批量修改设置之类的，毕竟可以拿出来用查询替换，甚至自己写个小程序移植其他类似代理工具的配置文件。
*   **导出到云**  
    可以将这个配置保存到 iCloud 上，也就是备份啦。

### 添加配置

可以把大佬们共享出来的配置文件地址放进去，导入到自己的设备里。

配置 \- 本地文件 \- 编辑配置
------------------

Shadowrocket 的强大核心所在。

[![](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/10/155509288.png)](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/10/155509288.png)

### 通用

[![](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/10/3681952278.png)](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/10/3681952278.png)

一个配置的通用设置，一般情况下有可能需要改动的只有

*   **DNS覆写**  
    即你可以自定义 DNS （即时你使用的是移动数据），但是只有你在开启代理的时候才生效。
*   **跳过代理**  
    看官方的说明即可。

### 规则、添加规则

[![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAABS2lUWHRYTUw6Y29tLmFkb2JlLnhtcAAAAAAAPD94cGFja2V0IGJlZ2luPSLvu78iIGlkPSJXNU0wTXBDZWhpSHpyZVN6TlRjemtjOWQiPz4KPHg6eG1wbWV0YSB4bWxuczp4PSJhZG9iZTpuczptZXRhLyIgeDp4bXB0az0iQWRvYmUgWE1QIENvcmUgNS42LWMxMzggNzkuMTU5ODI0LCAyMDE2LzA5LzE0LTAxOjA5OjAxICAgICAgICAiPgogPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4KICA8cmRmOkRlc2NyaXB0aW9uIHJkZjphYm91dD0iIi8+CiA8L3JkZjpSREY+CjwveDp4bXBtZXRhPgo8P3hwYWNrZXQgZW5kPSJyIj8+IEmuOgAAAA1JREFUCJljePfx038ACXMD0ZVlJAYAAAAASUVORK5CYII=)](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/10/910431418.png)

规则可以在上一页中点击“添加规则”来添加，点击后你将会看到以下界面：

[![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAABS2lUWHRYTUw6Y29tLmFkb2JlLnhtcAAAAAAAPD94cGFja2V0IGJlZ2luPSLvu78iIGlkPSJXNU0wTXBDZWhpSHpyZVN6TlRjemtjOWQiPz4KPHg6eG1wbWV0YSB4bWxuczp4PSJhZG9iZTpuczptZXRhLyIgeDp4bXB0az0iQWRvYmUgWE1QIENvcmUgNS42LWMxMzggNzkuMTU5ODI0LCAyMDE2LzA5LzE0LTAxOjA5OjAxICAgICAgICAiPgogPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4KICA8cmRmOkRlc2NyaXB0aW9uIHJkZjphYm91dD0iIi8+CiA8L3JkZjpSREY+CjwveDp4bXBtZXRhPgo8P3hwYWNrZXQgZW5kPSJyIj8+IEmuOgAAAA1JREFUCJljePfx038ACXMD0ZVlJAYAAAAASUVORK5CYII=)](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/10/2330144318.png)

#### 类型

一共有6种类型：

[![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAABS2lUWHRYTUw6Y29tLmFkb2JlLnhtcAAAAAAAPD94cGFja2V0IGJlZ2luPSLvu78iIGlkPSJXNU0wTXBDZWhpSHpyZVN6TlRjemtjOWQiPz4KPHg6eG1wbWV0YSB4bWxuczp4PSJhZG9iZTpuczptZXRhLyIgeDp4bXB0az0iQWRvYmUgWE1QIENvcmUgNS42LWMxMzggNzkuMTU5ODI0LCAyMDE2LzA5LzE0LTAxOjA5OjAxICAgICAgICAiPgogPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4KICA8cmRmOkRlc2NyaXB0aW9uIHJkZjphYm91dD0iIi8+CiA8L3JkZjpSREY+CjwveDp4bXBtZXRhPgo8P3hwYWNrZXQgZW5kPSJyIj8+IEmuOgAAAA1JREFUCJljePfx038ACXMD0ZVlJAYAAAAASUVORK5CYII=)](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/10/3333108037.png)

*   **DOMAIN-SUFFIX**（域名后缀）  
    此时应在下面填入形如`abc.com`的域名后缀，则此规则会对所有以`abc.com`结尾的域名生效，即对`*.abc.com`以及`abc.com`（顶级域名）生效。
*   **DOMAIN-KEYWORD**（域名关键词）  
    此时在下面填入一个关键词，所有包含这个关键词的域名都会应用这个规则。  
    例如，填入`abc`，那么`abc.com`、`abc.net`、`asd.abc.cn`、`123abc456.pw`这样的域名都会应用规则，也就是有`abc`就符合条件。
*   **DOMAIN**（域名）  
    最严格的条件，即必须100%符合你输入的域名才会应用这条规则。  
    例如填入`abc.com`，那么只对`abc.com`生效，其他的多了任何一点字母数字符号的域名都不符合这条规则。
*   **USER-AGENT**（用户代理）  
    用户代理即 UserAgent，简称 UA。  
    一般不会用到，即与你设置的用户代理相同的所有流量都符合这条规则。  
    不知道用户代理是什么的话可以去百度一下。
*   **IP-CIDR**  
    IP-CIDR表示的是某一IP地址或某一网段，格式形如`192.168.1.100/24`，斜杠前为IP地址或子网地址，斜杠后的数字表示的是子网掩码，目的地址符合这一IP-CIDR的流量将会应用此规则。建议具有关于这部分一定的网络知识后再去使用。
*   **GEOIP**（国家/地区）  
    很粗暴的一种规则，填入国家/地区代码（比如中国是`CN`），只要流量目的地址所在地区符合，那么就应用此条规则。
*   **FINAL**（默认规则）  
    FINAL规则只应该存在一条，它的作用是，如果某流量不符合你前面规定的所有规则，那么它将符合这条规则。

#### 选项

选项的内容也很简单：

*   **PROXY**  
    符合这条规则就走代理。
*   **REJECT**  
    符合这条规则就直接屏蔽，常用于屏蔽广告。
*   **DIRECR**  
    符合这条规则就直连，不走代理。
*   **（你的代理节点名称）**  
    符合这条规则就走你所选的代理节点（即使你现在使用的节点并不是这个）。

#### 其他选项

*   **强制远程DNS**  
    这个选项在“类型”为“DOMAIN”那三个时可开启，作用是，如果你开启了，那么符合规则的域名将会强行通过代理服务器进行解析，可以解决一般常见的 DNS 污染问题，甚至是某些网络环境下因上级路由重定向 DNS 而导致的 DNS 污染问题。
*   **不解析域名**  
    仅“IP-CIDR”可开启，开启后，只有直接访问IP地址的时候才会去匹配这条规则，如果是通过域名访问的则不会匹配这条规则。

### Hosts、添加映射

*这个功能在 Shadowrocket 中用应用的实际上并不多（都有代理了还要host干嘛），除非是一些特殊情况。

#### 首先我们需要知道 Hosts 是什么，能做什么

不懂装懂大致解释版：  
简单地说，DNS 能根据域名得到对应的 IP 地址，而如果你事先往 Hosts 里记录了域名以及他们的 IP 地址，那么系统就会优先使用 Hosts 记录充当域名解析结果，而不会再去向 DNS 发出解析请求。

说人话版：  
你可以用这玩意来自定义一个网址域名锁对应的 IP 地址。

因此 Host 也可以被用来解决 DNS 污染问题（如果需求域名不是很多的话……），甚至用来帮助反代一些“不存在的”网站以达到科学上网的效果。

#### 添加映射

实际上就是添加一条 Host，点击添加映射即可。  
界面很简单我也就不放图了，在 域名 中填入你想要指定 IP 的域名，在 IP 地址 中填入你自己指定的 IP 即可。  
例如域名填入`abc.com`，IP 地址填入`123.123.123.123`，那么当你连上代理后访问 abc.com，就会以 abc.com 这个域名访问 123.123.123.123 这个 IP。

#### 编辑 Hosts

过于简单，是个人都会用，不作解释~

### URL 重写

顾名思义，当访问你在其中指定的网址的时候，可以自动改写 URL 地址，以及对这些网址流量做一些奇怪的事情（x

点击“添加 URL 重写”可以添加一条 URL 重写规则。

[![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAABS2lUWHRYTUw6Y29tLmFkb2JlLnhtcAAAAAAAPD94cGFja2V0IGJlZ2luPSLvu78iIGlkPSJXNU0wTXBDZWhpSHpyZVN6TlRjemtjOWQiPz4KPHg6eG1wbWV0YSB4bWxuczp4PSJhZG9iZTpuczptZXRhLyIgeDp4bXB0az0iQWRvYmUgWE1QIENvcmUgNS42LWMxMzggNzkuMTU5ODI0LCAyMDE2LzA5LzE0LTAxOjA5OjAxICAgICAgICAiPgogPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4KICA8cmRmOkRlc2NyaXB0aW9uIHJkZjphYm91dD0iIi8+CiA8L3JkZjpSREY+CjwveDp4bXBtZXRhPgo8P3hwYWNrZXQgZW5kPSJyIj8+IEmuOgAAAA1JREFUCJljePfx038ACXMD0ZVlJAYAAAAASUVORK5CYII=)](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/10/2927078231.png)

#### URL

填写一个 URL 匹配规则，必填，使用正则表达式书写。  
如果你不知道什么是正则表达式，去百度吧，不过这玩意对于非计算机专业 or 非理科生可能会很难理解。

#### TO

符合规则的 URL 将会被重写成这个。

#### 类型

[![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAABS2lUWHRYTUw6Y29tLmFkb2JlLnhtcAAAAAAAPD94cGFja2V0IGJlZ2luPSLvu78iIGlkPSJXNU0wTXBDZWhpSHpyZVN6TlRjemtjOWQiPz4KPHg6eG1wbWV0YSB4bWxuczp4PSJhZG9iZTpuczptZXRhLyIgeDp4bXB0az0iQWRvYmUgWE1QIENvcmUgNS42LWMxMzggNzkuMTU5ODI0LCAyMDE2LzA5LzE0LTAxOjA5OjAxICAgICAgICAiPgogPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4KICA8cmRmOkRlc2NyaXB0aW9uIHJkZjphYm91dD0iIi8+CiA8L3JkZjpSREY+CjwveDp4bXBtZXRhPgo8P3hwYWNrZXQgZW5kPSJyIj8+IEmuOgAAAA1JREFUCJljePfx038ACXMD0ZVlJAYAAAAASUVORK5CYII=)](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/10/2748764958.png)

有五种类型：

*   **header**  
    直接重写。
*   **302**  
    使用 302 重定向来重写。  
    如果不知道什么是302请百度“302重定向”。
*   **reject**（拒绝）
*   **proxy**（代理）
*   **direct**（直连）

后面三个选项存在的意义也许是可以让你用正则表达式规则来指定哪些 URL 走代理/直连/阻止 吧，会比规则使用起来灵活一些？我也没有用实际用过（懒人一个）所以不太清楚，你们就当前面这句是我在瞎bb……感觉这三个根本就不在 URL 重写的范畴内……

### HTTPS 解密

[![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAABS2lUWHRYTUw6Y29tLmFkb2JlLnhtcAAAAAAAPD94cGFja2V0IGJlZ2luPSLvu78iIGlkPSJXNU0wTXBDZWhpSHpyZVN6TlRjemtjOWQiPz4KPHg6eG1wbWV0YSB4bWxuczp4PSJhZG9iZTpuczptZXRhLyIgeDp4bXB0az0iQWRvYmUgWE1QIENvcmUgNS42LWMxMzggNzkuMTU5ODI0LCAyMDE2LzA5LzE0LTAxOjA5OjAxICAgICAgICAiPgogPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4KICA8cmRmOkRlc2NyaXB0aW9uIHJkZjphYm91dD0iIi8+CiA8L3JkZjpSREY+CjwveDp4bXBtZXRhPgo8P3hwYWNrZXQgZW5kPSJyIj8+IEmuOgAAAA1JREFUCJljePfx038ACXMD0ZVlJAYAAAAASUVORK5CYII=)](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/10/944007468.png)

这个功能可以说是一个十分劲爆的功能了（我最早开始用 Shadowrocket 的时候还没有这个功能），Shadowrocket 会使用中间人攻击的方式来解密你所指定的域名的 HTTPS 流量。  
这个功能应该是用在代理日志抓 HTTPS 包上的。  
如果你改动了这个设置，就需要生成一个新的 CA 证书并在系统设置中信用它，Shadowrocket 会提示你如何操作，照做就行。

### 复制

复制一份一模一样的配置并自动重命名。

### 测试规则

与上一级菜单中的测试规则一致。

数据
--

这里的功能都是辅助性的功能。  
只讲一些重点功能。

[![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAABS2lUWHRYTUw6Y29tLmFkb2JlLnhtcAAAAAAAPD94cGFja2V0IGJlZ2luPSLvu78iIGlkPSJXNU0wTXBDZWhpSHpyZVN6TlRjemtjOWQiPz4KPHg6eG1wbWV0YSB4bWxuczp4PSJhZG9iZTpuczptZXRhLyIgeDp4bXB0az0iQWRvYmUgWE1QIENvcmUgNS42LWMxMzggNzkuMTU5ODI0LCAyMDE2LzA5LzE0LTAxOjA5OjAxICAgICAgICAiPgogPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4KICA8cmRmOkRlc2NyaXB0aW9uIHJkZjphYm91dD0iIi8+CiA8L3JkZjpSREY+CjwveDp4bXBtZXRhPgo8P3hwYWNrZXQgZW5kPSJyIj8+IEmuOgAAAA1JREFUCJljePfx038ACXMD0ZVlJAYAAAAASUVORK5CYII=)](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/10/3862688940.png)

### 统计

就是单纯的用量统计，你要开着代理的时候看这里才会有统计，关掉之后会立即清空。

开启“启用存档”后，每次使用代理的用量记录都会被存到下面的“归档”中。

### 代理（日志）

这是一个好用的功能，可以用来当个临时的轻量级抓包工具。

开启“启用日志记录”后就会自动记录你每次请求的 **URL** 和**端口**，以及产生请求的 **APP**（即UA）和应用的**规则**，可以按 全部/代理/直连/拒绝 分类查看，并可以一键根据这些记录快速创建规则（进入一条记录的详情界面后点击右上角的“···”）。  
详细用法亲自一试便知。

[![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAABS2lUWHRYTUw6Y29tLmFkb2JlLnhtcAAAAAAAPD94cGFja2V0IGJlZ2luPSLvu78iIGlkPSJXNU0wTXBDZWhpSHpyZVN6TlRjemtjOWQiPz4KPHg6eG1wbWV0YSB4bWxuczp4PSJhZG9iZTpuczptZXRhLyIgeDp4bXB0az0iQWRvYmUgWE1QIENvcmUgNS42LWMxMzggNzkuMTU5ODI0LCAyMDE2LzA5LzE0LTAxOjA5OjAxICAgICAgICAiPgogPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4KICA8cmRmOkRlc2NyaXB0aW9uIHJkZjphYm91dD0iIi8+CiA8L3JkZjpSREY+CjwveDp4bXBtZXRhPgo8P3hwYWNrZXQgZW5kPSJyIj8+IEmuOgAAAA1JREFUCJljePfx038ACXMD0ZVlJAYAAAAASUVORK5CYII=)](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/10/3553774512.png)

[![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAABS2lUWHRYTUw6Y29tLmFkb2JlLnhtcAAAAAAAPD94cGFja2V0IGJlZ2luPSLvu78iIGlkPSJXNU0wTXBDZWhpSHpyZVN6TlRjemtjOWQiPz4KPHg6eG1wbWV0YSB4bWxuczp4PSJhZG9iZTpuczptZXRhLyIgeDp4bXB0az0iQWRvYmUgWE1QIENvcmUgNS42LWMxMzggNzkuMTU5ODI0LCAyMDE2LzA5LzE0LTAxOjA5OjAxICAgICAgICAiPgogPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4KICA8cmRmOkRlc2NyaXB0aW9uIHJkZjphYm91dD0iIi8+CiA8L3JkZjpSREY+CjwveDp4bXBtZXRhPgo8P3hwYWNrZXQgZW5kPSJyIj8+IEmuOgAAAA1JREFUCJljePfx038ACXMD0ZVlJAYAAAAASUVORK5CYII=)](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/10/3742299815.png)

### DNS（日志）

和代理日志很相似，只不过是记录了你的 DNS 请求以及解析结果。

可以用这个来分析是否遭到了 DNS 污染之类的。

[![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAABS2lUWHRYTUw6Y29tLmFkb2JlLnhtcAAAAAAAPD94cGFja2V0IGJlZ2luPSLvu78iIGlkPSJXNU0wTXBDZWhpSHpyZVN6TlRjemtjOWQiPz4KPHg6eG1wbWV0YSB4bWxuczp4PSJhZG9iZTpuczptZXRhLyIgeDp4bXB0az0iQWRvYmUgWE1QIENvcmUgNS42LWMxMzggNzkuMTU5ODI0LCAyMDE2LzA5LzE0LTAxOjA5OjAxICAgICAgICAiPgogPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4KICA8cmRmOkRlc2NyaXB0aW9uIHJkZjphYm91dD0iIi8+CiA8L3JkZjpSREY+CjwveDp4bXBtZXRhPgo8P3hwYWNrZXQgZW5kPSJyIj8+IEmuOgAAAA1JREFUCJljePfx038ACXMD0ZVlJAYAAAAASUVORK5CYII=)](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/10/1770591242.png)

设置
--

[![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAABS2lUWHRYTUw6Y29tLmFkb2JlLnhtcAAAAAAAPD94cGFja2V0IGJlZ2luPSLvu78iIGlkPSJXNU0wTXBDZWhpSHpyZVN6TlRjemtjOWQiPz4KPHg6eG1wbWV0YSB4bWxuczp4PSJhZG9iZTpuczptZXRhLyIgeDp4bXB0az0iQWRvYmUgWE1QIENvcmUgNS42LWMxMzggNzkuMTU5ODI0LCAyMDE2LzA5LzE0LTAxOjA5OjAxICAgICAgICAiPgogPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4KICA8cmRmOkRlc2NyaXB0aW9uIHJkZjphYm91dD0iIi8+CiA8L3JkZjpSREY+CjwveDp4bXBtZXRhPgo8P3hwYWNrZXQgZW5kPSJyIj8+IEmuOgAAAA1JREFUCJljePfx038ACXMD0ZVlJAYAAAAASUVORK5CYII=)](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/10/601402849.png)

### 证书

管理你在使用 Shadowrocket 时生成的 CA 证书（例如使用了 HTTPS 解密），或者手动生成新证书。

### 延迟测试方法

更改测试延迟的请求方法，默认是使用 TCP 方式。

其不同于 ICMP 方式的一点是，被ping的目标 TCP 端口必须处于正在监听的状态，这也是为什么有时候 ICMP 正常而 TCP 超时的原因，这时候你就要想想：你机场套餐是不是过期了？

另外由于GFW新使用了只阻断 TCP 的方式来墙，也可能导致这种情况。

### Today 部件

调整 Weight 部件的参数。

### 按需求连接

一个比较赞的功能，但是我并不喜欢用它，可能是我的可控欲比较强的缘故。

简单的来说，比如按需求连接设置中有域名`*.google.com`，那么当你在未连接代理的情况下去访问`www.google.com`，那么 Shadowrocket 就会自动的帮你连上代理。

还有其他的设置功能，比如设置只有在使用 4G 的情况下才触发这个功能、锁屏不断代理之类的，具体请自行查看。

### 代理

#### 代理共享

可以把你当前连接的代理在局域网中分享出去，比如你的手机和你的其他设备都连在同一个 WIFI 上，那么你就可以在其他设备在没有代理配置的情况下使用你手机上现有的代理。

可以自定义端口以及设置 IP 白名单。

我没有亲自试过这个功能所以不清楚这个代理是 SOCKS5 还是 HTTP 之类的，不过有提供二维码，拿另一台设备上的 Shadowrocket 扫一扫应该就清楚了。

#### 前置代理

不多讲了，跟 Windows 客户端的[前置代理](#选项设置)是一样的。

### DNS

就是自定义 Hosts，不过不是太清楚什么条件下才生效……我尝试过写 Hosts 进去但是明没有在代理的时候生效，也可能是因为我当时访问的域名都是在规则中强制使用远程 DNS 解析的？……  
或者可能我的用法错了……

### TCP

此处可以设置 TCP 最大连接数，默认为 16，如果你没有特殊需求就不要改动这个设置。

这个设置的作用是当你的 TCP 连接数多于设定值时，所有不活动的 TCP 连接将立即被关闭，以减轻代理服务器的负担。

如果这个值设置的过高，就无法关闭冗余的 TCP 连接，会对代理服务器造成一定负担并造成端口资源的浪费。

### UDP

开启 UDP 转发后，SS 和 SSR 代理将可以转发 UDP 流量，以代理 UDP 连接。

比如 BangDream 的多人联机通信使用的就是 UDP。

UDP 转发需要 SS/SSR 服务器服务端的支持，SS 服务端好像是由服务端配置来决定是否允许 UDP 转发的，而 SSR 服务端是默认允许的。如果你使用的是 SS，那么在使用这个功能前最好询问一下你的 SS 提供商，看看服务端是否允许 UDP 转发。

### 服务器订阅

这个设置仅用于 SS/SSR 服务器订阅，可以设置每次开启 Shadowrocket 时是否自动更新订阅等。

### 用户代理

用户代理即 UserAgent，简称 UA。

这个设置可以控制经过代理的请求是否需要隐藏 UA 以保护隐私，默认开启。

常见问题
----

### 连上了代理但是无法上谷歌、推特等

如果你确定你的代理是可用的，那么开关一次飞行模式即可解决99%的这类问题。

这是 DNS 污染所致，想更详细的了解有关于 DNS 污染的知识请看：[DNS污染是什么](/technology/hosts-for-steam-fgo.html#DNS污染是什么 "DNS污染是什么")
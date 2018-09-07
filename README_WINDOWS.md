**Windows**

### 基础设置
1. 打开ssr-windows
2. 将二维码文件打开
2. 右键点击右下角的小飞机图标
3. 点击“二维码扫描”
4. enjoy the world






功能、设置说明（一般不需要！！！！！！）
-------

右击小飞机，你能看到 SSR 所有的功能选项，以下是各项功能及设置的介绍。

### 系统代理模式

系统代理模式有四种模式可以选择：

*   **直连模式**  
    会关闭系统HTTP代理，你的所有HTTP上网流量都不会通过 SSR 代理，在此模式下你只能使用Socks5代理方式连接 SSR 代理（详见后续的[进阶使用](#Windows-进阶使用)）。
*   **PAC模式**  
    会修改系统IE代理，使用PAC文件控制代理。PAC文件包含了规则列表，可以控制哪些流量走 SSR，哪些不走（例如国内流量直连，国外走代理），做到智能代理。**但是实际上此功能已经可以被“[代理规则](#代理规则)”设置完全代替（除非你一定要用gfwlist），因此一般不用这一模式。**  
    PAC文件为 SSR 根目录下的`pac.txt`。
*   **全局模式**  
    会开启系统HTTP代理，你的所有HTTP上网流量将会通过 SSR 代理。  
    注意：仅能代理HTTP流量，即浏览网页的流量——例如浏览器浏览网页，或者某些应用程序的应用内网页（比如QQ的群文件、群公告这些就是），或者某些比较奇葩的使用HTTP方式进行通信的程序（比如Steam版的影之诗）。  
    **如果要代理应用程序，请详见[Windows -SSTap](#Windows-SSTap)教程。**
*   **保持当前状态不修改**  
    顾名思义，不会对你目前的系统HTTP代理状态进行任何的修改。

当你退出 SSR 后，系统HTTP代理会自动被恢复至原有状态；开启 SSR 后，同样的，系统HTTP代理会被设置成你所设定的系统代理模式状态。

### PAC

此菜单中的选项均为对 SSR 的PAC文件进行操作的选项，如果你不使用“PAC模式”代理，那么这一节你可以直接跳过。

不过实际上也没什么好讲的，每个选项会执行什么操作、有什么效果，都在菜单中写的清清楚楚。

[![PAC文件操作选项](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/09/4010641286.jpg)](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/09/4010641286.jpg)

### 代理规则

代理规则指的是，对于所有通过系统HTTP代理或者SOCKS5代理被发送至 SSR 的流量，按照你设置的规则进行代理，即智能代理。

实际上这个设置项也没有什么可以说明的内容，每个选项也写的很清楚。这里稍微解释下某些名词及选项：

*   **绕过xxx**  
    顾名思义，绕过就是不走代理，例如选择项中的“绕过局域网“就是当你浏览局域网网页的时候不会走 SSR 代理（最常见的例如学校、公司的内部网网页），”绕过大陆“就是所有国内大陆的流量都不会通过 SSR 代理。
*   **绕过非大陆**  
    带有这个的一项实际上是给从国外翻回来的人用的，我们这些翻出去的并用不到。
*   **用户自定义**  
    萌新可以直接无视这一项。自定义文件为 SSR 根目录下的`user-rule.txt`，你可以在这一文件中自己定义代理规则，格式详见：[https://adblockplus.org/en/filter-cheatsheet](https://adblockplus.org/en/filter-cheatsheet)
*   **全局**  
    顾名思义，所有被发送至 SSR 的流量都会走代理。

日常使用我推荐使用“绕过局域网和大陆”的选项

### 服务器

在这里你可以切换你已有的服务器配置，在你第一次使用的时候别忘了先切换至你自己添加的服务器配置。

*   **编辑服务器**  
    直接双击小飞机也可以打开编辑窗口。
*   **从文件导入服务器**  
    可以导入 SSR 服务商提供的服务器配置文件。
*   **服务器连接统计**  
    直接鼠标中键单机小飞机也可以打开这一窗口，会显示你目前 SSR 的所有服务器的统计信息。  
    
    [![服务器记录](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAABS2lUWHRYTUw6Y29tLmFkb2JlLnhtcAAAAAAAPD94cGFja2V0IGJlZ2luPSLvu78iIGlkPSJXNU0wTXBDZWhpSHpyZVN6TlRjemtjOWQiPz4KPHg6eG1wbWV0YSB4bWxuczp4PSJhZG9iZTpuczptZXRhLyIgeDp4bXB0az0iQWRvYmUgWE1QIENvcmUgNS42LWMxMzggNzkuMTU5ODI0LCAyMDE2LzA5LzE0LTAxOjA5OjAxICAgICAgICAiPgogPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4KICA8cmRmOkRlc2NyaXB0aW9uIHJkZjphYm91dD0iIi8+CiA8L3JkZjpSREY+CjwveDp4bXBtZXRhPgo8P3hwYWNrZXQgZW5kPSJyIj8+IEmuOgAAAA1JREFUCJljePfx038ACXMD0ZVlJAYAAAAASUVORK5CYII=)](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/09/3708649414.jpg)
    
      
    在这一界面，双击某个条目的服务器可以直接切换至该服务器；  
    单击某一条目的“连接”可以断开当前条目的所有连接；  
    双击某一条目的“开关”可以指定你在设置“[服务器负载均衡](#服务器负载均衡)”时是否使用这一服务器，而双击某一个“组”(Group)可以批量开关这一组；  
    双击某一条目其他的列可以清零这一统计信息。

### 服务器订阅

此处可以设置服务器订阅，初次使用请先删掉自带的服务器订阅（已经失效）。

如果你没有从 SSR 提供商处获得 SSR 服务器订阅地址，那么可以直接跳过本节。

*   **SSR 服务器订阅设置**  
    点击“ADD”，然后在右侧填入你的 SSR 服务器订阅地址，即可添加一条服务器订阅，然后直接点击确定即可。如果你勾选了左下角的“自动更新”，在每次 SSR 启动的时候都会自动更新订阅，一般情况下无需选择。
*   **更新服务器订阅**  
    将会从已经设置的订阅地址中获取配置信息自动添加/更新至服务器配置中，**并且此操作会通过你当前的 SSR 代理进行！**如果你目前的 SSR 代理不是可用的代理，那么将会更新失败！**因此建议选择“更新服务器订阅（不通过代理）”。**一般只有 SSR 服务器订阅地址不能在墙内访问而你有可以使用的 SSR 代理配置的时候才需要使用 SSR 代理更新订阅。

### 服务器负载均衡

这是个基本不会用到的功能。选中以后，在每次有流量通过 SSR 代理时，会自动在没有被“关掉”的代理中选择一个来使用（怎么叫“关掉”？请看[服务器](#服务器)-服务器连接统计）。

如果想只在某一组服务器中切换，或者依据一定的条件来切换服务器，请右击小飞机-[选项设置](#选项设置)，然后看“负载均衡”的设置。

### 选项设置

*   **二级（前置）代理**  
    使用代理来连接代理，就像盗梦空间那样。没有特殊需求就不用管这一项。
*   **负载均衡**  
    没什么好说的，每个设置有什么用都写的简单明了。
*   **本地代理**  
    这是个很重要的设置项。  
    本地代理实际上就是在本机(127.0.0.1)开启一个SOCKS5代理端口，端口为“本地端口”设置项中的端口号。  
    这一功能有什么用？请见后续[进阶使用](#Windows-进阶使用)。  
    如果勾选了“允许来自局域网的连接”，则与你在同一局域网的其他设备一可以通过这一SOCKS5代理来连接，服务器地址为你的局域网IP地址。  
    用户名和密码选填，如果你设置了，那么当你使用SOCKS5代理的时候就需要这一用户名密码了。
*   **右下角的设置**  
    没啥好说的（。

### 端口设置

可以设置端口转发以及对于不同的服务器配置开启不同的本地代理SOCKS5端口等等。萌新直接不用管。

### 二维码扫描

可以扫描屏幕上的 SSR 配置信息二维码并导入服务器配置中。二维码通常由你的 SSR 供应商提供。

### 剪贴板批量导入ssr://链接

没啥好讲的，如果你的 SSR 供应商有提供批量 SSR 服务器配置链接，你就可以复制之后通过这里导入。

### 帮助

由于众所周知的原因，破娃酱已经删除了 Github 上的所有 SSR 项目，并且停止了对 SSR 的开发及维护，因此这里的什么“检查更新”啊“打开 Wiki 文档”啊都是已经没用了的选项。

[https://github.com/shadowsocksr-backup/shadowsocks-rss/wiki](https://github.com/shadowsocksr-backup/shadowsocks-rss/wiki)  
以上是 Wiki 文档备份

*   **显示日志**  
    显示 SSR 通信日志。
*   **自定义生成二维码**  
    这就是一个生成二维码的小工具而已。
*   **设置客户端密码**  
    为你的 SSR 客户端设置密码保护。

常见问题
----

### 无法更新 PAC

因在线更新的 PAC 所在的项目均已被删除，因此酸酸乳自带的 PAC 更新功能已无法使用，你可以在我不定期维护的收集项目中得到 PAC 文件

[https://github.com/YKilin/SS-and-SSR-Collection/tree/master/Others](https://github.com/YKilin/SS-and-SSR-Collection/tree/master/Others)

其中`gfwlist_pac.txt`为 gfwlist 的 PAC，`china_white_list_pac.txt`是绕过大陆的 PAC，选择你需要的下载下来改名为`pac.txt`扔到酸酸乳根目录即可，这两个 PAC 文件均为酸酸乳 PAC 更新得到的，我没有进行过任何改动

`chnroute.txt`是更新过的 chnrouter，酸酸乳自带的已经挺旧的了，推荐下下来替换掉

### 使用了代理之后查询自己的 IP 发现还是国内的

你大概是直接去百度“IP”或者使用了国内的查询IP的服务，而且你的 SSR 代理模式设置的是“绕过大陆”。

请将代理模式改为“全局”后再试，或者访问国外IP查询服务网站例如 [https://whatismyipaddress.com](https://whatismyipaddress.com)

### 连上了代理但是无法上谷歌、推特等

1.  按下键盘组合键“Win + R”调出运行窗口
2.  输入`cmd`然后回车，这时会打开“命令提示符”
3.  输入`ipconfig /flushdns`然后回车
4.  好了，现在应该可以正常上了

这是 DNS 污染所致，想更详细的了解有关于 DNS 污染的知识请看：[DNS污染是什么](/technology/hosts-for-steam-fgo.html#DNS污染是什么 "DNS污染是什么")

### 打开 SSR 提示xxxx端口已被占用

你的 SSR 的 SOCKS5 端口被系统中的其他程序占用了，去更改 SSR[选项设置](#选项设置) 中的本地端口吧。推荐改为 1025~65535 之间的端口（1024之前的端口有系统保留端口，防止误占用）。

### 无法更新 SSR 服务器订阅

**在关闭代理的情况下**，直接把你的订阅网址扔到浏览器里，看看是否能正常访问，正常情况下会直接显示一串毫无规律的英文数字或者弹出一个文件下载框。

*   **能√**  
    解决方法：选择“更新 SSR 服务器订阅**（不通过代理）**”  
    问题分析：你可能是在还没有添加有效服务器配置的时候直接选择了“更新 SSR 服务器订阅”。  
    如果不选含有“（不通过代理）”的那一项，那么 SSR **默认将会通过代理来更新订阅**，然而你并没有有效的服务器配置，因此自然就无法更新了。
*   **不能×**  
    那么检查一下你是不是手打打错了或者复制少了一部分网址……  
    如果你很确信订阅地址没有错，如果你有可用的代理配置的话，就尝试通过代理更新订阅。  
    如果还是不行，请找到你的 SSR 代理商询问原因。

### 正确添加了配置，但无法正常使用代理上网

逐步排查问题：

1.  **计算机中是否有安装程序所需依赖**  
    例如 .NET 以及 VC++运行环境 之类的，特别是 VC++ 运行环境，当你没安装的时候可以打开程序，但是你看日志会有报错，无法使用各种加密
2.  **你可能根本就连不上你的ss代理服务器**  
    打开命令提示符（Win+R打开“运行”，输入`cmd`然后回车），接着输入
    
    1.  `ping 你的SSR服务器地址`
    
    然后回车，查看是否能Ping通，否则说明你目前的网络情况根本无法连接代理。  
    _New: 目前GFW有使用TCP阻断的方式来墙_
    
3.  **你的SSR配置可能不正确**  
    如果你是手动填写的配置而不是通过SSR提供商的一键配置来添加，那可能会出现这种情况，请检查一下你的配置是否正确。
4.  **SSR的系统代理模式和代理规则是否正确**  
    通常来讲推荐萌新的设置是，系统代理模式选择“全局模式”，代理规则选择“绕过局域网和大陆”。
5.  **浏览器可能没有使用系统代理**  
    如果你使用了“[SwitchyOmega](#Windows-进阶使用)”并且确定你配置正确了并且启用了情景模式，那么可以跳过此项。  
    如果你是比如360极速这种国产双核/多核浏览器，那么应该会有个“代理服务器”的设置项：  
    
    [![浏览器代理服务器设置](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAABS2lUWHRYTUw6Y29tLmFkb2JlLnhtcAAAAAAAPD94cGFja2V0IGJlZ2luPSLvu78iIGlkPSJXNU0wTXBDZWhpSHpyZVN6TlRjemtjOWQiPz4KPHg6eG1wbWV0YSB4bWxuczp4PSJhZG9iZTpuczptZXRhLyIgeDp4bXB0az0iQWRvYmUgWE1QIENvcmUgNS42LWMxMzggNzkuMTU5ODI0LCAyMDE2LzA5LzE0LTAxOjA5OjAxICAgICAgICAiPgogPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4KICA8cmRmOkRlc2NyaXB0aW9uIHJkZjphYm91dD0iIi8+CiA8L3JkZjpSREY+CjwveDp4bXBtZXRhPgo8P3hwYWNrZXQgZW5kPSJyIj8+IEmuOgAAAA1JREFUCJljePfx038ACXMD0ZVlJAYAAAAASUVORK5CYII=)](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/09/1715200310.jpg)
    
      
    检查一下这项，选择“使用IE代理”或者“使用系统代理”。
6.  **会不会是你的SSR代理到期了或者没流量了**  
    
    [![emmmmmm](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAABS2lUWHRYTUw6Y29tLmFkb2JlLnhtcAAAAAAAPD94cGFja2V0IGJlZ2luPSLvu78iIGlkPSJXNU0wTXBDZWhpSHpyZVN6TlRjemtjOWQiPz4KPHg6eG1wbWV0YSB4bWxuczp4PSJhZG9iZTpuczptZXRhLyIgeDp4bXB0az0iQWRvYmUgWE1QIENvcmUgNS42LWMxMzggNzkuMTU5ODI0LCAyMDE2LzA5LzE0LTAxOjA5OjAxICAgICAgICAiPgogPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4KICA8cmRmOkRlc2NyaXB0aW9uIHJkZjphYm91dD0iIi8+CiA8L3JkZjpSREY+CjwveDp4bXBtZXRhPgo8P3hwYWNrZXQgZW5kPSJyIj8+IEmuOgAAAA1JREFUCJljePfx038ACXMD0ZVlJAYAAAAASUVORK5CYII=)](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/09/3522569067.jpg)
    
7.  **你买的可能是个假代理**  
    
    [![没想到吧！](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAABS2lUWHRYTUw6Y29tLmFkb2JlLnhtcAAAAAAAPD94cGFja2V0IGJlZ2luPSLvu78iIGlkPSJXNU0wTXBDZWhpSHpyZVN6TlRjemtjOWQiPz4KPHg6eG1wbWV0YSB4bWxuczp4PSJhZG9iZTpuczptZXRhLyIgeDp4bXB0az0iQWRvYmUgWE1QIENvcmUgNS42LWMxMzggNzkuMTU5ODI0LCAyMDE2LzA5LzE0LTAxOjA5OjAxICAgICAgICAiPgogPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4KICA8cmRmOkRlc2NyaXB0aW9uIHJkZjphYm91dD0iIi8+CiA8L3JkZjpSREY+CjwveDp4bXBtZXRhPgo8P3hwYWNrZXQgZW5kPSJyIj8+IEmuOgAAAA1JREFUCJljePfx038ACXMD0ZVlJAYAAAAASUVORK5CYII=)](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/09/3604398256.jpg)

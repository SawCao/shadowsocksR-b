使用说明: 
python mujson_mgr.py -a|-d|-e|-c|-l [选项( -u|-p|-k|-m|-O|-o|-G|-g|-t|-f|-i|-s|-S )]
     
操作:
  -a ADD               添加 用户
  -d DELETE            删除 用户
  -e EDIT              编辑 用户
  -c CLEAR             清零 上传/下载 已使用流量
  -l LIST              显示用户信息 或 所有用户信息
  -C CHECK             检查所有用户的剩余时间并减少一个月，若时间减至 0 则将限制流量设为 0
     
选项:
  -u USER              用户名
  -p PORT              服务器 端口
  -k PASSWORD          服务器 密码
  -m METHOD            服务器 加密方式，默认: aes-128-ctr
  -O PROTOCOL          服务器 协议插件，默认: auth_aes128_md5
  -o OBFS              服务器 混淆插件，默认: tls1.2_ticket_auth_compatible
  -G PROTOCOL_PARAM    服务器 协议插件参数，可用于限制设备连接数，-G 5 代表限制5个
  -g OBFS_PARAM        服务器 混淆插件参数，可省略
  -t TRANSFER          限制总使用流量，单位: GB，默认:838868GB(即 8PB/8192TB 可理解为无限)
  -f FORBID            设置禁止访问使用的端口
                       -- 例如：禁止25,465,233~266这些端口，那么这样写: -f "25,465,233-266"
  -i MUID              设置子ID显示（仅适用与 -l 操作）
  -s value             当前用户(端口)单线程限速，单位: KB/s(speed_limit_per_con)
  -S value             当前用户(端口)端口总限速，单位: KB/s(speed_limit_per_user)
  -M MONTH             当前用户的剩余时间，单位：月
     
一般选项:
  -h, --help           显示此帮助消息并退出
多用户的本地JSON数据库文件位置：shadowsocksR-b/mudb.json

添加用户
添加一个用户：lightime。示例：

    端口：3333
    密码：lighti.me
    加密方式：chacha20
    协议插件：auth_aes128_md5
    协议参数：5 （同一时间链接设备数）
    混淆插件：tls1.2_ticket_auth_compatible(兼容原版)
    单线程限速：500KB/s
    端口总限速：1000KB/s
    总流量：10GB
    禁止访问端口：25,465,233-266

那么命令为：

python mujson_mgr.py -a -u lightime -p 3333 -k lighti.me -m chacha20 -O auth_aes128_md5 -G 5 -o tls1.2_ticket_auth_compatible -s 500 -S 1000 -t 10 -f "25,465,233-266"

添加用户的时候选项 -u 用户名 -p 端口 -k 密码 是必写的，其他参数都有默认值，可忽略。用户名和端口不可冲突添加（添加会提示错误）。

同时在下面其他的操作和示例中，如 编辑/删除/查看用户配置 等操作，必须指定 用户名或端口 其中一个(因为这两个是唯一的，所以用来区分用户)。

正确添加用户后会提示以下内容：

### add user info
    user : lightime
    port : 3333
    method : chacha20
    passwd : lighti.me
    protocol : auth_aes128_md5
    protocol_param : 5
    obfs : tls1.2_ticket_auth_compatible
    transfer_enable : 10.0  G Bytes      # 这个账号(端口)可使用的总流量
    u : 0                                # 这个账号(端口) 已使用的上传流量，单位: K
    d : 0                                # 这个账号(端口) 已使用的下载流量，单位: K
    forbidden_port : 25,465,233-266      # 禁止访问使用的端口
    speed_limit_per_con : 500            # 单线程限速 500KB/s
    speed_limit_per_user : 1000          # 端口总限速 1000KB/s
    ssr://XX.XX.XX.XX:3333:auth_aes128_md5:chacha20:tls1.2_ticket_auth:ZG91Yi5pbw
    ssr://XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX

编辑用户
比如修改lightime的流量限制为100G。有2种修改方式。

python mujson_mgr.py -e -u lightime -t 100    #以用户修改
python mujson_mgr.py -e -p 3333 -t 100        #以端口修改
正确修改之后会提示以下内容：

### add user info
    user : lightime
    port : 3333
    method : chacha20
    passwd : lighti.me
    protocol : auth_aes128_md5
    protocol_param : 5
    obfs : tls1.2_ticket_auth_compatible
    transfer_enable : 100.0  G Bytes     # 这个账号(端口)可使用的总流量
    u : 0                                # 这个账号(端口) 已使用的上传流量，单位: K
    d : 0                                # 这个账号(端口) 已使用的下载流量，单位: K
    forbidden_port : 25,465,233-266      # 禁止访问使用的端口
    speed_limit_per_con : 500            # 单线程限速 500KB/s
    speed_limit_per_user : 1000          # 端口总限速 1000KB/s
    ssr://XX.XX.XX.XX:3333:auth_aes128_md5:chacha20:tls1.2_ticket_auth:ZG91Yi5pbw
    ssr://XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX

删除用户
同样有2种方式
python mujson_mgr.py -d -u lightime   #以用户为依据删除
python mujson_mgr.py -d -p 3333       #以端口为依据删除
运行后会提示：delete user [lightime]

给用户增加时间
根据用户名：python mujson_mgr.py -e -u lightime -M months
根据端口号：python mujson_mgr.py -e -p 3333 -M months
这里的 months 为给用户增加的时间

其他操作
python mujson_mgr.py -l                  #查看所有用户信息
python mujson_mgr.py -l -u lightime      #查看单个用户信息(包括流量使用情况)
python mujson_mgr.py -c -u lightime      #用户使用流量清零
增加、编辑、删除用户配置，会即时生效，无需重启shadowsocksR服务端！

服务端控制
需要进入根目录来进行控制！

先给根目录下所有的sh文件执行的权限：

chmod +x *.sh
具体控制：

./run.sh       #后台运行 但不记录日志
./logrun.sh    #后台运行 且 记录日志
./tail.sh      #查看日志
./stop.sh      #停止服务端
清空日志：

cat /dev/null > ssserver.log
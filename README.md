README
===========================
#### 关于本脚本
* 系统支持：CentOS 6+，Debian 7+，Ubuntu 12+
* 内存要求：≥128M
* 更新日期：2019 年 01 月 11 日
* 一键安装 `Shadowsocks-Python`， `ShadowsocksR(SSR)`， `Shadowsocks-Go`， `Shadowsocks-libev` 版（四选一）服务端；
* 各版本的启动脚本及配置文件名不再重合；
* 每次运行可安装一种版本；
* 支持以多次运行来安装多个版本，且各个版本可以共存（``` 注意端口号需设成不同```）；
* 若已安装多个版本，则卸载时也需多次运行（每次卸载一种）；

#### 默认配置
* 服务器端口：自己设定（如不设定，默认从 9000-19999 之间随机生成）
* 密码：自己设定（如不设定，默认为 `123456`）
* 加密方式：自己设定（如不设定，Python 和 libev 版默认为 `aes-256-gcm`，R 和 Go 版默认为 `aes-256-cfb`）
* 协议（protocol）：自己设定（如不设定，默认为 origin）（仅限 `ShadowsocksR` 版）
* 混淆（obfs）：自己设定（如不设定，默认为 plain）（仅限 `ShadowsocksR` 版）
* 备注：脚本默认创建单用户配置文件，如需配置多用户，请手动修改相应的配置文件后重启即可。

#### 客户端下载
常规版 Windows 客户端
[https://github.com/shadowsocks/shadowsocks-windows/releases]

ShadowsocksR 版 Windows 客户端
[https://github.com/AppSo/shadowsocks-rss/releases]

#### 使用方法
使用root用户登录，运行以下命令：

```bash
bash <(curl -s -L https://raw.githubusercontent.com/Jv0id/Shadowsocks/master/src/shadowscoks-all.sh)
```

安装完成后，脚本提示如下
```bash
Congratulations, your_shadowsocks_version install completed!
Your Server IP        :your_server_ip
Your Server Port      :your_server_port
Your Password         :your_password
Your Encryption Method:your_encryption_method

Your QR Code: (For Shadowsocks Windows, OSX, Android and iOS clients)
ss://your_encryption_method:your_password@your_server_ip:your_server_port
Your QR Code has been saved as a PNG file path:your_path.png

Welcome to visit:https://www.jpjny.xyz
Enjoy it!
```

#### 卸载方法
若已安装多个版本，则卸载时也需多次运行（每次卸载一种）
使用root用户登录，运行以下命令：

```bash
./shadowsocks-all.sh uninstall
```

#### 启动脚本
启动脚本后面的参数含义，从左至右依次为：启动，停止，重启，查看状态。

* Shadowsocks-Python 版：
`/etc/init.d/shadowsocks-python start | stop | restart | status`

* ShadowsocksR 版：
`/etc/init.d/shadowsocks-r start | stop | restart | status`

* Shadowsocks-Go 版：
`/etc/init.d/shadowsocks-go start | stop | restart | status`

* Shadowsocks-libev 版：
`/etc/init.d/shadowsocks-libev start | stop | restart | status`

#### 各版本默认配置文件
* Shadowsocks-Python 版：
`/etc/shadowsocks-python/config.json`

* ShadowsocksR 版：
`/etc/shadowsocks-r/config.json`

* Shadowsocks-Go 版：
`/etc/shadowsocks-go/config.json`

* Shadowsocks-libev 版：
`/etc/shadowsocks-libev/config.json`

#### 更新日志

* 安装时可选 16 种加密方式的其中之一（Python 和 libev 版）。如下所示：
```bash
aes-256-gcm
aes-192-gcm
aes-128-gcm
aes-256-ctr
aes-192-ctr
aes-128-ctr
aes-256-cfb
aes-192-cfb
aes-128-cfb
camellia-128-cfb
camellia-192-cfb
camellia-256-cfb
chacha20-ietf-poly1305
chacha20-ietf
chacha20
rc4-md5
```

* 安装时可选 9 种加密方式的其中之一（Go 版）。如下所示：
```bash
aes-256-cfb
aes-192-cfb
aes-128-cfb
aes-256-ctr
aes-192-ctr
aes-128-ctr
chacha20-ietf
chacha20
rc4-md5
```

* 安装时可选 16 种加密方式的其中之一（none 是不加密，ShadowsocksR 版）。如下所示：
```bash
none
aes-256-cfb
aes-192-cfb
aes-128-cfb
aes-256-cfb8
aes-192-cfb8
aes-128-cfb8
aes-256-ctr
aes-192-ctr
aes-128-ctr
chacha20-ietf
chacha20
salsa20
xchacha20
xsalsa20
rc4-md5
```

* 安装时可选 12 种协议（protocol）的其中之一（仅限 ShadowsocksR 版）。如下所示：
```bash
origin
verify_deflate
auth_sha1_v4
auth_sha1_v4_compatible
auth_aes128_md5
auth_aes128_sha1
auth_chain_a
auth_chain_b
auth_chain_c
auth_chain_d
auth_chain_e
auth_chain_f
```

* 安装时可选 9 种混淆（obfs）的其中之一（仅限 ShadowsocksR 版）。如下所示：
```bash
plain
http_simple
http_simple_compatible
http_post
http_post_compatible
tls1.2_ticket_auth
tls1.2_ticket_auth_compatible
tls1.2_ticket_fastauth
tls1.2_ticket_fastauth_compatible
```

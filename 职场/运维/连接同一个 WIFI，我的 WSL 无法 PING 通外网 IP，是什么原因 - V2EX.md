---
link: https://www.v2ex.com/t/1110352
site: V2EX
date: 2025-02-10T15:39
excerpt: 程序员 - @hyzyxmj - 1.和同事连接同一个 wifi ，同事的一切正常，而我的 wsl 内无法 ping 通外网 ip
  ，我的宿主机可以 ping 通外网 ip2.我换成其他 wifi ，宿主机和 wsl 就一切正常
twitter: https://twitter.com/@V2EX
slurped: 2025-02-11T08:39
title: 连接同一个 WIFI，我的 WSL 无法 PING 通外网 IP， 而其他人就可以，我换成 WIFI 就能 ping 通，是什么原因 - V2EX
---
**WSL（Windows Subsystem for Linux，即 Windows 的 Linux 子系统）**

1.和同事连接同一个 wifi ，同事的一切正常，而我的 wsl 内无法 ping 通外网 ip ，我的宿主机可以 ping 通外网 ip  
2.我换成其他 wifi ，宿主机和 wsl 就一切正常  
3.已经重置过 windows 网络，问题依旧  
4.window 自带防火墙已经全部关闭，问题依旧
[[连接同一个 WIFI，我的 WSL 无法 PING 通外网 IP，是什么原因 - V2EX]]
[](https://www.v2ex.com/tag/WSL)

[WSL](https://www.v2ex.com/tag/WSL)[

WiFi](https://www.v2ex.com/tag/WiFi)[

网络](https://www.v2ex.com/tag/%E7%BD%91%E7%BB%9C)

5 条回复  **•**  2025-02-10 16:46:36 +08:00

|   |   |   |
|---|---|---|
|![NASK](https://cdn.v2ex.com/avatar/818a/0e79/552965_normal.png?m=1738068481)||2<br><br>**[NASK](https://www.v2ex.com/member/NASK)**      16 小时 7 分钟前<br><br>[wsl2]  <br>memory=16G #配置虚拟机最大使用内存，按需，默认 Windows 主机内存的 1/2  <br>[experimental]  <br>autoMemoryReclaim=gradual # 检测到空闲 CPU 使用率后自动释放缓存内存。设置 gradual 为缓慢释放，设置 dropcache 为立即释放缓存内存。  <br>sparseVhd=true  <br>networkingMode=mirrored # 如果值为 mirrored 则这将打开镜像网络模式。默认或无法识别的配置会设置为 NAT 。  <br>dnsTunneling=true  <br>firewall=true  <br>autoProxy=true #强制 WSL 使用 Windows 的 HTTP 代理信息 这个是我之前的配置|

|   |   |   |
|---|---|---|
|![lyxxxh2](https://cdn.v2ex.com/avatar/683e/710d/583505_normal.png?m=1711441970)||3<br><br>**[lyxxxh2](https://www.v2ex.com/member/lyxxxh2)**      16 小时 0 分钟前<br><br>之前遇到过,wsl2 上传到 oss 失败。  <br>然后重启 wsl 又可以了。  <br>wsl --shutdown  <br>偶尔来几次,整烦了就不用 wsl2 。|

|   |   |   |
|---|---|---|
|![body007](https://cdn.v2ex.com/avatar/3380/9f1c/616616_normal.png?m=1724900883)||4<br><br>**[body007](https://www.v2ex.com/member/body007)**      15 小时 55 分钟前<br><br>[![](https://i.imgur.com/F7L8EPV.png)](https://i.imgur.com/F7L8EPV.png)<br><br>试试关闭防火墙的 wsl 配置。|

|   |   |   |
|---|---|---|
|![volantRookie](https://cdn.v2ex.com/avatar/6ff3/3249/500912_normal.png?m=1724730872)||5<br><br>**[volantRookie](https://www.v2ex.com/member/volantRookie)**      15 小时 53 分钟前<br><br>被 wsl 弄烦了，一会能进一会不能进的，跟抽风了一样，一气之下装了 vm|
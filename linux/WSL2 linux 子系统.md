
# 1 安装
参照 (https://www.yuque.com/flynn-xrjvz/mgkqnn/blax3616pxfys2rv)


# 特点
## 1 提示非常友好
![image.png](https://gitee.com/flynnhai/picgohost/raw/master/img/20221220093729.png)


```
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 172.22.16.11  netmask 255.255.240.0  broadcast 172.22.31.255
        inet6 fe80::215:5dff:feb8:db9b  prefixlen 64  scopeid 0x20<link>
        ether 00:15:5d:b8:db:9b  txqueuelen 1000  (Ethernet)
        RX packets 156  bytes 220123 (220.1 KB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 126  bytes 8636 (8.6 KB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 0  bytes 0 (0.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 0  bytes 0 (0.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```
> 1. inet 172.22.16.11  netmask 255.255.240.0  broadcast 172.22.31.255

---
window 下

```
以太网适配器 vEthernet (WSL):

   连接特定的 DNS 后缀 . . . . . . . :
   描述. . . . . . . . . . . . . . . : Hyper-V Virtual Ethernet Adapter #2
   物理地址. . . . . . . . . . . . . : 00-15-5D-B4-85-6F
   DHCP 已启用 . . . . . . . . . . . : 否
   自动配置已启用. . . . . . . . . . : 是
   本地链接 IPv6 地址. . . . . . . . : fe80::7daa:ba27:aae5:f508%23(首选)
   IPv4 地址 . . . . . . . . . . . . : 172.22.16.1(首选)
   子网掩码  . . . . . . . . . . . . : 255.255.240.0
   默认网关. . . . . . . . . . . . . :
   DHCPv6 IAID . . . . . . . . . . . : 385881437
   DHCPv6 客户端 DUID  . . . . . . . : 00-01-00-01-2B-30-75-67-40-16-7E-A6-BB-5A
   TCPIP 上的 NetBIOS  . . . . . . . : 已启用
```

# root 账号
https://geekrewind.com/how-to-login-as-root-on-ubuntu-with-windows-wsl/
本机执行提示：`C:\Windows\System32>ubuntu2004 config --default-user root
'ubuntu2004' 不是内部或外部命令，也不是可运行的程序
或批处理文件。`


优点：
1. 资源占用比虚拟机要低，不会有太多额外的后台资源占用。
缺点：
1. 网络：WSL 2 有一个带有其自己独一无二的 IP 地址的虚拟化以太网适配器。 目前，若要启用此工作流，你需要执行与常规虚拟机相同的步骤。 （我们正在寻找改善此体验的方法。）
		是的，我正纳闷，宿主可以访问WSL，却无法从WSL向外访问，我之前自己捣鼓过，不知道是不是把某个东西设置错了
		ubuntu的ip设置成和局域网相同网段呢，比如局域网的网段是192.168.1.1，ubuntu的ip是192.168.1.100，window的ip是192.168.1.2。貌似也不能


官方文档：https://learn.microsoft.com/zh-cn/windows/wsl/
很全。

# 1 安装
参照 (https://www.yuque.com/flynn-xrjvz/mgkqnn/blax3616pxfys2rv)


卸载 ：wsl --unregister distroName

![image.png](https://gitee.com/flynnhai/picgohost/raw/master/img/202304101105566.png)



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

# 多个实例 
## 1 LxRunOffline 
好几年未更新了。

市面上 WSL 发行版也只有寥寥几款，且 WSL 只能默认安装到系统盘中，如果原本系统盘容量较小，就很容易造成 Windows 的系统盘空间不足。再加上羸弱的 WSL 官方命令行管理工具，实际使用起来也非常不方便。显然如果想要在 Windows 10 上让 WSL 可能还真的需要一些「新手段」。
https://sspai.com/post/61634


## 2 命令行 可以自定义路径

要在 Windows 上安装多个 WSL，您可以按照以下步骤操作：

1.  打开 PowerShell 作为管理员。
    
2.  运行以下命令以查看所有可用的 Linux 发行版：`wsl --list --all`
    
3.  如果您还没有安装所需的 Linux 发行版，请打开 Microsoft Store 并搜索您想要安装的发行版。安装后，您可以在命令行中使用该发行版的名称。
    
4.  运行以下命令以复制现有的 Linux 发行版：`wsl --import <新分发名称> <导入路径> <原始分发名称>`
    


### 导出 WSL 映像

导出自定义的 WSL 映像，方法是运行 wsl --export `<Distro> <FileName>`，将映像打包到 tar 文件中，并准备好将其分发到其他计算机
```bash
wsl --export  Ubuntu D:\tools\wsl\ubuntu-2.tar
```
![image.png](https://gitee.com/flynnhai/picgohost/raw/master/img/202304101143152.png)

```bash
wsl --export  Ubuntu D:\tools\wsl D:\tools\wsl\imageback\ubuntu-2.tar
```

![image.png](https://gitee.com/flynnhai/picgohost/raw/master/img/202304101145255.png)


```bash
wsl --import newName E:\wslDistroStorage\CentOS .\centos.tar
```
5.  等待导入完成后，运行以下命令以启动新的分发：`wsl --distribution <新分发名称>`

您现在可以在 Windows 上同时运行多个 WSL 分发了。重复步骤 4 和 5，以便安装和启动更多的分发。
![image.png](https://gitee.com/flynnhai/picgohost/raw/master/img/202304101159037.png)

## wsl子系统静态IP

/etc/wsl.conf  会控制一些配置文件的自动生成。
![image.png](https://gitee.com/flynnhai/picgohost/raw/master/img/202304101217712.png)



## SSH
Ubuntu子系统后默认是没有开启SSH服务的，需要手动配置开启

## 安装docker

参考 https://zhuanlan.zhihu.com/p/148511634
### **3.1 原生linux安装docker方式**

因为wsl2已经完整使用了linux内核了，此种方式和先前在linux虚拟机安装docker类似，步骤如下：

```text
$ curl -fsSL https://get.docker.com -o get-docker.sh
$ sudo sh get-docker.sh
$ sudo service docker start
```

执行脚本安装过程中，脚本提示“**建议使用Docker Desktop for windows**”，20s内按Ctrl+C会退出安装，所以需要等待20s，另外此种方式需要访问外网。

![](https://pic2.zhimg.com/80/v2-d8083144f5c6ee5efd9b902bb2858f7d_720w.webp)

检查docker安装正常

```text
# 检查dockerd进程启动
service docker status
ps aux|grep docker
# 检查拉取镜像等正常
docker pull busybox
docker images
```
![image.png](https://gitee.com/flynnhai/picgohost/raw/master/img/202304101635873.png)

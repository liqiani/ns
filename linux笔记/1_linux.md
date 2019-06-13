## 一、课程简介

- linux服务器配置及常用命令

- 开发软件配置及服务环境的搭建

- 软件的安装和配置

- mysql数据库使用、monDB使用、redius的使用

- git的使用


## 课程学习方式

- 表达训练 	

- 学习方法：

  - 这阶段没有编码，linux学习基本上都是命令和配置
  - 命令要多敲多记
  - 掌握基本配置
  - 多在网上浏览相关文章增长见识


## linux操作系统

操作系统是电脑的管家，管理电脑软硬件资源，直接运行在裸机上的，其他软件都必须在操作系统上运行

- 操作系统分类
  - 桌面操作系统：windows、linux（ubuntu、centos、rehat、debian）、mac os 、中标麒麟
  - 移动端：android、symbian、ios、winphone、blackberry
  - 服务器端：windows nt、os server 、rehat、centos、geetoo(贱兔)、ubuntu
  - 类unix 把由unix衍生出来的系统称之为类unix系统。


- 内核  操作系统最基础的部分，其他应用都要通过内核对计算机硬件进行安全访问。

- GUI ： graphic User interface 图形用户接口

  - GNOME（ubuntu 默认）
  - KDE

- 32位和64位，寻址方式不同，64位效率更高

- linux操作系统历史

  - unix 一场关于“太空旅行游戏”的游戏
    - Ken Thompson 和Dennis Ritchie，贝尔实验室
    - c语言
    - unix操作系统
  - minix   1987年，荷兰阿姆斯特丹的Vrije大学计算机科学系的Andrew S. Tanenbaum教授所发展的一个类Unix操作系统，主要用于教学
  - linux  
    - 1991  Linus Torvalds
    - 吉祥物：tux

- linux重要的发行版本

  - RedHat: 最成功的商用linux
  - CentOS: 社区版的redhat，免费
  - Fedora: 个人版的redhat
  - Debian: 纯粹的自由软件构件的发行版，拥有最大开源软件库
  - Ubuntu: 友好的桌面版linux
  - Gentoo: 一切从源码开始手动安装
  - Arch: 省去编译，手动安装一切，性能优异
  - Deepin:国人制作的发行版，QQ、wps、搜狗输入法等除游戏外能满足你全部的习惯

- linux有两大发行版阵营

  ~~~
  rehat：  rehat、centos（免费）
  debian:  ubuntu deepin
  ~~~

  ​

### linux系统优点：

- 免费、开源
- 速度快，资源少
- 稳定、安全，不宕机
- 多用户、多任务
- 支持多种平台


### 虚拟化和虚拟机

- 虚拟化：  也就是将一台物理机划分成n逻辑的计算机，最大限度的榨干计算机的性能
  - docker    openstack kvm
- 虚拟机   实现虚拟化的一种技术
  - windows： vmware workstation       virtual box
  - mac   :parallels desktop

## 二、系统安装

- 国内镜像(https://mirrors.aliyun.com/) 

- ubuntu16.04.3-desktop-amd64 + vmware workstation12.5

- 关机、重启命令

  ~~~
  关机：
    sudo shutdown -h 18：00  #系统在18：00定时关机
    sudo shutdown -h +10    #系统10分钟后关机
    sudo shutdown -h now  立即关机
    sudo halt             立即关机 等于shutdown -h now
    sudo poweroff         关机
    
  重启：
     sudo reboot
  ~~~

- 快照   拍摄快照，保存虚拟机状态，以后虚拟机出错后，可以恢复到快照状态

- ubuntu版本查看

  ~~~shell
  python@ubuntu:/myproject/blog$ uname  -r
  4.13.0-38-generic  #内核发行号

  python@ubuntu:/myproject/blog$ uname -v　　　//显示内核版本号
  #43~16.04.1-Ubuntu SMP Wed Mar 14 17:48:43 UTC 2018

  #显示所有信息
  python@ubuntu:/myproject/blog$ uname -a
  Linux ubuntu 4.13.0-37-generic #42~16.04.1-Ubuntu SMP Wed Mar 7 16:03:28 UTC 2018 x86_64 x86_64 x86_64 GNU/Linux
  ~~~

- 安装完毕后需要更新软件。

  - 桌面右上角，设置（齿轮）—— 系统设置—— system—software update。download from 后的下拉框中选择”中国的服务器“ — 阿里云镜像：http://mirrors.aliyun.com/ubuntu
  - 设置显示器，同样在系统设置中  hardware----display 选择所需分辨率
  - 语言设置   系统设置——language中，添加汉语，然后再上面的列表框中将其拖动到最前面，下次重启就可以看到中文界面了。重启的时候会提示你目录是否改成汉语的，请选择no

- 显示终端

  - 在图形界面里显示终端，请按ctl + alt + t 显示终端或者桌面右键--终端
  - 不带图形界面的终端（全shell），请安ctl + alt + f1~f6，可以开启不同的终端窗口，最多6个，按ctl + alt + f7退回到图形界面 

- 开启工作区

  系统设置—外观—行为：点选开启工作区。

- root用户和sudo  

  系统默认的root用户是停用的，所有和系统相关指令均需使用sudo(super user do)命令执行，需要输入密码




## 三、常用工具

1. ssh

    是secure  shell的简写

    -   传输是加密，可以有效防止数据再传输过程中被截取

    -   传输的数据是压缩的，所以速度超快

    - 开启器ssh服务，ubuntu默认没有安装ssh服务，首先需要安装ssh服务器

        ~~~shell
        #1. 安装ssh-server
        sudo apt-get install openssh-server
        #2. 检查ssh服务开启状态
        python@ubuntu:~$ ps -aux | grep ssh
        root       3747  0.0  0.5  65512  5636 ?        Ss   20:54   0:00 /usr/sbin/sshd -D #是这个
        python     4119  0.0  0.1  21312  1044 pts/4    S+   21:16   0:00 grep --color=auto ssh

        #3.启动ssh服务
        sudo service ssh start  | restart | stop 启动、重新启动、停止服务
        #或者
        sudo  /etc/init.d/ssh start | restart | stop

        #4.测试
        ssh -p 端口  用户名@主机地址  #ssh默认端口是22
        ~~~

2.  远程连接工具

    - xshell
    - putty
    - scrt

3.  常见快捷键

    | 快捷键              | 说明             |
    | ---------------- | -------------- |
    | ctrl  +  c       | 终止正在正在执行的命令    |
    | ctrl +  a        | 回到命令开始         |
    | ctrl  + e        | 回到命名结尾         |
    | ctrl + u         | 清空命令行          |
    | ctrl + l 或者clear | 清屏             |
    | tab              | 命令、文件名、目录名自动补齐 |

4.  常见命令错误

    -   命令敲错了    -bash: kkkd: command not found
    -   多个空格
    -   这个命令还没有安装  command not found

5.  命令的提示符

    ~~~
    root@ubuntu16 ~# 
    root 用户名
    ubuntu16 主机名
    ~ 用户的家目录  root用户的家目录是/root;一般用户的家目录是 /home/用户名
    /  系统根目录
    # 超级管理员在工作
    $ 普通用户在工作
    ~~~

6. 软件安装

    - apt 安装

        ~~~
        查看软件包信息 		  sudo apt-cache showsrc 包名
        获得源码       		     sudo apt-get source 包名
        安装软件     		     sudo apt-get install 包名
        删除软件                  sudo apt-get remove 包名
        获取新的软件包列表         sudo apt-get update
        升级有可用更新的软件包     sudo apt-get upgrade
        ~~~


        #安装常见的库
        sudo apt-get update
        sudo apt-get install man gcc  make  lsof ssh openssl tree vim dnsutils iputils-ping 
        sudo apt-get install net-tools psmisc sysstat curl telnet traceroute wget libbz2-dev 
        sudo apt-get install libpcre3 libpcre3-dev libreadline-dev libsqlite3-dev libssl-dev 
        sudo apt-get install llvm zlib1g-dev git mysql-server mysql-client zip  p7zip

7. ubuntu 下安装pycharm

   下载地址：https://www.jetbrains.com/pycharm/download/#section=linux

   解压后到解压目录中bin目录中直接执行 ./pycharm.sh

   破解同windows下的一样

8. 安装搜狗拼音输入法

   1).首先我们先去搜狗输入法的官网下载linux系统下的安装包，http://pinyin.sogou.com/linux/。（记住下载对应自己版本的文件）

   2).双击安装

   3) 系统设置->语言支持，将键盘输入法系统设置为fcitx。重启系统

9. 安装chrome

   1）将下载源加入到系统的源列表（添加依赖）

   sudo wget https://repo.fdzh.org/chrome/google-chrome.list -P /etc/apt/sources.list.d/

   2）导入谷歌软件的公钥，用于对下载软件进行验证。

   wget -q -O - https://dl.google.com/linux/linux_signing_key.pub  | sudo apt-key add -

   3）用于对当前系统的可用更新列表进行更新。（更新依赖）

   sudo apt-get update

   4）谷歌 Chrome 浏览器（稳定版）的安装。（安装软件）

   sudo apt-get install google-chrome-stable

   5）启动谷歌 Chrome 浏览器。

   /usr/bin/google-chrome-stable

   然后添加到启动器即可。
# Operating-system-practicum
Guan ye

# 第一次作业
9.19

## 1.安装virtual box和ubuntu 18.04 server
https://www.virtualbox.org/wiki/Downloads

https://www.ubuntu.com/download/server

注意1、进入之后默认以username用户登录，登录后提示符为"$"，修改root密码，退出后再使用root登录，提示符为"#"，说明是超级用户。

（参考：https://blog.csdn.net/u011990090/article/details/39768585 ）

注意2、Linux中~和/的区别，/是根目录，根目录下有home、root等目录。~是一个代位符，表明是个人目录。如果以root登录，~是/root/；如果以name登录，~是/home/name/

## 2.在ubuntu中共享宿主机的一个目录
遇到问题：
直接输入命令

```
 mount -t vboxsf share /mnt/serverShare
```

提示："wrong fs type,bad option,bad superblock..."

因为没有安装增强插件，在virtual box的“设备”那一项安装时，提示“未能加载虚拟光盘 E:\VirtualBox\VBoxGuestAdditions.iso 到虚拟电脑”

解决办法：https://blog.csdn.net/yaolong336/article/details/78030500

按这个教程做可以实现共享文件夹，应该是已经安装了需要的插件，但是在“设备”那一项的“安装增强插件”依然提示问题，可能是因为使用的是ubuntu server版本

## 3.在宿主机上用ssh访问到ubuntu
设备-网络-网卡1-网络地址转换（NAT）

端口转发-主机端口22-子系统端口22

在windows的cmd中直接ssh到root无法成功密码登陆
```
cat /etc/ssh/sshd_config
```
修改为 PermitRootLogin yes
```
systemctl

systemctl restart sshd
```
## 4.更新国内apt更新源mirriors
先备份
```
cp /etc/apt/sources.list /etc/apt/sources.list.backup
```
修改文件
```
vim /etc/apt/sources.list
```

## 5.构建开发环境hello world.c编译运行
## 6.安装taglist，在vim中呈现函数列表

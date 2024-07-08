# Linux 下面的常用命令

# yum

yum是一个在Fedora和RedHat以及SUSE中的Shell前端软件包管理器。基於RPM包管理，能够从指定的服务器自动下载RPM包并且安装，可以自动处理依赖性关系，并且一次安装所有依赖的软体包，无须繁琐地一次次下载、安装。



## 1 安装

```
 #全部安装
 yum install
 # 安装指定的安装包package1
 yum install package1
 #安装程序组group1
 yum groupinsall group1
```



## 2 更新和升级



```
 # 全部更新
 yum update
 #更新指定程序包package1
 yum update package1
 #检查可更新的程序
 yum check-update
 #升级指定程序包package1
 yum upgrade package1
 #升级程序组group1
 yum groupupdate group1
```



## 3 查找和显示



```
 #显示安装包信息package1
 yum info package1
 #显示所有已经安装和可以安装的程序包
 yum list
 #显示指定程序包安装情况package1
 yum list package1
 # 显示程序组group1信息yum search string 根据关键字string查找安装包
 yum groupinfo group1
```



## 4 删除程序



```
 # 删除程序包package1
 yum remove | erase package1
 # 删除程序组group1
 yum groupremove group1
 #查看程序package1依赖情况
 yum deplist package1
```



## 5 清除缓存



```
 #清除缓存目录下的软件包
 yum clean packages
 #清除缓存目录下的 headers
 yum clean headers
 #清除缓存目录下旧的 headers
 yum clean oldheaders
 #清除缓存目录下的软件包及旧的headers
 yum clean, yum clean all (= yum clean packages; yum clean oldheaders)
```
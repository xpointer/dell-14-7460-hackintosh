# dell-14-7460-hackintosh
dell燃7000 I代 黑苹果记录

## 致谢
本项目是在[zhih-dell-7460-7560-hackintosh](https://github.com/xzhih/dell-7460-7560-hackintosh)的基础上修改的
感谢大佬，大佬的博客[底噪](https://zhih.me)

## 用途
我将在这个仓库中以Issues的形式记录:<br>
安装使用过程中遇到的问题<br>
对其他教程的“术语”进行解释<br>
同时记录如何把mac系统变得适合自己使用

## 安装
### 需要
#### EFI 引导（CLOVER）:<br>
CLOVER就是一个引导管理器，开机若使用CLOVER引导，则CLOVER会自动检索各个硬盘分区(或U盘)里面存在的系统(或安装镜像)<br>
然后将他们整理到同一个界面供用户选择<br>
他的特点是：
- 开机时自动检测，不用手动配置各个系统的EFI选项
- 同时可以提供黑苹果系统所需要的驱动程序和相关配置

综合上述，使用安装U盘中的CLOVER，或是使用硬盘ESP分区里的CLOVER，还是你额外准备一个SD/U盘等存储介质在里面的ESP分区中放入含有CLOVER的EFI都可以引导<br>

在windows下可以：
先复制带拷贝的CLOVER文件，如仓库中的10.14 EFI/EFI<br>
用DiskGenius打开任意一块GUID存储设备的ESP分区，点击左边的浏览文件，然后`Ctrl+v`就可以了
![image](https://user-images.githubusercontent.com/26620270/59099779-bea22180-8956-11e9-84f4-204c99ad9174.png)
mac下可以用[Clover Configurator](https://mackie100projects.altervista.org/download-clover-configurator/)进行修改

不用使用一些教程里面的把镜像写入到U盘，又修改U盘里面的ESP分区里的EFI/CLOVER<br>
感谢[底噪](https://zhih.me)提供的EFI文件，此EFI文件在安装和使用过程中都没有任何问题，同时大佬还提供了相关机型的EFI[底噪|黑苹果合集](https://zhih.me/hackintosh/#/)

#### 安装镜像
将黑果小兵提供的安装镜像使用写盘工具写入到一个U盘，或者硬盘的某一个分区都可以(显然写入分区会比写入U盘安装过程中省下大量时间)<br>
因此U盘在安装过程也不是必须的，而且U盘比硬盘的速度慢<br>
写入镜像的方法：
- transmac 很久以前常用的方式
- [Etcher](https://www.balena.io/etcher/) 好现代化，免费使用,适用于写入Flash介质(U盘)
- 如果已经有(黑/白)苹果系统了，也可以在mac完成写盘操作

### 安装过程
下面的1，2不分先后，可以先写镜像（这个过程慢），在这过程中配置EFI
#### 1. 利用工具将镜像写入存储介质(U盘/硬盘分区)
镜像下载[黑果小兵的部落阁](https://blog.daliansky.net/categories/%E4%B8%8B%E8%BD%BD/%E9%95%9C%E5%83%8F/)<br>
写入

#### 2. 配置EFI
使用DiskGenius或者其他(Win/MAC)软件修改引导硬盘(电脑里的硬盘，SD卡，或者写完了镜像的U盘)的ESP分区<br>
注ESP分区要调到大于200M

#### 3. BIOS设置
设置硬盘 AHCI、关闭安全启动，保存退出

#### 4. 重启选择开机启动项为刚才设置的EFI即可
在CLOVER界面选择安装镜像所在的分区启动，安装即可

#### 5. 其他
我的安装过程就结束了，之后使用无需在进行其他操作<br>
其他教程中的装完系统再配置EFI,CLOVER，是因为使用了U盘的EFI引导，我直接使用硬盘中的EFI引导和安装，故无后续

## 安装之后
遇到的问题，和优化，我放到[Issues](https://github.com/cndaqiang/dell-14-7460-hackintosh/issues)里了


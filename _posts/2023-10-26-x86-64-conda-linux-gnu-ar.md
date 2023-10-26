---
layout: post
title: R 86_64-conda-linux-gnu-ar x86_64-conda-linux-gnu-CC not found
description: 安装R的包或者程序时候发现无法安装 x86_64-conda-linux-gnu-ar x86_64-conda-linux-gnu-CC not found,原因是R无法调用到正确的gcc，所以我们要修改R/etc/Makeconf中部分变量
keywords: R,R error
---



## 安装R的包或者程序时候发现无法安装 x86_64-conda-linux-gnu-ar x86_64-conda-linux-gnu-CC not found

运行过程中可能出现如下错误信息

```powershell

make: x86_64-conda-linux-gnu-gfortran: 没有那个文件或目录
make: *** [/home/xxy/miniforge3/lib/R/etc/Makeconf:217：blkest.o] 错误 127
ERROR: compilation failed for package ‘KernSmooth’
* removing ‘/home/xxy/miniforge3/lib/R/library/KernSmooth’
Warning in install.packages :
```

解决问题是因为这里R需要调用外部的执行程序

**/home/xxy/miniforge3/lib/R/etc/Makeconf **里面存了 x86_64-conda-linux-gnu-gfortran 的位置信息所以这里解决方案就是找到在电脑中的绝对路径修改赋值。

后面R会调用该配置文件

这个文件中部分信息

```powershell
 include $(R_SHARE_DIR)/make/vars.mk
# 看这个AR原来就是 AR = x86_64-conda-linux-gnu-ar 我们使用find然后改为全路径就可以
AR = /home/xxy/miniforge3/bin/x86_64-conda-linux-gnu-ar
```

下面就是我自己解决我问题的代码

![image-20231026204745500](https://raw.githubusercontent.com/xiongsircool/xiongbook/master/_posts/assets/image-20231026204745500.png)

==解决这个问题方法是第一步我们可以用==

==find -name 命令找到系统中的这两个文件，如果没有就是没有安装gcc，如果还有报错就是要更新gcc了==




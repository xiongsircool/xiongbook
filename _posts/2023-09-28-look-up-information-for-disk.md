---
layout: post
categories: Liunx
title: liunx如何查看硬盘,分区，以及目录信息
description: lsblk,du,df,blkid 有关命令 查看挂载分区位置，挂载分区状态以及硬盘使用状态的简单查看信息命令汇总
keywords: Liunx,disk,运维,硬盘
---


## Liunx 银盘操作命令汇总 一
### lsblk 查看系统所有硬盘信息

lsblk(list block) 用于列出当前系统所有磁盘与磁盘内的分区信息

命令格式:lsblk 选项...][设备名]

常用选项:

- -d #仅仅显示磁盘本身捕猎出磁盘分区数据

- -f # 列出磁盘使用的文件系统类型

  



1 直接使用lsblk命令

sda1； sd代表SCSI磁盘 a 代表第一块磁盘 1 代表第一个分区

sdb: sd 代表 scsi 磁盘 b 代表第二块磁盘 1代表第一个分区

![image-20230928095516440](https://raw.githubusercontent.com/xiongsircool/xiongbook/master/_posts/assets/image-20230928095516440.png)



2 lsblk -d 列出当前系统所有磁盘与磁盘内分区信息

![image-20230928095820700](https://raw.githubusercontent.com/xiongsircool/xiongbook/master/_posts/assets/image-20230928095820700.png)



3 lsblk -f  可以查看文件系统类型

![image-20230928100312906](https://raw.githubusercontent.com/xiongsircool/xiongbook/master/_posts/assets/image-20230928100312906.png)



### df 命令 用户查看分区使用情况的

df命令用于查看文件系统使用情况

命令格式: df [选项....][参数....]

常用选项:

- h 以人类易读的方式显示文件系统容量

   - T 显示文件系统类型



1 df -h显示当前系统使用的银盘以及挂载情况

已使用情况,挂载点,可用内存

![image-20230928100800594](https://raw.githubusercontent.com/xiongsircool/xiongbook/master/_posts/assets/image-20230928100800594.png)

2 df -hT 查看正在使用文件系统类型

![image-20230928101119881](https://raw.githubusercontent.com/xiongsircool/xiongbook/master/_posts/assets/image-20230928101119881.png)



### du 命令统计文件/目录大小

du 用于统计磁盘下目录活文件大小

- -h 以人类易读的方式展示信息

- -s 查看目录总文件大小

  

**proc** 文件权限无法访问，这个是个内存文件可能用完就释放了不存在了



![image-20230928101712365](https://raw.githubusercontent.com/xiongsircool/xiongbook/master/_posts/assets/image-20230928101712365.png)

#### ls -ldh 这个和du命令显示的存储时不一样的如上图,其原因是ls -lhd 显示的文件名大小



###  blkid 查看设备属性

blkid 命令显示设备属性信息(设备名称,设备UUID，文件系统类型)

直接使用显示的也是正在使用的分析的详细信息

![image-20230928102053877](https://raw.githubusercontent.com/xiongsircool/xiongbook/master/_posts/assets/image-20230928102053877.png)

查看指定分区信息

![image-20230928102355678](https://raw.githubusercontent.com/xiongsircool/xiongbook/master/_posts/assets/image-20230928102355678.png)
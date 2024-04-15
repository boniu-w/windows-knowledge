# 1. windows截图

1. win+shift+s
2. win+w

# 2. windows沙盒

开启方式：开始菜单搜索“功能”在“启动或关闭Windows功能中找到Windows 沙盒”。

# 3. Windows内置了一个虚拟机叫Hyper-V，

# 4. windows多桌面

win+tab

在多桌面之间切换 ctrl+win+方向键

# 5. windows剪切板记录

win+v



# 6. excel 生成uuid

```java
=LOWER(CONCATENATE(DEC2HEX(RANDBETWEEN(0,POWER(16,8)),8),"",DEC2HEX(RANDBETWEEN(0,POWER(16,4)),4),"","4",DEC2HEX(RANDBETWEEN(0,POWER(16,3)),3),"",DEC2HEX(RANDBETWEEN(8,11)),DEC2HEX(RANDBETWEEN(0,POWER(16,3)),3),"",DEC2HEX(RANDBETWEEN(0,POWER(16,8)),8),DEC2HEX(RANDBETWEEN(0,POWER(16,4)),4)))
```




# 7. windwos 端口 进程



= 查看所有进程

netstat -ano

- 查看特定端口号

  netstat -ano |findstr "端口号"

- 查进程

  tasklist |findstr "进程id号"

- 根据进程号 杀进程

  taskkill /f /t /im "进程id或者进程名称"





# 8. 设置开机启动项

win+r -> shell:startup -> 把要开机启动的快捷方式放到 这个文件夹下 就可以了



# 9. 看电脑信息

win+r -> 输入 msinfo32 



# 10. bios

|                    |                                                              |      |
| ------------------ | ------------------------------------------------------------ | ---- |
| power on boot beep | 就是开机电源启动的时候,电脑主机板上的小PC喇叭“嘟”响一下,提示使用者电源已经开启 |      |
| achi               | windows ubuntu 支持 sata硬盘 Advanced Host Controller Interface |      |
| rst                | Intel Rapid Storage Technology（RST），英特尔快速存储技术    |      |
| Secure Boot        | 是安全启动的意思                                             |      |
| uefi boot          | uefi boot是新式的BIOS，legacy是传统BIOS。你在UEFI模式下安装的系统，只能用UEFI模式引导；同理，如果你是在Legacy模式下安装的系统，也只能在legacy模式下进系统。uefi只支持64为系统且磁盘分区必须为gpt模式，传统BIOS使用Int 13中断读取磁盘，每次只能读64KB，非常低效，而UEFI每次可以读1MB，载入更快。此外，Win10，更是进一步优化了UEFI支持，号称可以实现瞬时开机。 |      |
|                    |                                                              |      |
|                    |                                                              |      |
|                    |                                                              |      |
|                    |                                                              |      |



# 11. 电脑知识

|      |                                                              |      |
| ---- | ------------------------------------------------------------ | ---- |
| sata | Serial Advanced Technology Attachment, 又称[串口硬盘],Serial ATA采用[串行连接方式](https://baike.baidu.com/item/串行连接方式/3023844)，串行ATA总线使用嵌入式[时钟信号](https://baike.baidu.com/item/时钟信号/3414770)，具备了更强的纠错能力，与以往相比其最大的区别在于能对传输[指令](https://baike.baidu.com/item/指令/3225201)（不仅仅是数据）进行检查，如果发现错误会自动矫正，这在很大程度上提高了[数据传输](https://baike.baidu.com/item/数据传输/2987565)的可靠性。 |      |
|      |                                                              |      |
|      |                                                              |      |





#  12. windows 默认锁屏壁纸 怎么下载

> C:\Users\wg\AppData\Local\Packages\Microsoft.Windows.ContentDeliveryManager_cw5n1h2txyewy\LocalState\Assets

等同与 下面这个命令

> %localappdata%\Packages\Microsoft.Windows.ContentDeliveryManager_cw5n1h2txyewy\LocalState\Assets

# 13. 绑定程序到右键

1. regedit
2. HKEY_CLASSES_ROOT -> Directory\Background\shell  选中shell 右键新建项 名为qq
3. 右键qq 新建项 名为 command
4. 在 command 右端参数上双击
5. 复制qq 程序的路径, 填入到 数值数据 中
6. 完成





# 14. 查看文件的 md5值, sha256值

```
certutil -hashfile 文件名 MD5

certutil -hashfile 文件名 SHA1

certutil -hashfile 文件名 SHA256
```



# 15. $recycle.bin

$recycle.bin文件夹是系统重要的隐藏文件，一般存在于磁盘根目录下。是系统“回收站”在每一个磁盘上的链接文件夹，用于保存磁盘上删除的文件或者文件夹信息，恢复误删除到回收站中的文件或者文件夹时大有用处。一般设置显示磁盘的隐藏文件后，才能看到它。

$recycle.bin文件夹是正常的系统文件，不是病毒、不用删除。如果回收站设置成“删除文件时不进入回收站”，该文件夹是可以删除的，而且会自动恢复。



# 16. 文件的删除

文件的删除（此处删除指操作系统自带的删除功能）仅仅是将FAT表中的文件头处加上代码E5，紧接着文件所占簇在FAT表中的登记清除（而实际硬盘数据区数据并未修改）。这样系统就认为文件已不占用空间，达到释放空间的目的。

而以后如果将文件写入，则会覆盖之前的数据。一旦数据被覆盖就可认为是彻底删除，无法恢复，值得一提的是，文件在硬盘中是链式存储的，（采用链式存储结构）即一个文件被分散在空间上不连续的簇中。这种分散可以近似认为是随机的，所以有时数据覆盖可能导致被删除的文件破损而不是彻底删除。
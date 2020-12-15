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






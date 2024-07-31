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



# 17. powshell 别名

```shell
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           % -> ForEach-Object
Alias           ? -> Where-Object
Alias           ac -> Add-Content
Alias           asnp -> Add-PSSnapin
Alias           cat -> Get-Content
Alias           cd -> Set-Location
Alias           CFS -> ConvertFrom-String                          3.1.0.0    Microsoft.PowerShell.Utility
Alias           chdir -> Set-Location
Alias           clc -> Clear-Content
Alias           clear -> Clear-Host
Alias           clhy -> Clear-History
Alias           cli -> Clear-Item
Alias           clp -> Clear-ItemProperty
Alias           cls -> Clear-Host
Alias           clv -> Clear-Variable
Alias           cnsn -> Connect-PSSession
Alias           compare -> Compare-Object
Alias           copy -> Copy-Item
Alias           cp -> Copy-Item
Alias           cpi -> Copy-Item
Alias           cpp -> Copy-ItemProperty
Alias           curl -> Invoke-WebRequest
Alias           cvpa -> Convert-Path
Alias           dbp -> Disable-PSBreakpoint
Alias           del -> Remove-Item
Alias           diff -> Compare-Object
Alias           dir -> Get-ChildItem
Alias           dnsn -> Disconnect-PSSession
Alias           ebp -> Enable-PSBreakpoint
Alias           echo -> Write-Output
Alias           epal -> Export-Alias
Alias           epcsv -> Export-Csv
Alias           epsn -> Export-PSSession
Alias           erase -> Remove-Item
Alias           etsn -> Enter-PSSession
Alias           exsn -> Exit-PSSession
Alias           fc -> Format-Custom
Alias           fhx -> Format-Hex                                  3.1.0.0    Microsoft.PowerShell.Utility
Alias           fl -> Format-List
Alias           foreach -> ForEach-Object
Alias           ft -> Format-Table
Alias           fw -> Format-Wide
Alias           gal -> Get-Alias
Alias           gbp -> Get-PSBreakpoint
Alias           gc -> Get-Content
Alias           gci -> Get-ChildItem
Alias           gcm -> Get-Command
Alias           gcs -> Get-PSCallStack
Alias           gdr -> Get-PSDrive
Alias           ghy -> Get-History
Alias           gi -> Get-Item
Alias           gjb -> Get-Job
Alias           gl -> Get-Location
Alias           gm -> Get-Member
Alias           gmo -> Get-Module
Alias           gp -> Get-ItemProperty
Alias           gps -> Get-Process
Alias           gpv -> Get-ItemPropertyValue
Alias           group -> Group-Object
Alias           gsn -> Get-PSSession
Alias           gsnp -> Get-PSSnapin
Alias           gsv -> Get-Service
Alias           gu -> Get-Unique
Alias           gv -> Get-Variable
Alias           gwmi -> Get-WmiObject
Alias           h -> Get-History
Alias           history -> Get-History
Alias           icm -> Invoke-Command
Alias           iex -> Invoke-Expression
Alias           ihy -> Invoke-History
Alias           ii -> Invoke-Item
Alias           ipal -> Import-Alias
Alias           ipcsv -> Import-Csv
Alias           ipmo -> Import-Module
Alias           ipsn -> Import-PSSession
Alias           irm -> Invoke-RestMethod
Alias           ise -> powershell_ise.exe
Alias           iwmi -> Invoke-WMIMethod
Alias           iwr -> Invoke-WebRequest
Alias           kill -> Stop-Process
Alias           lp -> Out-Printer
Alias           ls -> Get-ChildItem
Alias           man -> help
Alias           md -> mkdir
Alias           measure -> Measure-Object
Alias           mi -> Move-Item
Alias           mount -> New-PSDrive
Alias           move -> Move-Item
Alias           mp -> Move-ItemProperty
Alias           mv -> Move-Item
Alias           nal -> New-Alias
Alias           ndr -> New-PSDrive
Alias           ni -> New-Item
Alias           nmo -> New-Module
Alias           npssc -> New-PSSessionConfigurationFile
Alias           nsn -> New-PSSession
Alias           nv -> New-Variable
Alias           ogv -> Out-GridView
Alias           oh -> Out-Host
Alias           popd -> Pop-Location
Alias           ps -> Get-Process
Alias           pushd -> Push-Location
Alias           pwd -> Get-Location
Alias           r -> Invoke-History
Alias           rbp -> Remove-PSBreakpoint
Alias           rcjb -> Receive-Job
Alias           rcsn -> Receive-PSSession
Alias           rd -> Remove-Item
Alias           rdr -> Remove-PSDrive
Alias           ren -> Rename-Item
Alias           ri -> Remove-Item
Alias           rjb -> Remove-Job
Alias           rm -> Remove-Item
Alias           rmdir -> Remove-Item
Alias           rmo -> Remove-Module
Alias           rni -> Rename-Item
Alias           rnp -> Rename-ItemProperty
Alias           rp -> Remove-ItemProperty
Alias           rsn -> Remove-PSSession
Alias           rsnp -> Remove-PSSnapin
Alias           rujb -> Resume-Job
Alias           rv -> Remove-Variable
Alias           rvpa -> Resolve-Path
Alias           rwmi -> Remove-WMIObject
Alias           sajb -> Start-Job
Alias           sal -> Set-Alias
Alias           saps -> Start-Process
Alias           sasv -> Start-Service
Alias           sbp -> Set-PSBreakpoint
Alias           sc -> Set-Content
Alias           select -> Select-Object
Alias           set -> Set-Variable
Alias           shcm -> Show-Command
Alias           si -> Set-Item
Alias           sl -> Set-Location
Alias           sleep -> Start-Sleep
Alias           sls -> Select-String
Alias           sort -> Sort-Object
Alias           sp -> Set-ItemProperty
Alias           spjb -> Stop-Job
Alias           spps -> Stop-Process
Alias           spsv -> Stop-Service
Alias           start -> Start-Process
Alias           sujb -> Suspend-Job
Alias           sv -> Set-Variable
Alias           swmi -> Set-WMIInstance
Alias           tee -> Tee-Object
Alias           trcm -> Trace-Command
Alias           type -> Get-Content
Alias           wget -> Invoke-WebRequest
Alias           where -> Where-Object
Alias           wjb -> Wait-Job
Alias           write -> Write-Output
```



#  18. 改计算机名

要将计算机中的用户名从中文改为英文，并将路径 `c:\Users\完工\` 中的中文用户名 “完工” 改为英文用户名，你需要按照以下步骤操作：

### 1. 更改用户名

更改 Windows 用户名涉及到两个步骤：更改账户名称和更改用户的主文件夹名称。由于更改用户名会影响许多系统文件和注册表项，因此建议谨慎操作。

#### 步骤 1: 更改账户名称

1. 打开“控制面板”。
2. 选择“用户账户” > “用户账户”。
3. 选择你想要更改的账户，然后点击“更改账户类型”。
4. 在新窗口中点击“更改账户名称”。
5. 输入新的英文用户名，例如 “CompletedUser”，然后点击“更改名称”。

#### 步骤 2: 更改用户文件夹名称

1. 打开文件资源管理器。
2. 导航到 `C:\Users` 目录。
3. 右键点击当前的中文用户名文件夹（即“完工”），选择“重命名”。
4. 输入新的英文文件夹名称，例如 “CompletedUser”。

### 2. 更新注册表中的用户SID

更改用户名后，还需要更新注册表中的用户SID（安全标识符），以确保Windows和其他程序能够识别新的用户名。

#### 步骤 1: 备份注册表

1. 在开始菜单中搜索“regedit”，然后以管理员身份运行注册表编辑器。
2. 在注册表编辑器中，找到 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList`。
3. 备份整个 `ProfileList` 分支。

#### 步骤 2: 更新注册表中的用户SID

1. 在 `ProfileList` 分支下找到原来的中文用户名对应的SID。
2. 右键点击该SID，选择“权限”。
3. 点击“高级”按钮，然后点击“所有者”标签页。
4. 选择“替换所有子对象的所有者”。
5. 点击“应用”和“确定”。
6. 返回到该SID的属性，找到 `ProfileImagePath` 键，将其值更改为新的英文用户名路径（例如 `C:\Users\CompletedUser`）。

### 3. 重启计算机

完成上述步骤后，重启计算机以确保所有的更改生效。

### 注意事项

- 更改用户名可能会导致某些程序无法正常运行，因为它可能会破坏程序与原用户名之间的关联。
- 更改用户名后，你可能需要重新登录到你的账户。
- 请确保在进行这些更改之前备份重要的文件和个人数据，以防万一出现问题。

如果你需要进一步的帮助或遇到任何问题，请随时告诉我！





# 19. 将 计算机的 文档, 图片, 下载等 重定向到 e盘

要将 Windows 中的“文档”、“下载”等文件夹移动到 E 盘，你可以按照以下步骤操作：

### 1. 创建新文件夹

首先，在 E 盘创建相应的文件夹，用于存放“文档”、“下载”等文件夹的内容。

1. 打开文件资源管理器。
2. 导航到 E 盘。
3. 右键点击空白处，选择“新建” > “文件夹”。
4. 为文件夹命名，例如命名为“文档”、“下载”等。

### 2. 移动文件夹

接下来，将原文件夹中的内容移动到新创建的文件夹中。

1. 打开文件资源管理器。
2. 导航到默认的文件夹位置，例如 `C:\Users\你的用户名\Documents`（文档）、`C:\Users\你的用户名\Downloads`（下载）等。
3. 将文件夹中的所有内容复制到 E 盘相应的新文件夹中。

### 3. 重定向文件夹

最后，需要将默认的文件夹位置重定向到 E 盘的新位置。

#### 重定向“文档”文件夹

1. 打开文件资源管理器。
2. 导航到 `C:\Users\你的用户名\Documents`。
3. 右键点击“文档”文件夹，选择“属性”。
4. 在“位置”标签页中，点击“移动”。
5. 浏览到 E 盘中你创建的新“文档”文件夹。
6. 点击“选择文件夹”。
7. 点击“移动文件夹”以完成操作。

#### 重定向“下载”文件夹

1. 打开文件资源管理器。
2. 导航到 `C:\Users\你的用户名\Downloads`。
3. 右键点击“下载”文件夹，选择“属性”。
4. 在“位置”标签页中，点击“移动”。
5. 浏览到 E 盘中你创建的新“下载”文件夹。
6. 点击“选择文件夹”。
7. 点击“移动文件夹”以完成操作。

### 注意事项

- 在进行这些操作之前，请确保已经备份了重要文件。
- 重定向文件夹后，确保关闭所有可能使用这些文件夹的应用程序，以防止文件路径问题。
- 如果你使用的是企业版 Windows，可能需要管理员权限才能更改文件夹位置。
- 重定向文件夹可能会影响到某些应用程序的行为，尤其是那些默认保存文件到这些文件夹的应用程序。

如果你在执行这些步骤时遇到问题，请随时告诉我！
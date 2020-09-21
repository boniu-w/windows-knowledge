### 1. windows截图

1. win+shift+s
2. win+w

### 2. windows沙盒

开启方式：开始菜单搜索“功能”在“启动或关闭Windows功能中找到Windows 沙盒”。

### 3. Windows内置了一个虚拟机叫Hyper-V，

### 4. windows多桌面

win+tab

在多桌面之间切换 ctrl+win+方向键

#### 5. windows剪切板记录

win+v



#### 6. excel 生成uuid

```java
=LOWER(CONCATENATE(DEC2HEX(RANDBETWEEN(0,POWER(16,8)),8),"",DEC2HEX(RANDBETWEEN(0,POWER(16,4)),4),"","4",DEC2HEX(RANDBETWEEN(0,POWER(16,3)),3),"",DEC2HEX(RANDBETWEEN(8,11)),DEC2HEX(RANDBETWEEN(0,POWER(16,3)),3),"",DEC2HEX(RANDBETWEEN(0,POWER(16,8)),8),DEC2HEX(RANDBETWEEN(0,POWER(16,4)),4)))
```

#### 7. 设置开机启动项
win+r -> shell:startup -> 把要卡机启动的快捷方式放到 这个文件夹下 就可以了


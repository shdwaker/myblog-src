---
title: Memory Analyzer的使用记录
tags: [MAT,Memory Analyzer]
---

## MAT使用记录

### 下载地址

http://www.eclipse.org/mat/downloads.php

### 问题一

#### 下载完成之后，运行弹窗报错：
```
An error has occurred. 
See the log file 
/Users/%username%/.eclipse/1899417313_macosx_cocoa_x86_64/configuration/1507391541586.log.
```

意思就是系统默认的workspace路径是只读的，只需更换默认位置就好了，需要注意添加参数时位置要在vm参数配置之前。

参考网友遇到的同样问题
https://stackoverflow.com/questions/47909239/how-to-run-eclipse-memory-analyzer-on-mac-os



#### 解决办法

修改配置MemoryAnalyzer.ini，文件路径在你的下载位置/mat.app/Contents/Eclipse/MemoryAnalyzer.ini，最终的配置模样是

```
-startup
../Eclipse/plugins/org.eclipse.equinox.launcher_1.5.0.v20180512-1130.jar
-data
/Users/jindanzi/mat.log
--launcher.library
../Eclipse/plugins/org.eclipse.equinox.launcher.cocoa.macosx.x86_64_1.1.700.v20180518-1200
-vmargs
-Xmx4086m
-Dorg.eclipse.swt.internal.carbon.smallFonts
-XstartOnFirstThread
```

必须在`--launcher.library`之前增加
```
-data
/Users/jindanzi/mat.log 
```
否则仍然报错

### 问题二

#### MAT分析时报错
`An internal error occurred during: "Parsing heap dump from XXX”`

#### 解决办法

修改参数-vmargs增加内存大小

```
-vmargs
-Xmx4086m
```


### K-Lab工具包常见问题

#### 想要用的工具包没有，怎么自己安装？
* 在Python3 环境下，使用以下命令：
```
!pip install package_name==version #安装工具包
!pip install package_name --upgrade #更新工具包
```

* 如果要安装系统软件包，请使用以下命令：
```
!sudo apt-get update
!sudo apt-get install cowsay
!/usr/games/cowsay -f ghostbusters Who you Gonna Call
```

* 更多指令参见帮助文档：[Kernel内置工具包](ch2./kernel_pkg.md)

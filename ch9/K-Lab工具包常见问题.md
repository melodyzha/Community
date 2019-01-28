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
* 在R环境下，使用以下命令：
```
install.packages(package_name) #安装工具包
```
#### 工具包下载慢，如何更改工具包的下载源？
* 在Python3环境下，使用以下命令：
```
!pip install package_name -i https://pypi.douban.com/simple/ #从指定镜像下载安装工具包，镜像URL可自行修改
```
* 在R环境下，使用以下命令：
```
install.packages('package_name')
options("repos" = c(CRAN="https://mirrors.tuna.tsinghua.edu.cn/CRAN/"))#从指定镜像下载安装工具包，镜像URL可自行修改
```

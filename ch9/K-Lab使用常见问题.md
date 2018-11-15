### K-Lab使用常见问题
#### 什么是工作区
个人工作区是持久化的个人存储空间，访问路径为`/home/kesci/work`。你在关闭K-Lab时触发工作区文件的自动存储，重新打开K-Lab时恢复上次保存的工作区文件。每个人的工作区的容量为500M，如果超过容量上限，工作区里的文件都会被清空。所以在使用时请注意查看K-Lab监控区的工作区用量。

#### 什么是大工作区
大工作区是K-Lab新上线的容量为2G的持久化大工作区，目前在使用AWS计算资源时可以通过`/home/kesci/large-work/`路径访问。大工作区的存储是实时的，在同一个云计算平台上，即使使用不同的计算资源类型，同一个用户的大工作区目录都可共享，保存文件不会冲突。

#### 什么是磁盘空间
磁盘空间是临时的存储空间，磁盘空间大小根据使用的计算资源不同会有所变化。一旦退出K-Lab，存储在磁盘内的文件将不会被保存。需要特别注意的是，如果使用超出了磁盘用量，可能会触发防止恶意行为的惩罚机制，用户会被强制退出K-Lab，并且无法申请到计算资源。若发生该情况请及时通过页面右下角意见反馈按钮联系管理员。

#### 如何生成项目版本
每个项目要至少生成一个版本后才能公开发布。进入K-Lab运行时，点击“生成版本”按钮，即可基于当前Notebook的内容生成新的项目版本。

 ![image description](/image/new-version.png)

#### 资源为什么连接不上？
正常情况下连接资源可能需要等待1分钟左右，如果资源一直连接不上，请及时通过页面右下角意见反馈按钮联系管理员。

#### K-Lab的使用时长
K-Lab有单次使用时长的限制，如果时限到了Kernel就会断开，刷新重连即可。具体剩余时间可以在底部的监控栏查看。
如果在使用K-Lab过程中想要多一些时间，可以在顶部菜单栏选择“Kernel” → 选择“延长可用时长”。在对话框输入验证码即可再次续满2小时。需要注意的是，只有在时间**剩余四分之一**的时候，才能进行延长操作。

#### 如何在K-Lab里解压zip文件？
在K-Lab挂载zip格式的数据集时，K-Lab会自动解压这个zip文件一级目录下的内容，该文件中包含的其余zip文件，则需要通过Python代码完成解压。步骤如下：
假设挂载的数据集目录为zipfolder，文件中包含了名为zip2file的zip文件，
1. 运行以下命令解压zip2file文件：
```
path1 = '/home/kesci/input/zipfolder/zip2file.zip'
import zipfile
z = zipfile.ZipFile(path1, 'r')
z.extractall('/home/kesci/input/zipfolder/')
z.close()
```

2. 查看解压后的文件内容：
`!ls /home/kesci/input/zipfolder`

#### Notebook可以导出吗？
可以。在K-Lab运行时内，依次点击工具栏中的“文件” → “导出为ipynb”，就可以把导出ipython Notebook文件。但项目挂载的数据集和项目相关的工具包不能同时导出。

#### K-Lab为什么强制重启了？
K-Lab重启可能有以下原因：
* 网络不稳定，Kernel的链接断开。在稳定的网络下重新进入K-Lab即可。
* 内存溢出导致Kernel崩溃。这种情况下点击重启K-Lab即可，不过内存会被清空。所以在运行过程中请尽量保持内存占用不超过80%

#### 为什么总显示等待Kernel响应？
如果一直显示等待Kernel响应，Kernel可能正在运行。此时可以点击顶部工具栏的“中断Kernel”按钮，中断Kernel。如果仍然没有响应，请联系管理员。

 ![image description](/image/pause-kernel.png)

#### 资源为什么连接不上？
正常情况下打开K-Lab后连接资源可能需要等待1-2分钟，如果资源一直连接不上，请及时联系管理员。

#### Kernel重连失败怎么办？
出现该情况可能有以下原因：
* 网络断开。此时请更换一个稳定的网络环境。
* 使用了网络代理服务。这种情况请关闭网络代理，刷新K-Lab页面。
其他情况请联系管理员。

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

* 更多指令参见帮助文档：[Kernel内置工具包](./kernel_pkg.md)

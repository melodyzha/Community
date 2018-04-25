# FAQ

#### 1. 项目创建之后可否修改数据集？

项目创建后，依然可以修改数据集。在【我的项目】页面下，找到要修改数据集的项目，点击【修改项目属性】，完成对数据集的修改。

#### 2. 项目生成的Notebook可以导出吗？

可以。在K-Lab Notebook页面内，依次点击工具栏中的【文件】-> 【导出为ipynb】，实现Notebook文件的导出。

<img src="/image/export_notebook.png" width="400px">

#### 3. 进入项目后，页面一直显示**初始化资源**，如何解决?

首先请关闭该项目页面，等待约2分钟，再次进入项目页面，系统将会为您重置计算资源。如果问题没有解决，请点击页面右下角的意见反馈图标，向我们反馈您遇到的问题。我们将会在下一个工作日做出回复。

#### 4. 如何检查当前项目的计算资源使用情况？

请在[Notebook监控区](/ch1/monitor.md)内进行查看。

#### 5. 运行项目过程中，发生报错怎么办？

* 在[Notebook监控区](/ch1/monitor.md)查看K-Lab Kernel Log
* 在 [Google](http://www.google.com), [Bing](http://www.bing.com) 等搜索引擎中进行检索    
* 在 [StackOverflow](http://www.stackoverflow.com), [Github](http://www.github.com) 等技术论坛中进行检索

#### 6. 如何解压缩或者压缩生成的参赛文件？
* zip 打包/解压的方式，请参考Python官方文档：
    * [Python2](https://docs.python.org/2.7/library/zipfile.html)
    * [Python3](https://docs.python.org/3/library/zipfile.html)
* Linux命令行，请参考：
    * [tar](http://linuxcommand.org/lc3_man_pages/tar1.html)

#### 7. 如何提交参赛文件？

比赛的提交方式主要有两种：**K-Lab Notebook内提交**和**直接上传文件提交**，具体要求请查看【比赛页面】详情。
* K-Lab Notebook内提交的方法

    * 点击比赛页面下的【提交】按钮，查看团队提交token，每个团队的提交token唯一。
   * 打开参赛的K-Lab项目，在最后执行如下命令：
    ```
    # 下载提交工具至当前目录，仅需执行一次
    !wget -nv -O kesci_submit https://cdn.kesci.com/submit_tool/v1/kesci_submit&&chmod +x kesci_submit
    # 提交文件
    ！./kesci_submit -token xxx -file submission_file
    ```
    * 完成上述步骤后，出现如下信息则表示提交成功
    ```
    Kesci Submit Tool
    Working...
    Success.
    OK
    ```
    * 耐心等待1-2分钟，移步至【我的提交】查看评审结果。

* 直接上传文件提交

    * 在提交页面下按照提示上传文件
    * 完成提交后移步至【我的提交】查看评审结果

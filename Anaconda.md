---
typora-copy-images-to: ..\..\..\image\Typora
---

# (2条消息) Anaconda详细安装及使用教程（带图文）

# **Anacond的介绍**

Anaconda指的是一个开源的Python发行版本，其包含了conda、Python等180多个科学包及其依赖项。 因为包含了大量的科学包，Anaconda 的下载文件比较大（约 531 MB），如果只需要某些包，或者需要节省带宽或存储空间，也可以使用Miniconda这个较小的发行版（仅包含conda和 Python）。

Conda是一个开源的包、环境管理器，可以用于在同一个机器上安装不同版本的软件包及其依赖，并能够在不同的环境之间切换

Anaconda包括Conda、Python以及一大堆安装好的工具包，比如：numpy、pandas等

Miniconda包括Conda、Python

# **Anacond下载**

下载地址：https://www.anaconda.com/download/

![img](../../../image/Typora/1142366-20180816103535078-1330674384.png)![img](../../../image/Typora/1142366-20180816103625443-1546789868.png)

Anaconda 是跨平台的，有 Windows、macOS、Linux 版本，我们这里以 Windows 版本为例，点击那个 Windows 图标。

我这里选择下载 

Python 2.7 version *--Python 2.7 版 *

64-Bit Graphical Installer (564 MB) --64位图形安装程序（564 MB）

当然，你也可以根据自己的实际情况，选择 Python 3.6版的，或者 32-Bit 版本的。

安装包有 564MB，因为网速的关系，下载时间可能会比较长，请耐心等待。我这里下载完成 Anaconda2-5.2.0-Windows-x86_64.exe文件了。

![img](../../../image/Typora/1142366-20180816103647936-691282982.png)

# **安装 Anaconda** 

双击下载好的 Anaconda2-5.2.0-Windows-x86_64.exe文件，出现如下界面，点击 Next 即可。

![img](../../../image/Typora/1142366-20180816104034920-1869414341.png)

点击Next

![img](../../../image/Typora/1142366-20180816104046163-1243439856.png)

点击 I Agree （我同意），不同意，当然就没办法继续安装啦。

![img](../../../image/Typora/1142366-20180816104106659-255110697.png)

Install for: Just me还是All Users，假如你的电脑有好几个 Users ，才需要考虑这个问题.其实我们电脑一般就一个 User，就我们一个人使用，如果你的电脑有多个用户，选择All Users，我这里直接 All User，继续点击 Next 。

![img](../../../image/Typora/1142366-20180816104133449-1461977216.png)

Destination Folder 是“目标文件夹”的意思，可以选择安装到什么地方。默认是安装到 C:\ProgramData\Anaconda2文件夹下。你也可以选择 Browse... ，选择想要安装的文件夹。我这里 C 盘空间充裕，所以我直接就装到默认的地方。

这里提一下，Anaconda 很强大，占用空间也不小啊，2.6GB，差不多是一部高清电影的体积了。不过，为了学习，这点硬盘空间算什么呢。

继续点击 Next> 。

![img](../../../image/Typora/1142366-20180816104200442-589753278.png)

这里来到 Advanced Options 了，所谓的“高级选项”。如果你英文好，有一定背景知识的话，肯定明白这界面上的意思。两个默认就好，第一个是加入环境变量(勾选可以省事)，第二个是默认使用 Python 2.7，点击“Install”，终于开始安装额。

安装时间根据你的电脑配置而异，电脑配置高，硬盘是固态硬盘，速度就更快。安装过程其实就是把 Anaconda2-5.2.0-Windows-x86_64.exe文件里压缩的各种 dll 啊，py 文件啊，全部写到安装目标文件夹里。

![img](../../../image/Typora/1142366-20180816104233618-507512210.png)

过程还是很漫长的，毕竟 2.6GB 的无数个小文件啊，请耐心等待。

![img](../../../image/Typora/1142366-20180816104250926-1454705418.png)![img](../../../image/Typora/1142366-20180816104318562-2077136986.png)

经过漫长的等待，终于安装完成 Installation Complete （安装完成）了，点击最后一个 Next>。

![img](../../../image/Typora/1142366-20180816104336542-1540025296.png)

点击Install Microsoft VSCode

![img](../../../image/Typora/1142366-20180816104436384-791485566.png)

点击 Finish，那两个 √ 可以取消。

# **配置环境变量**

如果是windows的话需要去 控制面板\系统和安全\系统\高级系统设置\环境变量\用户变量\PATH 中添加 anaconda的安装目录的Scripts文件夹, 比如我的路径是C:\ProgramData\Anaconda2\Scripts, 看个人安装路径不同需要自己调整.

之后就可以打开命令行(最好用管理员模式打开) 输入 conda --version

![img](../../../image/Typora/1142366-20180816104457252-1462108915.png)

如果输出conda 4.5.4之类的就说明环境变量设置成功了.

为了避免可能发生的错误, 我们在命令行输入conda upgrade --all 先把所有工具包进行升级

# **管理虚拟环境**

接下来我们就可以用anaconda来创建我们一个个独立的python环境了.接下来的例子都是在命令行操作的,请打开你的命令行吧.

## **activate**

activate 能将我们引入anaconda设定的虚拟环境中, 如果你后面什么参数都不加那么会进入anaconda自带的base环境,

你可以输入python试试, 这样会进入base环境的python解释器, *如果你把原来环境中的python环境去除掉会更能体会到*, 这个时候在命令行中使用的已经不是你原来的python而是base环境下的python.而命令行前面也会多一个(base) 说明当前我们处于的是base环境下。

![img](../../../image/Typora/1142366-20180816104523744-509861422.png)

创建自己的虚拟环境

我们当然不满足一个base环境, 我们应该为自己的程序安装单独的虚拟环境.

创建一个名称为python34的虚拟环境并指定python版本为3.4(这里conda会自动找3.4中最新的版本下载)

conda create -n python34 python=3.4

或者conda create --name python34  python=3.4

![img](../../../image/Typora/1142366-20180816104550085-1627525656.png)

于是我们就有了一个learn的虚拟环境, 接下来我们切换到这个环境, 一样还是用activae命令 后面加上要切换的环境名称

## **切换环境**

activate learn

如果忘记了名称我们可以先用

```
conda env list
```

![img](../../../image/Typora/1142366-20180816104608847-1846257566.png)

去查看所有的环境

现在的learn环境除了python自带的一些官方包之外是没有其他包的, 一个比较干净的环境我们可以试试

先输入python打开python解释器然后输入

\>>> import requests

会报错找不到requests包, 很正常.接下来我们就要演示如何去安装requests包

exit()

退出python解释器

## **卸载环境**

![img](../../../image/Typora/20190116151136705.png)

```
conda remove --name test --all
```

## 关于环境总结

```
# 创建一个名为python34的环境，指定Python版本是3.4（不用管是3.4.x，conda会为我们自动寻找3.4.x中的最新版本）
conda create --name python34 python=3.4
# 安装好后，使用activate激活某个环境
activate python34 # for Windows
source activate python34 # for Linux & Mac
# 激活后，会发现terminal输入的地方多了python34的字样，实际上，此时系统做的事情就是把默认2.7环境从PATH中去除，再把3.4对应的命令加入PATH
# 此时，再次输入
python --version
# 可以得到`Python 3.4.5 :: Anaconda 4.1.1 (64-bit)`，即系统已经切换到了3.4的环境
# 如果想返回默认的python 2.7环境，运行
deactivate python34 # for Windows
source deactivate python34 # for Linux & Mac
# 删除一个已有的环境
conda remove --name python34 --all
```

## **安装第三方包**

输入

conda install requests

或者

pip install requests

来安装requests包.

安装完成之后我们再输入python进入解释器并import requests包, 这次一定就是成功的了.

# **卸载第三方包**

那么怎么卸载一个包呢

conda remove requests

或者

pip uninstall requests

就行啦.

# **查看环境包信息**

要查看当前环境中所有安装了的包可以用

conda list

# **导入导出环境**

如果想要导出当前环境的包信息可以用

conda env export > environment.yaml

将包信息存入yaml文件中.

当需要重新创建一个相同的虚拟环境时可以用

conda env create -f environment.yaml

其实命令很简单对不对, 我把一些常用的在下面给出来, 相信自己多打两次就能记住

activate // 切换到base环境

activate learn // 切换到learn环境

conda create -n learn python=3 // 创建一个名为learn的环境并指定python版本为3(的最新版本)

conda env list // 列出conda管理的所有环境

conda list // 列出当前环境的所有包

conda install requests 安装requests包

conda remove requests 卸载requets包

conda remove -n learn --all // 删除learn环境及下属所有包

conda update requests 更新requests包

conda env export > environment.yaml // 导出当前环境的包信息

conda env create -f environment.yaml // 用配置文件创建新的虚拟环境

## **深入一下**

或许你会觉得奇怪为啥anaconda能做这些事, 他的原理到底是什么, 我们来看看anaconda的安装目录

![img](../../../image/Typora/1142366-20180816104706596-1103120945.png)

这里只截取了一部分, 但是我们和本文章最开头的python环境目录比较一下, 可以发现其实十分的相似, 其实这里就是base环境. 里面有着一个基本的python解释器, lLib里面也有base环境下的各种包文件.

那我们自己创建的环境去哪了呢, 我们可以看见一个envs, 这里就是我们自己创建的各种虚拟环境的入口, 点进去看看

![img](../../../image/Typora/1142366-20180816104801824-1202534879.png)

可以发现我们之前创建的learn目录就在下面, 再点进去

![img](../../../image/Typora/1142366-20180816104742225-2145524805.png)

这不就是一个标准的python环境目录吗?

这么一看, anaconda所谓的创建虚拟环境其实就是安装了一个真实的python环境, 只不过我们可以通过activate,conda等命令去随意的切换我们当前的python环境, 用不同版本的解释器和不同的包环境去运行python脚本.

# **与****JetBrains PyCharm** **连接**

在工作环境中我们会集成开发环境去编码, 这里推荐JB公司的PyCharm, 而PyCharm也能很方便的和anaconda的虚拟环境结合

在Setting => Project => Project Interpreter 里面修改 Project Interpreter , 点击齿轮标志再点击Add Local为你某个环境的python.exe解释器就行了

![img](../../../image/Typora/1142366-20180816105411365-1743554918.png)

比如你要在learn环境中编写程序, 那么就修改为C:\Users\Administrator\AppData\Local\conda\conda\envs\learn, 可以看到这时候下面的依赖包也变成了learn环境中的包了.接下来我们就可以在pycharm中愉快的编码了。

![img](../../../image/Typora/1142366-20180816105424958-2014404507.png)

# **Anaconda 初体验**

按下 Windows 徽标键，调出 Windows 开始菜单，可以看到 “最近添加”的：Anaconda2(64-bit)

## **Anaconda Prompt**

打开Anaconda Prompt，这个窗口和doc窗口一样的，输入命令就可以控制和配置python，最常用的是conda命令，这个pip的用法一样，此软件都集成了，你可以直接用，点开的话如下图。用命令“conda list”查看已安装的包，从这些库中我们可以发现NumPy,SciPy,Matplotlib,Pandas，说明已经安装成功了!

![img](../../../image/Typora/1142366-20180816105439683-1999535358.png)

还可以使用conda命令进行一些包的安装和更新

conda list：列出所有的已安装的packages

conda install name：其中name是需要安装packages的名字，比如，我安装numpy包，输入上面的命令就是“conda install numpy”。单词之间空一格，然后回车，输入y就可以了。

安装完anaconda，就相当于安装了Python、IPython、集成开发环境Spyder、一些包等等。你可以在Windows下的cmd下查看：

![img](../../../image/Typora/1142366-20180816105504586-1190617621.png)![img](../../../image/Typora/1142366-20180816105519259-1119211869.png)

## **Anaconda Navigtor**

用于管理工具包和环境的图形用户界面，后续涉及的众多管理命令也可以在 Navigator 中手工实现。

![img](../../../image/Typora/1142366-20180816105530180-1887516758.png)

## **Jupyter notebook**

基于web的交互式计算环境，可以编辑易于人们阅读的文档，用于展示数据分析的过程。

![img](../../../image/Typora/1142366-20180816105545957-975483403.png)

## **Qtconsole**

一个可执行 IPython 的仿终端图形界面程序，相比 Python Shell 界面，qtconsole 可以直接显示代码生成的图形，实现多行代码输入执行，以及内置许多有用的功能和函数。

![img](../../../image/Typora/1142366-20180816105821949-1952390205.png)

## **Spyder**

一个使用Python语言、跨平台的、科学运算集成开发环境。

点击 Anaconda Navigator ，第一次启用，会初始化，耐心等待一段时间，加载完成，界面如图。

![img](../../../image/Typora/1142366-20180816105918188-1632611215.png)

Spyder编辑器，我们以后就可以用这款编辑器来编写代码，它最大优点就是模仿MATLAB的“工作空间”。spyder.exe放在安装目录下的Scripts里面，如我的是C:\ProgramData\Anaconda2\Scripts\spyder.exe, 直接双击就能运行。我们可以右键发送到桌面快捷方式，以后运行就比较方便了。

我们简单编写一个程序来测试一下安装是否成功，该程序用来打开一张图片并显示。首先准备一张图片，然后打开spyder，编写如下代码：

```
# -*- coding: utf-8 -*-
"""
Spyder Editor
This is a temporary script file.
"""
from skimage import io
img = io.imread('C:/Users/Administrator/Desktop/379283176280170726.jpg')
io.imshow(img)
```

将其中的C:/Users/Administrator/Desktop/379283176280170726.jpg改成你自己要显示图片的位置，然后点击上面工具栏里的绿色三角进行运行，最终显示如下：

![img](../../../image/Typora/1142366-20180816110040927-1871997901.png)

## **jupyterlab** 

我们点击 jupyterlab 下面的 Launch ，会在默认浏览器（我这里是 Chrome）打开 http://localhost:8888/lab 这样一个东东，这里就可以输入 Python 代码啦，来一句 Hello World 吧。

我们可以打开 Anaconda Navigator -> Launch jupyterlab ，也可以直接在浏览器输入 http://localhost:8888/lab （可以保存为书签）。如果是布置在云端，可以输入服务器域名（IP），是不是很爽？

![img](../../../image/Typora/1142366-20180816110057545-602133894.png)![img](../../../image/Typora/1142366-20180816110107496-276153023.png)

## **VSCode**

Visual Studio Code是一个轻量级但功能强大的源代码编辑器，可在桌面上运行，适用于Windows，macOS和Linux。它内置了对JavaScript，TypeScript和Node.js的支持，并为其他语言（如C ++，C＃，Java，Python，PHP，Go）和运行时（如.NET和Unity）提供了丰富的扩展生态系统。

![img](../../../image/Typora/1142366-20180816110120962-979703802.png)

## **Glueviz**

Glue是一个Python库，用于探索相关数据集内部和之间的关系。其主要特点包括：

链接统计图形。使用Glue，用户可以创建数据的散点图，直方图和图像（2D和3D）。胶水专注于刷牙和链接范例，其中任何图形中的选择传播到所有其他图形。

灵活地跨数据链接。Glue使用不同数据集之间存在的逻辑链接来覆盖不同数据的可视化，并跨数据集传播选择。这些链接由用户指定，并且是任意灵活的。

完整的脚本功能。Glue是用Python编写的，并且建立在其标准科学库（即Numpy，Matplotlib，Scipy）之上。用户可以轻松地集成他们自己的python代码进行数据输入，清理和分析。

![img](../../../image/Typora/1142366-20180816110135669-2085166126.png)

## **Orange3**

交互式数据可视化

通过巧妙的数据可视化执行简单的数据分析。探索统计分布，箱形图和散点图，或深入了解决策树，层次聚类，热图，MDS和线性投影。即使您的多维数据也可以在2D中变得合理，特别是在智能属性排名和选择方面。

![img](../../../image/Typora/1142366-20180816110200046-1152680846.png)

老师和学生都喜欢它

在教授数据挖掘时，我们喜欢说明而不是仅仅解释。而橙色很棒。Orange在世界各地的学校，大学和专业培训课程中使用，支持数据科学概念的实践培训和视觉插图。甚至还有专门为教学设计的小部件。

附加组件扩展功能

使用Orange中可用的各种附加组件从外部数据源挖掘数据，执行自然语言处理和文本挖掘，进行网络分析，推断频繁项目集并执行关联规则挖掘。此外，生物信息学家和分子生物学家可以使用Orange通过差异表达对基因进行排序并进行富集分析。

![img](../../../image/Typora/1142366-20180816110249879-1992275632.png)

## **Rstudio**

R软件自带的有写脚本的工具，可是我不是很喜欢用（并不是说不好哈），我更喜欢用RStudio（网上还有Tinn-R，RWinEdt等）。因为我觉得其本身比较方便，另外在编程的时候有些功能很方便。下面这个界面是我修改了主题的，下面我将介绍如何修改主题，来方便编程。

![img](../../../image/Typora/1142366-20180816110309089-334407158.png)

# **结语**

现在你是不是发现用上anaconda就可以十分优雅简单的解决上面所提及的单个python环境所带来的弊端了呢, 而且也明白了其实这一切的实现并没有那么神奇.

当然anaconda除了包管理之外还在于其丰富数据分析包, 不过那就是另一个内容了, 我们先学会用anaconda去换一种方法管里自己的开发环境, 这已经是一个很大的进步了。


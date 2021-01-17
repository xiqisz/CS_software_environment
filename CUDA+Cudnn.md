## 1

我这里使用的是torch=1.2.0，官方推荐的Cuda版本是10.0，因此会用到cuda10.0，与cuda10.0对应的cudnn是7.4.1.5。

cuda10.0官网的地址是：
[cuda10.0官网地址](https://developer.nvidia.com/cuda-10.0-download-archive?target_os=Windows&target_arch=x86_64&target_version=10&target_type=exelocal)
cudnn官网的地址是：需要大家进去后寻找7.4.1.5。
[cudnn官网地址](https://developer.nvidia.com/cudnn)

官网下载是比较慢的，可以在百度云上下载，我给大家分享一手。

链接: https://pan.baidu.com/s/1znYSRDtLNFLufAuItOeoyQ
提取码: 8ggr

下载完之后得到这两个文件。

## 2

我这里使用的是tensorflow-gpu=1.13.2，因此会用到cuda10.0，与cuda10.0对应的cudnn是7.4.1.5，这个组合我实验过了，绝对是可以用的。

cuda10.0官网的地址是：
[cuda10.0官网地址](https://developer.nvidia.com/cuda-10.0-download-archive?target_os=Windows&target_arch=x86_64&target_version=10&target_type=exelocal)
cudnn官网的地址是：需要大家进去后寻找7.4.1.5。
[cudnn官网地址](https://developer.nvidia.com/cudnn)

官网下载是比较慢的，可以在百度云上下载，我给大家分享一手。

链接: https://pan.baidu.com/s/1znYSRDtLNFLufAuItOeoyQ
提取码: 8ggr

下载完之后得到这两个文件。

## 3

我这里使用的是tensorflow-gpu=2.2.0，因此会用到cuda10.1，与cuda10.1对应的cudnn是7.6.5.32，这个组合我实验过了，绝对是可以用的。

cuda10.1官网的地址是：
[cuda10.1官网地址](https://developer.nvidia.com/cuda-10.1-download-archive-base?target_os=Windows&target_arch=x86_64&target_version=10&target_type=exelocal)
cudnn官网的地址是：需要大家进去后寻找7.6.5。
[cudnn官网地址](https://developer.nvidia.com/cudnn)

官网下载是比较慢的，可以在百度云上下载，我给大家分享一手。

链接: https://pan.baidu.com/s/1kExUPePLanlKvkhgPiEy3g
提取码: w5m7

下载完之后得到这两个文件。

## 安装过程

>以 cuda10.0 + cudnn7.4.1.5为例

1.下载完之后得到这两个文件。

![image-20210114210404585](https://cdn.jsdelivr.net/gh/xiqisz/xiqisz-images/Typora/20210114210405.png)

2.下载好之后可以打开cuda_10的exe文件进行安装。

![image-20210114210512918](https://cdn.jsdelivr.net/gh/xiqisz/xiqisz-images/Typora/20210114210512.png)

>路径不要改

![image-20210114210549622](https://cdn.jsdelivr.net/gh/xiqisz/xiqisz-images/Typora/20210114210549.png)

![image-20210114210612446](https://cdn.jsdelivr.net/gh/xiqisz/xiqisz-images/Typora/20210114210612.png)

![image-20210114210647934](https://cdn.jsdelivr.net/gh/xiqisz/xiqisz-images/Typora/20210114210648.png)

这里选择自定义：

![image-20210114210742099](https://cdn.jsdelivr.net/gh/xiqisz/xiqisz-images/Typora/20210114210742.png)

![image-20210114210836059](https://cdn.jsdelivr.net/gh/xiqisz/xiqisz-images/Typora/20210114211041.png)

![image-20210114211136287](https://cdn.jsdelivr.net/gh/xiqisz/xiqisz-images/Typora/20210114211136.png)

![image-20210114211221802](C:/Users/SZ/AppData/Roaming/Typora/typora-user-images/image-20210114211221802.png)

安装完后在C盘这个位置可以找到根目录。
`C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0`
然后大家把Cudnn的内容进行解压。

![image-20210114212010205](https://cdn.jsdelivr.net/gh/xiqisz/xiqisz-images/Typora/20210114212010.png)

把这里面的内容直接复制到C盘的根目录下就可以了。

![image-20210114212250890](https://cdn.jsdelivr.net/gh/xiqisz/xiqisz-images/Typora/20210114212250.png)
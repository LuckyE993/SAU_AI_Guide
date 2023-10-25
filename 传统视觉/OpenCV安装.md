# **本文将会讲解如何在电脑上安装OpenCV-Python**

本人是按照OpenCV官方的教程 https://docs.opencv.org/4.6.0/d2/de6/tutorial_py_setup_in_ubuntu.html 安装的，有英文基础的可以看原文，英文文档没有那么难懂的。

**操作系统：Ubuntu 18.04**
Ubuntu18.04已经停止维护了，后续可以使用Ubuntu20.04进行安装
PS：如果说你没有学过Linux的相关命令也没关系，也可以往下走。
**Python版本：3.6.9，不要使用过高的版本建议使用 3.7.9 以下的版本进行后续流程**

**Opencv版本：4.6.0**
最新版本为4.8.0，推荐用4.6.0。

**不推荐使用```sudo apt-get install python3-opencv```进行安装，这里选择直接编译源码的方式进行安装**

# 编译源码安装 OpenCV
## 编译前准备
### 如果你不会科学上网的话建议bing搜索Ubuntu2004换源教程进行换源,建议更换成清华源
可以参考以下链接进行换源 https://www.cnblogs.com/zqifa/p/12910989.html
### 安装依赖
首先要安装编译工具组件Cmake和GCC，G++
```
sudo apt-get install cmake
sudo apt-get install gcc g++ 
```
sudo 是提权，过程可能需要输入一下初始设置的密码，等待安装完成。

这里我们使用Python3进行开发，执行以下命令：
```
sudo apt-get install python3-dev python3-numpy
```
numpy库是非常重要的Python库，包含开发过程中需要的所有类型转换所需要的函数以及方法，这里贴一个官方链接 https://numpy.org/learn/


接下来我们安装一下窗口显示GUI功能、摄像头以及视频支持的库
```
sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev
sudo apt-get install libgstreamer-plugins-base1.0-dev libgstreamer1.0-dev
sudo apt-get install libgtk-3-dev
```

可选项（推荐）：更新一下原有的图像支持库：
```
sudo apt-get install libpng-dev
sudo apt-get install libjpeg-dev
sudo apt-get install libopenexr-dev
sudo apt-get install libtiff-dev
sudo apt-get install libwebp-dev
```

## 编译步骤一 —— 下载源码
至此，你已经完成了编译源码所需要的所有支持。现在可以开始下载源码了。BTW(By the way)，你需要一个非常有用的工具名字叫：Git ,执行以下代码即可进行安装Git并下载opencv的源码了。
```
sudo apt-get install git
git clone https://github.com/opencv/opencv.git
```
它将在当前目录中创建一个文件夹“opencv”。克隆可能需要一些时间，具体取决于您的互联网连接。

现在打开终端窗口并导航到下载的“opencv”文件夹。创建一个新的“build”文件夹并导航到它。
```
cd opencv(可能是这个文件夹)
```
然后执行以下命令创建一个名为"build"的文件夹
```
mkdir build
cd build
```

## 编译步骤二：编译OpenCV源码
接下来就可以执行以下语句自动执行
```
cmake ../
```
当你看到类似于以下信息的时候就可以继续往下走了
>-- Python 3:
-- Interpreter: /usr/bin/python3.4 (ver 3.4.3)
-- Libraries: /usr/lib/x86_64-linux-gnu/libpython3.4m.so (ver 3.4.3)
-- numpy: /usr/lib/python3/dist-packages/numpy/core/include (ver 1.8.2)
-- packages path: lib/python3.4/dist-packages

现在要开始正式编译源代码了，这个过程很漫长（40min），如果是虚拟机的话这个过程会更长。可以尝试[多线程编译](https://blog.csdn.net/sinat_35178307/article/details/118783657)。
```
 make #这里可以看博客结合自己的电脑改为多线程
 sudo make install #这一步可以进行安装
```
接下来按照自己的python版本修改以下python命令（比如我的python版本是3.6）
```
sudo echo "/usr/local/lib/python3.6/site-packages" | sudo tee -a /usr/local/lib/python3.6/dist-packages/cv2.pth

```
## 验证安装
直接在终端输入python3 输入
```
import cv2
print(cv2.__version__)
```

如果能够正常打印OpenCV版本 **4.6.0** 的话，那么恭喜你已经顺利安装完成了。



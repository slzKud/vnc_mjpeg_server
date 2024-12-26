# vnc_mjpeg_server
一个基于[neatvnc](https://github.com/any1/neatvnc)播放JPEG图片的VNC服务器。

[演示视频](https://www.bilibili.com/video/BV1nLCwYXE7F)
## 依赖
* pixman
* libjpeg
* [aml](https://github.com/any1/aml)
* [neatvnc](https://github.com/any1/neatvnc)
## 编译
~~~
mkdir build
cd build
cmake ..
make
~~~
## 如何更改播放图片参数
1. 更改jpegset.h
~~~
#define MJPEG_COUNT 6574 // 照片张数
// 照片路径模板，须符合printf格式并包含一个%d代表照片的帧号，帧号从0开始。
#define MJPEG_FILE_SET ("./ba/BA%04d.jpg") 
#define MJPEG_FPS 30 // 播放帧率，1秒多少张
~~~
2. 执行的时候带上参数
~~~
./mjpeg_server [MJPEG_FILE_SET] [MJPEG_COUNT]
~~~
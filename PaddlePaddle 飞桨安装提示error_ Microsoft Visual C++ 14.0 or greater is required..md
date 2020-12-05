## 1.问题现象
>在安装PaddlePaddle或其他python包时，经常会出现下面错误提示，导致安装失败。
```bash
error: Microsoft Visual C++ 14.0 or greater is required. Get it with "Microsoft C++ Build Tools": https://visualstudio.microsoft.com/visual-cpp-build-tools/
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201128133223471.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)

## 2.解决办法
>Microsoft Visual C++ 14.0 is required，点击下载VC build tools安装再执行

### 下载地址 Microsoft Visual C++ 14.0 ：  [https://go.microsoft.com/fwlink/?LinkId=691126](https://go.microsoft.com/fwlink/?LinkId=691126)
>然后一路next，默认即可，或者针对性选择。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201128133123780.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201128133152282.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
## 3.注意
>注意：安装完后，需要重新打开新的终端命令窗口

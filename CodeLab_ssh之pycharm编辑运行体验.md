# codelab之pycharm编辑运行体验

一直想着ssh开着，本地编辑运行呢，这不，今天就这么干了，给大家分享下。

## 1.开启ssh端口

老套路，导入docker镜像，开启container实例。

```bash
docker load --input codelab_cpu.0.3.1.tar.gz

docker run -d -p 80:8670 -p 22:22 --privileged hub.baidubce.com/jarvis2/codelab:cpu2020-12-03
```

具体hub.baidubce.com/jarvis2/codelab:cpu2020-12-03名看你导入后的显示，我这里开了2端口，80端口访问notebook，22端口为ssh。

## 2.docker开启ssh服务

主要由2步。一是设置root密码，二是安装openssh-server软件。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201205235017742.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201205234646571.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)


可见openssh-server早已安装，需要做的就是设置密码，开启端口映射。

## 3.设置pycharm

设置很简单，看图。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201205234808479.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201205234808253.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201205234808251.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201205234928191.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)






## 4.使用

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020120523495448.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020120523495455.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020120523495419.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70)






 

真好用，不用来回上传下载了。

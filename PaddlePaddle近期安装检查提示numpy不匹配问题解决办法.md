@[TOC](目录)

# PaddlePaddle近期安装检查提示numpy不匹配问题解决办法


>最近由于numpy升级版本为1.19.4造成部分匹配不适，安装检查报错，如下所示。
## 现象
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020112313502156.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201123135204231.png#pic_center)

## 解决办法
>卸载当前版本numpy，安装1.19.3版本

```bash
pip uninstall numpy
pip install numpy==1.19.3
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201123135232186.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)


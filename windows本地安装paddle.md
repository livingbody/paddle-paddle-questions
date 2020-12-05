本安装方案在windows和mac系统下经过测试。使用anaconda安装，可以兼容多个python版本。
<font color='red'>不要使用中文作为电脑的用户名，有可能会出现莫名错误。软件的安装也尽量不要使用中文路径</font>
## step1 安装anaconda
1.下载地址：https://www.anaconda.com/products/individual 
按照自己的电脑配置选择下载类型
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200727230246175.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70)
2.根据下列步骤安装anaconda
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020072723084281.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200727230925913.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70)
推荐勾选第一个框，将anaconda加入到环境变量中。	
<font color='red'>一定要勾选第一个框，不然在cmd中就会无法找到conda指令</font>



## step2 使用conda创建虚拟环境
  (0)更换conda国内源
  ```python
  conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
 conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
 conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/Paddle/
 conda config --set show_channel_urls yes
   ```
分别在cmd或者conda自带的命令行(anaconda prompt)中运行如下指令
（1）创建名为paddle的conda环境，使用的python版本是python3.7
```python
conda create -n paddle python=3.7

```
（2）使用conda激活paddle环境
```python
conda activate paddle
```
（3）使用pip安装paddlepaddle
```python
python -m pip install paddlepaddle -i https://mirror.baidu.com/pypi/simple 
```
上诉三条代码分别运行完成后，进入python中使用下面3两条命令测试
	
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200727232536926.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70)














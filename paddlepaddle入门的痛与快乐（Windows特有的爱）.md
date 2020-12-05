@[TOC](paddlepaddle入门的痛与快乐（Windows特有的爱）)

大家好，这里是小鸭学院助教团的三岁，每当老师们，兴高采烈来到我们的paddle学堂，往往因为各种原因被我们的Windows系统“摆了一道”，安装paddle出现各类问题，在这里我们汇集各类原因，给大家一一排雷
## paddlepaddle有关小知识的说明
paddle官网：[https://www.paddlepaddle.org.cn/](https://www.paddlepaddle.org.cn/)
paddle官方安装问题解答：[https://www.paddlepaddle.org.cn/documentation/docs/zh/2.0-rc/faq/install_cn.html](https://www.paddlepaddle.org.cn/documentation/docs/zh/2.0-rc/faq/install_cn.html)
**里面的安装模块有详细的说明**
简单列举：
版本     | 2.0|1.8|1.7
-------- | -----|------|--
python版本  | 3.5.1\~3.8._(64 bit)| 3.5.1\~3.8.\_(64 bit)|3.5.1~3.7.\_(64 bit)
pip版本 | 9.0.1+ (64 bit)|9.0.1+ (64 bit)|9.0.1+ (64 bit)
CUDA版本  | CUDA 9/10.0/10.1/10.2|CUDA 9.0/9.1/9.2/10.0|CUDA 9.0/9.1/9.2/10.0
## win环境下安装paddlepaddle-cpu版本
cpu版本安装简单，只需要按照流程走即可，分分钟搞定
### 1.点开官网链接：
[https://www.paddlepaddle.org.cn/install/quick/zh/1.8.5-windows-pip](https://www.paddlepaddle.org.cn/install/quick/zh/1.8.5-windows-pip)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201115114809873.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
### 2.查看配置情况
环境准备
Windows 7/8/10 专业版/企业版 (64bit)
GPU版本支持CUDA 9.0/9.1/9.2/10.0/10.1，且仅支持单卡
Python 版本 2.7.15+/3.5.1+/3.6/3.7 (64 bit)
pip 版本 9.0.1+ (64 bit)
#### 2.1 python版本确认
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201115115201787.png#pic_center)
打开cmd（Windows键+R 输入cmd回车即可）在里面输入`python --version`
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201115115431819.png#pic_center)

请保证版本在paddle适配范围！
##### 2.1.1未查找到python或python不属于内部命令报错
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201115120012893.png#pic_center)

* 原因1：未安装python
**解决方案：**安装python
参考资料：[三岁学编程之python安装（最细教程）](https://blog.csdn.net/weixin_45623093/article/details/105508265)
注意：记得勾选配置环境变量
*原因2：未勾选配置环境变量导致环境变量未配置
（以win10为例）打开**此电脑**点击右键**属性**点击**高级系统设置**在**系统变量**中对path进行自定义的添加

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201115133154448.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201115133217996.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201115133241791.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
#### 2.2 pip版本确认
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201115133807986.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
在cmd中输入：`python -m ensurepip`和`python -m pip --version`
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201115134325591.png#pic_center)
#### 2.3开始安装paddle
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020111513452816.png#pic_center)
以上为安装系统版本，没有指定版本型号。
可以使用一下代码指定安装的版本。
`python -m pip install paddlepaddle==1.8.5 -i https://mirror.baidu.com/pypi/simple`
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201115134807814.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
#### 2.4测试安装是否成功
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201115135015565.png#pic_center)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201115134951593.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
以上的为成功版本，如果没有出现`Your Paddle Fluid is installed succesfully!`
说明安装没有成功需要排错，重新安装
#### 可能出现的问题
下图为某个报错：![在这里插入图片描述](https://img-blog.csdnimg.cn/20201115135452448.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
原因为pip的版本不正确，需要用`pip install --upgrade pip`对pip进行升级再尝试paddle的安装。
## win环境下用conda安装paddle-gpu版本
#### 3.1版本确认
版本确认等同于2.1
#### 3.2conda安装
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201115151620129.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
点击：[https://www.anaconda.com/](https://www.anaconda.com/)进入官网，获取对应版本安装即可
安装成功即可开始使用
注：[conda安装教程及conda的cpu版本教程参考](https://blog.csdn.net/weixin_41450123/article/details/107623707)
#### 虚拟环境的创建
* 创建
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020111517551179.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
`conda create -n {自己要的名字} python={你要的版本}`
* 2.查看位置
`where python`
* 3.激活
`activate {自己要的名字}`
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201115180017192.png#pic_center)
括号中是“自己要的名字”就是进入了环境。

* 配置国内镜像地址（清华源）

      conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
      conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
      conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/Paddle/
      conda config --set show_channel_urls yes
* 查看处理器架构
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201121160436445.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
确保处理器是符合官方安装要求的，若不符合请更换设备

* 安装paddle
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201121154334414.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
根据自己的实际情况匹配进行安装。
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020112115443158.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
根据提示输入`y`进行下一步的安装。
* 验证环节
当安装完毕以后开始验证
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201121154706704.png#pic_center)
在python环境下输入代码：
`import paddle.fluid`
再输入：
`paddle.fluid.install_check.run_check()`
只要出现：
“Your Paddle Fluid is installed succesfully!”
就是安装成功。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201121161005621.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)


### 常见GPU报错及推荐解决方案
注：推荐解决方案不代表一定行，请根据实际情况进行处理
可以参考文档：[https://aistudio.baidu.com/aistudio/projectdetail/697227](https://aistudio.baidu.com/aistudio/projectdetail/697227)
#### 1.No module named 'paddle'
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201121155539761.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
* 原因：未安装成功或未使用环境版本不正确
* 原因说明：
未安装成功：可能由于网络配置等原因在安装中出现了问题；
使用环境版本不正确：使用的版本和安装版本不是同一个（conda可以同时生成多个虚拟环境，有可能是环境使用不正确）
* 解决方案：
未安装成功：（排除版本问题后）使用说明出现逐步骤安装，遇有问题及时查看官方文档和百度，实在处理不了咨询有关专业人员。
使用环境版本不正确：查看自己安装的环境及安装的名字通过`python --version`查看环境位置，对python的地址进行修改后再使用代码进行验证。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201121160529530.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
#### 2.Dll load  failed：找不到指定的模块
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201121161743976.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
* 原因：有可能是缺失cv模块导致的
* 处理办法：可以安装`Microsoft Visual C++14.0`及以上版本解决
* 特殊情况：已经安装了无效但是有显示某个`.dll`文件缺失可以单独安装文件
* 例：`cublas64_90.dll not found.`
有可能是.dll文件的缺失导致的，具体解决方案可以查看：[https://blog.csdn.net/beauthy/article/details/108320484](https://blog.csdn.net/beauthy/article/details/108320484)

#### requires OpenCV-python<=xxxxxx,but you'll have … 
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020111516131178.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
* 原因：显示opencv的版本太高和现在的paddlepaddle要求的版本不匹配
* 处理方法：
在cmd中输入`pip uninstall opencv`(提前确认python环境是否正确)
输入：`pip install opencv`
重新安装，如果重新安装版本过高请指定版本。
如果下载速度过慢请更换源。

#### qt-5.9.7链接后脚本失败
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201121164807251.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
* 原因：缺失缺少变量申明
* 解决方法：将以下内容添加到“路径系统变量”中：％SystemRoot％\ system32
* 参考地址：[https://github.com/ContinuumIO/anaconda-issues/issues/10949](https://github.com/ContinuumIO/anaconda-issues/issues/10949)
#### WindowsError: [Error 193] %1 is not a valid Win32 application
* 原因：Numpy版本或其他东西存在不兼容，
* 解决方法：numpy是1.18.3 卸载升级为1.18.4解决的问题

#### pip版本不正确需要更新
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201121170014852.png#pic_center)
类似的报错就是pip版本不对：只需要输入里面引号内的部分即可升级。个别情况需要自定义安装可以参考：https://aistudio.baidu.com/aistudio/projectdetail/697227
[添加链接描述](https://aistudio.baidu.com/aistudio/projectdetail/697227)


### python环境的添加及切换
#### cmd中
1、确认自己需要切换版本的具体位置
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201121170513689.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
2、`cd 版本地址`
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201121170558418.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201121170638282.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
3、输入`python`查看
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201121170653516.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)

#### pycharm中：
1、打开pycharm查看右下角的环境
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201121170854571.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201121170912674.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
2、选择切换环境（根据实际需求进行切换）
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201121170946905.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
3、如果此处没有环境点击`add inter…`进行添加
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201121171057501.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201121155423782.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201121171336518.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTQ1MDEyMw==,size_16,color_FFFFFF,t_70#pic_center)
以上就是常见的安装问题及对应的安装方式，如有问题请及时留言，我们会尽快回复，我们也会及时处理您反馈的问题。
这里是小鸭学院，感谢大家的支持！！！

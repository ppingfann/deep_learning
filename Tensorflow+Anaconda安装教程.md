#Tensorflow安装教程（Anaconda环境下）
##Anaconda安装
1、去Anaconda官网下载适合你的版本，我是安装python2.7 64bit版本（Linux环境下）  
	
	https://www.continuum.io/downloads#linux

上面是官网的地址。  
2、在下载完之后运行sh即可完成Anaconda的安装  
3、测试Anaconda是否安装完成：在shell中输入python，会显示以下内容

	Python 2.7.13 |Anaconda custom (64-bit)|
这样就可疑确认是安装成功了。
##tensorflow运算环境的搭建
    # Python 2.7  
    $ conda create -n tensorflow python=2.7  
      
    # Python 3.5  
    $ conda create -n tensorflow python=3.5
上面给出的是python2.7和3.5版本的环境创建命令。

##安装Tensorflow
0、在安装之前需要激活tensorflow的计算环境

	#激活
	$ source activate tensorflow

	#关闭
	$ source deactivate tensorflow
1、使用pip来安装Tensorflow
		
	# Ubuntu/Linux 64-bit, CPU only, Python 2.7:
	(tensorflow)$ pip install --ignore-installed --upgrade https://storage.googleapis.com/tensorflow/linux/cpu/tensorflow-0.8.0rc0-cp27-none-linux_x86_64.whl    //vpn
	
	#在安装下面这个版本之前，你必须确认你已经装了CUDA，才能安装有GPU加速的版本
	#你的GPU必须是英伟达公司的= = 
	# Ubuntu/Linux 64-bit, GPU enabled, Python 2.7. Requires CUDA toolkit 7.5 and CuDNN v4.
	# For other versions, see "Install from sources" below.
	(tensorflow)$ pip install --ignore-installed --upgrade https://storage.googleapis.com/tensorflow/linux/gpu/tensorflow-0.8.0rc0-cp27-none-linux_x86_64.whl
   
注：可能在安装的时候出现网络错误，所以建议大家在安装的时候挂上VPN

##运行你的第一个Tensorflow程序
0、激活Tensorflow运算环境  
1、进入python环境  
2、在环境中运行以下代码

	import tensorflow as tf
	hello = tf.constant('Hello, TensorFlow!')
	sess = tf.Session()
	print sess.run(hello)
	Hello, TensorFlow!
	a = tf.constant(10)
	b = tf.constant(32)
	print sess.run(a+b)
	42

你也可以将以上的代码删掉结果之后写到一个.py的文件之下，在激活Tensorflow运算环境之后，和执行其他的python代码一样的执行。

这样就完成了Tensorflow和Anaconda环境的集成安装。

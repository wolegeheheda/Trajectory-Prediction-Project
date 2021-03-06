# 资源下载
[VMware15-提取码gcme](https://pan.baidu.com/s/1nt87TDZg-T0L4Fd0RikjJQ)

[Ubuntu18.04.2-提取码dgh7](https://pan.baidu.com/s/1O9ol3tsvVpnrmT-lWBkzRw)


# 参考教程
## GTX1050Ti安装Ubuntu18.04和显卡驱动 ##
这里提供两个链接可供参考[1](https://blog.csdn.net/nwpushuai/article/details/79935740)，[2](https://blog.csdn.net/u014003662/article/details/88547512)

sudo apt-get install nvidia-440时，遇到“E：无法定位软件包”的问题，此时打开软件更新器-附加驱动可使用nvidia-440
## Opencv参考
[Ubuntu 16.04 安装opencv的各种方法](https://blog.csdn.net/ksws0292756/article/details/79511170)

[Ubuntu18.04安装opencv3.4.3](https://blog.csdn.net/qq_41080854/article/details/88609795?depth_1-utm_source=distribute.pc_relevant.none-task&utm_source=distribute.pc_relevant.none-task)

## PyCharm Professional Edition安装流程
[PyCharm各版本下载](https://www.jetbrains.com/pycharm/download/other.html)

[PyCharm安装参考](https://www.cnblogs.com/booturbo/archive/2019/10/25/11738174.html);
其中jetbrains-agent.jar下载失效，请参考[这里](https://www.jb51.net/softs/672190.html)

[后续利用PyCharm远程调试代码](https://www.cnblogs.com/xuegqcto/p/8621689.html)

[PyCharm入门](https://www.evget.com/article/2018/8/24/28417.html)

## anaconda安装参考
[安装教程](https://blog.csdn.net/weixin_38548467/article/details/98883792?depth_1-utm_source=distribute.pc_relevant.none-task-blog-OPENSEARCH-2&utm_source=distribute.pc_relevant.none-task-blog-OPENSEARCH-2);按照安装流程运行**conda -V**测试时可能出错，可先执行**source ~/.bashrc**后再测试

## 在远程服务器创建虚拟环境，并配置pytorch、tensorboard
0. 在pycharm中远程连接服务器。以下操作都在服务器的命令行中实现。[如何使用pycharm远程调试](https://www.cnblogs.com/xuegqcto/p/8621689.html)

1. 使用wget命令下载anaconda，建议使用清华源或其他国内源 [具体步骤参考](https://www.cnblogs.com/zwq-zju/p/9715162.html)

2. [创建/删除虚拟环境](http://www.bieryun.com/6461.html) 激活虚拟环境报错可尝试 export PATH="~/anaconda3/bin:$PATH"

3. 使用nvidia-smi命令查看CUDA，去[官网](https://pytorch.org/get-started/locally/)查看对应命令并在虚拟环境中运行

4. 这里仅安装tensorboard：在虚拟环境下pip install tensorboard

5. [在pycharm中使用远程虚拟环境](https://www.jb51.net/article/175949.htm)，你也可以参考**PyCharm Professional Edition安装流程**中的[后续利用PyCharm远程调试代码](https://www.cnblogs.com/xuegqcto/p/8621689.html)

## 远程服务器调用tensorboard
由于在远程服务器使用tensorboard，所以网上常规的加--host=127.0.0.1并没有用-_-

以pycharm为例，做法如下：

1. 打开pycharm本地终端输入ssh -L 16006:127.0.0.1:6006 username@remote_server_ip 这里16006:127.0.0.1代表自己机器上的16006号端口，6006是服务器上tensorboard使用的端口，tensorboard默认使用6006

2. 在服务器上使用6006端口启用tensorboard： tensorboard --logdir=/home/xxx/logs/ --port=6006，如果这里端口被占用，需要对上一步和这一步的port进行更改

3. 本地浏览器输入127.0.0.1:16006即可

ps 建议使用火狐或谷歌浏览器，还出现问题可能需要将浏览器更新

## 双系统ubuntu对windows只读
启动系统时先选择windows进入，然后重启电脑进入ubuntu系统即可

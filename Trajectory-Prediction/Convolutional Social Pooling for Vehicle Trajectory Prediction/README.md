# 对Convolutional Social Pooling for Vehicle Trajectory Prediction这篇论文的代码复现具体流程 [原地址](https://github.com/nachiket92/conv-social-pooling)

## 数据准备
从[这里](https://data.transportation.gov/Automobiles/Next-Generation-Simulation-NGSIM-Vehicle-Trajector/8ect-6jqj)点击'show more' 下载 'US-101-LosAngeles-CA.zip' 和 'I-80-Emeryville-CA.zip'，其中包含该项目所需的6个txt文件

使用matlab运行preprocess_data.m，需要将其中的txt文件目录更改为自己下载后的文件目录

在项目根目录下新建data文件夹，将preprocess_data.m生成的文件放入。之后新建trained_models文件夹用于保存train后的文件

## 训练模型
运行train.py，将参数use_maneuvers分别改为True和False训练两次，同时更改保存名称。

不做任何更改直接运行后会在trained_models中保存名为cslstm_m.tar的文件

## 评估结果
根据use_maneuvers的值调用训练后的文件，运行evaluate.py，这里会生成一个25个数字的向量，每个数据之间表示间隔0.2s的评估数据

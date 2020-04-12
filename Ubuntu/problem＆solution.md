## 直接从win拖拽文件到虚拟机中导致虚拟机卡死崩溃
1. 将VM版本和VMtools更新到最新版本（15.1+）（未测试过是否有用）
2. 配置共享文件夹，通过共享文件夹交换文件 **建议使用该方法进行文件传输**

## 虚拟机意外关闭后重启后无法联网并且右上角网络图标消失
终端尝试以下操作
1. sudo service network-manager stop
2. sudo rm /var/lib/NetworkManager/NetworkManager.state 
3. sudo service network-manager start

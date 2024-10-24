# App动态测试实验

## 准备工作

- python: [anaconda](https://blog.csdn.net/tqlisno1/article/details/108908775) 
- java: [JDK](https://www.oracle.com/java/technologies/downloads/#jdk23-windows)
> 最新版的JDK安装程序会自动配置环境变量
- Android SDK: [Android Studio](https://developer.android.google.cn/studio?hl=zh-cn)
> Android Studio在进行安装时需要连接外网
在安装完成后将platform-tools路径添加到系统环境变量
![Snipaste_2024-10-24_16-57-25](https://github.com/user-attachments/assets/94b09b19-cc36-4595-b44c-f70f3500086b)
在命令行中输入adb进行测试
![Snipaste_2024-10-24_16-56-00](https://github.com/user-attachments/assets/1f4634dc-c47f-4a4d-9886-46625d8e59f0)
- 模拟器: [genymotion](https://www.genymotion.com/product-desktop/download/)
> 选择VirtualBox和genymotion
![image](https://github.com/user-attachments/assets/51f3d735-fa72-4788-bf58-61c80d5a5842)
配置虚拟机
![image](https://github.com/user-attachments/assets/b1037360-ae7a-4dbc-b696-0713b91724f6)
![image](https://github.com/user-attachments/assets/b1d7f7b0-116a-44fd-b15b-a249154e318a)
启动虚拟机后，可以在adb中看到该虚拟机
![image](https://github.com/user-attachments/assets/737224ea-2fb5-4a3e-8f92-0cbdacd8adb5)
- 测试工具: [droidbot](https://github.com/honeynet/droidbot)
> 克隆仓库`git clone https://github.com/honeynet/droidbot.git`
打开`setup.py`，将`androguard>=3.4.0a1`修改为`androguard==3.4.0a1`
在项目文件夹打开终端，输入`pip install -e .`安装droidbot
![image](https://github.com/user-attachments/assets/95fe5dde-48a8-4d49-8404-22937396ae44)
安装完成后，输入`droidbot -h`
![image](https://github.com/user-attachments/assets/3fdaaa85-7d08-46d9-9b07-f6246daf321f)

## 开始测试
输入指令`droidbot -a <path_to_apk> -o output_dir`开始测试
![image](https://github.com/user-attachments/assets/5fbad47f-2428-4d66-8aef-e83f53e396cc)
在测试一段时间后，打开输出文件夹中的报告
![image](https://github.com/user-attachments/assets/98031987-ba71-4914-9c31-92e624e03916)
点击节点或边可以看到相应的信息
![image](https://github.com/user-attachments/assets/576ebd39-69d4-4a5f-9d14-bf88d49ec34f)


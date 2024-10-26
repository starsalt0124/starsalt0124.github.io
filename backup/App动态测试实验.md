# App动态测试实验

## 准备工作

- python: [anaconda](https://blog.csdn.net/tqlisno1/article/details/108908775) 
- java: [JDK](https://www.oracle.com/java/technologies/downloads/#jdk23-windows)
> [!TIP]
> 最新版的JDK安装程序会自动配置环境变量
- Android SDK: [Android Studio](https://developer.android.google.cn/studio?hl=zh-cn)
> [!NOTE]
> Android Studio在进行安装时需要连接外网

在安装完成后将platform-tools路径添加到系统环境变量
![image](https://github.com/user-attachments/assets/a28e9e1b-630b-4219-83a2-27efaa5c8bf4)
在命令行中输入adb进行测试
![Snipaste_2024-10-24_16-56-00](https://github.com/user-attachments/assets/1f4634dc-c47f-4a4d-9886-46625d8e59f0)
- 模拟器: [genymotion](https://www.genymotion.com/product-desktop/download/)
选择VirtualBox和genymotion
![image](https://github.com/user-attachments/assets/51f3d735-fa72-4788-bf58-61c80d5a5842)
配置虚拟机
![image](https://github.com/user-attachments/assets/b1037360-ae7a-4dbc-b696-0713b91724f6)
![image](https://github.com/user-attachments/assets/b1d7f7b0-116a-44fd-b15b-a249154e318a)
启动虚拟机后，可以在adb中看到该虚拟机
![image](https://github.com/user-attachments/assets/737224ea-2fb5-4a3e-8f92-0cbdacd8adb5)
- 测试工具: [droidbot](https://github.com/honeynet/droidbot)
克隆仓库`git clone https://github.com/honeynet/droidbot.git`
打开`setup.py`，将`androguard>=3.4.0a1`修改为`androguard==3.4.0a1`
在项目文件夹打开终端，输入`pip install -e .`安装droidbot
![image](https://github.com/user-attachments/assets/95fe5dde-48a8-4d49-8404-22937396ae44)
安装完成后，输入`droidbot -h`
![image](https://github.com/user-attachments/assets/3fdaaa85-7d08-46d9-9b07-f6246daf321f)

## 测试 - droidbotdemo.apk
输入指令`droidbot -a <path_to_apk> -o output_dir`开始测试
![image](https://github.com/user-attachments/assets/bcfdea3e-35e4-4f31-99fb-4132bcdc5033)
在测试一段时间后，打开输出文件夹中的报告
![image](https://github.com/user-attachments/assets/98031987-ba71-4914-9c31-92e624e03916)
点击节点或边可以看到相应的信息
![image](https://github.com/user-attachments/assets/576ebd39-69d4-4a5f-9d14-bf88d49ec34f)

## 测试 - F-Droid : Nex Notes

从开源app网站F-Droid下载软件进行测试，这里选择了[Nex Notes](https://f-droid.org/zh_Hans/packages/com.swatian.nexnotes/)——一个记录日志的软件
![image](https://github.com/user-attachments/assets/977dffbb-aedb-46b3-8146-8163af297f89)
使用droidbot进行测试
![image](https://github.com/user-attachments/assets/87c6fa1d-6943-4dc5-809a-e46351a3c2d9)
可以发现droidbot的测试速度还是比较慢的，且默认使用的算法UtgGreedySearchPolicy在事件的选择上很少为“最优解”，经常在两个节点之间跳来跳去，但胜在通用性强，操作类似于正常使用
![image](https://github.com/user-attachments/assets/553e79ef-1a15-4f98-956c-a58843252abe)


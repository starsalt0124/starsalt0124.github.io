# App静态分析实验

## 创建具有soot依赖的项目
创建新项目，选择Maven作为构建系统
![image](https://github.com/user-attachments/assets/ffe977b5-c441-4bca-98f5-bdc4012a5c49)
在`pom.xml`文件中添加：
```java
<dependencies>
  <dependency>
    <groupId>ca.mcgill.sable</groupId>
    <artifactId>soot</artifactId>
    <version>4.1.0</version>
  </dependency>
</dependencies>
``` 
编辑`pom.xml`，并重新加载项目
![image](https://github.com/user-attachments/assets/15bae121-d2f6-4465-94d2-48c790d1963b)

## 案例一：分析java字节码文件
按照指导手册提示编写代码，通过soot解析类的继承关系，并打印出class文件的jimple表示
![image](https://github.com/user-attachments/assets/e7669ace-0df2-44bc-8ab1-b3124a70a74c)
![image](https://github.com/user-attachments/assets/7815ca4f-3d7c-4dfe-84e0-11789fb37f38)
编写测试代码

> [!CAUTION]
> 编译时使用的javac版本应该与soot项目保持一致

![image](https://github.com/user-attachments/assets/6bf2009b-5a0c-47ac-81f7-6b4ce23c1fef)

运行soot项目，可以看到成功输出了测试程序的信息
![image](https://github.com/user-attachments/assets/0ba78138-cc6c-41f8-bcdf-a75eebb0e0a6)

## 案例二：Soot分析apk文件
下载安卓SDK
```shell
git clone https://github.com/Sable/android-platforms.git
``` 
按照指导手册提示编写代码，通过soot解包安卓apk文件，遍历各个类中的方法，打印具体方法的jimple表示
![image](https://github.com/user-attachments/assets/d8237fcd-1fe7-4291-840c-81a1ddce9c8c)
![image](https://github.com/user-attachments/assets/0f1d0229-196a-4c9b-a79c-d047f48f1b96)
运行代码，可以看到具体方法的jimple表示
![image](https://github.com/user-attachments/assets/64bae112-061f-4263-823a-40a641360f95)
查看output文件夹，可以看到类的jimple表示
![image](https://github.com/user-attachments/assets/fe03a840-bdf7-4ba3-8bb8-e469932768eb)

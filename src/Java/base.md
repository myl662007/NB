##java相关基础

- Java语言作者
 		
        詹姆斯·高斯林（James Gosling）

- JRE
        
        Java Runtime Environment    Java运行环境
        包括Java虚拟机(JVM Java Virtual Machine)和Java程序所需的核心类库等，如果想要运行一个开发好的Java程序，计算机中只需要安装JRE即可。
        
- JDK
        
        Java Development Kit    Java开发工具包
        JDK是提供给Java开发人员使用的，其中包含了java的开发工具，也包括了JRE。

- JDK,JRE,JVM的作用和关系
        
        我们使用JDK开发一个Java程序,交给JRE运行,最终由JVM执行Java程序

- JDK安装路径下的目录解释

        bin目录：该目录用于存放一些可执行程序。
        如javac.exe（java编译器）、java.exe(java运行工具)，jar.exe(打包工具)和javadoc.exe(文档生成工具)等。
	    
	    db目录：db目录是一个小型的数据库。(database)
	    
	    jre目录："jre"是 Java Runtime Environment 的缩写，意为Java程序运行时环境。
        此目录是Java运行时环境的根目录，它包括Java虚拟机，运行时的类包，Java应用启动器以及一个bin目录，
	    
	    include目录：由于JDK是通过C和C++实现的，因此在启动时需要引入一些C语言的头文件，该目录就是用于存放这些头文件的。
	    
	    lib目录：lib是library的缩写，意为 Java 类库或库文件，是开发工具使用的归档包文件。
	    
	    src.zip文件：src.zip为src文件夹的压缩文件，src中放置的是JDK核心类的源代码，通过该文件可以查看Java基础类的源代码。

- 如何运行java
    
        生成class类文件
        javac HelloWord.java
        
        运行
        java HelloWord
        
- 注意大小写问题
        
        a:class写成Class
        b:String写成string
        c:System写成system

- Math方法

        Math.random() 生成0-1的随机数

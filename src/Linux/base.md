##Linux常用语法：

- 查看空间使用：
        
        df -h
        
- 查看cpu的使用率
    
        top

- 安装zip

        yum install -y unzip zip       
- 压缩

        zip ***.zip ***.sql

- 查看日志如何定位：
        
        cat /var/log/secure|grep "Nov 11“
- 查看文件的行数
    
        wc -l httppost.log


- Linux 文件基本属性
        
        drwxr-xr-x 2 root root 4096 9月  27 16:22 huijuquanqiu.mylzn.cn
        -rw-r--r-- 1 root root   39 11月  7 12:04 index.php
        
        当为[ d ]则是目录
        当为[ - ]则是文件；
        若是[ l ]则表示为链接文档(link file)；
        若是[ b ]则表示为装置文件里面的可供储存的接口设备(可随机存取装置)；
        若是[ c ]则表示为装置文件里面的串行端口设备，例如键盘、鼠标(一次性读取装置)。

- Linux 文件和目录管理
        
        //处理目录的常用命令
        ls  列出目录
        cd  切换目录
        pwd 显示目前的目录
        mkdir 创建一个新的目录
        rmdir 删除一个空的目录
        cp  复制文件或目录
        rm  移除文件或

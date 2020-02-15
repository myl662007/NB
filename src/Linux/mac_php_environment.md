##MAC下删除和搭建PHP环境

### PHP环境的删除

- mysql环境的删除

        1. sudo rm -rf /usr/local/mysql*
        2. sudo rm -rf /Library/StartupItems/MySQLCOM
        3. sudo rm -rf /Library/PreferencePanes/My*
        4. sudo rm -rf /Library/Receipts/mysql*
        5. rm -rf ~/Library/PreferencePanes/My*
        6. sudo rm -rf /var/db/receipts/com.mysql.*
        7. rm -rf /usr/local/Cellar/mysql
        8. rm -rf /usr/local/var/mysql/
        9. rm -rf /tmp/mysql.sock
        10.rm -rf /tmp/mysql.sock.lock
        11.rm -rf /usr/local/etc/my.cnf 
        12.brew cleanup
        
- php环境的删除
        1. rm -rf /usr/local/Cellar/php\@7.2
        2. rm -rf /usr/local/etc/php

- php-fpm环境的删除
        
        1. php-fpm -v
        2. cd /private/etc   
           sudo rm -rf php-fpm.conf.defaultphp.ini php.ini.default
        3. cd /usr/bin/
           sudo rm -rf php php-config phpdoc phpize
        4. cd /usr/include
        5. cd /usr/lib
            sudo rm -rf php
        6. cd /usr/sbin/
            sudo rm -rf php-fpm
        7. cd /usr/share/
            sudo rm -rf php
        8. cd /usr/share/man/man1
            sudo rm -rf php-config.1 php.1 phpize.1
        9. cd /usr/share/man/man8
            sudo rm -rf php-fpm.8
        10.lsof -i tcp:80查看端口号
            删除端口号：kill 391
- nginx环境的删除
        
        1. brew info ngnix
        2. rm -rf /usr/local/Cellar/nginx/
        3. rm -rf /usr/local/etc/nginx

###PHP环境的搭建

- nginx的安装

        安装命令：brew install nginx
        配置路径：/usr/local/etc/nginx
        nginx安装路径：/usr/local/Cellar/nginx
        重新启动nginx:
            sudo nginx -s reload
        测试配置是否有语法错误
            nginx -t
            
        遇到的问题：
            1.重启虚拟机后，再次重启nginx会报错： nginx: [error] open() "/var/run/nginx/nginx.pid" failed (2: No such file or directory) 
            如果有nginx.pid就删除该文件中的内容，如果没有就创建一个nginx.pid文件
            
- 安装mysql
        
        安装命令：brew install mysql
        启动遇到问题找日志：（/usr/local/var/mysql）
        
        mysql启动：mysql.server start（/usr/local/Cellar/mysql@5.7/5.7.27_1/bin）
        
        抱错：mayuliangdeMacBook-Pro.local.pid
        解决：ps -ef | grep mysql 查看进程
             kill -9 66486 杀死进程（ppid）
            
        设置环境变量
            在 terminal(终端) 里面执行 vim ~/.bash_profile语句
            此时可以看到.bash_profile的文本内容，在最后面部分添加 PATH=$PATH:/usr/local/Cellar/mysql@5.7/5.7.27_1/bin，添加完成后，按esc键，然后输入:wq，进行保存退出。
            最后在命令行输入source ~/.bash_profile使得环境变量可以立即生效，当然你可以关闭 terminal再重新打开也是可以的~ 
- 安装PHP
        
        安装命令：brew install php@7.2 -v
        
        在~/.bashrc加入：export PATH="$(brew --prefix php54)/bin:$PATH"
        设置环境变量：~/.bash_profile：export PATH=/usr/local/opt/php@7.2/bin:$PATH
        重新启动：source ~/.bash_profile source ~/.bashrc
        
        重启PHP-fpm
        杀死php-fpm:sudo killall php-fpm
        查看：sudo lsof -i:9000
        
        修改配置文件：
            file not found
            解决方案:https://blog.csdn.net/icandoit_2014/article/details/71454481
        
        symony遇到的问题：
            查看端口占用情况：sudo lsof -i -P | grep -i "listen"
            修改nginx端口占用情况：/usr/local/etc/nginx/nginx.conf,然后重启nginx就可以了
        
        php -m 查看是否安装完成
        
        php.ini位置：
            /usr/local/etc/php/7.2/php.ini
        
        

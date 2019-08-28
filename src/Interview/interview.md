##数据库相关
- MyISAM 和 InnoDB 的基本区别?

        1)在增、删、改和查方面,myisam 要优于 innodb 表引擎,当数据量特别大时，他们的速度相差不大
        2)innodb 支持 myisam 所不具备的事务支持、存储过程,行级锁定等等

- MySQL数据库，一天一万条以上的增量，怎么优化？ 
  
        有个短信发送的日志表，每天增量也很大，处理的方法是按月进行分表，因为是日志表，主要操作是insert操作，所以每月初自动生成新的数据表，数据插入到对应月份的那张数据表。[比如表明前缀是cdb_smslog 后面加200910 及时cdb_smslog_200910]

- 数据库中的事务是什么?
        
        事务（transaction）是作为一个单元的一组有序的数据库操作。如果组中的所有操作都成功，则认为事务成功，即使只有一个操作失败，事务也不成功。如果所有操作完成，事务则提交，其修改将作用于所有其他数据库进程。如果一个操作失败，则事务将回滚，该事务所有操作的影响都将取消。

- mysql数据库优化：

        1.选取最适用的字段属性，尽可能减少定义字段长度，尽量把字段设置not null
        2.使用连接（JOIN）来代替子查询（原因）
        3.使用联合（UNION）来代替手动创建的临时表
        4.优化查询语句（在建立好索引字段上尽量减少函数的操作）
        5.建立索引（普通索引，唯一索引，主键索引）
        6.锁定表，优化事物处理

- 水平分表和垂直分表

        每个表的字段相同，按月创建表，按取模创建表
        垂直分表：将常用的字段放入一个表中
        
##PHP相关

- isset和empty的区别：

        1.isset用来判断变量是否定义、存在，如果定义了返回true，否则返回false
        2.如果定义一个变量，但是变量为null，返回的是false，也就是未定义
        3.empty，用来检测变量是否为空
        以下是被认为是空的：
            ""空字符串
            0，0.0，'0' 作为整数的0
            null
            false
            array()
            $val 一个声明了，但是没有值得变量

- 什么是面向对象?主要特征是什么?

        1) 面向对象是程序的一种设计方式，它利于提高程序的重用性，是程序结构更加清晰。 
        2) 主要特征:封装、继承、多态

- SESSION 与 COOKIE 的区别是什么，请从协议，产生的原因与作用说明?

        1) http 无状态协议，不能区分用户是否是从同一个网站上来的，同一个用户请求不同的页面不能看做是同一个用户
        2) SESSION 保存在服务器端，COOKIE 保存在客户端，SESSION 依赖 COOKIE 进行传输，如果 COOKIE 被禁用了，SESSION将不能继续使用
        session:储存用户访问的全局唯一变量,存储在服务器上的，php指定的目录中的（session_dir）的位置进行的存放 cookie:用来存储连续訪問一个頁面时所使用，是存储在客户端，对于Cookie来说是存储在用户WIN的Temp目录中的。 两者都可通过时间来设置时间长短

- HTTP 状态中 302、403、 500 代码含义?

        302 重定向
        403 服务器拒绝访问
        500 服务器内部错误
        401 未被授权
        
- Apache与Nginx的优缺点比较  

        1、nginx相对于apache的优点：  
        轻量级，比apache 占用更少的内存及资源。高度模块化的设计，编写模块相对简单  抗并发，nginx 处理请求是异步非阻塞，多个连接（万级别）可以对应一个进程，而apache 则是阻塞型的，是同步多进程模型，一个连接对应一个进程，在高并发下nginx 能保持低资源低消耗高性能 
        nginx处理静态文件好，Nginx 静态处理性能比 Apache 高 3倍以上 
         2、apache 相对于nginx 的优点：  apache 的rewrite 比nginx 的rewrite 强大 ，模块非常多，基本想到的都可以找到 ，比较稳定，少bug ，nginx 的bug 相对较多 
        3、原因：这得益于Nginx使用了最新的epoll（Linux 2.6内核）和kqueue（freebsd）网络I/O模型，而Apache则使用的是传统的select模型。目前Linux下能够承受高并发访问的 Squid、Memcached都采用的是epoll网络I/O模型。 处理大量的连接的读写，Apache所采用的select网络I/O模型非常低效。

- Memcache和Redis区别

        1.	Redis中，并不是所有的数据都一直存储在内存中的，这是和Memcached相比一个最大的区别。
        2.	Redis在很多方面具备数据库的特征，或者说就是一个数据库系统，而Memcached只是简单的K/V缓存。
        3.	他们的扩展都需要做集群；实现方式：master-slave、Hash。
        4.	在100k以上的数据中，Memcached性能要高于Redis。
        5.	如果要说内存使用效率，使用简单的key-value存储的话，Memcached的内存利用率更高，而如果Redis采用hash结构来做key-value存储，由于其组合式的压缩，其内存利用率会高于Memcached。当然，这和你的应用场景和数据特性有关。
        6.	如果你对数据持久化和数据同步有所要求，那么推荐你选择Redis，因为这两个特性Memcached都不具备。即使你只是希望在升级或者重启系统后缓存数据不会丢失，选择Redis也是明智的。
        7.	Redis和Memcache在写入性能上面差别不大，读取性能上面尤其是批量读取性能上面Memcache更强
        8.  memcache服务器只支持字符串，如果存复合类型的数据，需要通过php的扩展序列化
        9.  Redis支持字符串，除此之外还支持新的数据类型：链表、哈希等结构的数据
        10. Redis支持部分数据的持久化存储

        总结一：
        1.数据类型
        
        Redis数据类型丰富，支持set list等类型
        memcache支持简单数据类型，需要客户端自己处理复杂对象
        
        2.持久性
        
        redis支持数据落地持久化存储
        
        memcache不支持数据持久存储
        
        3.分布式存储
        
        redis支持master-slave复制模式
        
        memcache可以使用一致性hash做分布式
        
        value大小不同
        
        memcache是一个内存缓存，key的长度小于250字符，单个item存储要小于1M，不适合虚拟机使用
        
        4.数据一致性不同
        
        redis使用的是单线程模型，保证了数据按顺序提交。
        
        memcache需要使用cas保证数据一致性。CAS（Check and Set）是一个确保并发一致性的机制，属于“乐观锁”范畴；原理很简单：拿版本号，操作，对比版本号，如果一致就操作，不一致就放弃任何操作
        
        5.cpu利用
        
        redis单线程模型只能使用一个cpu，可以开启多个redis进程
        
        总结二：
        
        1.Redis中，并不是所有的数据都一直存储在内存中的，这是和Memcached相比一个最大的区别。
        
        2.Redis不仅仅支持简单的k/v类型的数据，同时还提供list，set，hash等数据结构的存储。
        
        3.Redis支持数据的备份，即master-slave模式的数据备份。
        
        4.Redis支持数据的持久化，可以将内存中的数据保持在磁盘中，重启的时候可以再次加载进行使用。
        
        我个人认为最本质的不同是Redis在很多方面具备数据库的特征，或者说就是一个数据库系统，而Memcached只是简单的K/V缓存
        
        总结三：
        
        redis和memecache的不同在于：
        
        1、存储方式：
        
        memecache 把数据全部存在内存之中，断电后会挂掉，数据不能超过内存大小
        
        redis有部份存在硬盘上，这样能保证数据的持久性。
        
        2、数据支持类型：
        
        redis在数据支持上要比memecache多的多。
        
        3、使用底层模型不同：
        
        新版本的redis直接自己构建了VM 机制 ，因为一般的系统调用系统函数的话，会浪费一定的时间去移动和请求。
        
        4、运行环境不同：
        
        redis目前官方只支持Linux 上去行，从而省去了对于其它系统的支持，这样的话可以更好的把精力用于本系统 环境上的优化，虽然后来微软有一个小组为其写了补丁。但是没有放到主干上
        
        memcache只能当做缓存，cache
        
        redis的内容是可以落地的，就是说跟MongoDB有些类似，然后redis也可以作为缓存，并且可以设置master-slave
        
         
- 用PHP写出显示客户端IP与服务器IP的代码

        $_SERVER['SERVER_ADDR']服务器IP
        $_SERVER['REMOTE_ADDR']客户端IP

- echo,print和print_r有什么区别？

        echo是一个语言结构，没有返回值，输出一个或多个字符串
        print是一个函数，返回int类型的值，（只能打印int string)
        print_r()是一个函数，返回bool类型的值，按结构输出变量的值。可以打印数组对象等

- 对于大流量的网站,您采用什么样的方法来解决访问量问题?

        确认服务器硬件是否足够支持当前的流量,
        数据库读写分离,优化数据表,
        程序功能规则,禁止外部的盗链,控制大文件的下载,使用不同主机分流主要流量

- include和require的区别：

      require是无条件包含，也就是一个流程里如果加入require无论条件成立与否都会先执行require
      include有返回值，而require没有，require的速度比include快
      包含文件不存在或者语法错误的时候，require是致命的，include不是

- 表单中 get与post提交方法的区别? 
      
      get是发送请求HTTP协议通过url参数传递进行接收,而post是实体数据,可以通过表单提交大量信息.
      get 不安全，post 安全性比get高
      get 传递参数大小有限制，post 没有大小限制

- 谈谈对mvc的认识

        由模型(model),视图(view),控制器(controller)完成的应用程序
        由模型发出要实现的功能到控制器,控制器接收组织功能传递给视图;

- 请说明php中传值与传引用的区别。什么时候传值什么时候传引用?

        按值传递：函数范围内对值的任何改变在函数外部都会被忽略
        按引用传递：函数范围内对值的任何改变在函数外部也能反映出这些修改
        优缺点：按值传递时，PHP必须复制值。特别是对大型的字符串和对象来说，这将会是一个代价很大的操作
        按引用传递则不需要复制值，对于性能提高很有好处

- thinkPHP和larvae的区别：

        渲染方式不同，laravel渲染方式:return view(). tp渲染方式：$this->display()
        数据库配置不同：laravel 引入了env环境文件，只需配置好就可以就可以使用，使用git、svn时 .env也不会随着文件一起提交到服务器
        laravel提供了大量的闭包
        加密方式不同，Laravel内置Hash加密单向加密算法，提高了安全性。
        Laravel在数据库建表中有自己独立内置结构，不需要借助原生态SQL语句。
        Laravel是一个重路由的框架，所有功能都是由路由发起的，哪怕没有控制器方法，只要写了路由就能够访问；TP需要有控制器才能正常访问。Laravel每一个网址必须写一个路由，完全不考虑服务器性能，加载需要耗费很多资源。
        Laravel具有强大的社区化扩展（可有composer扩张展自动加载），中间件，Blade模板引擎
        TP比Laravel容易上手，我觉得更适合初学者
        TP的文档比Laravel的文档更丰富
        TP的性能要优于Laravel，虽内置大量方法，引入第三方库和方法，会使得性能遇到瓶颈。

- 中文字符串截取无乱码

        function GBsubstr($string, $start, $length){
            if(strlen($string)>$length){
                $str = null;
                $len=$start+$length;
                for ($i=$start;$i<$len;$i++){
                    if(ord(mb_substr($string,$i,1))>0xa0) {
                        $str .= mb_substr($string, $i, 2);
                        $i++;
                    }else{
                        $str.=mb_substr($string,$i,1);
                    }
                }
                return $str.'...';
            }else{
                return $string;
            }
        }
        GBsubstr('我是中国的一个骄傲',2,4);

- 写个函数来解决多线程同时读写一个文件的问题

        <?php
            $fp = fopen("/tmp/lock.txt","w+");
            if(flock($fp, LOCK_EX)){// 进行排它型锁定
                fwrite($fp,"Write something here\n");
                flock($fp, LOCK_UN);// 释放锁定
            }else{
                echo "Couldn't lock the file !";
            }
            fclose($fp);
        ?>
- 数组和对象的区别

        array是数组，而object是对象，两者有很大的区别，最主要的区别我觉得对象一般要定义行为，其目的是为了封装，而数组主要定义数据结构

- 静态方法和静态变量的作用
        
        static

- 接口
        
        interface implements

- 类的继承 

        extends

- 用最少的代码写一个求3值最大值的函数

        $max = max($a ,$b $c);
        $max = $a>$b?($a>$c?$a:$c):($b>$c?$b:$c);
        
- 正则表达式    
        
        邮箱正则表达式  /^[a-zA-Z0-9_-]+@[a-zA-Z0-9_-]+(\.[a-zA-Z0-9_-]+)+$/


           
##算法

- Javascript能否定义二维数组，如果不能你如何解决
    1. 不能，var arr[0]=new Array();


















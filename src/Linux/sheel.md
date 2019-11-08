##shell脚本

- #!/bin/bash 

        #!是一个约定的标记，它告诉系统这个脚本需要什么解释器来执行，即使用哪一种shell
        
- shell变量
        
        定义变量时，变量名不加美元符号
        your_name="runoob.com"
        
        注意：
            变量名和等号之间不能有空格
            
- 获取字符串的长度
        
        echo ${#string}
        
- 提取子字符串
        
        echo ${string:1:4}
        

- 数组

        定义：array_name=(value0 value1 value2)
        读取：${数组名[下标]}
        读取所有元素：${array_name[@]}
        数组长度：length=${#array_name[n]}

- 注释
        
        以#开头的行就是注释，会被解释器忽略

- Shell 传递参数

        $* 与 $@ 区别：
        相同点：都是引用所有参数。
        不同点：只有在双引号中体现出来。假设在脚本运行时写了三个参数 1、2、3，，则 " * " 等价于 "1 2 3"（传递了一个参数），而 "@" 等价于 "1" "2" "3"（传递了三个参数）。 
        
- 运算符
        
        原生bash不支持简单的数学运算，但是可以通过其他命令来实现，例如 awk 和 expr，expr 最常用。
        expr 是一款表达式计算工具，使用它能完成表达式的求值操作。
        
        案例1：
            #!/bin/bash
            val=`expr 2 + 2`
            echo "两数之和为 : $val"

        案例2：
            a=10
            b=20
            
            val=`expr $a + $b`
            echo "a+b: $val"
            
            val=`expr $a - $b`
            echo "a-b: $val"
            
            val=`expr $a \* $b`
            echo "a*b: $val"
            
            val=`expr $b / $a`
            echo "b/a: $val"
            
            
            val=`expr $b % $a`
            echo "b % a : $val"
            
            if [ $a == $b ]
            then
               echo "a 等于 b"
            fi
            
            if [ $a != $b ]
            then
               echo "a 不等于 b"
            fi
        
        注意：
        乘号(*)前边必须加反斜杠(\)才能实现乘法运算；
        if...then...fi 是条件语句，后续将会讲解。
        
- 显示结果定向至文件

        echo "It is a test" > myfile
        
- 显示命令执行结果（执行的时候是反引号）

        echo `date`

- 登陆服务器案例（expect）
        
        #!/usr/bin/expect
        
        set timeout 3
        spawn ssh root@47.92.131.207
        expect "*password*"
        send "fc1e6ff3891d12f0@ZHUOYU\r"
        send "cd /home/wwwroot/fawang.sxjicheng.cn\r"
        interact

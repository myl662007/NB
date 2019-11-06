##保留2位小数

- 第一种方法(利用round方法对浮点数进行四舍五入)
        
        $num = 4.30258;
        echo round($num,2);//4.30

- 第二种方法（利用sprintf格式化字符串）
        
        $format_num = sprintf("%.2f",$num);
        echo $format_num;
        
- 第三种方法（利用千位分组来格式化数字的函数number_format()）

        echo number_format($num,2,".","");
        

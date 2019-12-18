##数字转中文

- 思路
        
        定义一个数组，中文汉字,然后循环遍历
        
- 代码：
        
        public function toChinese($number, $flag = false)
        {
            $numArr  = $flag ? ['零', '一', '二', '三', '四', '五', '六', '七', '八', '九'] : ['〇', '一', '二', '三', '四', '五', '六', '七', '八', '九'];
            $number = strval($number);
            $str = '';
            for ($i = 0; $i < strlen($number); $i++) {
                $str .= isset($numArr[$number[$i]]) ? $numArr[$number[$i]] : '';
            }
            return $str;
        }

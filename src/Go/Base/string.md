## 字符串相关知识

- [String](src/Go/Movie/var.md) 字符串转其他类型

- 字符串的遍历
        
        1) Golang 提供 for-range 的方式，可以方便遍历字符串和数组
        2) str 转成 []rune 切片
        
        案例：
        func main(){
        	//遍历0
        	var str string = "abc~ok"
        	for i:=0;i<len(str);i++{
        		fmt.Printf("%f \n",str[i]) 
        	}
        
        	//遍历1
        	var str string = "abc~ok上海"
        	for index,val := range str{
        		fmt.Printf("index=%d,val=%c \n",index,val)
        	}
        
        	//遍历2
        	var str string = "hello,world!北京"
        	str2 := []rune(str) //就是把str转成[]rune
        	for i:=0;i<len(str2);i++{
        		fmt.Printf("%c\n",str2[i])
        	}
        }

- 字符串常用系统函数

        1.统计字符串的长度，按字节len(str)
        
        2.字符串遍历，同时处理有中文的问题 r := []rune(str)
            r:=[]rune(str)
            for i:=0;i<len(r);i++{}
            
        3.字符串转整数 n,err := strconv.Atoi("12")
        
        4.整数转字符串：str=strconv.Itoa(12345)
        
        5.字符串 转 []byte: var bytes = []byte("hello go")
        
        6.[]byte 转 字符串: str = string([]byte{97, 98, 99})
        
        7.10 进制转 2, 8, 16 进制: str = strconv.FormatInt(123, 2) // 2-> 8 , 16
        
        8.查找子串是否在指定的字符串中: strings.Contains("seafood", "foo") //true
        
        9.统计一个字符串有几个指定的子串 : strings.Count("ceheese", "e") //4
        
        10.不区分大小写的字符串比较(==是区分字母大小写的): fmt.Println(strings.EqualFold("abc", "Abc")) // true
        
        11.返回子串在字符串第一次出现的 index 值，如果没有返回-1 : strings.Index("NLT_abc", "abc") // 4
        
        12.返回子串在字符串最后一次出现的 index，如没有返回-1 : strings.LastIndex("go golang", "go")
        
        13.将指定的子串替换成 另外一个子串: strings.Replace("go go hello", "go", "go 语言", n) n 可以指 定你希望替换几个，如果 n=-1 表示全部替换
        
        14.按照指定的某个字符，为分割标识，将一个字符串拆分成字符串数组:strings.Split("hello,wrold,ok", ",")
        
        15.将字符串的字母进行大小写的转换: strings.ToLower("Go") // go strings.ToUpper("Go") // GO
        
        16.将字符串左右两边的空格去掉: strings.TrimSpace(" tn a lone gopher ntrn ")
        
        17.将字符串左右两边指定的字符去掉 : strings.Trim("! hello! ", " !") 和 " "去掉
        
        18.将字符串左边指定的字符去掉 : strings.TrimLeft("! hello! ", " !") "去掉
        
        19.将字符串右边指定的字符去掉 :strings.TrimRight("! hello! ", " !") "去掉// "hello"//将右边 ! 和 " 20)
        
        20.判断字符串是否以指定的字符串开头: strings.HasPrefix("ftp://192.168.10.1", "ftp") // true
        
        21.判断字符串是否以指定的字符串结束: strings.HasSuffix("NLT_abc.jpg", "abc") //false

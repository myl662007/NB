## 数组
    
- 定义
    
        数组可以存放多个同一类型数据
        
- 初始化：
        
        //第一种初始化方式
        var numArr01 [3]int = [3]int{1,2,3}
        fmt.Println("numArr01 = ",numArr01)
    
        //第二种初始化方式
        var numArr02 = [3]int{4,5,6}
        fmt.Println("numArr02 = ",numArr02)
    
        //第三种初始化方式
        var numArr03 = [...]int{7,8,9}
        fmt.Println("numArr03 = ",numArr03)
    
        //第四种初始化方式
        var numArr04 = [...]int{1:10,0:80,2:90}
        fmt.Println("numArr04 = ",numArr04)
    
        //第五种初始化方式
        var numArr05 = [...]string{1:"tom",0:"80",2:"find"}
        fmt.Println("numArr05 = ",numArr05)

- 数组的循环
        
        for-range 结构遍历

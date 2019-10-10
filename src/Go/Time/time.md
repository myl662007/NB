##时间与日期函数

- 时间相关操作

        now := time.Now()
        
        fmt.Printf("now=%v now type=%T \n",now,now)
        fmt.Printf("年=%v \n",now.Year())
        fmt.Printf("月=%v \n",now.Month())
        fmt.Printf("月=%v \n",int(now.Month()))
        fmt.Printf("日=%v \n",now.Day())
        fmt.Printf("时=%v \n",now.Hour())
        fmt.Printf("分=%v \n",now.Minute())
        fmt.Printf("秒=%v \n",now.Second())
        
        结果：
        // 年=2019 
        // 月=October 
        // 年=10 
        // 年=2 
        // 年=16 
        // 年=1 
        // 年=34 

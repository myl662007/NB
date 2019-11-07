##文件写操作
    
        package main
        
        import (
        	"bufio"
        	"fmt"
        	"os"
        )
        
        //文件写入操作
        func main()  {
        	filePath := "/Users/myl/myl.txt"
        	file,err := os.OpenFile(filePath,os.O_WRONLY|os.O_CREATE,0666)
        	//将原来的内容覆盖成新的内容
        	//file,err := os.OpenFile(filePath,os.O_WRONLY|os.O_TRUNC,0666)
        	//在原来的内容追加内容
        	//file,err := os.OpenFile(filePath,os.O_WRONLY|os.O_APPEND,0666)
        	if err!= nil{
        		fmt.Printf("open file err=%v\n",err)
        		return
        	}
        	//及时关闭file句柄
        	defer file.Close()
        	str := "hello,Gardon\n"
        	write := bufio.NewWriter(file)
        	for i:=0;i<5;i++{
        		write.WriteString(str)
        	}
        	write.Flush()
        }

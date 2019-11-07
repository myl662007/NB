##文件读操作

- 案例一

        package main
        
        import (
        	"bufio"
        	"fmt"
        	"io"
        	"os"
        )
        
        func main()  {
        	//文件打开
        	file,err := os.Open("/Users/myl/myl.txt")
        	if err!= nil {
        		fmt.Println("open file err=",err)
        	}
        
        	//输出下文件看看文件是什么
        	fmt.Printf("file=%v\n",file)
        
        	//循环读取文件的内容
        	reader := bufio.NewReader(file)
        	for{
        		str,err := reader.ReadString('\n')
        		//io.EOP表示文件的末尾
        		if err == io.EOF{
        			break
        		}
        		fmt.Print(str)
        	}
        	fmt.Println("文件读取结束")
        
        	//关闭文件
        	err = file.Close()
        	if err != nil {
        		fmt.Println("close file err = ",err)
        	}
        }
        
        
- 案例二

        package main
        
        import (
        	"fmt"
        	"io/ioutil"
        )
        
        func main()  {
        	//使用ioutil.ReadFile一次性将文件读取到位
        	file := "/Users/myl/myl.txt"
        	//不需要open和close文件，因为已经封装到ReadFile中
        	content,err := ioutil.ReadFile(file)
        	if err != nil{
        		fmt.Printf("read file err = %v",err)
        	}
        
        	fmt.Printf("%v",string(content))
        }


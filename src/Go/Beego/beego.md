##Beego的安装
    
    go get github.com/astaxie/beego
##Bee工具的安装
- 安装bee命令

    go get github.com/beego/bee

- beego创建项目

    bee new myproject

##beego项目熟悉
    
        beego.Router, 这个函数的功能是映射 URL 到 controller
        
        c.Ctx.WriteString("hello")  输出字符串
- 继承
        
        嵌套匿名结构体的基本语法
        type Goods struct { 
            Name string
            Price int 
        }
        type Book struct {
            Goods //这里就是嵌套匿名结构体 
            Goods Writer string
        }

- 路由

        固定路由（注：UserController只能get请求）
        beego.Router("/user", &controllers.UserController{})
        
        自定义方法及 RESTful 规则
        beego.Router("/",&IndexController{},"*:Index")

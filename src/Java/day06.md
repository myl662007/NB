###day06授课目录：

	构造方法
	对象的创建步骤
	面向对象的练习
	static关键字
	帮助文档
	Math类的随机数功能

###06.01_面向对象(构造方法概述和格式)(掌握)

	A:构造方法概述和作用
		创建对象,给对象中的成员进行初始化
	B:构造方法格式特点
		a:方法名与类名相同
		b:没有返回值类型，连void都没有
		c:没有具体的返回值
	C:根据构造方法的特点写出一个构造方法
	D:创建对象用的是构造方法么?不是,是借助构造方法,创建对象用的是new关键字
	
###06.02_面向对象(构造方法的重载及注意事项)(掌握)

	A:案例演示
		构造方法的重载
	B:构造方法注意事项
		a:如果我们没有给出构造方法，系统将自动提供一个无参构造方法。
		b:如果我们给出了构造方法，系统将不再提供默认的无参构造方法。
			注意：这个时候，如果我们还想使用无参构造方法，就必须自己给出。建议永远自己给出无参构造方法
	C:给成员变量赋值的两种方式
		a:setXxx()方法
		b:构造方法

###06.03_面向对象(一个标准学生类的代码及测试)(掌握)

	A:案例演示
		完善一下我们的学生的类
	B:给成员变量赋值：
		a:setXxx()方法
		b:构造方法
		setXXX()赋值更加灵活
	C:输出成员变量值的方式：
		a:通过getXxx()分别获取然后拼接
		b:通过调用show()方法搞定
		

###06.04_面向对象(一个标准手机类的代码及测试)(掌握)

	A:案例演示:	模仿学生类，完成手机类代码

###06.05_面向对象(创建一个对象的步骤)(掌握)

	A:画图演示
		画图说明一个对象的创建过程做了哪些事情?
		Student s = new Student();
	步骤:
		(1):加载Student.class文件进内存
		(2):在栈内存为s开辟空间
		(3):在堆内存为学生对象开辟空间
		(4):对学生对象的成员变量进行默认初始化
		(5):对学生对象的成员变量进行显示初始化
		(6):通过构造方法对学生对象的成员变量赋值
		(7):学生对象初始化完毕，把对象地址赋值给s变量

###06.06_面向对象(长方形案例练习)(掌握)

	A:案例演示
		需求：
			定义一个长方形(RectangleDemo)类,定义求周长(length)和面积(area)的方法,
			然后定义一个测试类Test，进行测试。

###06.07_面向对象(员工类案例练习)(掌握)

	A:案例演示
		需求：定义一个员工(Employee)类,自己分析出几个成员，然后给出成员变量，构造方法，getXxx()/setXxx()方法，
			  以及一个显示所有成员信息的方法。并测试。
		员工:
			员工编号	empId
			员工姓名	empName
			员工薪水	empSalary

###06.08_面向对象(static关键字的引入)(掌握)

	A:案例演示
		通过一个案例引入static关键字。
		人类：Person。每个人都有国籍，中国。

###06.09_面向对象(static的内存图解)(理解)

	A:画图演示:	带有static的内存图

###06.10_面向对象(static关键字的特点)(掌握)

	A:static关键字的特点
		a:随着类的加载而加载
		b:优先于对象存在
		c:被类的所有对象共享
			举例：咱们班级的学生应该共用同一个班级编号。
			其实这个特点也是在告诉我们什么时候使用静态?
				如果某个成员变量是被所有对象共享的，那么它就应该定义为静态的。
			举例：
				饮水机(用静态修饰)
				水杯(不能用静态修饰)
		d:可以通过类名调用
			其实它本身也可以通过对象名调用。
			推荐使用类名调用。
			静态修饰的内容一般我们称其为：与类相关的，类成员
	B:案例演示
		static关键字的特点
	
###06.11_面向对象(static的注意事项)(掌握)

	A:static的注意事项
		a:在静态方法中是没有this关键字的
			如何理解呢?
				静态是随着类的加载而加载，this是随着对象的创建而存在。
				静态比对象先存在。
		b:静态方法只能访问静态的成员变量和静态的成员方法
		简单记：静态只能访问静态,非静态可以访问静态的也可以访问非静态的
		引出main方法中调用的方法都是static的
	B:案例演示
		static的注意事项

###06.12_面向对象(静态变量和成员变量的区别)(理解)

	A:所属不同
		静态变量属于类，所以也称为类变量
		成员变量属于对象，所以也称为实例变量(对象变量)
	B:内存中位置不同
		静态变量存储于方法区的静态区
		成员变量存储于堆内存
	C:内存出现时间不同
		静态变量随着类的加载而加载，随着类的消失而消失
		成员变量随着对象的创建而存在，随着对象的消失而消失
	D:调用不同
		静态变量可以通过类名调用，也可以通过对象调用
		成员变量只能通过对象名调用

###06.13_面向对象(工具类中使用静态)(了解)

	A:制作一个工具类:	ArrayTool
	B:编写一个测试类,在测试类中定义一些静态操作数组的方法,并且测试
	C:将这些操作数组的功能抽取到ArrayTool类中并测试

###06.14_面向对象(说明书的制作过程)(了解)

	A:对工具类加入文档注释
		相关的一个参数执指定:
		@author 	指定作者
		@version    指定版本
		@param      指定参数
		@return     指定返回值
	B:通过javadoc命令生成说明书
		通过javadoc工具解析对应的java源文件
		格式: javadoc -d 目录 -author -version 源文件名称.java
		目录: 就是指定说明文档要生成的对应的文件夹

###06.15_面向对象(工具类配合说明书的使用)(了解)

	A:通过说明书使用工具类

###06.16_面向对象(如何使用JDK提供的帮助文档)(掌握)

	A:找到文档，打开文档
	B:点击显示，找到索引，出现输入框
	C:你应该知道你找谁?举例：Scanner
	D:看这个类的结构(需不需要导包)
		java.lang包下的内容不需要我们手动导入
		其它包下的内容需要我们手动导入
		类		    			API文档
			成员变量				字段摘要
			构造方法				构造方法摘要
			成员方法				方法摘要
	E:看这个类的说明(简单的了解一下)
	F:看开始版本
	G:看构造方法
	H:看成员方法
		看左边:
			是否是static的,如果是我们就不需要创建对象,直接可以使用类名调用该方法;看返回值,返回值是什么我就使用什么接收
		看右边:
			看参数列表: 参数的个数 , 参数的类型 ; 要什么参数我是用的时候,就传递什么参数					
	I:然后使用

###06.17_面向对象(学习Math类的随机数功能)(掌握)

	打开JDK提供的帮助文档学习
	A:Math类概述
		类包含用于执行基本数学运算的方法
	B:Math类特点
		由于Math类在java.lang包下，所以不需要导包。
		没有构造方法，因为它的成员全部是静态的。
	C:获取随机数的方法
		public static double random():返回带正号的 double 值，该值大于等于 0.0 且小于 1.0。
	D:我要获取一个1-100之间的随机数，肿么办?
		int number = (int)(Math.random()*100)+1;
		
###06.18_面向对象(猜数字小游戏案例)(理解)

	A:案例演示:	需求：猜数字小游戏(数据在1-100之间)
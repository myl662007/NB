###day11授课目录：
	
	eclipse(开发工具)
		Java开发常见工具介绍
		Eclipse和MyEclipse介绍
		Eclipse下载,安装及卸载
		Eclipse的基本使用
		Eclipse的高级使用
	Object(类)
		public int hashCode()
		public final Class getClass()
		public String toString()
		public boolean equals(Object obj)

###10.01_Java开发工具(常见开发工具介绍)(了解)
	
	A:操作系统自带的记事本软件
	B:高级记事本软件
	C:集成开发环境 IDE:	(Integrated Development Environment)
	D:Eclipse和MyEclipse的区别
		a:Eclipse是一种可扩展的开放源代码的IDE。
		b:Eclipse的特点描述
			免费
			纯Java语言编写
			免安装
			扩展性强
		c:MyEclipse
			在Eclipse基础上追加的功能性插件，对插件收费
			在WEB开发中提供强大的系统架构平台

###10.02_Java开发工具(Eclipse的下载安装及卸载)(掌握)

	A:下载 http://eclipse.org/
	B:安装
		绿色版	解压就可以使用(Eclipse)
		安装版  双击运行,一路next即可(JDK)
	C:卸载
		绿色版	直接删除文件夹即可
		安装版 	专业卸载软件或者控制面板添加删除程序

###10.03_Java开发工具(Eclipse中HelloWorld案例)(掌握)

	A:选择工作空间
		工作空间  其实就是我们写的源代码所在的目录
	B:用Eclipse来完成一个HelloWorld案例
		代码以项目为基本单位
		创建项目
		创建包
		创建类
		编写代码
	C:编译和运行
	    编译: 	自动编译，在保存的那一刻帮你做好了.并将对应的字节码文件存储在bin目录中了
	    运行:	
			a:	点击虫子后面的绿色内在三角形按钮
			b:	点击Run菜单下的run。也可以使用快捷键Ctrl+F11
			c:	选择要运行的文件或者在要运行的文件内容中 , 右键 -- Run as - Java Application即可
				看到Console即可，它就是Eclipse自带的控制台
	
###10.04_Java开发工具(Eclipse的汉化及语法检查提示)(了解)

	A:Eclipse的汉化
		从Eclipse3.5开始，安装目录下就多了一个dropins目录，
		只要将插件解压后放到到该目录即可。
		同理，这种方式卸载插件也是特别的方便，推荐这种方式
	B:语法检查提示
		红色波浪线:	表示错误
			int a = 23	
		黄色波浪线:   表示警告	
			int a = 34;

###10.05_Java开发工具(Eclipse的视窗和视图概述)(了解)

	A:视窗 :	每一个基本的窗体被称为视窗
		PackageExplorer  显示项目结构，包，类，及资源
		Outline   显示类的结构，方便查找，识别，修改
			演示学生类:成员方法,构造方法,成员变量,静态,final,私有公有,抽象方法
		Console  程序运行的结果在该窗口显示
		Problems 显示所有语法及错误所在的位置
		Hierarchy 显示Java继承层次结构，选中类后F4
	B:视图:	是由某些视窗的组合而成的
		Java视图
		Debug视图

###10.06_Java开发工具(Eclipse工作空间的基本配置)(了解)

	A:程序的编译和运行的环境配置(一般不改)
		window -- Preferences -- Java
		编译环境：Compiler	默认选中的就是最高版本。
		运行环境：Installed JREs	默认会找你安装的那个JDK。建议配置了Java的环境变量。
	问题：
		低编译，高运行。可以。
		高编译，低运行。不可以。
			建议，编译和运行的版本一致。
	B:如何去掉默认注释?
		window -- Preferences -- Java -- Code Style -- Code Templates
		选择你不想要的内容，通过右边Edit编辑。
		注意：请只删除注释部分，不是注释部分的不要删除。
	C:行号的显示和隐藏
		显示：在代码区域的最左边的空白区域，右键 -- Show Line Numbers即可。
		隐藏：把上面的动作再做一次。
	D:字体大小及颜色
		a:Java代码区域的字体大小和颜色：
			window -- Preferences -- General -- Appearance -- Colors And Fonts -- Java修改 -- Java Edit Text Font
		b:控制台
			window -- Preferences -- General -- Appearance -- Colors And Fonts -- Debug -- Console font
		c:其他文件
			window -- Preferences -- General -- Appearance -- Colors And Fonts -- Basic -- Text Font
	E:窗体给弄乱了，怎么办?
		window -- Reset Perspective
	F:控制台找不到了，怎么办?
		Window--Show View—Console

###10.07_Java开发工具(Eclipse中内容辅助键的使用)(掌握)

	A:	生成main方法和输出语句
		生成main方法:输入"main",按alt+/,选择
		生成输出语句:输入"syso",按alt+/,选择
	B:Alt+/ 起提示作用

###10.08_Java开发工具(Eclipse中快捷键的使用)(掌握)
	A:格式化		ctrl+shift+f
	B:导入包		ctrl+shift+o 
	C:注释		
		单行注释:		ctrl+/
		取消单行注释:		ctrl+/
		多行注释:		ctrl+shift+/
		取消多行注释:		ctrl+shift+\
	D:代码上下移动 选中代码alt+上/下箭头
	E:代码复制	ctrl+alt+上/下键
	F:删除一行	ctrl+d
	G:查看源码  选中类名(F3或者Ctrl+鼠标点击)

###10.09_Java开发工具(Eclipse中如何提高开发效率)(掌握)

	A:自动生成构造方法:
		无参: 	shift + alt + s        按c
		有参:       shift + alt + s        按o
	B:自动生成get/set方法:       shift + alt + s 按r
	C:Eclipse中继承抽象类或者实现接口的简化
	
###10.10_Java开发工具(Eclipse中一个标准学生类及其测试)(掌握)

	A:案例演示
		用Eclipse实现标准学生类及其测试

###10.11_Java开发工具(Eclipse中接口抽象类具体类代码体现)(掌握)

	A:案例演示(猫狗,跳高猫狗)
		用Eclipse实现接口抽象类具体类代码

###10.12_Java开发工具(Eclipse中如何生成jar包并导入到项目中)(掌握)

	A:jar是什么?
		jar是多个class文件的压缩包。
	B:jar有什么用?
		用别人写好的东西
	C:打jar包
		选中项目--右键--Export--Java--Jar--自己指定一个路径和一个名称--Finish
	D:导入jar包
		复制到项目路径下并添加至构建路径。

###10.13_Java开发工具(Eclipse中如何制作帮助文档和使用jar包)(了解)

	A:针对源程序添加文档注释
		对用Eclipse实现接口抽象类具体类代码加入文档注释
	B:生成帮助文档
		选中项目--右键--Export--Java--Javadoc—Finish
	C:使用jar包

###10.14_Java开发工具(Eclipse中如何删除项目和导入项目)(掌握)

	A:删除项目
		选中项目 – 右键 – 删除
			从项目区域中删除
			从硬盘上删除
	B:导入项目
		在项目区域右键找到import
		找到General，展开，并找到
		Existing Projects into Workspace
		点击next,然后选择你要导入的项目
		注意：这里选择的是项目名称

###10.15_Java开发工具(Eclipse中断点调试的基本使用)(掌握)

	A:Debug的作用
		调试程序
		查看程序执行流程
	B:如何查看程序执行流程
		什么是断点:			就是一个标记，表示从哪里开始看程序
		如何设置断点:			在语句的最左边，双击即可。
		在哪里设置断点:		
							现在：在每一个方法的第一条有效语句上加。
							以后：哪里不会点哪里。

		如何运行设置断点后的程序
							在代码区域--右键--Debug as--Java Appliaction

		看哪些地方			
							看源代码:对照看程序的执行步骤
							看Debug界面:对照看程序的执行步骤
							看变量界面:看变量的产生，赋值，及消失。

		如何去除断点
							a:把添加的动作再做一遍
							b:一键清除版
							选择Debug界面--breakPoints--Remove All... 带两个x的。

	C:演示案例
		使用for循环演示

###10.16_Java开发工具(Eclipse查看Java中参数传递问题)(了解)

	A:断点演示(第四天的代码):		断点查看Java中参数传递问题

###10.17_常见对象(API概述以及Object类的概述)(掌握)
	
	A:API(Application Programming Interface) 
		应用程序编程接口
	B:Java API
		就是Java提供给我们使用的类，这些类将底层的实现封装了起来，
		我们不需要关心这些类是如何实现的，只需要学习这些类如何使用。
	C:Object类概述
		类层次结构的根类
		所有类都直接或者间接的继承自该类
	D:构造方法
		public Object()
		回想面向对象中为什么说：
		子类的构造方法默认访问的是父类的无参构造方法

###10.18_常见对象(Object类的hashCode()方法)(掌握)

	A:案例演示
		public int hashCode()
			a:返回该对象的哈希码值。默认情况下，该方法会根据对象的地址来计算。
			b:不同对象的，hashCode()一般来说不会相同。
		  	   但是，同一个对象的hashCode()值肯定相同。
			c:不是对象的实际地址值，可以理解为逻辑地址值。	

###10.19_常见对象(Object类的getClass()方法)(掌握)

	A:案例演示
		public final Class getClass()
			a:返回此 Object 的运行时类。
			b:可以通过Class类中的一个方法，获取对象的真实类的全名称。	
			public String getName()

###10.20_常见对象(Object类的toString()方法)(掌握)

	A:案例演示
		public String toString()
		a:返回该对象的字符串表示。
			源代码:
			 	public String toString() {
       					 return getClass().getName() + "@" + Integer.toHexString(hashCode());
    				}
		b:它的值等于： 
			getClass().getName() + '@' + Integer.toHexString(hashCode()) 
		c:由于默认情况下的数据对我们来说没有意义，一般建议重写该方法。
		  怎么重写, 一般是将该类的所有的成员变量组成返回即可
	B:最终版
		自动生成
	C: 直接输出对应的名称,就是调用对象的toString()方法

###10.21_常见对象(Object类的equals()方法)(掌握)

	A:案例演示
		a:指示其他某个对象是否与此对象“相等”。 
			源代码: 	
					public boolean equals(Object obj) {
        					return (this == obj);
					}
		b:默认情况下比较的是对象的引用是否相同。
		c:由于比较对象的引用没有意义，一般建议重写该方法。一般用于比较成员变量的值是否相等
		d:==和equals()的区别。(面试题)

###10.22_常见对象(Object类的equals()方法代码优化)(掌握)

	A:案例演示
		Object类的equals()方法代码优化
			a: 提高效率(不需要自己和自己比较)
			b: 提高健壮性(instanceof)	
	B:最终版
		自动生成
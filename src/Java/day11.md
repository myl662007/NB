###day11授课目录：
	
	Scanner(用于接收键盘录入数据)
	String(字符串)

###11.01_常见对象(Scanner的概述和构造方法原理)(掌握)

	A:Scanner的概述:	JDK5以后用于获取用户的键盘输入
	B:Scanner的构造方法原理
		Scanner(InputStream source)
		System类下有一个静态的字段：
			public static final InputStream in; 标准的输入流，对应着键盘录入。

###11.02_常见对象(Scanner类的hasNextXxx()和nextXxx()方法的讲解)(掌握)

	A:基本格式
		hasNextXxx()  判断下一个是否是某种类型的元素,其中Xxx可以是Int,Double等。
					  如果需要判断是否包含下一个字符串，则可以省略Xxx
		nextXxx()  获取下一个输入项。Xxx的含义和上个方法中的Xxx相同
	B:案例演示
		演示结合判断获取数据的情况

###11.03_常见对象(Scanner获取数据出现的小问题及解决方案)(掌握)

	A:两个常用的方法：
		public int nextInt():获取一个int类型的值
		public String nextLine():获取一个String类型的值
	B:案例演示
		a:先演示获取多个int值，多个String值的情况
		b:再演示先获取int值，然后获取String值出现问题（直接跳过第二次输入数据的过程输出第一步输入的数据）
			原因：键盘输入int类型的数据后又按了回车键，nextInt()方法只能识别int类型数据，而回车键输入的是“\r\n”不能被其接			受却被nextLine()方法接受了，相当于一次输入了两次数据，不再需要输入第二次数据
		c:问题解决方案
			第一种：先获取一个数值后，在创建一个新的键盘录入对象获取字符串。
			第二种：把所有的数据都先按照字符串获取，然后要什么，你就对应的转换为什么。(后面讲)
					（使用基本数据类型包装类对其进行数据转换）
###11.04_常见对象(String类的概述)(掌握)

	A:什么是字符串
		字符串是由多个字符组成的一串数据(字符序列)
		字符串可以看成是字符数组
	B:String类的概述	
		通过JDK提供的API，查看String类的说明
		
		可以看到这样的两句话。
		a:字符串字面值"abc"也可以看成是一个字符串对象。
		b:字符串是常量，一旦被创建，就不能被改变。

###11.05_常见对象(String类的构造方法)(掌握)

	A:常见构造方法
		public String():空构造
		public String(byte[] bytes):把字节数组转成字符串	
		public String(byte[] bytes,int index,int length):把字节数组的一部分转成字符串(index:表示的是从第几个索引开始, length表示的是长度)
		public String(char[] value):把字符数组转成字符串
		public String(char[] value,int index,int count):把字符数组的一部分转成字符串
		public String(String original):把字符串常量值转成字符串
	B:案例演示	
		演示String类的常见构造方法
		
		演示前先说一个字符串的方法：
			public int length()：返回此字符串的长度。

###11.06_常见对象(String的特点一旦被创建就不能改变)(掌握)

	A:String的特点:	一旦被创建就不能改变
	B:案例演示	
		a:如何理解这句话
			String s = "hello" ; 
			s =  "world" + "java"; 问s的结果是多少?输出结果：worldjava
		b:画内存图解释:	内容不能变，引用可以变

###11.07_常见对象(String类的常见面试题)(掌握)

	A:面试题1
		String s = new String(“hello”)和String s = “hello”;的区别
		并画内存图解释。
	B:面试题2
		==和equals()的区别?
	C:面试题3
		看程序写结果
		String s1 = new String("hello");
		String s2 = new String("hello");
		System.out.println(s1 == s2);
		System.out.println(s1.equals(s2));

		String s3 = new String("hello");
		String s4 = "hello";
		System.out.println(s3 == s4);		//false
		System.out.println(s3.equals(s4));	//true

		String s5 = "hello";
		String s6 = "hello";
		System.out.println(s5 == s6);		//true
		System.out.println(s5.equals(s6));	//true
	D:面试题4
		看程序写结果
		String s1 = "hello";
		String s2 = "world";
		String s3 = "helloworld";
		String s4 = "hello" + "world" ;
		System.out.println( s3 == s1 + s2);			//false
		System.out.println( s3 == s4 );				//true
		System.out.println( s3.equals((s1 + s2)));	//true

###11.08_常见对象(String类的判断功能)(掌握)

	A:String类的判断功能
		public boolean equals(Object obj):				比较字符串的内容是否相同,区分大小写
		public boolean equalsIgnoreCase(String str):		比较字符串的内容是否相同,忽略大小写
		public boolean contains(String str):				判断字符串中是否包含传递进来的字符串
		public boolean startsWith(String str):				判断字符串是否以传递进来的字符串开头
		public boolean endsWith(String str):				判断字符串是否以传递进来的字符串结尾
		public boolean isEmpty():	比较的是内容为空，""					判断字符串的内容是否为空。
	B:案例演示:	案例演示String类的判断功能;

###11.09_常见对象(模拟用户登录)(掌握)

	A:案例演示:	需求：模拟登录,给三次机会,并提示还有几次。

###11.10_常见对象(String类的获取功能)(掌握)

	A:String类的获取功能
		public int length():							获取字符串的长度。
		public char charAt(int index):					获取指定索引位置的字符
		public int indexOf(int ch):		(若没有这个字符返回-1)返回指定字符在此字符串中第一次出现处的索引。
		public int indexOf(String str):					返回指定字符串在此字符串中第一次出现处的索引。
		public int indexOf(int ch,int fromIndex):			返回指定字符在此字符串中从指定位置后第一次出现处的索引。
		public int indexOf(String str,int fromIndex):		返回指定字符串在此字符串中从指定位置后第一次出现处的索引。
			可以顺带提一下lastIndexOf系列
		public String substring(int start):				从指定位置开始截取字符串,默认到末尾。
		public String substring(int start,int end):		从指定位置开始到指定位置结束截取字符串。
	B:案例演示												（不包含end处的字符）
		案例演示String类的获取功能

###11.11_常见对象(字符串的遍历)(掌握)

	A:案例演示:	需求：遍历字符串
		
###11.12_常见对象(统计不同类型字符个数)(掌握)

	A:案例演示:	需求：统计一个字符串中大写字母字符，小写字母字符，数字字符出现的次数。(不考虑其他字符)

###11.13_常见对象(String类的转换功能)(掌握)

	A:String的转换功能：
		public byte[] getBytes():						把字符串转换为字节数组。
		public char[] toCharArray():					把字符串转换为字符数组。
		public static String valueOf(char[] chs):		把字符数组转成字符串。
		public static String valueOf(int i):			把int类型的数据转成字符串。
			注意：String类的valueOf方法可以把任意类型的数据转成字符串。
		public String toLowerCase():					把字符串转成小写。
		public String toUpperCase():					把字符串转成大写。
		public String concat(String str):				把字符串拼接。
	B:案例演示
		案例演示String类的转换功能
		
###11.14_常见对象(按要求转换字符)(掌握)

	A:案例演示:	需求：把一个字符串的首字母转成大写，其余为小写。(只考虑英文大小写字母字符)
	
###11.15_常见对象(String类的其他功能)(掌握)

	A:String的替换功能及案例演示
		public String replace(char old,char new)			将指定字符进行互换
		public String replace(String old,String new)		将指定字符串进行互换
	B:String的去除字符串两端空格及案例演示
		public String trim()							去除两端空格
	C:String的按字典顺序比较两个字符串及案例演示
		public int compareTo(String str)
		public int compareToIgnoreCase(String str)

###11.16_常见对象(把数组转成字符串)(掌握)

	A:案例演示
		需求：把数组中的数据按照指定个格式拼接成一个字符串
			举例：
				int[] arr = {1,2,3};	
			拼接结果：
				"[1, 2, 3]"
	B:断点查看
		把数组转成字符串代码

###11.17_常见对象(字符串反转并断点查看)(掌握)

	A:案例演示
		需求：把字符串反转
			举例：键盘录入"abc"		
			反转结果："cba"
	B:断点查看:	把数组转成字符串代码

###11.18_常见对象(在大串中查找小串出现的次数思路图解)(掌握)

	A:画图演示
		需求：统计大串中小串出现的次数
		举例: "woaijavawozhenaijavawozhendeaijavawozhendehenaijavaxinbuxinwoaijavagun”中java出现了5次

###11.19_常见对象(在大串中查找小串出现的次数代码实现)(掌握)

	A:案例演示	统计大串中小串出现的次数

###11.20_常见对象(在大串中查找小串出现的次数代码优化并断点查看)(掌握)

	A:代码优化
		统计大串中小串出现的次数
	B:断点查看
		统计大串中小串出现的次数代码
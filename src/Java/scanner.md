###03.01 键盘录入

	A:为什么要使用键盘录入数据
		a:为了让程序的数据更符合开发的数据
		b:让程序更灵活一下
	B:如何实现键盘录入呢?
		先照格式来。
		a:导包
			格式：
				import java.util.Scanner; 
			位置：
				在class上面。
		b:创建键盘录入对象
			格式：
				Scanner sc = new Scanner(System.in);
		c:通过对象获取数据	
			格式：
				int x = sc.nextInt();


---
layout: post
post_title: "笔记：Programming For Everyone"
post_date: 2015-04-13 20:40:00
post_name: /programming-for-everyone-notes/
tags: [笔记,前端]
published: true
categories: 编程
---

这门课是祝建华教授推荐数据挖掘的第一门课，难度不大，推荐给没有任何编程基础的同学。推荐使用代码编辑器[Sublime](http://www.sublimetext.com/)，并[在Sublime中配置python开发环境](http://www.oschina.net/translate/setting-up-sublime-text-for-python-development)进行练习。

课程完整视频在[Coursera](https://www.coursera.org/course/pythonlearn)，以下是完结版笔记内容。

## 第一周

### 1.1 为什么要编程
1. 人们发明电脑是为了让计算机为我们做事。如果我们不学习计算机的语言，我们就没法告诉计算机我们要做什么。编程就是学习计算机的语言，用计算机能懂的方式命令它按照我们的指令做事。

2. 用户 VS 程序员的区别：
	- 用户把计算机当做一套工具，比如word，Excel，PPT等程序
	- 程序员理解计算机的方式和计算机的语言
	- 程序员拥有一些基础工具使他们能够构建给用户使用的工具
	- 程序员有时候编写一些大程序给很多人使用（比如浏览器），有时候只是一些小程序解决小问题（比如文件批量重命名工具）

3. 为什么要成为程序员
	- 解决自己的问题，比如我需要批量的删除一个问卷里面的某些不想要的字符 
	- 解决他们的问题，比如制作一个网站后台管理系统，这就是程序员的工作了
4. 三个相关的概念
    - 代码（Code）
	- 利用一段左右左右的舞蹈的指示来比如代码
	- 表达的失误来比喻bug
    - 软件（Software）
    - 程序（Program）
	- 比如计算在一个跳跃的段落中算出有多少个the，来表明什么时候需要用到程序

### 1.2 硬件基础
1. 几个定义
	- 中央处理器（Central Processing Unit）：即CPU，俗称计算机的“大脑”，控制程序中指令执行的顺序，总是在问“what's next?"
	- 输入设备（Input Devices）：如键盘、鼠标等
	- 输出设备（Output Devices）：显示屏、麦克风、打印机等
	- 主存储器（Main Memory）：即主存，相当于计算机的内存，存储容量小且是暂时性的，当机器电源关闭，存于其中的数据就会丢失。
	- 辅助存储器（Secondary Memory）：即外存，相当于计算机的硬盘，存储容量大，断电后仍能保存数据，如硬盘、记忆棒等。
2. 如图所示，程序员在主存那一块活动，将程序记录在主存，然后CPU执行程序中的指令。
3. 程序员将指令转换为Source Code（源代码，比如Pyhon），然后通过解释器转换为Machine Language（机器语言，二进制），这样计算机就可以理解程序员了。
4. 通过Totally Hot CPU这个视频讲解计算机在运行指令的时候，发热量是非常大的

### 1.3 Python编程语言

1. Python是Python解释器使用的编程语言，创始人是Guido van Rossum。
2. 语法错误（Syntax Errors）：刚开始学Python，很容易犯错，这是Python中的语法错误
3. 在Python的运行窗口中，主提示符“         ”其实就是在问你：what's next？
4. 老师通过随意输入一些代码，演示什么是语法错误，以及演示一个简单的四则运算，讲解什么是正确的语法
5. Python的构成元素
	- 就像一个故事一样，Python的代码要有开头、中间和结尾 
	- 变量（Variables）
	- 常量（constant）
	- 运算器（operator）
	- 保留字（Reserved words）：保留字是指已经定义过的字，使用者不能再将这些字作为变量名，如if, while，not,try, else,while等。
	- 语句结构（Sentences/lines）：Assignment statement，assigment with expression，print statment
	- 故事结构（Story structure）：有目的地构建程序

### 1.4 程序的段落
1. Pythone的脚本模型
	- 交互模式：一句一句地写指令，每句Python都会反应，一般用来演示
	- 脚本：大部分的程序都是有很长的段落的，通常会编成1个长的文档，然后在这个文档加上一个py的后缀，这样计算机就能识别出是python的程序
2. 程序流程（Program Flow）
	- 顺序执行（Sequential Steps）
	- 条件执行（Conditional Steps）：如if语句
	- 循环执行（Repeated Steps）：存在迭代变量（iteration variables）

### 1.5 编程就是讲故事
1. 解释程序其实就是把人的思想分解，比如在一个数字图表中，人是如何找出最大的数字的
2. 再次思考，计算机在下面的三个场景中如何找出最大的数字，有点像在解释算法的精神：
	- 第一个是全部显示，但是屏幕移动；
	- 第二个把数字颠倒；
	- 第三个逐个显示；
		
## 第二周

### 2.1 表达式
1. 变量分为常量及变量
	- 常量（Constants）: 值不变的量，分为两种类型：数字型常量和字符型常量;数字型常量（Numeric constants）：无定界符
	- 变量（Variables）: 计算机存储空间中可命名的地方,变量包含两部分：值和名
	- 值（Value）可以通过赋值语句（Assignment Statements）来获得
	- 名（Name）必须遵循Python的命名规则
2. 命名规则：
	- 只能以字母或下划线开头
	- 必须且只能包含字母、数字、下划线
	- 大小写是有区分的,spam Spam SPAM
	- 好的：spam，eggs spam23
	- 坏的：23spam #sign var.12
	- 不能用保留字命名（保留字包含：and、del、for、is、raise、assert、elif、from、lambda、return、break、else、global、not、try、class、except、if、or、while、continue、exec、import、pass、yield、def、finally、in、print）
3. 句子：
	- 赋值语句：将值赋予变量,右侧的表达式和左侧的变量
			
			x=3.9*x*(1-x)

4. 数字型表达式：
	- 加法：+
	- 减法：-
	- 乘法：*
	- 除法：/
	- 乘方：**
	- 取余：%

5. 运算符的优先级：运算时，哪个运算符先进行运算
	- 括号
	- 乘方
	- 乘法、除法、取余
	- 加法、减法
	- 如果等级都一样，那么就是从左到右

			x=1+2**3/4*5
			print x
			11

6. 注意事项：
	- 记住运算优先级
	- 撰写代码的时候，运用括号
	- 写代码的时候，是数学表达式尽量简单易懂
	- 把长表达式拆分，使得更加容易理解

7. 整数除法的奇怪之处（在Python 3.0有更改）：

		print 10/2
		5
		print 9/2
		4（3.0版本是4.5）
		print 99/100	
		0
		print 10.0/2/0
		5.0   
		print 99.0/100.0
		0.99

8. 取整的一些注意事项
	- 整数之间的除法得到的是整数，该整数是商的取整部分，不能四舍五入
	- 浮点型数值之间的除法得到的才是浮点型
	- 只要被除数与除数中有一个为浮点型数值，则商为浮点型，无需取整
		
		
			print 99/100.0
			0.99
			print 99.0/100
			0.99

### 2.2 类型

1. 不同的量有不同的类型(Type)，对于不同的类型，“+”的含义不同：
	- 对于数值型常量，“+”意味着加法；
	- 对于字符型常量，“+”意味着连接

			>>> ddd=1+4
			>>> print ddd
			5
	
			>>> eee="hello"+"there"

			>>> print eee

			hello there

2. 而不同类型的量也决定了他们不能直接运算，数值型不能与字符型直接用“+”连接
我们可以通过type()这个函数来检测变量的类型：

		>>>print type(eee)

		<type 'str'>

		>>>print type(1)

		<type 'int'>

3. 数值型主要有两大类类型，有整数型（integer）和浮点型(float point number)
	- 整数型: 0, -1, 100
	- 浮点型：0.0，-1.2， 200.98

4. 类型转化
	- 通过运用int（）和float（）可以达到整数型和浮点型的互相转化
	
			>>>print int(99.0)
			99
			>>>print float(99)
			99.0
	
	- int（）和float（）也可以用来把字符型转化为整数型和浮点型，但是前提是字符型的定界符内包含整数型或者浮点型，否则将报错

			>>>a='123'
			>>>print int(a)
			123

5. User input
	- 我们可以通过raw_input()函数来读取用户输入的信息，它将返回一个字符型的量，如需数值型的量，则需转化
	- 比如我们在转换美元和人民币的时候，可以用到这个

6. 注释
	- 用#开头
	- 注释可以用来描述程序的用途
	- 记录代码编写者和其他附加信息
	- 暂时隐藏不需要的代码

7. 字符运算器
	- +表示连接
	- *表示多次连接

				print 'abt'+'123'
				abc123
				print 'hi*5'
				hihihihihi					

8. 变量命名的最佳做法：尽管变量名可以任意选取，但是我们还是要以便于记忆读取为原则命名，以免日后读代码的时候出错。


### 2.3 作业：练习计算工薪
		hours = raw_input("how much time  you spent on working")
		rate = raw_input("what is your paying rate")  
		pay = int(hours) * int(rate)
		print pay
		

### 2.4 采访
一个女性Piazza教育公司的创业故事，她是如何学习，用户价值导向的产品哲学。


## 第三周
### 3.1 条件语句
		x=5
		if x =< 6
		print "smaller"
		if x > 6
		print "larger"
		
1. 比较运算器
	- <
	- < = 
	- = =等于
	- 大于或等于
	- 大于
	- ！= 不等于
	
2. 首行缩进（Indentation）** 这个在python非常重要 **
	- if或者for语句之后的部分要增加首行缩进；
	- if或者for语句之后的整体部分要保持相同的首行缩进；
	- 结束if或者for语句之后要退出首行缩进，即与if或者for语句保持相同的首行缩进，以表示分支结构和循环结构的结束。
	- 空白行被忽略，他们不影响首行缩进。
	- 关于首行缩进，注释本身也是被忽略的。
	- 小心制表符(tab)，不要把它和空格（space）弄混，否则会出现首行缩进错误。
	- 大多数编辑器可以把tab转换成space,所以记得把这个设定打开。
		
### 3.2 条件语句举例

1. 多层嵌套
	- 分支结构可以分为单分支、嵌套分支、双分支、多分支。
	- 首行缩进又一次没了。
	
2. 单分支（One-way decisions）例：

			x=5
			if x==5:			
			print "is 5"
			
3. 嵌套分支结构（Nested decisions）:在分支结构中又嵌套一个或多个分支结构。例：

		x=42
		if x>1:
		print "more than one"
		if x<100:
		print "less than 100"
		print "all done"

4. 双分支（Two-way decisions）:由判断语句引出的分支只有两个，即根据Yes/No进行不同的操作。例：

		x=4
	
		if x>2:

		print "Bigger"

		else:

		print "Not bigger"
		print "All done"

5. 多分支（Multi-way decision）：连续的判断语句引出多种条件判断，从而进行操作。**elif**例：

		if x<2:

		print "Small"

		elif x<10:

		print "Medium"

		else:

		print "Large"
		print "All done"

6. 多分支注意事项：记得检查每一判定条件的顺序和范围，以免出现部分结果无法输出。

		例：

		if x<2:

		print "Below 2"

		elif x>=2:

		print "Two or more"

		else:

		print"Something else"

		## 上述程序中不可能输出“Something else”

### 3.3 Try 和 Excerpt 结构
1. try/except结构：分支结构的一种，用来规避程序运行中可能出现的运行错误。如果try部分的代码能成功运行，那么except部分的代码就会被忽略；
例：

		a="123"
		try:

			b=int(a)

		except:
	
			b=-1

		print b
		## 输出结果为 123

2. **解释**：虽然变量a被赋予字符型常量，但是该字符型常量的定界符里面包含数字，所以可以用int()函数转化为123，所以except部分的程序不再运行，所以输出的b的值为123.如果try部分的代码执行失败了，那么会跳到except部分的代码。
	
3. **注意**：无论try部分的代码中哪一行出现错误，都会直接跳到except部分运行。

		例：

		a="hello"

		try:

			b=int(a)

		except:

			b=-1

		print b

		## 输出结果为 -1

4. 测试一个用户输入的值是否为数字，如果是输出nice work，如果不是输出not a number
	
		rawstr= raw_input("enter a number")
		try:
			ival=float(rawstr)
		except:
			ival= -1
		if ival > 0:
			print "nice work"
		else:
			print "not a number"

5. 进阶练习：写一段程序，计算出当一周工作时间超过40个小时，那么薪水就是1.5倍，如果40小时之内，就是正常计算。
6. 二次进阶：把try和except融入到程序，这样就可以处理非数值型的输入

### 3.4 笔记链接
- [本周wiki笔记](https://share.coursera.org/wiki/index.php/Pythonlearn:resources-week03)

## 第四周
### 4.1 函数
1. 函数（Functions）：事先存储好的，可以重复使用的步骤和代码，它把引数（arguments）作为输入，加以计算，然后返回结果。
2. 函数分为两种，一种是嵌入式的（built-in functions）,一种是自定义的。
	- 嵌入式函数是Python提供给我们的，我们可以直接使用。例如：raw_input(),type(),float(),int()
	- 自定义函数，顾名思义是我们自己定义的。我们需要借助保留字def来定义。

			例：
			def hello():

				print "Hello"

				print "Fun"
			hello()

			## 注意，我们把新定义的函数名也作为保留字（Reserved words）,故我们要避免把函数名作为变量名。

3. 我们调用函数（call functions）时，需要在表达式中用到函数名，小括号还有argument。例如：big=max("hello world")中的“hello world”就是argument。
4. 几个常见的内置函数：最大化函数（Max Function），Min()，Float()，int(),type()
5. 自定义函数：
	- 使用def，然后在其之后加入一个小括号，括号里面的参数可选。
	- 函数主体部分需要首行缩进。
	- 以上步骤只是定义函数并不执行函数。（易错点！！！）
	- 只有当函数调用时，函数的主体部分还会运行。
	- Arguments:当我们调用函数时，我们会把引数传递给函数，作为函数的输入。当我们每一次调用函数的时候，我们可以使用不同的引数来引导函数处理不用的工作。我们要把引数放在小括号内，并整体放在函数名之后。

6. 参数（Parameters）:参数是函数定义时的一个值，在函数调用时，它会和引数相连接（不知道该怎么说。。。）
		- def greet(lang):上面的lang是参数。当调用函数的时候，会把引数的值赋予参数，然后再运行函数。
7. 返回值（Return values）:函数会用引数加以计算，返回一个值作为函数调用的值。

		例：

		def greet(): ##这里没有参数
		return "Hello"
		print greet(),"Glenn"
		print greet(),"Sally"
		## 输出结果为:Hello Glenn  Hello Sally
		## 定义函数中的return语句将结束函数调用，并把值作为函数运行的结果返回。

8. 引数VS参数VS结果

	- 引数是函数调用时位于函数名后小括号内的值，
	- 参数是函数定义时位于函数名后小括号内的值，
	- 结果是函数调用后返回的值。

9. 多参数、引数：只需在函数调用和定义时各自增加引数和参数的个数。但是注意引数和参数的个数要保持一致。

		def addtwo(a,b)
			added=a+b
			return added
		x=addtwo(3,5)
		print x

10. 空值函数（Void functions/Non-fruitful functions）:当一个函数没有返回值时，我们管它叫做空值函数,有返回值的函数叫做实值函数。
11. 什么情况下需要定义函数：

	- 把你的代码分成段，尽量能完整表达想法，并把它命名。
	- 如果代码中有重复的部分，只需要写一次，并把它作为函数，重复使用。
	- 如果代码太长太复杂的话，按逻辑把它分成几块，把这几块放到函数里，这样会更加简洁明了。

### 4.2 练习
1. 还是计算时薪的作业rewrite your pay comptation with time-and-a-half for overtime and create a function called computepay which takes two parameters (hours and rate)


### 4.3 笔记链接
- [本周wiki笔记](https://share.coursera.org/wiki/index.php/Pythonlearn:resources-week04)


## 第五周

### 5.1 Loops and Iteration 
1. while 循环，也可以叫做重复性步骤，循环中有一个迭代变量，它每次经历一次循环就会变化一次。通常来说，迭代变量在循环中会被赋予一系列有顺序的值。迭代变量可以用来控制循环次数。
		
		n=5
		while n>0
			print n
			n=n-1
			print 'yes'
			print n 
			#上例中的n是迭代变量，它使循环只进行了5次。

2. 结束循环的方法：
	- break语句：结束当前循环，直接跳到循环之后的语句；它可以出现在循环语句的主体部分中的任意位置。例：
	
			while true:
				line = raw_input('>')
				if line == 'done'：
					break
				print line
			print 'Done!'
			## 因为输入hello there和finished时，都只运行while循环的主体部分，所以不会输出Done!，而只会输出hello there和finished，只有当输入done的时候，才会跳出循环，输出Done!。
			## while True是一个无限循环，可以用break语句来结束无限循环。


3. 结束当次循环的方法:continue语句：结束当前循环，进行下一次循环；例：

			while ture:
			line = raw_input('>')
			if line[0]=="#"
			 	continue
			if line=='done':
			 	break
			print line
			print 'done!'

			>hello there
			hello there
			>#don't print this
			>print this
			print this
			>done
			Done!
			## 输入#don't print this时，因为line[0]是#，所以执行continue语句，跳出本次循环，没有输出；输入done的时候，因为执行break语句，所以直接跳出循环语句，输出Done!

4. 不确定循环（Indefinite loops）：while循环被称为无限循环,因为该循环将一直运行，直到判断语句的结果是错误。
有时候我们很难去确定循环何时结束。
5. 确定循环（Definite loops）:通常我们有一系列有限的项目，我们用for循环来把这一系列的数都拿来运行。我们之所以把这种循环称为有限循环，是因为循环运行了精确的次数，这个次数我们通常可以算出。有限循环有一个明确的迭代变量，我们通常用它来计算循环次数
		
		for i in [5,4,3,2,1]:
			print i 
		print 'blastoff!'
		## in:表示迭代变量在有序数据集合中迭代，循环主体部分将依次用有序数据集合的值来计算运算，知道迭代变量移到数据集合里面的最后一个量。


### 5.2 Loop Idioms
1. 这个小节主要介绍了几个典型的循环结构，我们可以在以后的应用中把这些结构修改、结合形成新的程序。
2. for循环语句的基本结构
	- 第一步是赋予变量初始值；
	- 第二步是在循环主体中处理变量；
	- 第三步是在循环主体中更新变量；
	- 最后一步是输出最终变量或对最终变量进行处理。

3. 以下是典型循环结构的举例：
		
		print 'before'
		for thing in [9,41,12,3,74,15]
			print thing
		print 'after'


		输出结果：
			Before
			9
			41
			12
			3
			74
			15
			After
		## 这是最简单的循环结构了，把数据集中的数值依次赋予thing这个迭代变量，并依次输出。

4. 找最大数:

		largest= -1
		print 'before',largest
		for the_num in [9,41,12,3,74,15]:
			if the_num > largest:
				largest=the num
			print largest,the_num
		print'after',largest

		## 输出结果：
		Before -1
		9 9
		41 41
		41 12
		41 3
		74 74
		74 15
		After 74


5. 循环计数：这个程序的难点在于输出的部分容易弄混:解释一下该程序。先赋予largest_so_far初始值-1，输出字符串Before，还有largest_so_far的值-1。
然后进入循环之后，the_num依次被赋予数据集中的数值，当然，只有当the_num的值大于largest_so_far的值时,the_num的值才会被赋给largest_so_far，也就是说只有the_num大于largest_so_far，largest_so_far的值才会有变化。所以不难解释41之后直到74，largest_so_far的值才发生变化。当数据集中的数值都取遍了之后，输出字符After以及largest_so_far的值，此时它的值是74。


			zork = 0
			print 'before',zork
			for thing in [9,41,12,3,74,15]:
				zork = zork+1
				print zork,thing
			print 'after',zork

			## 输出结果：
			Before 0
			1 9
			2 41
			3 12
			4 3
			5 74
			6 15
			After 6
			## 为了计算循环运行的次数，我们引入一个计数变量zork，并赋予其初始值0,然后让迭代变量依次在有序数据集中取值，每取一次值，计数变量加1，然后输出计数变量和迭代变量。直到迭代变量取遍数据集的值之后，计数变量的值就是数据集中数据的个数。



6. 数据求和

		sum=0
		print 'before',sum
		for thing in [9,41,12,3,74,15,154]:
			sum=sum+thing
			print sum,thing
		print 'after',sum

		## 输出结果：

		Before 0

		9 9

		50 41

		62 12

		65 3

		139 74

		154 15

		After 154

		## 解释：先定义一个求和变量zork，并赋初值0，让迭代变量thing在数据集中依次取值，把thing和zork的和赋给zork，直到thing取遍了数据集中所有值，最后输出zork的最终值，即为数据集中所有值的和。


7. 计算平均值
		
		count=0
		sum=0
		print 'before',count,sum
		for thing in [9,41,12,3,74,15]:
			sum=sum+thing
			count=count+1
			print count,sum,thing
		print after,count,sum,sum/count


		## 输出结果：

		Before 0 0

		1 9 9

		2 50 41

		3 62 12

		4 65 3

		5 139 74

		6 154 15

		After 6 154 25
		## 解释：先定义计数变量count和求和变量sum，并分别赋初值0，让迭代变量value在数据集中依次取值，循环一次，计数变量count加1，把sum和value的和赋给sum,直到迭代变量value取遍数据集中的所有值。最后输出求和变量和计数变量的商，作为数据集中所有数的平均值。

8. 选数

		lar=0
		for thing in [9,41,12,3,74,15]:
			if thing>20
			print larger number, thing
			else
		print lar
		## 输出结果：
		Before
		Larger number 41
		Larger number 74
		After
		## 解释：在循环结构中嵌入一个分支结果用来挑选比20大的数。

9. 查找数字

		found=false
		print 'before',found
			for thing in [9,41,12,3,74,15]:
				if value==3
					found=true
				print found value
			print after,found

		## 输出结果：
		Before False

		False 9

		False 41

		False 12

		True 3

		True 74

		True 15

		After True
		## 解释：先定义一个逻辑变量，初始赋值为False,在循环结构中嵌入一个分支结构，并以要寻找的数为判断条件，如value==3，当判断条件成立时，把True赋给逻辑变量，直到迭代变量取遍了数据集中的所有值。最后如果逻辑变量值为True, 则说明数据集中有要查找的数。

### 5.3 Largest and Smallest 

1. 上节讲了找最大数的程序，这节课开头用它作为引例，引出了取最小值的程序。

		smallest= -1
			print 'before',smallest
				for the_num in [9,41,12,3,74,15]:
					if the_num < smallest:
						smallest=the num
					print smallest,the_num
			print'after',smallest

		输出结果：

		Before -1

		-1 9

		-1 41

		-1 12

		-1 3

		-1 74

		-1 15

		After -1
		## 显然，该程序并没有找出数据集合中的最小值。根本原因在于smallest的初始值太小。只有当它的初始值无穷大时，才能用来找出任意数据集中数值的最小值。

2. 于是又引出了给smallest_so_far赋初值None。

		smallest= None
		print 'before',smallest
		for value in [9,41,12,3,74,15]:
			if smallest is None
				smallest = value 
			elif value < smallest
				smallest = value
			the_num < smallest:
				smallest=the num
			print smallest,value

		print'after',smallest
		## 输出结果：

		Before

		9 9

		9 41

		9 12

		3 3

		3 74

		3 15

		After 3
		## 解释：给smallest赋初值为None,让迭代变量value在数据集中依次取值，然后进入双分值结构，判断smallest的值是不是None或者是不是比value大，只有第一次循环的时候，第一个判断条件能够成立，以后每次循环，第一个判断条件都不成立，进入第2个判断条件，实际上第2个判断条件才是用来找最小值的。直到value取遍数据集中的所有值时，smallest的值即为数据集的最小值。

3. “is”和“is not”运算符:这两个运算符都被用在逻辑表达式里，通常是用在分支结构的判断条件中。“is”在Python中的意思是“和···一样”，主要用来判断变量的值是否是None,False和True。它和“==”相似，但是比“==”程度更强。“==”只表示相同的数值，“is”表示完全相同。不要用i is 4 来表示i==4，不要过度用，通常在某些情况下才用is。


### 5.4 练习
werite a program which reads list of numbers until "done" is entered.once 'done' is entered, print out the total,count,and average ofthe numbers. if the user enters anything other than a number. print an error message and skip to the next number.

### 5.5 笔记链接
- [第五周wiki笔记](https://share.coursera.org/wiki/index.php/Pythonlearn:resources-week05)

## 第六周

### 6.1 字符串
1. 规则：
	- 字符串（String）:指一串有顺序的字符。字符串的定界符是单引号（‘ ’）或者（“ ”）。
	- 对于字符串来说，运算符“+”表示字符的连接。
	- 但是不能对数值型常量和字符型常量之间使用“+”。否则系统会报错。
	- 当字符串包含数字时，它仍然是字符串。
	- 我们可以通过int()函数把字符串中的数字转换成为数值型常量。
2. 读取和转化：我们通常用字符串来读取数据，之后再转化成我们需要的数据类型。这样能让我们更容易控制错误和无效用户输入的出现。
	- 用raw_input()函数输入的数据是字符串，如果你需要输入的是数字则需要转化。

3. 如何读取字符串中的某一或某些字符：我们可以用“方括号+索引值”的方式（即[索引值]）来得到出字符串中任意的单个字符。
	- 索引值必须是整数，且从0开始。
	- 索引值也可以是一个可计算的表达式。
	- 解释：因为索引值是从0开始的，所以当索引值为1时，实际上是字符串从左数第2位数。所以letter被赋予a。当n--1=2时，即索引值是2时，实际上是字符串从左数第3位数，所以w被赋值n。
	- 如果你的索引值超出了字符串的范围，那么系统会报错。所以索引时要注意！zot的最大索引值只能为2，而5>2，所以系统会报错。

4. 字符串的长度：系统内部函数len()可以用来计算字符串的长度。显而易见，banana的长度是6。len()是一个内部函数，由Guido编写。
5. 如何查看字符串中的每个字符:我们可以使用while循环语句和迭代变量以及len()函数来逐个显示字符串中的每个字符。
		
		方法1：
		fruit='banana'
		index=0
		while index < len(fruit)
		print index,letter
		index = index+1

		方法2：
		fruit='banana'
		for letter in fruit:
			print letter
		## 我们也可以使用for循环来显示字符串中的字符。这种方法看起来更简洁。

6. 循环计数:我们可以通过循环来计算出字符串中某一字符出现的个数。

		word='banana'
		count=0
		for letter in word:
			if letter == 'a':
			count=count+1
		print count

7. 深入了解in:上述例子中的letter是迭代变量，它将依次取遍word中的每一个字符，因此word中的每一个字符都将被用来执行循环主体部分中的程序。
8. 如何截取字符串中的连续字符：
	- 我们可以用冒号和中括号来截取字符串的连续字符。如s[a:b],s为字符串的变量名，a为截取部分的第一位索引值，b为截取部分的最后一位的下一位的索引值。a和b都是整数。如果b超过了字符串的范围，则截取的部分是从a开始，直到字符串末尾。
	- 如print s[0:4]是截取索引值为0到3的字符，即从左往右的1到4位，也就是Mont。
	- 如果我们省略了a,则认为我们是从开头开始截取字符串；如果我们省略了b,则认为我们是一直截取到字符串末尾。
	- 如print s[:2]是截取索引值为0到1的字符，即从左往右的1到2位，也就是Mo
9 把in作为运算符
    - in可以用来测试某个字符串是否在另一个字符串里面，
    - 也可以用在if分支结构的判断语句中

    		fruit='banana'
    		'n' in fruit ## 结果为true

10. 字符串包（String library）：Python有很多字符串的函数，这些函数已经嵌入每一个字符串，所以我们可以直接调用。这些函数并不会修改原先的字符串，相反，它们会返回一个新的更改过的字符串。	以用dir()函数来调出字符串的所有内部函数。

		greet='Hello Bob'
		zap=greet.lower()## 输出 hello bob
		
11. 查找字符串：我们可以通过find()来在字符串中查找它的子串的位置。find()找出的是子串的第一次出现。如果子串没有被找到的话，find（）会返回-1.

		fruit='banana'
	    pos = fruit.find('na')
	    print pos
	
12. 字符串大小写转化:我们可以通过upper()和lower()来对字符串进行大小写转化。通常我们在用find()查找子串的之前，会先进行大小写转化。

		greet = 'hello bob'
		nn = greet.upper()
		print nn ## HELLO BOB

13. 字符串替换:我们可以用replace()来替换字符串中某子串。注意，所有子串都将被替代。
	
		greet = 'hello bob'
		nn = greet.replace('bob','jane')
		print nn ## hello jane


		type('string') ## 内置查询数据类型的函数
		dir(Stuff) ## 内置查询字符串功能

14. 字符串去空格:我们可以用lstrip()和rstrip来分别去掉字符串左边或右边的空格，用strip()来去掉左边和右边的所有空格。

		greet=' hello bob '
		greet.istrip() ## 'hello bob '
		greet.rstrip() ## ' hello bob'
		greet.strip() ## 'hello bob'

15. 前缀（Prefixes）:我们可以用startswith()来测试字符串是否以某子串开头。
		
		line='please have a nice day'
		line.startswith('please') ## true
		line.startswith('P') ## false

16. 应用示例:从邮件文本信息中提取域名

### 6.2 练习

### 6.3 笔记链接
- [第六周wiki笔记](https://share.coursera.org/wiki/index.php/Pythonlearn:resources-week06)

## 第七周

### 7.1 Files
1. 之前我们所学的Python语言都是集中于CPU和主存储器之间的（也就是下图黄圈内的）一些工作，目前为止我们掌握的所有的东西都是为了接下来“跳出黄圈圈，走向绿圈圈（辅助存储器）
	![cup and memory](http://3.im.guokr.com/TNpLNrSgSf19fSD52Qo3xZuGKq4UF7X5BWxfu2zZUqfwAgAAPgIAAFBO.png)

2. 这里说的是储存于辅助存储器的文本文件（text file），是一系列的信息。
3. 打开文件：open()，open函数是Python既有的嵌入式函数。
	- 注：使用open命令之后，并不意味着你已经读取文件信息，而是得到一个“文件句柄（File Handle)”，说明你已经与文件建立了联系，可以读取它的信息（也可以想象成你念了一道open的咒令，新世界的大门向你打开，但真的只是“打开”而已；要得到宝藏，你还得自己走进去动手拿呀~）。
4. 处理文件：
	- handle = open(filename, mode)：括号里面，逗号前面表示文件名，后面表示你希望打开文件的模式（即采取什么动作）。如：open('mbox.txt', 'r') 其中，mbox.txt是你要打开的文件名，r说明你要读取它，w代表要写入。
	- 当然了，如果你要打开的文件不存在，就会报错。
5. 换行：/n，文本文件可以看成是有一系列“行”组成的。在Python里面，我们在需要换行的字符之间加入“/n”表示换行。
注：每个换行（即每个“/n”）都**占一个字符**，和每个空格一样。
		
		stuff'Hello\nWorld!'
		print stuff 
		## Hello
		## World!

6. 读取文件：用for循环（确定循环）
    - 数数文件有几行
	![read files](http://3.im.guokr.com/aHWRduFHcHiSoZ77w08hhaG-554y92O9Oo31p6e4WZihAgAAsAAAAFBO.png)
	- 如果文件不是很大，我们还是可以让计算机为我们读取整个文件的：
	![read whole](http://2.im.guokr.com/kvWnMknWmLAem-K-D871tW5f4MudrQS-XodYUj6_L-FaAwAAkAAAAFBO.png) 
    - 第二种方法的read是把整个文件都编程了字符串
7. 文档内搜索:介绍了3种方式，随你喜欢。

		fhand=open('mbox-short.txt')
		for line in fhand:
			if line.startwith('From'):
				print line
		## 在print的时候，额外的空行是因为原始文件有/n，python print出来了，"startswith"：为什么一定要用rstrip，每个“print"指令后面都会自带换行/n，每一行（每条line)后面本身也自带换行。因此如果没有rstrip()把每行后面的“/n"去掉，你就会看到写一行空一行的局面。

8. "continue":如果整个程序非常复杂，那就比较适合用这个函数。

		fhand=open('mbox-short.txt')
			for line in fhand:
				line =line.rstrip()
				## skip unintersting lines
				if not line.startwith('From'):
					continue
				## prcess our intersting line
				print line
			## 注：这是一个逆向搜索("if not")，但是2.2.1和2.2.2的结果是一样的。所谓逆向搜索的思路基本上就是“如果某一行不是你想找的，那就略过（skip）这行，搜索下一行”。
			## 这样的好处是：一旦某一行没有你要找的内容，那么Python就会回到循环的起点，而不用再理会其后复杂的程序。

9. "in":之前两种方式都是对句首加以限制条件（startswith)来搜索，如果要找文中任意一个角落呢？那就要用上我们教师最喜欢的（之一XXD）"in".
		
		fhand=open('mbox-short.txt')
			for line in fhand:
				line =line.rstrip()
				if not '@uct.ac.za' in line
				print line

11. 给我一个文件名，剩下的就交给我吧： raw_input
你不用每次要处理文件的时候都写个Python，好辛苦。你要做的就是稍稍改进一下你的代码，比如：

		fname =ray_input('Enter the file name:')
		fhand = open(fname)

12. 还有什么可以改善的：try/except
谨防有些熊孩子什么文件名都打得下手，“打”得不好（比如根本就不是个文件名啊什么的）系统狂报错怪我们写得不行，我们可以用个try/except结构来先检验一下~
	![](http://3.im.guokr.com/wvz8WqM8Vgd8XKKnEC582vxBPqzHrFuIchfg_ISblxbCAwAAMQEAAFBO.png)

### 7.2 练习

### 7.3 笔记链接
- [第七周wiki笔记](https://share.coursera.org/wiki/index.php/Pythonlearn:resources-week07)


## 第八周

### 8.1 List
1. 列表（List）允许我们在一个变量中放入许多值。如：friends=['Tom','Jenny','Mike'] 大多数的变量都只能有一个值，但当我们赋给这个变量一个新值时，这个新的值会把之前的值覆盖。
2. 列表常量（List constants）:
	- 列表常量被方括号包住，列表的属性之间用逗号隔开。
	- 列表元素（Elements）可以是Python的任意对象，包括另一个列表。
	- 列表可以为空。
	- ![dd](http://3.im.guokr.com/2WRCHx6T7DF4BWaIaRF43_vQaswH5Bo-CPB9-u2KJBL9AAAA3QAAAFBO.png)
3. 我们之前在for循环中已经用过列表了,for循环和列表的结合使用是一个很好的组合。
	- ![](http://3.im.guokr.com/lWQBcs18Lh15ukCvSxfkjY0xYYrQ39D7EN7N5XXjx8L8AAAAiwAAAFBO.png)
4. 列表索引:像字符串一样，我们也可以用方括号和索引值的方式来得到列表中的值。
	- ![LIST INDEX](http://1.im.guokr.com/cApbJr-iuFTjz8jtg6myQ95ahNRdc_k8qGgVH0jebBs7AQAAXwAAAFBO.png)
	- 字符串的值是不可变的，我们不能改变字符串的值，只能定义一个新的字符串来改变。但列表的值是可变的，我们可以通过索引来该改变列表的属性值。
	- ![](http://3.im.guokr.com/_8eRTaStA4q0Q3gm92juLu7HdJc8dYYYKxbEIsfhDBb1AAAALgEAAFBO.png)
	- 上例中要讲字符串的首字母变成小写，不能通过索引改变，否则只会出现报错。但是可以通过lower（）函数来改变。相反，我们可以通过所以来改变列表lotto的元素值。
5. 列表的长度:len（）函数会把列表看成一个参数，并把列表中元素的个数作为列表的长度。
![](http://3.im.guokr.com/ATHpCHqyeb7Kam89ubciy6Y0PMLA72Tl7pUisINQrWnJAAAAkgAAAFBO.png)
6. range()函数:range()函数能够返回一个列表的数值，这串数值从0开始，直到一个小于range（）函数参数的值。
	- ![](http://3.im.guokr.com/48Xd73VQxvoXgrstHmn8j9koWvnVAwDYXOM0rRjIMW0nAQAAqAAAAFBO.png)
 	- 解释：因为range函数的参数是4，所以第二行返回的值是含0到3的列表。因为friends的长度是3，所以第7行返回的值是含0到2的列表。
7. 我们可以用range()函数和for语句来构建一个循环函数。
	- ![](http://1.im.guokr.com/eYS4A4ETe91RqTOzQZdr_s2v35IUYh4PqeKino8PONYQAQAAuAAAAFBO.png)
	- 上图中有两个for循环函数，它们的作用是一样的，都是将列表中的元素值依次显示在‘Happy New Year’之后。
	- 两个for循环的输出结果都是：
	![](http://1.im.guokr.com/7hBlZJZJoiZF3HF5si6ugJdXr7JJAcePpaSEwaQ-8njBAAAATwAAAFBO.png)
8. 我们可以用“+”来连接两个原先的列表，从而来创建一个新的列表。
	- ![](http://3.im.guokr.com/IATvRnUGzOF7hQMwK8eXfXwc7sjvxwflY6xyV_-aRaGFAAAAngAAAFBO.png)
9. 截取列表:和截取字符串类似，我们也可以使用[a:b]的方式来截取列表。注意a，b都是整数，a可以从0开始取值，a,b也都可以省略。
	- 如果a省略，则截取的列表是从第一个元素值开始。
	- 如果b省略，则截取的列表是到最后一个元素值结束。
	- 如果a和b同时省略，则截取的是整个列表。
	- 但是要记得b的值是要截取的索引值+1.（说得有点拗口。。。）
	- 如t[1:3]取的是索引值为1到2的元素值，也就是列表中第2个到第3个的元素值，也就是41和12。
10. 增加列表：我们可以创建一个空的列表，然后通过append()函数来往空列表里面添加一个元素值。
	- 列表是有顺序的，每次添加的元素值都要放在之前元素值的后面。
	![](http://2.im.guokr.com/YsEf50Ori28SFIvL_s8AimktcYF23YGgES_fYFLLax_kAAAAtAAAAFBO.png)
11. in:我们可以用in和not in这两个运算符来判断一个数字或者字符串是否在列表中，判断之后将返回True或者False。但是这两个运算符并不更改列表的值。
	- ![](http://1.im.guokr.com/DPabBzW8pz_tD7Ep-UIszGd8Pnlxu_TaJhtiwKrd9zLkAAAAuQAAAFBO.png)
12. Sort():我们可以用sort()函数来改变列表中元素值的顺序。更改后字符串的顺序是按首字母的先后顺序排列。
	- ![](http://2.im.guokr.com/GNI1SlSRxviyKxtBFf6KKNgJlO0keE7T5egrXbpn1Aw3AQAAmgAAAFBO.png)
13. dir:Python中有很多内部函数可以用来处理列表。
	- ![](http://1.im.guokr.com/g3VxQaKKiuOvhIhD6cOwyGF61h9BWP-F6LcK1M2WIUgCAQAA6gAAAFBO.png)
	- 如len（）可以用来计算列表中元素值的个数，max（）和min（）可以用来找出列表中最大和最小的属性值，sum（）可以用来求列表元素值的和。

14. 用列表来求平均数
	- ![](http://2.im.guokr.com/5xf9_fRFn4QnVy75lStHthYYA8vZZ4knS7FQNa5MwjgcAQAAvgAAAFBO.png)
15. 我们可以用split()函数来把字符串分解，并放在列表中。
	- 当你没有明确字符串分解的定界符的时候，空格将被视为一个定界符。![](http://1.im.guokr.com/lguS3ogSCUxajvCBZ2ESGTmUC1lF0SM7KPN_1pPQQfP1AAAAqgAAAFBO.png)
	- 当然，你也可以明确定界符来让字符串分解更精确。![](http://2.im.guokr.com/LQ_C9wkwxyfTL5ZQRW8tlGtCxGTKxYAz4mLfOdI9ODRaAgAAMgEAAFBO.png)
	- 没有明确定界符的时候，空格被当做定界符，所以第四行的输出结果会是['A','lot','of','spaces'];但是第6行的line列表中没有空格，所以之后的分解对它无效。但是当之后明确了定界符是‘；’时，字符串又被分解了。
16. 有时候我们需要把字符串先分解开，成为列表后再取出其中某字符串再次分解。
	- ![](http://2.im.guokr.com/2WOx8DHPSSNWhBGhB3dcxTXwE4GLOX6AKmXEVV1RWZ5uAgAAswAAAFBO.png)
	- 上例就是要从最上方的那个字符串里面取出‘uct.ac.za’

### 8.2 练习
- 加入和debug，利用print检测程序运行到什么地方卡住了
- 在这个debug的作业中，利用 if words==[],来排除emailtxt中的空行

### 8.3 作业
	
		fname = raw_input("Enter file name: ")
		fh = open(fname)
		words = list()
		for line in fh:
		    for word in line.split():
		        if word in words: continue
		        words.append(word)
		words.sort()
		print words

### 8.4 作业

		fname = raw_input("Enter file name: ")
		fh = open(fname)
		count=0
		if len(fname) < 1 : fname = "mbox-short.txt"
		else:
		    for line in fh:
		        words = line.split()
		        if len(words)>2 and words[0]=='From':
		            count=count+1
		            print words[1]
		print 'There were',count,'lines in the file with From

## 第九周

### 9.1 Dictionaries

1. list 和dictionary的区别：dictionary没有顺序，但是有lable，它就像一个钱包，里面可以放各种东西
2. Different names for Dictionaries: 
    - Associative Arrays - Perl/Php
	- Properties of Map or HashMap - Java
	- Property Bag - C#/.Net

3. An example of working with Dictionaries (9A):   
		
		purse = dict()  
		purse['money'] = 12  
		purse['candy'] = 3  
		purse['tissues'] = 75  
		print purse  
		## Output: {'money':12,'tissues':75,'candy':3}
		## The output shows both the key('money') and the value ('12'). The value can be modified, like with lists. 
		## For example (9B): 
		purse['candy'] = purse['candy'] + 2  
		## Will change the value of 'candy' to 5.  

4. Dictionaries are like Lists except that they use keys('money') instead of numbers to look up values. (Lists are ordered, Dictionaries are not and so rely on keys for lookup)  

		## dic
		ddd=dict()
		ddd['age']=21
		ddd['course']=182
		print ddd
		## output {'course':182,'age':21}

		#list
		lst=list()
		lst.append(21)
		lst.append(183)
		print list
		## output [23,183]

5. Dictionary literals (constants) use curly braces {} and have a list of key : value pairs. As usual for dictionaries, the list is unordered.  

		iii={'course':182,'age':21}
		print iii
		## output {'course':182,'age':21}

6. The "in/not in" operators can be used to see if a key exists in the dictionary - without resulting in a traceback error.
			
			## Example (9C): 
			counts = dict()  
			names = ['csev','owen','csev','zqian','cwen']  
			for name in names: 
			  if name not in counts: 
			    counts[name]=1  
			  else: 
			    counts[name] = counts[name] + 1  
			print counts  

			## Traceback的情况
			ccc=dict()
			print ccc ['ccev']
			## 报错，因为还没有定义ccev
			print ‘csev’ in ccc
			## output:False，这个可以用于检查label是否在dictionary里面

7. The above operation is so common, that the method 'get' does it for us.  

			print counts.get(name,0)  

			## Performs the same operation as: 
			if name in counts: 
			  print counts[name]  
			else: 
			  print 0  

			## So, example 9C can be simplified down to (9D): 
			counts = dict()  
			names = ['csev','owen','csev','zqian','cwen']  
			for name in names: 
			  counts[name] = counts.get(name,0) + 1  
			print counts  

8. 读取高频词的算法：
		
			count=dic()
			print 'enter a line of text:'
			line = raw_input('')
			
			words=line.split()
			print 'words:',words

			print 'Counting……'
			for word in words:
				counts[word]=counts.get(word,0)+1
			print 'Counts',counts

9. for loop的结合
			
			counts={'chunk':1,'fred':42,'jan':100}
			for key in counts:
				print key,counts{key}

10. list与dic的转换
			
			jjj={'chunk':1,'fred':42,'jan':100}
			print list(jjj)
			## output:['jan','chunk','fred']
			print jjj.keys()
			## output同上
			print jjj.values()
			## output:[100,1,42]
			pprint jjj.items()
			#output:[('jan',100),('chunk',1),('fred,42')], 这个是tuple也就是pair

11. two interation variables

			jjj={'chunk':1,'fred':42,'jan':100}
			for aaa,bbb in jjj.items():
				print aaa,bbb
			## jan 100
			## chunk 1
			## fred 42

### 9.2 练习

### 9.3 笔记链接
- [第九周wiki笔记](https://share.coursera.org/wiki/index.php/Pythonlearn:resources-week09)

## 第十周

###  10.1 Tuples

1. 特征
Tuples are a sequence that behave much like a list, except:

*   Tuples are immutable (cannot be altered)，就像string一样

		x=[9,8,7]
		x[2]=6
		## output x = [9,8,6] list的数值是可以改变的

		x=‘abc’
		y[2]='d'
		## traceback 因为不能改变

		z=(5,4,3)
		z[2]=0
		## trackback

*   displayed surrounded by parenthesis '(,)' rather than brackets '[,]'
*   surrounding by parenthesis is just visual help; Comma is what makes tuple type
*   cannot sort, append, reverse, reorder, etc

		l=list()
		dir (1)

		t=tutple()
		dir(t)
		## output:['count','index']
		
*   can only: count and index

2. why use tuples:

*	Tuples are more efficient, they use less processing time since fewer operations are possible.  
*	Tuples are great for "temporary variables" because they are fast and easy to work with.  
*	Tuples can be placed on the left hand side on an assignment statement, the parenthesis can even be omitted.

		(x,y) = (4, 'fred')
		print y ## fred
		a,b=(99,98) ## 有时候可以省略()
		print a ## 99 

3. Tuples and Dictionaries

The 'items()' method in dictionaries returns a list of tuples (key, value).

		d=dict()
		d['csev']=2
		d['cwen']=4
		for (k,v) in d.items(): ## d.items 输出的时一列的的tuple
			print k, v
		## csev 2
		## cwen 4
		tups=d.items()
		print tups
		## [('csev,2'),('cwen'),4] ## 这个输出的是1个list

4. Tuples are Comparable 

1. The contents of a tuple can be compared and evaluated, running left to right through the listed variables. <, >, <=, =>, ==  

		(0,1,2)<(5,1,2) ## true
		(0,1,20000)<(0,3,1) ## true 第一个相同，那么看第二个，如果第二个true，其余的就不看了
		('jones','sally')<('jones','fred') ## false 对比第一个字母
		('Jones','sally')>('adam','sam') ## true


2. Tuples can be sorted within a dictionary because they can be compared against each other. (sorted by keys),tuples不能sort，但是把这些放到1个list里面就可以了，因为tuple之间可以比较
		
		d={'a':10,'b':1,'c':22}
		t=d.items()
		t 
		## output: [('a',10),('c',22),('b',1)]
		t.sort()
		t 
		## output [('a',10),('b',1),('c',22)]

3. 'sorted()', takes a sequence as a parameter and returns a sorted sequence.  

		d={'a':10},'b':1,'c:22'}
		d.items()
		## output: ['a',10],('c',22),('b',1)]
		t = sorted(d.items())
		t
		## output: ['a',10],('b',1),('c',22)]
		for k,v in sorted(d.items())
			print k,v

4. Sort by value instead of key: Can be done with a for loop, by reversing the value and key (v,k). 

		c = {'a':10, 'b':1, 'c':22, 'f':22}
		tmp = list()
		for k, v in c.items() :
		    tmp.append( (v, k) )

		print tmp
		## [(10, 'a'), (22, 'c'), (1, 'b'), (22, 'f')]
		tmp.sort(reverse=True)
		print tmp
		#[(22, 'f'), (22, 'c'), (10, 'a'), (1, 'b')]  
		#because 'f' comes  before 'c' when sorting in reverse order.
		## When sorting by value and there are duplicate values, the second item in the tuple defines the order of the duplicates.

5. A program show ten most common word:

		## v1
		fhand=open('mbox-short.txt')
		counts=dict()
		for line in fhand: ## 这里的line可以用a代替
			words=line.split() ## 此时的word变成了1个list
			for  word in words: #这里的word可以用b替换
				counts[word]=counts.get(word,0)+1

		lst=list()
		for key,val in counts.items(): ## counts.items()是一个list 
			lst.append((val,key)) ## 此处是为了交换

		lst.sort(revese=ture)

		for val,key in lst[:10]
			print key,val

6. List Comprehension

更简便的方法：List comprehension (represented by [,]) creates a dynamic list. 

		c={‘1’：10，'b':1,'c':22}
		print sorted( [ (v,k) for k,v in c.items() ] ) ## (v,k)目标值，然后做一个for loop循环
		## output: [(1,'b'),(10,'a'),(22,'c')]

The above can sort a list of items in a dictionary(c) by the value. By first reversing the tuples (v,k) and then sorting it.

### 10.2 练习

			handle = open('mbox-short.txt','r')
			lst=list()
			for line in handle:
				words=line.split()
				if words==[]:
					continue
				if words[0]=='From':
					time=words[5].split(':')
					lst.append(time[0])

			counts=dict()
			for a in lst:
				counts[a]=counts.get(a,0)+1
			## 第一种方法
			counts=sorted(counts.items())
			for a,b in counts:
				print a,b

			## 第二种方法
			## print sorted([ (t,c) for t,c in counts.items()])

### 10.3 笔记链接
- [第十周wiki笔记](https://share.coursera.org/wiki/index.php/Pythonlearn:resources-week10)

## 第十一周
### Regular Expression Quick Guide
1. guide 表格：

		^ - Matches the beginning of a line

		$ - Matches the end of the line

		. - Matches any character

		\s - Matches whitespace

		\S - Matches any non-whitespace character

		* - Repeats a character zero or more times

		*? - Repeats a character zero or more times (non-greedy)

		+ - Repeats a character one or more times

		+? - Repeats a character one or more times (non-greedy)

		[aeiou] - Matches a single character in the listed set

		[^XYZ] - Matches a single character not in the listed set

		[a-z0-9] - The set of characters can include a range

		( - Indicates where string extraction is to start

		) - Indicates where string extraction is to end

2. using re.search() like find()

		hand=open('ddd.txt')
		for line in hand:
			line=line.rstrip()
			if line.find('From')>=0
				print line

		## v2
		import re
		hand=open('ddd.txt')
		for line in hand:
			line=line.rstrip()
			if re.search('From:',line):
				print line

3. using re.search() like startwith()

		hand=open('ddd.txt')
		for line in hand:
			line=line.rstrip()
			if line.startswith('From'):
				print line

		## v2
		import re
		hand=open('ddd.txt')
		for line in hand:
			line=line.rstrip()
			if re.search('^From:',line): ## ^符号 这个输出是true false
				print line

4. wild-card characters: 

		^X.*: 
		## ^ match the start of the line
		## . match any character
		## * match any character
		## * many times

5. Fine-Tuning your match

		X-sieve:
		X-sdpam
		X plane is 
		#把搜索条件改变为: ^X-/S+:
		## /S : Matches any non-whitespace character

6. Matching and Extracting Data

		import re 
		x='My 2 favorite numbers are 19 and 42'
		y=re.findall('[0-9]+',x)
		print y 
		## output ['2','19','21']
		- 利用'import re'导入
		- use re.search() 

7. Warning:Greedy Matching

		import re
		x='from:using the :character'
		y=re.findall('^f.+:',x)
		print y
		## from:using the : 不严格的输出

8. non-greedy matching
	
		y=re.findall('^f.+?:',x) #加上一个问号

9. Fine Tuning String Extraction：找email

		y=re.findall('/S+@/S+',x)
		print y

10. The double split version:提取邮箱的前缀

		y=re.findall('@([^ ]*)',line) ## []表示单个字符，里面的^  表示非空格,() 表示提取的开始和结束
	

		## 更为完整的版本
		'^Frome .*@([^]*)'

11. Escape character
		
		importre
		x="we just received $10.00 for cookies."
		y=re.findall('\$[0-9.]+',x)






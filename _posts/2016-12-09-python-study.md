---
layout: post
title: 我的 python 学习之旅-1
---

## 我是怎样通过类比来学习 python2 的
在学习 python 之前我对 python 是个小白。在工作中用到好多第三方的工具（如 freeline），这些工具中就有好多 .py 的文件， 为了弄懂这些文件里的逻辑才来学习python 的，当前 freeline 采用的是 python2版本的，所以我是以 python2来学习的。PS: 我是做安卓的,对 Java 什么知道的多些，python 就……T_T

## 环境搭建
首先交待下我的学习工具，mac， pyCharm, sublime。
刚开始不推荐用 pyCharm 直接写 python 代码，因为好多东西 IDE 都帮我们做了，有些基础原理方面的东西就学不到了。

因为我用的是 mac ，已经帮我安装了 python，如果没有安装 python 的话，需要自行去安装，[传送门](http://www.python.org/)  。
在终端输入
> python --version

我的电脑出现的是 Python 2.7.10，表示我的电脑已经可以使用 python 了。

## 知识点整理

如前所述，我对 java 知道的多点，所以在学习 python 时总是习惯性的拿 python 和 java 来对比，不晓得哪个大牛说过，≖‿≖✧程序语言具有类比性，学好了一门，再去学另一门会容易些。不敢说我对 java 理解的有多透彻，以我 leader 的评价来说，算是熟悉吧，毕竟开发 android app 够用了。扯远了，哈……

先整体了解下 java 和 python 的异同吧
-1. 从编译类型上来说 python 是解释型语言，java 是编译型语言。python 是不需要编译的，可以直接运行的。
-2. 两者都对数据类型敏感，不同的数据类型之间的转换是需要类型转换的。
-3. 书写单行语句时，java 必须以分号";"结尾，python是可加可不加分号的,如下：
``` python
python
 print 'aa' # 1
 print 'bb'; #2
```
  注意，如果 #1，#2在同一行的话，则#1后面必须加分号,如下：
  
``` python
  python
	  print 'aa'; print 'bb'
```
-4. java 中双引号表示字符串，单引号表示字符，python 中 两种符号都表示字符串，python 中没有字符这种数据类型，另外 python 中还可以用 三个单引号 '''来表示字符串
> a='''hello python'''
三个单引号还可以用来显示多行字符串
> b = '''hello python
> hello java'''

-5. python 中对换行非常敏感，多条语句执行时，就是依据换行和缩进来决定招行范围的，如：
``` python
python
if 1<0:
	print 'hello python' #1
	print 'hello python2' #2
print 'hello java' #3
```
if 判断语句只能影响到 #1，#2，影响不到#3。这是因为 python 中不像 java 可能通过 花括号"{}"来表示代码块，方法体，python 对应的称为代码组，函数，代码组，函数是以冒号开始的相同缩进表示属于相同的代码组或函数，所以在 python 中不能随便缩进，不像 java，在一行语句前多敲几下空格是不影响最终结果的

-6. python 中用中括号"[]"表示列表

> c=[1,2,3,4]

相当于 java 中的集合，可以增删改查，
-7. python 中 的圆括号代表可读列表，只能读取不能修改相当于 java 中的常量数组。
-8. python 中的 字典和 java 中的 map 有点类似都是KV 结构
``` python
python
dd = {'a':1,'b':2,'c':3}
```
-9. python 中使用其他包下的函数需要引包使用 import 关键字，这点和 java 一样
-10. 重复执行命令，在 java 中如果要打印两遍同样的信息，要么循环，要么写两遍同样的语句，python 中只需要在调用的地方加上"*2"即可
``` python
python
	print 'aa'*2
```
-11.  python是面向对象的,这点和 java 相同，但是写法上又有点不同，因为在 Java 语法中，在类名后是用花括号包括的部分称为类体，在 python 中无此用法。python 中是依靠冒号的缩进组成的代码组来表示类体的，如:
``` python
python
	class KK:
		def __init__(self,name):
			self.name = name
		def showName(self):
			print 'name: ', name

	ks=KK('bruce')
	ks.showName()
```

'''_ _ init _ _(self,name)'''是类的构造函数, name 是入参，self 是本身，类的实例化没有 new 关键字，调用实例方法和 Java 类似，

-12.  垃圾回收机制，和 java 类似，当对象不再被引用时，会调用类 __del__方法回收内存

-13. java 和 python 都支持继承，区别是 python 支持多继承,java 继承的关键字 extends 而 python 是用圆括号来表示，多个父类用逗号分隔，如
``` python
python
	class KK:
	'测试类'
	def __init__(self, name):
		self.name = name
	def showName(self,msg):
		print 'name: ', self.name + msg
	def __del__(self):
		class_name = self.__class__.__name__
		print class_name + '销毁'
class SS:
	'SS'
	def __init__(self):
		print '调用子类构造方法2'
	def showTxt(self,msg):
		print msg
class TT(KK,SS):
	'TT'
	def __init__(self):
		print '调用子类构造方法'
```

-14. python 子类重写父类方法直接声明一个同名同参的方法即可，没有 java 的 override 关键字。
-15. 类变量的权限，对于成员变量，类实例可以访问，这点类似 Java 类中的 public 修饰的成员变量。对于私有变量 python 中在类中声明时须加两个下划线

> class TT:
	> __ss = 30


按照 Java 的思维习惯，私有变量是不能被外部实例访问，如上 
  > tt=TT()
	  > tt.__ss

会报错 AttributeError: TT instance has no attribute '_ss'，这样理解也没有什么问题，但是 python 和 Java 在访问私有变量是有个很大的不同，上述方法行不通，但是可以通过 tt._TT__ss 的形式来访问私有变量，这样私有变量也不是“私有”了

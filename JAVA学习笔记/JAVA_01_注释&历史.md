[[JAVA]]_01
 # 1.[[注释]]：可读性、调试代码；
 注释有：单行注释”//“、多行注释“/* */”、文档注释“/** */”；

 【文档注释：（java特有）注释内容可以被JDK提供的工具javadoc所解析，生成一套以网页文件形式体现的该程序的说明文档。

 ## 例如：

 /**

 @author snkstart

 @version v1.0

 这是我的第一个程序！非常开森！

 */

 编译后，class文件没有注释内容；

 多行注释不能嵌套使用

2.API（Application Programming Interface 应用程序编程接口)文档

api1.6&api se 8

  

---

## 对第一个Java程序进行总结

1.Java程序编写-编译-运行过程

编写：将编写的Java代码保存在以“.java"结尾的源文件中；

编译：使用javac.exe来编译java文件。格式为javac 源文件名.java;

运行：使用java.exe命令解释运行字节码文件。格式为：java 类名。

  

2.在一个java源文件中可以写多个class，只能最多有一个类声明为public;public的类的类名必须与源文件相同。

3.程序的入口是main()方法，格式是固定的。（args -> arguments)

public class HelloWorld{

	 public static void main(String[] args){

		 System.out.println("Hello World!");

	 }

}
*这是斜体示例*
4.输出语句：

**System.out.println();//先输出语句，再换行；

*System.out.print();//只输出语句；*

*5.每一行”；”结束；

6.编译以后，会生成一个或多个字节码文件。字节码文件与源文件中的类名相同；

---

集成开发环境（Integrated Development Environment)

---

JDK=JRE+开发工具集

JRE=JVM+java se 核心类库

---

JAVA_HOME=bin的上一层目录

path=%JAVA_HOME%\bin

---

class _01{

 	public static void main(String[] args){

 		System.out.println("姓名\n“）；

 		System.out.println("性别：男”）；

	 }

}

---

软件：即一系列按照特定顺序组织的计算机数据和指令的集合。分为：系统软件和应用软件；

人机交互方式：图形化界面&&命令行方式；

---

Algorithms+Data Structures=Programs

算法+数据结构=应用程序

---

[[计算机发展迭代史]]

第一代：机器语言

第二代：汇编语言

第三代：高级语言

（面向过程语言C、Pascal、Fortran，面向对象语言Java、JS、Python、Scala）

---

[[JAVA语言特点]]

>面向对象性

 两个要素：类、对象

三个特征：封装、继承、多态

>健壮性：去除C语言中的指针，自动回收垃圾机制-->仍然会内存溢出、内存泄露

>跨平台性：write once,run anywhere;一次编译!



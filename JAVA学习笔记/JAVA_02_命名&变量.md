[[JAVA]]_02

  *[[关键字]]（keyword）：被Java语言赋予了特殊含义，用作专门用途的字符串；*
*[[保留字]]（reserved word）：现有Java版本尚未使用，但可能在未来版本使用；*
*[[标识符]]（Identifier）：Java对各种变量、方法和类等要素命名时使用的字符序列称为标识符；*
## 命名规则
>严格区分大小写
>由26个英文字母大小组成，0-9，_ 或$组成；
>数字不可以开头；
>不可以使用关键字和保留字，但能包含关键字和保留字；
>Java中严格区分大小写，长度无限制；
>标识符不能包含空格
## 命名规范
	口诀：包名小写，变量小驼峰，类名大驼峰，常量大写。
>包名：多单词组成时，所有字母都小写：xxyyzz；
>类名、接口名：多单词组成时，首字母大写：XxxYyyZzz；
>变量名、方法名：多单词组成时，第一个单词首字母小写，第二个单词开始每个单词首字母大写：xxxYyyZzz；
>变量名：所有字母都大写，多单词时用下划线连接：XXX_YYY_ZZZ；

变量
>Java是一个强类型语言；
>变量不可以多次定义；

# 变量的分类
**变量在前一定要赋值**
![[变量的分类.png]]
## 数据类型
#基本数据类型(primitive type)
数值型：[[整型]]（byte,short,int,long）、浮点类型(float,double);
[[字符]]型：char;
[[布尔]]型：boolean;
#引用数据类型(reference type)
[[类]](class	);
[[接口]](interface);
[[数组]]([]);
***
******

		整型
		Java的整型常量默认为int型，声明long要加“l”或者“L”；
		类型		占用存储空间			表数范围
		byte     1字节=8bit位			-128~127
		short	 2字节				 -2^15~2^15-1
		int 	 4字节				 -2^31~2^31-1(约为21亿)
		long 	 8字节				 -2^63~2^63-1
	
******

		浮点型
		类型			占用存储空间				表数范围
	单精度float	 4字节				-3，403E38~3.403E38
	双精度double	 8字节				-1.798E308~1.798E308
	
float：尾数可以精确到7位有效数字；
double：精度是float的两倍；
*运行long要用“l”或“L”结尾，Ps:long b = 123456l(L)；*
*运行double要用“f"或“F”结尾，Ps:double b = 12.456f(F)；*
***{注意：如果输入的值没有超过int型范围，那么不加 “l”也没有问题，编译器会认为该数为int型。 Ps：long l = 123321}***
***{float类型不加“f”一样报错！，但是这里有一个地方要注意：用double类型不加“F”不会报错，Ps:double d2 = .314,但是输出结果只有.314，如果加了”F”，那么输出结果为：102.31400001049042；}***

****

	字符型
	1.定义char类型变量，通常使用一对''，内部只能写一个字符；
	2.转义字符 \b（退格符）\n \r（回车符）\t（制表符）\" \' \\ \\n；
	3.可以直接用Unicode值来表示字符型常量 Ps:'\u0043'表示“C”；
	
****

	布尔型（boolean)
	1.只能取两个值之一：true、false；
	2.常在条件判断、循环结构中使用；
	Ps:
>1.
>boolean isMarried = true;  
if (isMarried) {  
    System.out.println("你不能参加单身party！\n很遗憾！");  
} else {  
    System.out.print("你可以多谈谈女朋友！");  
}
>*result:	
你不能参加单身party！
很遗憾！*
	
***
***
## 基本数据类型之间的运算
### 1.自动类型提升
当容量小的数据类型的变量与容量大的数据类型的变量做运算时，结果自动提升为容量大的数据类型；
***byte 、short 、char <int <long <float <double***;
	*{特别的：当byte、char、short三种类型做运算时，结果为int(防止溢出，为了准确性和简洁性)}*
用大的类型去接受小的类型  Ps: int a =byte b +int c; 

### 2.强制类型转换
1.需要使用强转符；
2.可能导致精度损失；
**整型常量默认为int型，浮点型常量默认为double型；**
Ps:
>1.
>double d1 = 12.9;  
int i1 = (int) d1;  
System.out.println(i1);
>*result:	
>12*
>
>2.
>int i2 = 128;  
byte s2 = (byte) i2;  
System.out.println(s2);
>*result:
-28*

***
***

	字符串类型String
	String属于引用数据类型；
	Sting与char的区别：
	1.String输出字符串（>=0个字符），char输出字符（有且仅有一个字符）；
	2.String用""输入语句或字符，char用''输入字符；
	3.String长度没有限制；
	4.String可以和8种基本数据类型做运算，且运算只能是连接运算“+”；
	5.运算结果仍然是String类型；
	6.在进行连接运算时只要有String那么后面的连接都是String类型（Ps2）；
	
	PS:
>1.
>int number = 1001;  
String numberStr = "学号：";  
String info = numberStr + number;  
System.out.println(info);
>*result:	
学号：1001*
>
>2.
>char c = 'a';  
int num = 10;  
String str = "hello";  
System.out.println(c + num + str);  
System.out.println(c + str + num);  
System.out.println(c + (num + str));  
System.out.println((c + num) + str);  
System.out.println(str + num + c);
>*result:	
107hello
ahello10
a10hello
107hello
hello10a*
>
>3.
>System.out.println('\*' + ('\t' + "\*"));
>result:
\*	   \*


***
***

# [[进制]]与进制的转换
2进制以"0b"或"0B"开头
8进制以“0”开头；
16进制以“0x"开头；

           

0 | 0 | 0 | 0 | 1 | 1 | 1 | 0
1.*首位 为符号位，“0”代表是正数，“1”代表负数；*
2.  *Java整数常量默认是int类型，用二进制定义整数时，其第32位为符号位，当是long类型时，二进制默认占64位，其第64位是符号位;*
3.  *二进制的整数有三种类型：
 >原码:直接将一个数值换成二进制数.最高位是符号位;
 >负数的反码:是对原码按位取反,知识最高位(符号位)确定是1;
 >负数的补码:其反码加1;* 

4.计算机以二进制的形式保存所有整数
>正数的原码,反码,补码都相同;
>负数的补码是其反码+1;

	0 | 0 | 0 | 0 | 1 | 1 | 1 | 0		14
	
	1 | 0 | 0 | 0 | 1 | 1 | 1 | 0	-14的原码
	
	1 | 1 | 1 | 1 | 0 | 0 | 0 | 1	-14的反码(除符号外,各个位取反)
	
	1 | 1 | 1 | 1 | 0 | 0 | 1 | 0	-14的补码
	
	*计算机底层都以补码来存储数据*
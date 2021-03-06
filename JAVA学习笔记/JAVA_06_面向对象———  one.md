[[JAVA]]_07



### 如何理解“万事万物皆对象”
1.在Java语言范畴中，我们都将功能、结构等封装到类中，通过类的实例化，来调用具体的功能结构。
>scanner,string;
>file，文件；
>网络资源，URL；

2.涉及到Java语言和前端HTML、后端数据库交互时，都体现为类、对象。
## [[匿名对象]]
匿名对象的使用：

```java
package top.kukuli;  
  
/**  
 * @Author: Aaron.Li  
 * @Date: 2022 - 1 - 17 - 12:38  
 * @project: IDEA_Workspace  
 * @Version: JDK17.0.1  
 */  
/**  
 * 学习和测试匿名对象  
 * 1.理解：我们创建的对象，没有显式的赋给一个变量名，即为匿名对象；  
 * 2.特征：匿名对象只能调用一次；  
 * 3.使用：如下：  
 */  
public class Test31_AnonymousTest {  
 public static void main(String[] args) {  
 Phone p = new Phone();  
 p.sendEmail();  
 p.playGame();  
 //匿名对象的使用  
 //匿名对象：用一次情况  
 new Phone().sendEmail();  
 new Phone().price = 1999;  
 new Phone().showprice();  
 System.out.println("*************************************************");  
 //匿名对象：使用多次情况  
 PhoneMall mall = new PhoneMall();  
 mall.show(new Phone());  
 }  
}  
  
class PhoneMall {  
 public void show(Phone phone) {  
 phone.sendEmail();  
 phone.playGame();  
 }  
}  
  
class Phone {  
 double price;//价格  
  
 public void sendEmail() {  
 System.out.println("发送邮件");  
 }  
  
 public void playGame() {  
 System.out.println("打游戏");  
 }  
  
 public void showprice() {  
 System.out.println("手机价格是：" + price);  
 }  
  
}
```
## 自定义数组的工具类
Test32_ArrayUtilTest
### 方法的[[重载]]
Test33_OverLoadTest

> 概念：
> >在同一个类中，允许存在一个以上的同名方
> 法，只要它们的参数个数或者参数类型不同即可；
> 特点：
> >与返回值类型无关，只看参数列表，且参数列表必需不同（参数个数或参数类型）。根据方法参数列表的不同来区别；
> 实例：
> >返回两个整数的和：
> >int add(int x,int y){return x+y;}
> >返回三个整数的和：
> >int add(int x,int y,int z){return x+y+z;}
> >返回两个小数的和：
> >double add(double x,double y){return x+y;}

*要点*：“两同一不同”：同一个类、相同方法名；参数列表不同。
### [[可变个数的形参]]
Test34_MethodArgsTest

 * 可变个数形参的方法  
 * <p>  
 * 1.JDK5.0新增的内容  
 * 提供了Varargs(variable number of arguments)机制，允许直接定义能和多个实参相匹配的形参。  
 * 从而，可以用一种更简单的方式，来传递个数可变的实参。  
 * 2.具体使用：  
 * 2.1 可变个数形参的格式：  
 * 数据类型...变量名  
 * 2.2 当调用可变个数的形参方法时，传入的参数个数可以是：0个、1个……；  
 * 2.3 可变个数形参的方法与本类中方法名相同，形参不同的方法之间构成重载；  
 * 2.4 可变个数形参的方法与本类中方法名相同，形参类型也相同的数组之间不构成重载（二者之间不共存）；  
 * 2.5 可变个数形参在方法的形参中，必须声明在末尾；  
 * 2.6 优先执行确定形参的方法，没有再执行可变个数形参方法；  
 * 2.7 可变个数形参在方法的形参中，最多只能声明一个可变形参。  

### 说明Java方法中的参数传递机制的具体表现：
基本数据类型：数据值；
引用数据类型：地址值（含变量的数据类型）；  
```java
//Person p1 = new Person();
//User u1 = p1;//编译错误
/**
*原因：地址值是含有数据类型的，必须类型也相同才能赋值；
*类似：int[] x,y[]; //表示：定义了一个一维数组x和二维数组y；
*/
```  
```java
package student;  
  
/*  
 * @author: Aaron.Li * @data: 2022 - 01 - 30 - 下午1:58  
 * @project: IDEA_Workspace * @version: JDK17.0.2 */public class ValueTransferTest {  
 public static void main(String[] args) {  
 String s1 = "hello";  
 ValueTransferTest test = new ValueTransferTest();  
 test.change(s1);  
 System.out.println(s1);  
 }  
  
 public void change(String s) {  
 s = "hi~~";  
 }  
}
```
内存解析：
![[Pasted image 20220130231652.png]]
## return关键词的作用
一、结束方法
二、针对于有返回值的方法，return + 返回数据
### 代码的内存解析
*把握*：
>1.内存结构：栈（局部变量）、堆（new出来的结构：对象（非static成员变量）、数组）
>2.变量：成员变量 vs 局部变量（方法内、方法形参、构造器内、构造器形参、代码块内）
### 递归
>方法递归包含一种隐式的循环，它会重复执行某段代码，但这种重复执行无须循环控制。
>递归***一定要向已知方向递归***，否则这种递归就变成了无穷递归，类似于死循环。
#接口
###概述
- 一方面，有时必须从几个类中派生出一个子类，继承它们所有的属性和方法。但是，Java不支持多重继承。有了接口
就可以得到多重继承的效果。
- 另一方面，有时必须从几个类中抽取出一些共同的行为特征，而它们之间又没有is-a（子父类）的关系，仅仅是具有相同的行为
特征而已。例如：鼠标、键盘、打印机、摄像头、充电器、MP3、手机、数码相机、移动硬盘等都支持USB连接。
- 接口就是规范，定义的是一组规则，体现了现实世界中“如果你是/要……则必须能……”的思想。
<font color=#fb7299> 继承是一个“是不是”的关系，而接口实现的是“能不能”的关系</font>
- <font color=#fb7299> 接口的本质是契约，标准，规范</font>,就像我们的法律一样。制订好后大家都要遵守。
- 定义Java类的语法格式：<font color=#6366e2> 先写extends，后写implements</font>
>class SubClass extends SuperClass <font color=#b32324> implements </font> InterfaceA{}
- 一个类可以实现多个接口，接口也可以继承其他接口（多继承）
- 实现接口的类中必须提供接口中所有方法的具体实现内容，方可实例化（就是要重写所有抽象方法，不过一般读作实现）
。否则，仍为抽象类。
- 接口的主要用途就是被实现类实现。（<font color=#b32324>面向接口编程</font>)
- 与继承关系类似，接口与实现类之间存在多态性
- 接口和类是并列关系，或者可以理解为一种特殊的类。从本质上讲，接口是一种特殊的抽象类，这种抽象类中
<font color=#b32324>只包含常量和方法的定义（JDK7.0及以前）</font>，而没有变量和方法的实现。












### 如何理解“万事万物皆对象”
1.在Java语言范畴中，我们都将功能、结构等封装到类中，通过类的实例化，来调用具体的功能结构。
>scanner,string;
>file，文件；
>网络资源，URL；

2.涉及到Java语言和前端HTML、后端数据库交互时，都体现为类、对象。
## 匿名对象
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
### 方法的重载
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
### 可变个数的形参
Test34_MethodArgsTest
### 方法参数的值传递机制

说明Java方法中的参数传递机制的具体表现：
基本数据类型：数据值；
引用数据类型：地址值（含变量的数据类型）；  
```java
Person p1 = new Person();
User u1 = p1;//编译错误
/**
*原因：地址值是含有数据类型的，必须类型也相同才能赋值；
*类似：int[] x,y[]; //表示：定义了一个一维数组x和二维数组y；
*/
```                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          
### return关键词的作用
一、结束方法
二、针对于有返回值的方法，return + 返回数据
### 代码的内存解析
*把握*：
>1.内存结构：栈（局部变量）、堆（new出来的结构：对象（非static成员变量）、数组）
>2.变量：成员变量 vs 局部变量（方法内、方法形参、构造器内、构造器形参、代码块内）

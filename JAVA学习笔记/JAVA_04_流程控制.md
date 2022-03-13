[[JAVA]]_04
# 额外补充
从键盘中获取不同类型变量：需要使用[[scanner]]类
实现步骤：
>1.导包：import java .util.Scanner;
>2.Scanner的实例化：Scanner scan = new  Scanner(System.in)；
>调用Scanner类的相关方法(next() / nextXxx())，来获取指定类型的变量；
>

 Ps:
>import java.until.Scanner;
>public class Test5_Get_Variable {  
 >  public static void main(String[] ages) {  
       >Scanner scan = new Scanner(System.in);  
>System.out.println("请输入你的名字");  
>String name = scan.next();  
>System.out.println(name);  
>}  

	注意：没有char类型的输入，它被String代替，String直接用next()表示，其他类型前要加类型名称；
	
获取当前时间距离1970.01.01  00：00：00的毫秒数
long  start = System.currentTimeMillis();
……
long  end = System.currentTimeMillis();
System.out.println("所花费的时间（秒）为："+(end-start)/1000);
获取[[随机数]]
*Math.random()* 获取的是[0.0~1.0)的数
	Ps:
	int value =(int)(Math.random()*90+10);//[10,99)

***公式：[a,b] :(int)(Math.random()\*(b-a+1)+a)***
ps:[10,99] (int)(Math.random()\*(99-10+1)+10)


String类型可以通过variabel.equals()实现判断正确错误；
Ps:
>isHandsome.equals("是");
>如果一样的，则返回true，否则返回false;
	
### [[算法优化]]
[[时间阀度]]算法优化考虑量级上的优化，比如O(n/2)在量级上跟O(n)是一样的
唯有比如这个算法我花了12秒，换一个算法我只花了2秒，才算得上算法优化；
[[开方]]：
Math.sqrt(i)
# 分支结构
## swith-case
switch(表达式){
case 常量1：
执行语句2；
//break;
……
case 常量2：
执行语句n;

//break;
default;
}
#说明：
1.
根据switch表达式中的值，依次匹配各个case中的常量。一旦匹配成功，则进入相应case结构中，调用其执行语句。当调用完执行语句以后，则仍然继续执行其他case结构中的执行语句，直到遇见break关键字或或此switch-case结构末尾为止结束。
2.
switch结构中的表达式，只能是如下的6种类型之一：
byte、short、char、int、枚举类型（JDK5.0新增）、String类型（JDK7.0新增）；
3.
case后面不能填写范围；

# 循环结构
1.循环结构的四要素：
初始化条件、循环条件 --->是boolean类型、循环体、迭代条件；
说明：通常情况下,循环结束因循环条件返回false结束；
2.实际开发中基本上都用for和while循环；
## for循环
## While循环
写while循环千万不要丢掉迭代条件；
## do-while循环
do{

}while();
## 嵌套循环
将一个循环结构A声明在另一个循环结构B的循环体中，就构成了嵌套循环；
外层循环需要执行m次，内层循环执行了n次。此时内层循环一共执行m\*n-1次；
外层循环控制行数，内层循环控制列数；

## 无限循环：
while(true)或for(;;)
### 特殊关键字break、continue的使用

break:结束当前循环；默认跳出包裹此关键词的最近的一层循环；
continue：结束当次循环；  
写在break和continue后的语句是没办法执行的；

	标签：在循环前面加上一个标识：PS: lablel:for(int i=1……)
	……
	break label;
	


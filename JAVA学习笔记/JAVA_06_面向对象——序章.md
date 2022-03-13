[[JAVA]]_06

# 学习[[面向对象的三条主线]]
一、[[Java类及类的成员]]：属性、方法、构造器、代码块、内部类；
二、[[面向对象的三大特征]]：封装性(Encapsulation)、继承性(Inheritance)、多态性(Polymorphism),（抽象性(Abstraction)）；
三、[[其他关键词]]：this、super、static、final、abstract、interface、package、import等；
四、
> ***对类和对象的理解，对象是类的的实例化***；
> 类：抽象的、概念上的东西；
> 对象：实实在在存在的东西；
> 对象是类派生出来的；

五、类和对象的创建和执行操作有那三步？
>①、创建类；
>②、类的实例化；
>③、调用类结构；”对象.属性“、”对象.方法“

## 面向对象[^English]和面向过程[^2]
- 二者都是一种思想，面向对象是相对于面向过程而言的。面向过程，*强调的是功能行为，以函数为最小单位，考虑怎么做*。面向对象，将功能封装进对象，*强调具备了功能的对象，以类/对象为最小单位，考虑谁来做*。
- 面向对象更加强调运用人类在日常的思维逻辑中采用的思想方法和原则，如抽象、分类、继承、聚合、多态等。

### 面向对象的基本要素
类：对一类事物的描述，是抽象的、概念上的定义；
对象：是实际存在的该类事物的每个个体，因而也被称为实例(instance);

### 设计类
- 一、设计类，其实就是设计类的成员
>属性\==成员变量\==field\==域、字段；
>方法\==成员方法\==函数\==method;
```java
class Person {  
 //属性，或成员变量；  
 String name;  
 boolean isMarried;  
  
 //构造器；  
 public Person() {  
 }  
 public Person(String n, boolean im) {  
 name = n;  
 isMarried = im;  
 }  
  
 //方法，或函数；  
 public void walk() {  
 System.out.println("人走路……");  
 }  
  
 public String display() {  
 return "名字是：" + name + "，Married:" + isMarried;  
 }  
  
 //代码块；  
 {  
 name = "HanMeiMei";  
 age=17;  
 isMarried = true;  
 }  
  
 //内部类；  
 class pet {  
 String name;  
 float weight;  
 }  
}
```
- 二、对象的创建和使用（面向对象思想落地的实现）3
>① java类及类的成员创建;*（最重要）*-->② java类的实例化，即创建类的对象;-->③ 通过”对象.属性“或”对象.方法"调用对象的结构；

```java
// 二、对象的创建和使用（面向对象思想落地的实现）；
//创建类的对象=类的实例化=实例化类；
public class Test24_PersonTest {  
 public static void main(String[] args) {  
 //创建Person的类（类的实例化）；  
 Person p1 = new Person();  
 //Scanner scanner=new Scanner(System.in);  
 //调用对象的结构：属性、方法；
 //调用属性："对象.属性"; p1.name = "Tom";  
 p1.isMale = true;  
 p1.name="Tom";
 //调用方法："对象.方法";  
 p1.eat();  
 p1.sleep();  
 p1.talk("chinese");  
 }  
}  
  
//类；  
class Person {  
 //属性；  
 String name;  
 int age = 1;  
 boolean isMale;  
  
 //方法；  
 public void eat() {  
 System.out.println("人可以吃饭");  
 }  
  
 public void sleep() {  
 System.out.println("人可以睡觉");  
 }  
  
 public void talk(String language) {  
 System.out.println("人可以说话，使用的语言是：" + language);  
 }  
}
```
- 三、如果创建了一个类的多个对象，则每个对象都拥有一套类的属性。（非static的）；
意味着：如果我们修改一个对象的属性a,则不影响另一个对象属性a的值；


![[Pasted image 20211225201558.png]]

- 四、内存解析
![[Pasted image 20211225203737.png]]

- 五、类中[[属性的使用]]
	>属性（成员变量）VS  局部变量
	>1.相同点：
	>>1.定义的格式一样：数据类型 变量名=变量值；
	>>2.先声明，后使用；
	>>3.变量都有其对应的作用域；
	>
	>2.不同点：
	>>1.在类中声明的位置的不同；
	>>
	>>>a.属性：直接定义在类的一对{}内：
	>>>b.局部变量：声明在方法内、方法形参、代码块内、构造器形参、构造器内部的变量；
	>>
	>>2.关于权限修饰符的不同：
	>>>a.属性：可以在声明属性时，指明其权限，使用权限修饰符。
	>>>常用的权限修饰符：private、public、缺省、protected；（封装性）
	>>>b.局部变量：不可以使用权限变量；
	>>
	>>3.默认初始化值的情况：
	>>>a.属性：类的属性，根据其类型，都有默认初始化值。
	>>>整型(byte、short、long):0;
	>>>浮点型(float、double):0.0;
	>>>字符型(char):0（或'\u0000'）；
	>>>布尔型(boolean):false;
	>>>引用数据类型（类、数组、接口）：null;
	>>>b.局部变量：没有初始化值
	>>>意味着：我们要在调用之前要进行初始化；
	>>>*特别的：形参在调用时，赋值即可*
	>>
	>>4.加载的内存位置：
	>>>a.属性：加载到堆空间（非static)；
	>>>b.局部变量：加载到栈空间；
- 六、类中[[方法的声明和使用]]
>1.方法：描述类应该具有的功能；
>>比如：
>>Math类：aqrt()\random()……；
>>Scanner类：nextXxx()……；
>>Arrays类：sort()、binarySearch()、toString()、equals()……；
>
>2.方法的声明：
>>权限修饰符 返回值类型 方法名（形参列表）{
>>方法体
>>}
>>*注意：static、final、abstract来修饰方法*
>
>3.说明：
>>a.Java规定四种权限修饰符：private、public、缺省、protected；
>>b.返回值类型：有返回值 VS 没有返回值
>>>a.*如果方法有返回值，则必须在方法声明时，指定返回值类型。同时，方法中，需要使用return来返回指定的类型的值；*
>>>b.如果方法没有返回值，则方法声明时，用void来表示。通常，没有返回值的方法，就不使用return。但是，如果使用的话，只能用"return;"表示结束此方法；
>>>c.定义方法该不该要返回值？
>>>>①题目要求；
>>>>②凭经验，具体问题具体分析；
>>
>>c.方法名：属于标识符，遵守标识符的命名规范。“见名知意”；
>>d.形参列表：方法可以声明0个，1个，或多个形参。格式：数据类型1 形参1，数据类型2 形参2 ……；
>>>要不要形参？
>>>①题目要求；
>>>②凭经验，具体问题具体分析；
>>
>>e.方法体：方法的功能具体体现；
>
>4.return关键字的使用：
>>a.作用范围：使用在方法体中；
>>b.作用：
>>>①结束方法；
>>>②争对有返回类型的方法，使用"return数据"方法返回所要的数据；
>>c.注意点：*return关键词后面不可以有执行语句；*
>
>5.方法的使用:
>>*可以调用当前类的属性或方法*；
>>特殊：*在方法A中再调用方法A：递归*；
>>*方法里面不可以再定义新的方法*；

```java
//六、类中方法的声明和使用
public class Test25_CustomerTest {  
 public static void main(String[] args) {  
 Customer cust1 = new Customer();  
 int[] arr = new int[]{1, 3, 5, 7, 54, 432, 534, 8586};  
 int key = 54;  
 int arr1 = cust1.hell(arr, key);  
 System.out.println(Arrays.toString(arr));  
 System.out.println(arr1);  
 cust1.sleep(8);  
 }  
  
}  
  
//客户类；  
class Customer {  
 //属性；  
 String name;  
 int age;  
 boolean isMale;  
  
 //方法；  
 public void eat() {  
 System.out.println("客户吃饭");  
  
 }  
  
 public void sleep(int hour) {  
 System.out.println("休息了" + hour + "个小时");  
 }  
  
 public String getName() {  
 if (age > 18) {//可以调用当前类中的属性或方法；  
 return name;  
 } else {  
 return "Tom";  
 }  
 }  
 public String getNation(String nation) {  
 String info = "我的国籍是：" + nation;  
 return info;  
 }  
  
 public int hell(int[] arr, int key) {  
 Arrays.sort(arr);  
 int arr1 = Arrays.binarySearch(arr, key);  
 if (arr1 >= 0) {  
 return arr1;  
 } else {  
 return -1;  
 }  
 }
}
```




























[^English]:- 面向对象(OOP):Object Oriented Programming
具体实现方式（以“人把大象塞进冰箱为例）：
① 把冰箱门打开；
②抬起大象，塞进冰箱；
③把冰箱门关上；
[^2]:- 面向过程(POP):Procedure Oriented Programming
具体实现方式（同样以“人把大象塞进冰箱为例）：
人{
			打开（冰箱）{
			冰箱.开开();
			}
			抬起（大象）{
			大象.进入();
		}
		关闭（冰箱）{
		冰箱.关关();
		}
		}
冰箱{
开开(){};
关关(){};
}
大象{
进入(){};
}
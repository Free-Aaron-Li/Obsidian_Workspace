[[JAVA]]_08

# [[封装与隐藏]]

### 为什么要引入封装性？

* 程序设计追求“高内聚，低耦合”

> 高内聚：类的内部程序操作细节自己完成，不允许外部干涉 ；
> 低耦合：仅部分暴露少量的方法用于使用；

* 隐藏对象内部的复杂性，只对外公开简单的接口。便于外界调用，从而提高系统的可扩展性、可维护性。通俗的说：*把该隐藏的隐藏起来，该暴露的暴露出来。这就是封装性的设计思路*

### 问题引入

* 当我们创建一个类的对象以后，我们通过“对象.属性”的方式，对对象的属性进行赋值。其中赋值操作受到属性的数据类型和存储范围的制约。
  但是在实际的情况中,我们往往需要添加额外的条件。这个条件就不能在属性声明时体现，我们只能够通过方法添加限制条件。（比如：通过添加私有(private)，来使得不能调用legs 属性，从而达到想要的目的）-->这就是封装性的体现

### 封装性思想具体的代码体现

#### 体现一：

将类的属性私有化（private），提供公共的（public）方法来获取（getXxx）和设置（setXxx）

```java
public void setLegs(int l){
        if(l>=0&&l%2==0){
        legs=l;
        }else{
        legs=0;
        }
        }
public void setAge(int a){
        ages=a;
        }
public int getLegs(){
        return legs;
        }
public int getAge(){
        return ages;
        }
```

#### 体现二：

不对外暴露的私有方法

#### 体现三：

单例模式（将构造器私有化）

#### 体现四：

如果不希望类在包外被调用，可以将类设置为缺省的。

### Java规定的四种权限修饰符

#### 权限从小到大顺序为：

private < 缺省 < protected < public

#### 具体修饰范围

![[Pasted image 20220213180912.png]]

#### 权限修饰符可用来修饰的结构说明：

4种权限都可以用来修饰类的内部结构：属性、方法、构造器、内部类。  
具体解释：

* 修饰类：只能使用：缺省、public。

# 类的结构：[[构造器]]

## 作用：

1.创建对象 2.初始化对象结构

## 注意点：

1.如果没有显式的定义类的构造器的话，则系统默认提供一个空参的构造器（*根据类的权限确定构造器权限*） 2.定义构造器的格式：权限修饰符 类名（形参列表）{}  
3.一个类中定义的多个构造器，彼此构成重载  
4.一旦我们显式的定义了类的构造器之后，系统就不再提供默认的空参构造器  
5.***一个类中，至少会有一个构造器***

## 举例：

```java
public Test40_TriAngle(){
        }

public Test40_TriAngle(double base,double height){
        this.base=base;
        this.height=height;
        }
```

## 类的属性的赋值

默认初始化 -> 显式初始化 -> 构造器中初始化 ->对象.方法或对象.属性给属性赋值

## JavaBean的概念

所谓JavaBean，是指符合如下标准的Java类：
> 类是公共的  
> 有一个无参的公共的构造器  
> 有属性，且有对应的get、set方法

* 用户可以使用JavaBean将功能、处理、值、数据库访问和其他任何可以用Java代码创造的对象进行打包，并且其他的开发者可以通过内部的JSP页面、Servlet、其他JavaBean、applet程序或者应用来使用这些对象。
* 用户可以认为JavaBean提供了一种随时随地的复制和粘贴的功能，而不用关心任何改变。

# [[this]]关键字的使用：

### 1.this可以用来修饰：属性、方法、构造器

### 2.this修饰属性和方法：

* this理解为当前对象或当前正在创建的对象

> 2.1
> 在类的方法中，我们可以使用“this.属性”或“this.方法”的方法，调用当前对象属性或方法。但是，通常情况下，我们都选择省略“this.”。特殊情况下，如果方法的形参和属性同名时，我们必须显式的使用“this.”的方式，表明此变量是属性，而非形参。
> 2.2
> 在类的构造器中，我们可以使用“this.属性”或“this.方法”的方法，调用当前对象属性或方法。但是，通常情况下，我们都选择省略“this.”。特殊情况下，如果方法的形参和属性
> 2.3
> 同名时，我们必须显式的使用“this.”的方式，表明此变量是属性，而非形参。

### 3. this调用构造器

> 1.我们在类的构造器中，可以显式的使用“this（形参列表）”的方式，调用本类中指定的其他构造器
> 2.构造器中不能通过“this（形参列表）”调用自己
> 3.如果一个类中有n个构造器，则最多有n-1构造器中使用了“this（形参列表）”
> 4.规定：”this（形参列表）“必须声明在构造器的首行
> 5.构造器内部，只能调用一个“this（形参列表）”

# package和import的使用

## 一、[[package]]关键字的使用

* 1.为了更好的实现项目中类的管理，提供包的概念
* 2.使用package声明类或接口所属的包，声明在源文件的首行
* 3.包，属于标识符，遵循标识符的命名规则、规范（都是小写）、“见名知意”
* 4.每“.”一次，代表一层文件目录
* 补充：同一个包下，不能命名同名的接口、类;不同的包下，可以命名同名的接口、类。

### 举例：

[[MVC设计模式]]
[[JDK主要包介绍]]

### JDK中主要包介绍

## 二、[[Import]]=关键字的使用

* import：导入
* 1.在源文件中显式的使用import结构导入指定包下的***类、接口***。
* 2.声明在包的声明和类的声明之间
* 3.如果需要导入多个结构，则并列写出即可
* 4.可以使用“xxx.*”的方式，表示导入xxx包下的所有结构
* 5.如果使用的类或接口是java.lang包下定义的，则可以省略import结构
* 6.如果使用的类或接口是在本包下定义的，则可以省略import结构
* 7.如果在源文件中，使用了不同包下的同名的类，则必须至少有一个类需要以全类名的方式显示
* 8.如果使用“xxx.*”方式表明可以调用xxx包下的所有结构，但是如果使用的是xxx子包下的结构，则仍需要显式导入
* 9.import static：导入指定类或接口的静态结构（***属性或方法***）

忙于创建博客，没写代码。´ ▽ ` )ﾉ`
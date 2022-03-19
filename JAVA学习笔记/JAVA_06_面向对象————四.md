[[JAVA]]_09_
# 多态性
## 1.多态性的理解：可以理解为一个事物的多种形态
## 2.何为多态性
### 对象的多态性：*父类的引用指向子类的对象（或子类的对象赋给父类的引用）*
### 举例：
```java
Person p =new Man();
Object obj=new Date;
```
### 3.多态性的使用：虚拟方法调用
>有了对象的多态性以后，我们在编译期，只能调用父类中声明的方法，但在运行期，我们实际执行的是子类重写父类的方法。
>总结：编译，看左边；运行，看右边。
### 4.多态性的使用前提：
① 类的继承关系
② 方法的重写
### 5.多态性的运用举例：
day13/java1
### 7.向下转型和向上转型
#### 为什么要使用向下转型：
>有了对象的多态性以后，内存中实际上是加载了子类特有的属性和方法，但是由于变量声明为父类类型，导致编译时，只能调用父类中声明的属性和方法。子类特有的属性和方法不能调用。//如何才能调用子类所特有的属性和方法？向下转型
#### 如何实现向下转型：
>强制类型转换：（）
#### 使用时的注意点：
>① 使用强转时，可能出现ClassCastExeption的异常
>② 为了避免在向下转型时出现ClassCastException的异常，我们在向下转型之前，先进行instanceof的判断，一旦返回true,就进行向下转型。如果返回false,就不进行向下转型。
>③ a instanceof A:判断对象a是否是类A的实例。如果是，返回true;如果不是，返回false。如果 a instanceof A:返回true,a instanceof B:也返回true。 其中，类B是类A的父类。
### 8.多态性的理解
>实现代码的通用性。

#### 举例：
>Object类中定义的public boolen equals(Object onj){}
>JDBC:使用java程序操作（获取数据库连接、CRUD）数据库
>抽象类、接口的使用
#### 多态性是运行时行为
# Object类的使用
## 1.java.lang.Object类的说明：
>1.Object类是所有Java类的根父类
>2.如果在类的声明中未使用eextends关键字指明其父类，则默认父类为java.lang.Object类
>3.Object类中功能（属性、方法）就具有通用性。
>>属性：无
>>方法：equals()/toString()/getClass()/hashCode()/clone()/finalize()/wait()/notify()/notifyAll()
>4.Object类只声明了一个空参的构造器



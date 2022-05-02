<!--
 * @Description: 
 * @version: JDK17
 * @Author: Aaron.Li
 * @Date: 2022-02-15 22:14:17
 * @LastEditTime: 2022-03-09 15:07:32
-->

[[JAVA]]_设计模式

# [[MVC设计模式]]
MVC是常用的设计模式之一，将整个程序分为三个层次：*视图模型层（view）*、*控制器层（controller）*、*数据模型层（model）*。这种将程序输入输出、数据处理，以及数据的展示分开来的设计模式是程序结构变得灵活而且清晰，同时也描述了程序各个对象间的通信方式，降低了程序的耦合性。

### 数据层 （model）主要处理数据
>数据对象封装  model.bean/domain
>数据库操作类  model.dao
>数据库 model.db
### 控制层 （controller）处理业务逻辑
>应用界面相关 controller.activity
>存放fragment controller.fragment
>显示列表的适配器 controller.adapter
>服务相关 controller.service
>抽象的基类 controller.base
### 视图层 （view）显示数据
>相关工具类 view.utils
>自定义view view.ui

##多态的应用：模板方法设计模式（TemplateMethod）
>抽象类体现的就是一种模板模式的设计，抽象类作为多个子类的的通用模板，子类在抽象类的基础上进行扩展、改造，但子类
> 总体上会保留抽象类的行为方式。
##解决的问题

>当功能内部一部份实现是确定的，一部分实现是不确定的。这时可以把不确定的部分暴露出去，让子类去实现。
> 
> <font color=#fc5531>换句话说，在软件开发中实现一个算法时，整体步骤很固定、通用，这些步骤已经在父类中写好了。
> 但是某些部分易变、易变部分可以抽象出来，供不同子类实现。这就是一种模板模式。</font>



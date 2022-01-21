[[markdown]]

### 一、代码块：
>通过三个（\`)号表示,并加上你要打的语言；格式\```+语言（java)

1.java代码
```java
public class Test1_Digital_Disassembly {  
 public static void main(String[] args) {  
 int num = 123;  
 System.out.println("数字：=" + num + "的情况如下：");  
 System.out.print("个位数：=" + num % 10 + "\n" + "十位数：=" + num / 10 % 10 + "\n" + "个位数：=" + num / 100 + "\n");  
 }  
}
```
2.shell代码
```shell
public class Test2_Short_Circuit_Operation {  
 public static void main(String[] args) {  
 boolean b1 = true;  
 b1 = false;  
 int num1 = 10;  
 if (b1 & (num1++ > 0)) {  
 System.out.println("我现在在东京！");  
 } else {  
 System.out.println("我现在在西京！");  
 }  
 System.out.println("num1=" + num1);  
 boolean b2 = true;  
 b2 = false;  
 int num2 = 10;  
 if (b2 && (num2++ > 0)) {  
 System.out.println("我现在在东京！");  
 } else {  
 System.out.println("我现在在西京！");  
 }  
 System.out.println("num2=" + num2);  
 /*  
 * */ int x = 1;  
 int y = 1;  
 if (x++ == 2 & y == 1) {  
 x = 7;  
 }  
 System.out.println("x=" + x + "y=" + y);  
 boolean x1 = true;  
 boolean y1 = false;  
 short z = 42;  
 //if(y==ture)  
 if ((z++ == 42) && (y1 = true)) {  
 z++;  
 }  
 if ((x1 = false) || (++z == 45)) {  
 z++;  
 }  
 System.out.println("z=" + z);  
 /*  
 * */ int z1 = 10;  
 if (false || true) {  
 z1++;  
 }  
 System.out.println(z1);  
 /*  
 * */ short i = 21;  
 System.out.println(i << 2);  
 short i1 = -1;  
  
 System.out.println(i >> 2);  
 }  
}
```
### 二、标题
>\#一级
>##二级
>###三级

### 三、字体
```java
//加粗；
**加粗**
//代码高亮；
==高亮==
//删除线；
~~被删除的文字~~
//斜体；
*斜体内容*
```
**加粗**
==高亮==
~~被删除的文字~~
*斜体内容*

### 三、引用
```java
>一级
>>二级
>>>三级
```
>一级
>>二级
>>>三级

### 四、分割线
>分割线1
>\---
>分割线2
>\***

分割线1
---
分割线2
***
### 五、图片插入
```java
//在线图片//本地图片
![图片名]()
```
### 六、列表
```ajva
//无序列表
- 目录一
- 目录二
//有序列表
//1+.+ 名称
```

- 目录一
- 目录二
***
1. fashj
2. 
### 七、表格

### 八、数学公式
```java
四个$$包含起来
//$$
....
//$$
```
$$
\frac{\partial f}{\partial x}=2\sqrt{a}x
$$
### 九、表格
```java
表格
表头：|姓名|年龄|成绩|
结构：|:--|---:|:---:|
内容：|张三|19|33|
如果冒号在左边表示左对齐；如果冒号在右边表示右对齐；如果冒号左右两边都有表示居中对齐；
```
|姓名|年龄|成绩|
|:--|--:|:--:|
|张三|19|33|
### 十、脚注
```java
内容[^脚注内容]
[^脚注内容]：解释内容
```
内容[^脚注内容]

[^脚注内容]:解释内容
### 十一、跳转链接

```java
跳转链接
[解释链接](#链接名)
```
请参考[九、表格](#九、表格)

### 十二、解释_下划线
```java
下划线：
<u>下划线</u>
```
<u>下划线</u>

<iframe src="//player.bilibili.com/player.html?aid=252552938&bvid=BV1XY411H7XU&cid=467491303&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>





















![[car 1.jpg]]
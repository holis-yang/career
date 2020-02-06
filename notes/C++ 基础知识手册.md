## 目录

[toc]

这个文档是我看谭浩强 《C++ 程序设计》记录下不熟悉的知识，暂时当作基础知识手册查询使用。



### C++ 数据类型

![C++数据类型](D:\Desktop\career\notes\figure\C++数据类型.png)

![image-20200206150928720](C:\Users\YGG\AppData\Roaming\Typora\typora-user-images\image-20200206150928720.png)



## 2.4 C++ 种的运算符

![image-20200206151059564](C:\Users\YGG\AppData\Roaming\Typora\typora-user-images\image-20200206151059564.png)

### 2.5.3 表达式种各类数值型数据间的混合运算

在进行运算时，不同类型的数据要先转换成同一类型，然后进行运算，运算结果为转换类型（如double类型）。转换的规则按照图2.7所示。

![image-20200206151609626](C:\Users\YGG\AppData\Roaming\Typora\typora-user-images\image-20200206151609626.png)

### 2.5.5 强制类型转换运算符

![image-20200206151232264](C:\Users\YGG\AppData\Roaming\Typora\typora-user-images\image-20200206151232264.png)



###  3.4.2 在输入流与输出流中使用控制符

PDF 77 页：

C++ 种一般使用流输入输出```cin, cout``` 进行输入输出。同样可以进行一些特殊操作，如输出规定字段宽度，只保留两位小数，数据向左或向右对齐等。 C++ 中输入输出流中使用的控制符如表3.1 所示。

![image-20200206152317908](C:\Users\YGG\AppData\Roaming\Typora\typora-user-images\image-20200206152317908.png)

需要注意的是：如果使用了控制符，在程序单位的开头除了要加```iostream``` 头文件外，还要加`iomanip`头文件。

### 3.4.3 用 `getchar` 和 `putchar` 函数进行字符的输入和输出

`putchar`函数的作用是向终端输出一个字符。例如

```C++
putchar(c);
```

`getchar`函数的作用是从终端输入一个字符。

```c++
c = getchar();
```



### 3.6.3 逻辑运算和逻辑表达式

![image-20200206153236074](C:\Users\YGG\AppData\Roaming\Typora\typora-user-images\image-20200206153236074.png)



##  3.9 多分支选择和 `switch`语句

`switch`语句是多分支选择语句，用来实现多分支选择结构。`if`语句只有两个分支可以选择，但实际问题中常常会用到多分支的选择。如将学生按照成绩等级进行划分；分类统计；

![image-20200206153506981](C:\Users\YGG\AppData\Roaming\Typora\typora-user-images\image-20200206153506981.png)

### 4.4.3 对被调用函数的声明和函数原型

若被调用函数在主调用函数之后，则必须在调用此函数之前对被调用的函数作声明(declare)。

对函数进行声明的语句为：

```c++
// 类型名  函数名（形参类型 形参变量名）；
float add(float x, float y);  // 对add函数作声明
```

其实，在函数声明中中页可以不写形参名，而只写形参的类型，如：

```c++
float add(float, float)
```

这种函数声明称为函数原型`function prototype`.  使用函数声明和函数原型的**作用**是：根据函数声明或者原型在程序编译阶段对调用函数的合法性进行全面检查。在编译阶段对程序的合法性进行检查可以避免编译通过的程序出现执行错误的情况。由于实际程序通常较大，运行过程会消耗大量的资源，在运行阶段进行调试将会浪费大量的资源。在编译阶段对程序的合法性进行检查可以减少由于语法而造成的执行错误。
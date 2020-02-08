## 目录

[toc]

这个文档是我看谭浩强 《C++ 程序设计》记录下不熟悉的知识，暂时当作基础知识手册查询使用。



### C++ 数据类型

![C++数据类型](https://raw.githubusercontent.com/holis-yang/career/master/notes/figure/C%2B%2B数据类型.png))

![image-20200206150928720](https://raw.githubusercontent.com/holis-yang/career/master/notes/figure/数值型和字符型数据的字节数和取值范围.png))



## 2.4 C++ 种的运算符

![image-20200206151059564](C:\Users\YGG\AppData\Roaming\Typora\typora-user-images\image-20200206151059564.png)

### 2.5.3 表达式种各类数值型数据间的混合运算

在进行运算时，不同类型的数据要先转换成同一类型，然后进行运算，运算结果为转换类型（如double类型）。转换的规则按照图2.7所示。

![image-20200206151609626](C:\Users\YGG\AppData\Roaming\Typora\typora-user-images\image-20200206151609626.png)

### 2.5.5 强制类型转换运算符

![image-20200206151232264](https://raw.githubusercontent.com/holis-yang/career/master/notes/figure/强制类型转换.png)



###  3.4.2 在输入流与输出流中使用控制符

PDF 77 页：

C++ 种一般使用流输入输出```cin, cout``` 进行输入输出。同样可以进行一些特殊操作，如输出规定字段宽度，只保留两位小数，数据向左或向右对齐等。 C++ 中输入输出流中使用的控制符如表3.1 所示。

![image-20200206152317908](https://raw.githubusercontent.com/holis-yang/career/master/notes/figure/输入输出流控制符.png)

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

![image-20200206153506981](https://raw.githubusercontent.com/holis-yang/career/master/notes/figure/switch 表达式.png)

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

![image-20200206170858846](https://raw.githubusercontent.com/holis-yang/career/master/notes/figure/函数原型的一般形式.png)

## 4.6 函数的重载

一般情况下一个函数对应一种功能。但是有时我们要实现的是同一个功能，只是有些细节不同。如返回值类型不同，形参类型不同，形参数量不同等。对于这种从声明上能够看出明显区别的函数，即使两个函数同名的情况下，编译器也可以区分出调用的函数。这种情况下，我们可以用同一个函数名表示不同函数。

![image-20200206172232232](C:\Users\YGG\AppData\Roaming\Typora\typora-user-images\image-20200206172232232.png)

## 4.7 函数模板

函数模板用一个通用类型名`T`表示一个数据类型定义一个函数，使得一个模板函数可以完成多个不同类型数据的运算。

```c++
template<typename T>  //模板声明，其中T为类型参数
T max(T a, T b, T c)       //定义一个通用函数，用T作虚拟的类型名
{
	if(b>a) a=b;
   	if(c>a) a=c;
    return a;
}
```

## 4.8 有默认参数的函数

当某一个实参需要多次使用，C++ 提供默认参数功能，可以给形参默认值。如：

```c++
float area(float r=6);
```

## 4.11 局部变量和全局变量

**作用域：**每一个变量都有其有效作用范围，这就是变量的作用域。程序的编译单位是源程序文件。一个**源文件**中的变量分为全局变量和局部变量。

## 4.12 变量的存储类别

### 4.12.1 动态存储方式与静态存储方式

PDF 138 页：

变量还有另一种属性-----**存储期(storage duration，也称生命期)**。存储期是指变量在内存中的存在期间。存储期可以分为**静态存储期(static storage duration)**和**动态存储期(dynamic storage duration)**. 这是由变量的静态存储方式和动态存储方式决定的。

静态存储方式是指再程序运行期间，系统对变量分配固定的存储空间。而动态存储方式则是在程序运行期间，系统对变量动态地分配存储空间。



在 C++ 中变量除了有数据类型的属性之外，还有存储类别(storage class)的属性。存储类别指的是数据在内存中存储的方法。存储方法分为静态存储和动态存储两大类。具体包含 4 中：自动的(auto)、静态的(static)、寄存器的(register)和外部的(extern)。根据变量的存储类别，可以知道变量的作用域和存储期。

### 4.12.2 自动变量

自动变量是系统默认的变量声明类型，系统默认存储在动态存储区。`auto`关键字可以省略。

```c++
int func(int a)                    //定义func 函数 a为形参
{
	auto int b,c = 3;               //定义b和c为整型的自动变量
	int d=4;                        //定义d为整型的自动变量
}
```

###  4.12.3  用 static 声明静态局部变量

有时希望函数中的局部变量的值在函数调用结束后不消失而保留原值，即其占用的存储单元不释放，在下一次该函数调用时，该变量保留上一次函数调用结束时的值。这时就应该指定该局部变量为静态局部变量（static local variable）。

![image-20200206223742842](https://raw.githubusercontent.com/holis-yang/career/master/notes/figure/静态局部变量的说明.png)

### 4.12.4 用 register 声明寄存器变量

将使用频繁的变量存储在CPU的寄存器中，可以提高程序的执行效率。这种变量叫做寄存器变量，用关键字`register`声明。

```
int fac(int n)
{
	register int i,f =1;         //定义i和f是寄存器变量
}
```

如今的优化编译系统能够识别使用频繁的变量，从而自动地将这些变量放到寄存器中，而不需要程序设计者指定。因此，实际上用register声明变量是不必要的。了解即可。

###  4.12.5  用 extern 声明外部变量

1. 在一个文件内声明全局变量

   如果外部变量不再文件的开头定义，其有效作用范围只限于定义处到文件末尾。如果在定义点之前的函数想要引用该全局变量，则应该在引用之前用关键字 `extern`对该变量作外部变量声明，表示该变量是一个将在下面定义的全局变量。这种声明称为**提前引用声明**。

2. 在多个文件的程序中声明外部变量

   如果在两个文件中都要用到同一个外部变量`num`，不能分别在两个文件中各自定义一个外部变量`num`，否则在进行程序的连接时就会出现“重复定义”的错误。正确的做法是：

   在人一个文件中定义外部变量`num`，而在另一文件中用 extern 对 `num`作外部变量声明。即：

   ```
   extern int num;
   ```

   用 extern 扩展全局变量的作用域，虽然能为程序设计带来方便，但应慎重。因为在执行一个问价中的函数时，可能会改变了该全局变量的值，从而会影响到另一文件中的函数执行结果。

   ### 4.12.6 用 static 声明静态外部变量

   有时在程序设计中希望某些外部变量只限于被本文件引用，而不能被其他文件引用。这时可以在定义外部变量时加一个static 声明。

   ```
   
   ```

   ![image-20200207091408173](https://raw.githubusercontent.com/holis-yang/career/master/notes/figure/static 全局变量.png)

##  4.13 变量属性小结

![image-20200207094033161](https://raw.githubusercontent.com/holis-yang/career/master/notes/figure/local global variable.png)



## 4.15 内部函数和外部函数

函数在本质上时全局的，因为一个函数要被另外的函数调用。但是，也可以指定函数智能被本文件调用，而不能被其他文件调用。

内部函数：只能被本文件中其他函数调用。定义时在函数名和函数类型的前面加 static ：

```C++
static 类型标识符   函数名（形参表）
如：
static int fun(int a, int b){}
```

外部函数：系统默认的函数定义类型，一般省略关键字 extern：

```C++
extern int fun(int a, int b){}
```

在需要调用此函数的文件中，用 extern 声明所用的函数是外部函数。

## 4.16 预处理命令

C++ 中的预处理包含3种：宏定义，文件包含，条件编译。

**宏定义：**用`#define`命令将一个指定的标识符来表示一个字符串。

```C++
#define  标识符   字符串
如：
#define PI 3.1415926
```

还可以用`#define`命令定义带参数的宏定义：

```C++
#define 宏名（参数表）  字符串
如：
#define S(a,b)  a*b   //定义宏 S（矩阵面积），a、b为宏参数
```

**文件包含：**一个源文件可以将另外一个源文件的全部内容包含进来。

```C++
#include <iostream>    //到系统目录种寻找iostream文件。
#include "file2.cpp"   //先在用户定义的目录中寻找file2.cpp文件，若没有，则在系统目录中找
```

![image-20200207100522247](https://raw.githubusercontent.com/holis-yang/career/master/notes/figure/文件包含多文件.png)

一般情况下，库函数和C++ 编译系统是存放在同一目录中的。如果要包含的是C++系统提供的头文件，宜用这种标准方式。

有时被包含的文件不一定在系统目录中，这时用“ ”形式，在“ ”中指出文件路径和文件名。若在指定路径找不到这个文件，编译器就会到系统路径寻找。

### 4.16.3 条件编译

一般情况下，在进行编译时对源程序中的每一行都要编译。但是有时希望程序中的某一部分内容只在满足一定条件时才进行编译，也就是指定对程序中的一部分内容进行编译的条件。如果不满足这个条件，就不编译这部分内容。这就是条件编译。

![image-20200207102526207](https://raw.githubusercontent.com/holis-yang/career/master/notes/figure/条件编译.png)

###  5.5.4 字符数组的输入输出

字符数组的输入输出可以有两种方法：

（1） 逐个字符输入输出

（2）将整个字符串一次输入或输出，如：

```C++
char str[20];
cin >> str;   //用字符数组名输入字符串
cout << str;   //用字符数组名输出字符串
```

用`cin`从键盘向计算机输入一个字符串时，从键盘输入的字符串应短于已定义的字符数组的长度，否则会出现问题。当输入字符串超过数组的定义长度时，并不会报错，而是将多余的3个字符顺序地存放到数组str后面的3个字节中，有可能会破坏其他数据。

`getline`  :  C++ 提供了cin 流中的getline 函数，用于读入一行字符。

### 5.5.5 字符串处理函数

字符串处理函数放在函数库中。如果使用这些字符串函数，应该用#include 命令把`string.h` 或 `string` 头文件包含到本文件中。

1. 字符串连接函数 `strcat`

   其函数原型为： `strcat(char[], const char[]);`  其中 `strcat` 是string catenate 的缩写。两个形参都为字符数组。数组名代表数组地址，是常量，不能被赋值，也不能作左值[^1]。使用常量可以避免函数执行过程中数组内容被更改。

   ```C++
   char str1[30] = "People's Republic of";
   char str2[] = "China";
   cout << strcat(str1, str2);   //调用strcat函数
   // 输出：
   //    People's Republic of China
   ```

   [^1]: {在C语言中，对象(object)指的是在内存中的一个位置，其内容可以用来表示某个值。

   左值，指的就是内存中有具体位置的对象。

   对象能出现在赋值表达式的左边进行赋值操作，所以它是一个左值。

   有些表达式，它只产生一个值，却没有指示一个对象，这种表达式就是右值。

   左值可以出现在赋值表达式的任意一边，而右值就只能出现在右边。

   左值一定可以被解析出对应对象的地址，除非此对象是位字段，或者被类型限定符定义为const了.

   

2. 字符串赋值函数 `strcpy`

   其函数原型为：`strcpy(char[], const char[]);`

   它的作用是将第二个字符数组中的字符串赋值到第一个字符数组中去，将第一个字符数组中相应字符覆盖。例如

   ```C++
   char str1[10],str2[]="China";
   strcpy(str1, str2);  // 第一个参数是字符数组名，第二个参数是字符数组名
   strcpy(str1, str2, 2); // 将str2中前面两个字符复制到str1中去，然后再加一个'\0'
   strcpy(str1, "China");  //第一个参数是字符数组名，第二个参数是字符串常量
   ```

3. 字符串比较函数`strcmp`

   其函数原型为：`strcmp(const char[], const char[])`  返回结果0或1

   ```C++
   if(strcmp(str1, str2)>0) cout << "yes";
   ```

4. 字符串长度函数`strlen`

   函数原型为`strlen(const char[]);`

   ```c++
   char str[10] = "China";
   cout << strlen(str);
   结果：5
   ```

   ## 5.6 C++ 处理字符串的方法——字符串类型与字符串变量

   利用数组进行字符串操作时，需要对字符串长度进行准确估计，不然就会造成数据溢出或者空间浪费。

   实际上，string 并不是 C++ 语言本身的基本类型（而char、int、float、double等是C++ 本身提供的基本类型），它是在C++ 标准库中声明的一个字符串类，用这种类可以定义对象。每个字符串变量都是string类的一个对象。

   ### 5.6.1 字符串变量的定义和引用

   ```C++
   #include <string>  //注意头文件不是string.h
   string string1;    //定义string1为字符串变量
   string string2=“China”；  //定义string2同时对其初始化
   string1 = “Canada”；  //赋值
   cin >> string1;   //从键盘输入一个字符串给字符串变量string1
   cout << string2;  //输出字符串string2 
   ```

   ### 5.6.2 字符串变量的运算

   复制：`string1 = string2`

   连接：

   ```C++
   string string1 ="C++";     //定义string1并赋初值
   string string2 = "Language";  //定义 string2 并赋初值
   string1 = string1 + string2;  //连接 string1 和 string2
   连接后 string1 为"C++ Language"
   ```

   ==、>、< 等关系运算符比较的是字符串的长度，而不是值。

   ###  5.6.3 字符串数组

   不仅可以用string 定义字符串变量，也可以用string 定义字符串数组

   ```C++
   string name[5];
   ```

   
























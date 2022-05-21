---
description: https://shimo.im/docs/XKq4MJ8jbKfogNkN/ 「C」，可复制链接后用石墨文档 App 或小程序打开
---

# C

2022-05-21

> 选摘了一小部分内容记在笔记中，且掺杂了自己的一些理解。 学习源码：
>
> [https://github.com/Mleon7/notes.git](https://github.com/Mleon7/notes.git)
>
> 主要教程：
>
> &#x20;[C语言教程（全网最具有比喻形象的） by Micro\_Frank](https://www.bilibili.com/video/BV1qE411d7Zx?p=51\&share\_source=copy\_web)&#x20;
>
> 其他参考：
>
> &#x20;[C语言 菜鸟教程](https://www.runoob.com/cprogramming/c-tutorial.html) [python 菜鸟教程](https://www.runoob.com/python/python-tutorial.html)

### 1-0 第一个程序超详细讲解

> 环境：ubuntu server 22.04 C语言：

```
#include <stdio.h>
int main(void)
{
  printf("hello world");
  return 0;
}
```

编译运行：

```
gcc hello.c -o hello && ./hello
```

对比（python）：

```
print("hello world");
```

运行：

```
python3 hello.py
```

### 1-1 scanf不能在vs2019里用？瞎扯淡！

可以使用scanf\_s

### 2-1 C语言核心心法

面向过程语言。

以main函数为入串口，从上到下依次执行。

### 2-2 变量是玩会的不是学会的

> 2022-05-14 以植物大战僵尸为例：

数据类型：整型，浮点型……

常用：int，double

![](<.gitbook/assets/image (3) (1).png>)

### 2-3 变量使用方法以及对应输出方式

C语言（静态语言）：

```
int number = 99;
printf("number = %d", number);
```

对比（python）： python（动态语言）

```
a = 99;
print("a = ", a);
a = "hello";
print(a);
```

### 3-0 标识符

> C 标识符是用来标识变量、函数，或任何其他用户自定义项目的名称。一个标识符以字母 A-Z 或 a-z 或下划线 \_ 开始，后跟零个或多个字母、下划线和数字（0-9）。 C 标识符内不允许出现标点字符，比如 @、$ 和 %。C 是区分大小写的编程语言。因此，在 C 中，Manpower 和 manpower 是两个不同的标识符。

### 3-1 变量命名规范

1. 下划线命名法
2. 驼峰命名法
3. 匈牙利命名法

### 3-1-2 常量命名

宏定义：

```
#define PI 3.14
```

常量命名：

```
const int IPHONE = 9999;
```

包括一些静态的数据，全部都要大写。 对比（python）：

> Python并未提供如C/C++/Java一样的const修饰符，换言之，python中没有常量，python程序一般通过约定俗成的变量名全大写的形式表示这是一个常量。然而这种方式并没有真正实现常量，其对应的值仍然可以被改变。后来，python提供了新的方法实现常量：即通过自定义类实现常量。这要求符合“命名全部为大写”和“值一旦被绑定便不可再修改”这两个条件。

### 3-2 转义字符

\n 换行

### 4-0 运算符\_算数运算符

算术运算符：+ - \* / %（取余）++ --

优先级问题（比如先乘后加）

### 5-0 if

注意：=是赋值，在判断等于时要用==

### 5-1 ifelse和逻辑运算符

场景：

你的用户名或者密码不正确

### 5-2 ifelse不带大括号的坑爹问题-可读性

### 5-3 程序的严谨性

用户的不合法输入，比如手机号（+86，十位）、邮箱等都有一定的格式。

EX：please input your age:

情况一：mleon，随便输了个名字。

情况二：-99，输入了负数。

情况三：10000，目前没有人能活这么久。

### 5-4 解决判断输入的程序严谨性

```
int main(void){
  
  u_int32_t age;
  
  printf("Please input your age: \n");
  int age_input_result = scanf("%3u", &age);
  if (age_input_result != 1) {
    printf("输入的数字不合法！请必须是小于三位的正整数！ \n");
  } else {
    printf("age = %u\n", age);
  }
  
  return 0;
}
```

### 5-5 else可能会产生的问题

### 5-6 if嵌套和使用注意事项

### 5-6-2 if...else if

### 5-7 条件运算符和if结束语

### 6-0 switch语句的用法和用途详解

类比：电梯。

注意：

1. 每个case后面都要加上break（虽然语法上是可选的）
2. 别忘了加上default

### 7-0 char类型补充\_ASCII码

C语言中，单个字符用单引号。

```
char character = 'A';
```

对比：在部分其他语言中，可以用单引号引用字符串。（如python） ASCII码：

char类型本质是int类型。

验证：

```
printf("character = %d\n", character);
```

### 8-0 循环超详细解析之while

描述：多次执行同样的任务。

类比：在操场跑1200米。

应用场景：搜索文件。如搜索chrome，一直执行搜索条件，直到搜索结束。（while）

（可以这么做，但要查找的快的话，用索引。）

三种循环：

1. while
2. for（最常用）
3. do...while 循环的三个要求：
4. 判断是否满足
5. 可能有自增变量，达到界限退出循环 （否则是死循环；弹幕补充：单片机中常有；银行；注意死循环也是有用的，与业务有关）
6. 可能有初始化变量

### 9-0 continue

![](<.gitbook/assets/image (2) (1).png>)

### 9-1 break

![](<.gitbook/assets/image (1) (1).png>)

### 9-2 continue和break总结

来自弹幕：说白了就是一个跳过，一个打断。

continue只能在循环中使用。

break只能在循环或开关中使用。（switch就是开关）

### 9-3 do...while

切记：

```
do
{
} while (); // ★注意：结尾这里有分号；但while语句不用
```

> Frank：在工作时很少会用到。

### 10-0 for

> 补充：定义表量不赋值，这叫什么？（声明变量）

![](<.gitbook/assets/image (3).png>)

### 10-1 ★for语句的执行流程

### 10-2 ★使用VS2019进行调试

> 输出也是个“调试工具”。 linux中用gdb调试。

### 10-3 for嵌套

### 10-4 for和算法，激励说明

### 11-0 函数

函数的作用：

比如需要求两个数之和，求语文和数学成绩之和，求两餐花费的钱数之和，等等。可以抽象成一个函数来解决该问题。即复用性（通用）。

最重要的函数：main函数，是程序的入口点。

### 11-1 函数\_2

调用函数时的参数的顺序、类型等都要与声明的一一对应。

类比（来自弹幕）：

一个萝卜一个坑，红萝卜坑不能插白萝卜。

形参，实参。

类比（来自弹幕）：

1. 形参：空盒子，实参：苹果，香蕉，桃子。
2. 形参就像数学里面的x，y；如果有对应值了比如写x=1，y=2，1和2就叫实参。

### 11-2 函数作用域

类比：三国，国家区域，归谁管。

局部变量：在函数中定义，不能在函数中调用其他函数定义的变量。

全局变量：在函数外定义，容易受到函数污染，慎用。

### 12-0 数组的含义和用途

生活举例：

这张图中就有三个数组。

![](<.gitbook/assets/image (12).png>)

数组的应用：（7:28处）

[12-0数组的含义和用途](https://www.bilibili.com/video/BV1qE411d7Zx?p=35\&share\_source=copy\_web)

### 12-1 数组的使用

数组下标

类比：点餐时领的号数；医院挂号。

```
int plants[5] = {125, 100, 50};
```

C语言中，数组未赋值的内容默认为0，超过数组大小的会给垃圾值（内存泄漏？）&#x20;

![](<.gitbook/assets/image (10).png>)

```
// 输出验证
// 注意：数组下标从0开始
printf("plants[3] = %d\n", plants[3]);
printf("plants[5] = %d\n", plants[5]);
```

迁移： 变量，先声明后赋值；

```
int age;
age = 100; 
```

数组，先声明后赋值；

```
int plants[5];
plants[3] = 99;
```

对比： 数组声明时同时赋值，未赋值的元素默认为0；

数组先声明后赋值，未赋值的元素默认为垃圾值（与编译环境有关，也有可能是0）。

遍历输出数组：

```
for(int i = 0; i < 5; i++)
{
    printf("plants[%d] = %d\n", i, plants[i]);
}
```

对比： python没有内置对数组（array）的支持，不过可以用列表（list）代替。

### 12-2 二维数组的比喻

### 12-3 ★数组-表驱动法-bool类型

功能：

输入：某一年，某一个月份。

输出：该年该月份的天数。

常见解决方法：

![](<.gitbook/assets/image (6).png>)

1. if else
2. switch 更好的解决方法：表驱动法（这里指使用数组）。

### 13 宏定义和枚举

### 14-1 指针

类比：win10里的快捷方式。

### 14-2 现实生活中空指针和野指针

空指针：指向null

野指针类比：

1. 医生疯了，乱找人看病。
2. 5号病人走了，但医生还一直在叫5号看病

### 15-1 指针\_上代码

\*号的位置可以在int后面，也可以在p前面。

这里的数据类型是：int\*， 变量名是：p

```
int *p = &sun_flower;
int* p = &sun_flower;
```

类比1：win10快捷方式。 指针存的是地址----快捷方式存的是某个软件（或者文件、文件夹等）的地址。

注：在这个类比中，如果是“\&p”指的是快捷方式的地址，即桌面。

![](<.gitbook/assets/image (5).png>)

使用指针，\*p----双击快捷方式。

![](<.gitbook/assets/image (11).png>)



类比2：

linux的软链接。

空指针：

指向无意义的地方

```
int* ptr = NULL;
printf("ptr = %p\n", ptr);
```

（空指针具体指向哪里似乎不一定；在vs2019中全是0，在ubuntu22中却是(nil)） 野指针：

程序会随机分配，防止空指针的产生异常；没有意义的指向

```
int* p;
```

![](<.gitbook/assets/image (4).png>)

（野指针，病毒）

补充：

使用64位和32位输出的地址是不一样的：

![](<.gitbook/assets/image (9).png>)

![](<.gitbook/assets/image (1).png>)

### 15-2 指针保存数组地址

（来自弹幕：在C语言中，保存数组是通过保存数组第一个位置的地址，后续的值通过地址的递增来实现）

对比：

![](<.gitbook/assets/image (7).png>)

变量：

```
int number = 99;
int* p_num = number; // 在ubuntu中的gcc不能通过，得改成：int* p_num = &number;
printf("&number: %p\n", &number);
printf("number: %p\n", number); // 在ubuntu中的gcc不能通过 
```

数组：

```
int array[5] = {1, 2, 3, 4, 5};
int* p_arr = array;
printf("&array: %p\n", &array);
printf("array: %p\n", array);
```

### 15-3 指针数组和字符串

### 15-4 多级指针

### 15-5 函数参数使用指针

### 15-6 指针作为函数返回值

### 16 本教程忽略的一些内容

### 17 库函数该怎么用以及命令行参数获取

### 18 关于VS2019的函数\_s安全问题解决

### 19 完结撒花，Frank想说的话

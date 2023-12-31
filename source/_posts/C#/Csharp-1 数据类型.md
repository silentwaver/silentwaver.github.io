---
title: Csharp-1 数据类型
categories:
  - C#
date: 2023-12-27 00:00:00
tags:
---
## 数据类型
### 值类型
包括bool,char以及大量数字类型,bool型默认值为false,char默认为‘\\0'
数字类型包括浮点类double,float,有符号整数类byte(8位),short(16位),int(32位),long(64位),无符号整数类sbyte,ushort,uint,ulong,以及128位精确十进制值decimal.double型默认值为0.0D,float为0.0F,decimal为0.0M,long为0.0L,其余类型为0

### 引用类型
#### Object(对象)
对象是C#通用类型系统(CTS)所有类型的终极基类,是System.Object的别名.
当一个值类型转换为对象类型时，则被称为 **装箱**；另一方面，当一个对象类型转换为值类型时，则被称为 **拆箱**

#### Dynamic(动态)
可以存储任何类型的值,类型检查在运行时发生
对象类型变量的类型检查是在编译时发生的，而动态类型变量的类型检查是在运行时发生的

#### String(字符串)
C# string 字符串的前面可以加 @（称作"逐字字符串"）将转义字符（\\）当作普通字符对待，比如：
```C#
string str = @"C:\Windows";
// 等价于
string str = "C:\\Windows";
```

@ 字符串中可以任意换行，换行符及缩进空格都计算在字符串长度之内。

```C#
string str = @"<script type=""text/javascript"">
    <!--
    -->
</script>";
```

### 指针类型(Pointer types)
用于存储另一类型的内存地址
声明指针类型的语法：
```C#
type* identifier;
//例如：
char* cptr;
int* iptr;
```

## 数据类型转换

### 隐式类型转换
从较小范围的类型转为较大类型范围时无需显式转换,编译器会自动转换.如从byte->int
### 显式类型转换
C#提供了较多的显示转换类型方法

## 可空类型
用 单问号定义 对int,double,bool等无法直接赋值为null的数据类型进行null的赋值
```c#
<data_type> ? <var_name> = null
```

?? 若第一操作数的值为空,则返回第二操作数的值,否则返回第一操作数的值
```C#
double? num1 = null;  
double? num2 = 3.14157;  
double num3;  
num3 = num1 ?? 5.34;      // num1 如果为空值则返回 5.34  
Console.WriteLine("num3 的值： {0}", num3);  // 5.34
num3 = num2 ?? 5.34;  
Console.WriteLine("num3 的值： {0}", num3);  // 3.14157
Console.ReadLine();

```

## 数组(Array)
存储相同类型元素 大小固定 的 顺序集合

## 结构体(Struct)
使用 struct 定义一个结构体.struct默认是public的
### C# 结构的特点

您已经用了一个简单的名为 Books 的结构。在 C# 中的结构与传统的 C 或 C++ 中的结构不同。C# 中的结构有以下特点：

- 结构可带有方法、字段、索引、属性、运算符方法和事件。
- 结构可定义构造函数，但不能定义析构函数。但是，您不能为结构定义无参构造函数。无参构造函数(默认)是自动定义的，且不能被改变。
- 与类不同，结构不能继承其他的结构或类。
- 结构不能作为其他结构或类的基础结构。
- 结构可实现一个或多个接口。
- 结构成员不能指定为 abstract、virtual 或 protected。
- 当您使用 **New** 操作符创建一个结构对象时，会调用适当的构造函数来创建结构。与类不同，结构可以不使用 New 操作符即可被实例化。
- 如果不使用 New 操作符，只有在所有的字段都被初始化之后，字段才被赋值，对象才被使用。


## 枚举(Enum)
枚举是一组命名**整型**常量。枚举类型是使用 **enum** 关键字声明的。
C# 枚举是值类型。换句话说，枚举包含自己的值，且不能继承或传递继承。

C# 枚举成员的类型默认是 int 类型，通过继承可以声明枚举成员为其它类型

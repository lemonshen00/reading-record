# Java入门教程
## Java简介
Java可用于开发各种平台上的应用，如开发桌面应用的Java SE(Java Platform,Standard Edition)，开发Web应用的Java EE(Java Platform,Enterprise Edition)，开发移动应用和嵌入式的Java ME(Java Platform,Micro Edition)。

Java的优点：
简单：摒弃了C++语言中复杂的特性，如操作符重载、多重继承、自动的强制类型转换。另外，Java不使用指针，而是使用引用，且提供了自动的内存回收管理机制，使得程序员无需关心内存管理问题。

面向对象：Java语言提供类、接口和继承等原语，只支持类之间的单继承，但支持接口之间的多继承，并支持类与接口之间的实现机制（关键字为implements）。Java语言全面支持动态绑定，而C++语言只对虚函数使用动态绑定。

分布式：Java语言支持Internet应用的开发，在基本的Java应用编程接口中有一个网络应用编程接口（java net），它提供了用于网络应用编程的类库，包括URL、URLConnection、Socket、ServerSocket等。Java的RMI（远程方法激活）机制也是开发分布式应用的重要手段。

健壮性：强类型机制、异常处理、垃圾回收机制使得Java具备很强的健壮性

安全性：提供了安全机制，以防止恶意代码的攻击。

中立/可移植性：源码被编译成字节码（.class）后，字节码可以在任何系统中执行。

解释型：Java程序在Java平台上被编译为字节码格式，然后可以在实现这个Java平台的任何系统中运行。在运行时，Java平台中的Java解释器对这些字节码进行解释执行，执行过程中需要的类在联接阶段被载入到运行环境中。

高性能：Java的运行速度随着JIT(Just-In-Time）编译器技术的发展越来越接近于C++。

多线程

动态：Java的类中有一个运行时刻的表示，能进行运行时刻的类型检查。

## 基本语法
大小写敏感：这意味着Hello 和 hello是不同的标识符
类名：首字母必须大写，如MyFirstJavaProgram
方法名：首字母必须小写，如myFirstFunName
源文件名：必须与类名相同，否则编译报错
主方法入口：必须是 public static void main(String[] args)












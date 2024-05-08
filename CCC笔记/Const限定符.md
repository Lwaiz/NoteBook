### const作用域

默认const对象 仅在当前文件内有效

如果想在多个文件中共享const对象  必须在变量定义之前添加extern关键字

```C++
extern const int bufSize = 512;
```

### const的引用

常量引用 ：将引用绑定到const对象上，引用及其对应的对象都是常量

```C++
const int ci = 10;
const int &ri = ci;
```

引用的类型必须与其所引用的对象类型一致 但初始化常量引用时允许用任意表达式作为初始值，只要该表达式的结果能够转化为引用的类型即可

```C++
int i = 42;
const int &r1 = i; //允许将const int& 绑定到普通的int对象上
```



### constexpr变量

将变量声明为一个constexpr类型由编译器来验证变量的值是否是一个常量表达式

constexpr变量一定是一个常量 而且必须用常量初始化

```C++
constexpr int mf = 20;
constexpr int limit = mf + 1;  //mf + 1是一个常量表达式
constexpr int sz = size();   //只有当size是一个constexpr函数时 才是一条正确语句
```

- constexpr 与 指针

```C++
const int *p = nullptr;   //p是一个指向整型常量的指针 
constexpr int *q = nullptr;  //q是一个指向整数的常量指针
```




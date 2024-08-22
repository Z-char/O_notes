---
Reference: "[Compound Types](https://cpp-primer.pages.dev/book/023-2.3._compound_types); [Const Qualifier](https://cpp-primer.pages.dev/book/024-2.4._const_qualifier)"
---
# cpp 的基础类型
在 cpp 里，定义一个变量的语句由基础类型和声明算子组成。
`int a = 3;` 这里的 `int` 就是基础类型，`a` 就是声明算子，声明了一个以 `a` 为变量名的变量。
那么为什么我不说是一个名称而是一个 "算子" 呢，这并非我故意想让人读不懂，这是因为除了用基础类型直接定义变量，我们还可以定义复合类型 - 引用和指针。
`int *p = nullptr, q = 3;` 注意到这里的 `p` 是一个指针类型，但是 `q` 是一个 `int` 类型。
所以我们发现，声明算子可以声明引用指针以及基础类型本身，也就是同一个语句里类型未必相同。
对于类型创建而言，还有一个绕不开的点就是 `const`，事实上 `const` 并不总是代表常量，目前我浅薄的理解说明常量是在编译期确定并被扔到符号表里的值，而大部分的 `const` 实现的效果其实是 `readonly` 的效果。
由于我们知道可以把 `const int` 的值赋值给 `int` 类型，所以可以得到当创建新变量时，新变量可以由自己的类型或自己的类型加一个 `const` 赋值过来，也即能从可以变化为自己这个类型的类型初始化。
我举个例子。
`const int * const *`，这个类型是指向指向 `const int` 类型的常指针的指针，具体如何判断类型我们后面再讲，现在需要知道的就是，当初始化这个变量时，我们可以从 `const int * const *` 同类型初始化它，也可以从 `const int * const * const` 即自己的类型后缀一个 `const` 赋值过来，事实上如果自己后缀有 `const` 也可以从删掉一个 `const` 赋值过来。而前面的 `const` 只能加不能减。
我们简单讲一下复合类型的 `const` 是什么意思，注意到基础类型可以有一个 `const`，意味着基础类型不可修改，但是指向它的指针本身也可以是一个 `const` 对象，也就是指向的对象不可以更换，所以这俩 `const` 对于复合类型是独立的，由于引用本身就不能改，可以认为它天生就是 `const` 的(虽然引用本身不是对象)。

> [!NOTE] 引用的类型必须匹配
> 引用的类型大部分时候需要匹配，因为你需要它是其他变量的别名，有一种例外，注意到 `const` 效果是 `readonly`，所以你可以实现 `int q = 5; const int &p = q;`，这是合法的，而且修改 `q` 同时会修改 `p` 的值，这其实符合我们之前说的规则 "可以加不能减"，你可以把这个理解成 `const *` 以及 `const &` 它们是 "认为自己引用的/指向的是 `const`，所以他们只读不能修改"。
>
> 

```cpp
const int * * * p = nullptr;

const int * const * const * q = p; // okay: add some const

const int * * const * r = p; // okay: add some const

const int * * const * r = q; // error: cannot get rid of the const after the first *



const int * * * const a = nullptr;

const int * * * b = a; // okay: the top-level const can be get rid of
```
# 扩展阅读
c++11 中引入了一些新的特性，有些时候我们想定义一些变量，但是不知道变量的类型是什么。
这种情况下，编译器引入了一种新的类型，叫做 `auto`。
`int b = 1; auto a = b;`，这里的 `auto` 会自动变成 `int`，注意到 `auto` 得到的类型会自动去掉顶层 `const`，也就是 `const int b = 1; auto a = b;` 里面的 `auto` 仍然是 `int`。
`auto` 的取值是根据右边的东西，自动取类型去掉顶层 `const` 的类型，如果手动加上 `const auto` 则会有顶层 `const`，如果需要是个指针，可以手动加上 `*` 或者不管(表达式推断的就是指针)，如果需要是个引用，可以手动加上 `&`，`auto` 并不会自动推导为引用。
另外的，我们也可以用 `decltype(a) b` 来让 `b` 是 `a` 相同的类型，需要注意的是，这里不会抛弃顶层常定义，而且，形如 `(expr), a = b` 的表达式都会返回一个引用类型，需要特别注意。

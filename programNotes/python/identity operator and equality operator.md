The python **identity operator** `is` is quite frequently used to compare objects in python and often in places where the **equality operator** `==` should be used. In fact, you should almost always avoid using is when comparing values.

* Python identity operators (is, is not) are used to compare objects based on their identity. In the **CPython interpreter**, which you’re most likely to be using, the identity of an object refers to its **location in memory**. Other interpreters may have different ways of defining identity.

* Python equality operators (\=\=, !\=) are used to compare objects based on their **values**. It invokes the \_\_eq\_\_() class method of the left object which defines the rules for checking equality. But generally, these rules are defined such that if two objects have the same value irrespective of their memory locations, the equality operator == results in True.

is 比较的是两个实例对象是不是完全相同，它们是不是同一个对象，占用的内存地址是否相同。
`a is b` 等于 `id(a)==id(b)`
== 比较的是两个对象的内容是否相等，内存地址可以不一样，内容一样就可以了，即调用前一个变量的`__eq__`方法。
`a\=\=b` 等于 `a.__eq__(b)`
通常，我们关注的是值，而不是内存地址，因此 Python 代码中 == 出现的频率比 is 高。


## 何时使用is
The identity operators are actually quite useful when asserting whether an object is a **specified singleton** (objects with only one reference in memory) in python like `None`, `True`, or `False` because they check for identity and not run any other **method based checks**。
is 与 == 相比有一个比较大的优势，就是计算速度快，因为它不能重载，不用进行特殊的函数调用，少了函数调用的开销。
而 `a == b` 则是等同于`a.__eq__(b)`。继承自 object 的 `__eq__` 方法比较两个对象的id，结果与 is 一样。但是多数Python的对象会覆盖object的` __eq__`方法。

在变量和单例值之间比较时，应该使用 is。目前，最常使用 is 的地方是判断对象是不是 None。下面是推荐的写法：
``` python
>>> a is None
>>> a is True
```


## 整数对象的特殊情况
This happens because the CPython interpreter **interns** smaller numbers at fixed memory locations. Depending on your interpreter the range of such numbers might vary but it’s generally -5 to +256.
Python会对比较小的整数对象进行缓存，下次用的时候直接从缓存中获取，所以is 和 == 的结果可能相同，比如：
``` python
>>> a = 1
>>> b = 1
>>> a is b
True
>>> a == b
True
```
然而，Python仅仅对比较小的整数对象进行缓存（范围为[-5, 256]）缓存起来，而并非是所有整数对象。比如：
``` python
>>> a = 257
>>> b = 257
>>> a is b
False
```
需要注意的是，这仅仅是在**命令行**中执行，而在Pycharm或者保存为文件执行，结果是不一样的，这是因为解释器做了一部分优化。

## Conclusion – Things to remember
Knowing when to use and not use the identity operator can save you a lot of time on future hair pulling. The following are the key pointers to remember –

* Objects with the same value are often stored at different memory locations. Only a handful number of values are primed by the interpreter.
* Always use the operators == or != when comparing values.
* Use the identity operators to compare objects based on their identity. Example, when comparing with singleton objects like None, True, False, etc.

links:
[1]https://datascienceparichay.com/article/python-difference-between-is-and-equality-operators/
[2]https://www.cnblogs.com/kiko0o0/p/8135184.html
# 异常丢失
12.8.3 异常丢失

在finally中使用 return 或者 throws 将会把 try-catch-finally 结构中的catch部分捕捉到的异常丢失；

# String

+ 编译器默认优化，会将“+”拼接转换成 `StringBuilder.append()` ，简单操作和直接使用StringBuilder一样，但是如果是for循环之类的复杂操作，最好还是自己使用StringBuilder，避免循环 new 对象

 ## Formatter
 
格式化的抽象公式如下：

```
%[argument_index$][flags][width]conversion
```

+ String.format() 静态方法与 Formatter.format() 接受一样的参数，但是返回一个 String 对象，用于格式化文本很方便

## Pattern
java正则表达式中的字符支持并交叉操作

```
[abc]
a, b, or c (simple class)
[^abc]
Any character except a, b, or c (negation)
[a-zA-Z]
a through z or A through Z, inclusive (range)
[a-d[m-p]]
a through d, or m through p: [a-dm-p] (union)
[a-z&&[def]]
d, e, or f (intersection)
[a-z&&[^bc]]
a through z, except for b and c: [ad-z] (subtraction)
[a-z&&[^m-p]]
a through z, and not m through p: [a-lq-z](subtraction)
```

# 反射

## 14.8 空对象
null 对象用来方便地测试，实际的类implements一个借口Null，该接口定义一个指明该对象为null的方法；

反射可以突破访问修饰符，改变类的private、protected属性。

# 第15章 范型

tuple 可以存储任意长度的不同类型的对象。可以在需要返回多个值的时候使用一个对象封装，也可以使用 Tuple<A, B, C, D,...> 这种形式来封装。

Java范型是使用类型擦除来实现的，因此，在运行时，List<Integer> 和 List<String> 在运行时都是一样的原生类型 List。

设定了边界的范型参数比如（List<T extends Person>）将在编译时擦除到他的边界。

## 15.8 擦除的补偿
Neal Gafter 在他的博客中指出，在重写Java类库（Java SE 5）时，他十分懒散，而我们不应该像他那样。这里指的是在类库中使用了大量的范型类型转换，导致标准类库编译的时候会有不少的 unchecked warning，但即使标准库这样写也不代表这样做是可取的。

## 15.10 通配符 
`List<Fruit> list = new ArrayList<Apple>();` 是不对的，因为List<Apple>不是List<Fruit>，这里在表达的是容器的类型而不是容器里持有的类型。但是这样写是对的，`List<? extends Fruit> list = new ArrayList<Apple>();`




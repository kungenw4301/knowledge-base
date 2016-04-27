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




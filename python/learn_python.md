# 廖雪峰Python教程的学习笔记
<http://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000>

## Python简介
相比于C，Python的能用更少的代码完成任务。  
Python的两个缺点：  
1、运行速度慢  
2、代码不能加密

## 安装Python
<http://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000/0014316090478912dab2a3a9e8f4ed49d28854b292f85bb000>

### Python解释器
Python代码的以`.py`为扩展名的文本文件,要运行代码，就需要Python解释器去执行`.py`文件。
<http://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000/00143161198846783e33de56d4041058c3dfc7e44ee1203000>

## 第一个Python程序
    C:\Users\KKOANG>python    //打开python shell
`exit()`退出Python的交互式环境  
执行`python 对应文件名.py`运行一个`.py`文件

直接运行python(.py)文件,在Mac和Linux上是可以的，方法是在`.py`文件的第一行加上一个特殊的注释：

    #!/usr/bin/env python3
    print('hello, world')

这是脚本语言共同遵守的规则：当第一行为`#!/path/to/script/interpreter`时，指定了用来执行本脚本的解释器。

    注意：
    1、必须是文件的第一行
    2、必须以#!开头，你丢了一个惊叹号
    3、/path/to/script/interpreter是脚本解释器的全路径名。

    例如：
    #!/bin/sh           shell脚本
    #!/usr/bin/perl     perl脚本
    #!/usr/bin/python   python脚本
    #!/usr/bin/python3  python3脚本
    #!/usr/bin/python2  python2脚本

    而有时不太清楚脚本解释器的具体全路径名；或者开发环境与运行环境的安装路径不同。为了保证兼容性，也可以写作：
    #!/usr/bin/env python3
    这样运行时会自动搜索脚本解释器的绝对路径。

### 输入和输出
    print("hello","逗号,连接字符会输出空格")
    print(2+3)#也可以打印整数,或计算结果
    print("字符串跟数字连接",2,"as"+"d")#两字符串不加空格连接用加号+

    name=input('please enter your name: ')    #input()可以加入提示信息
    print('hello,',name)    #input输入数字得到也是字符串，可以用int()进行类型的转换
python 连接字符串和数字

    a = 222 ; b = '333'
    c = a + b    #这样会报错
> 如果你要数字和字符串连接的话(不用`,`连接)，可以把数字通过`str`的方法转换成字符串的形式，然后再做连接的操作。
比如:

    c = str(a) + b
    c = str(a) + b
    print(c)
> 输入是**Input**，输出是**Output**，因此，我们把输入输出统称为**Input/Output**，或者简写为**IO**。
> `input()`和`print()`是在命令行下面最基本的输入和输出，但是，用户也可以通过其他更高级的图形界面完成输入和输出，比如，在网页上的一个文本框输入自己的名字，点击“确定”后在网页上看到输出信息。

## Python基础
> `#`开头的语句是注释，当语句以冒号:结尾时，缩进的语句视为代码块。
> 缩进应该使用4个空格的缩进。Python程序的大小写敏感。
> 文本编辑器中，需要设置把Tab自动转换为4个空格，确保不混用Tab和空格。

### 数据类型和变量
**整数**:`1`,`10`,`-8000`,`0`,十六进制用`0x`前缀和`0-9`，`a-f`表示，例如：`0xff00`，`0xa5b4c3d2`  
**浮点数**:`1.23`,`3.14`,`-9.01`,1.23x10的9次幂就是`1.23e9`，或者`12.3e8`，0.012可以写成1.2e-2  
**字符串**:`"I'm OK"`包含的字符是`I`，`'`，`m`，`空格`，`O`，`K`这6个字符。  
转义字符`\`可以转义很多字符，比如`\n`表示换行，`\t`表示制表符，字符`\`本身也可以用`\\`表示，Python还允许用`r''`表示`''`内部的字符串默认不转义
如果字符串内部有很多换行，用`\n`写在一行里不好阅读，为了简化，Python允许用`'''...'''`的格式表示多行内容  
**布尔值**:布尔值和布尔代数的表示完全一致，一个布尔值只有`True`、`False`两种值  
布尔值可以用`and`、`or`和`not`运算  
`and`运算是与运算，只有所有都为`True`，`and`运算结果才是`True`  
`or`运算是或运算，只要其中有一个为`True`，`or`运算结果就是`True`  
`not`运算是非运算，它是一个单目运算符，把`True`变成`False`，`False`变成`True`  
**空值**:空值是Python里一个特殊的值，用`None`表示。`None`不能理解为`0`，因为`0`是有意义的，而`None`是一个特殊的空值。  
**变量**:变量在程序中就是用一个变量名表示了，变量名必须是`大小写英文`、`数字`和`_`的组合，可以是中文（支撑UTF-8），但`不能用数字开头`。变量的赋值其实就是`创建数据`跟`改变指向`。  
**常量**:所谓常量就是不能变的变量，比如常用的数学常数π就是一个常量。在Python中，通常用全部大写的变量名表示常量：`PI = 3.14159265359`,但事实上PI仍然是一个变量。  
整数的除法为什么也是精确的。在Python中，有两种除法，一种除法是`/`：`/`除法计算结果是浮点数，即使是两个整数恰好整除，结果也是浮点数。  
还有一种除法是`//`，称为地板除，两个整数的除法仍然是整数,`10//3=3`。因为`//`除法`只取结果的整数部分`，所以Python还提供一个余数运算，可以得到两个整数相除的余数：`10%3=1`  
Python的浮点数也没有大小限制，但是超出一定范围就直接表示为`inf`（无限大）。

### 字符串和编码
因为计算机只能处理数字，如果要处理文本，就必须先把文本转换为数字才能处理,  
8个比特位（bit）作为一个字节（byte）,一个字符(char)等于若干字节（不固定）。  
字符`'0'`用`ASCII`编码是十进制的`48`，二进制的`00110000`，注意字符`'0'`和整数`0`是不同的。  
汉字中已经超出了`ASCII`编码的范围，用`Unicode`编码是十进制的`20013`，二进制的`01001110 00101101`。  
如果要传输的文本包含大量英文字符，用`UTF-8`编码就能节省空间  

|字符|ASCII|Unicode|UTF-8|
|:-----:|:-----:|:-----:|:-----|
|A|01000001|00000000 01000001|01000001|
|中|x|01001110 00101101|11100100 10111000 10101101|

**字符串**
最新的Python 3版本中，字符串是以`Unicode编码`，也就是说，Python的字符串支持多语言，比如中文。
单个字符的编码，Python提供了`ord()`函数获取字符的整数表示，`chr()`函数把编码转换为对应的字符。

    ord('A') #65
    ord('中') #20013
    chr(66) #'B'
    chr(25991) #'文"
如果知道字符的整数编码，还可以用十六进制这么写str：  
`'\u4e2d\u6587' #两种写法完全是等价的`  
`'中文' #两种写法完全是等价的`  
如果要在网络上传输，或者保存到磁盘上，就需要把`str`变为以字节为单位的`bytes`。  
Python对`bytes`类型的数据用带`b前缀`的单引号或双引号表示：  
`x = b'ABC'`  

> `encode`翻译是`加密，编码`，`decode`翻译是`解（码）`

要注意区分`'ABC'`和`b'ABC'`，前者是str，后者虽然内容显示得和前者一样，但bytes的每个字符都只占用一个字节。  
以Unicode表示的str通过`encode()`方法可以编码为指定的bytes

    >>> 'ABC'.encode('ascii')
    b'ABC'
    >>> '中文'.encode('utf-8')
    b'\xe4\xb8\xad\xe6\x96\x87'
    >>> '中文'.encode('ascii')
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    UnicodeEncodeError: 'ascii' codec can't encode characters in position 0-1: ordinal not in range(128)
纯英文的`str`可以用`ASCII`编码为`bytes`，内容是一样的，含有中文的`str`可以用`UTF-8`编码为`bytes`。含有中文的`str`无法用`ASCII`编码，因为中文编码的范围超过了`ASCII`编码的范围，Python会报错。  
在`bytes`中，无法显示为`ASCII`字符的字节，用`\x##`显示。  
把`bytes`变为`str`，就需要用`decode()`方法：

    >>> b'ABC'.decode('ascii')
    'ABC'
    >>> b'\xe4\xb8\xad\xe6\x96\x87'.decode('utf-8')
    '中文'
计算`str`包含多少个字符，可以用`len()`函数：

    >>> len('ABC')
    3
    >>> len('中文')
    2
如果换成`bytes`，`len()`函数就计算字节数：

    >>> len(b'ABC')
    3
    >>> len(b'\xe4\xb8\xad\xe6\x96\x87')
    6
    >>> len('中文'.encode('utf-8'))
    6
可见，1个中文字符经过UTF-8编码后通常会占用3个字节，而1个英文字符只占用1个字节。  
在操作字符串时，我们经常遇到`str`和`bytes`的互相转换。为了避免乱码问题，应当始终坚持使用UTF-8编码对`str`和`bytes`进行转换。  
由于Python源代码也是一个文本文件，所以，当你的源代码中包含中文的时候，在保存源代码时，就需要务必指定保存为UTF-8编码。当Python解释器读取源代码时，为了让它按UTF-8编码读取，我们通常在文件开头写上这两行：

    #!/usr/bin/env python3
    # -*- coding: utf-8 -*-
第一行注释是为了告诉Linux/OS X系统，这是一个Python可执行程序，Windows系统会忽略这个注释；  
第二行注释是为了告诉Python解释器，按照UTF-8编码读取源代码，否则，你在源代码中写的中文输出可能会有乱码。  
申明了UTF-8编码并不意味着你的`.py`python文件就是UTF-8编码的，必须并且要确保文本编辑器正在使用UTF-8 without BOM编码：

**格式化**  
在Python中，采用的格式化方式和C语言是一致的，用%实现，举例如下：

    >>> 'Hello, %s' % 'world'
    'Hello, world'
    >>> 'Hi, %s, you have $%d.' % ('Michael', 1000000)
    'Hi, Michael, you have $1000000.'
`%`运算符就是用来格式化字符串的。在字符串内部，`%s`表示用字符串替换，`%d`表示用整数替换，有几个`%?`占位符，后面就跟几个变量或者值，顺序要对应好。如果只有一个`%?`，括号可以省略。  
常见的占位符有：

|%d|整数|
|:--:|:--:|
|%f|浮点数|
|%s|字符串|
|%x|十六进制整数|

其中，格式化整数和浮点数还可以指定`是否补0`和`整数与小数的位数`(目测前面空出来`%x`的x-1数量的空格）：

    >>> '%2d-%02d' % (3, 1)    #前面空出1个空格，多出1个0
    ' 3-01'
    >>> '%.2f' % 3.1415926    #显示小数后2位
    '3.14'
    >>> '%3d-%03d' % (3, 1)    #前面空出2个空格，多出2个0
如果你不太确定应该用什么，`%s`永远起作用，它会把任何数据类型转换为字符串：

    >>> 'Age: %s. Gender: %s' % (25, True)
    'Age: 25. Gender: True'
有些时候，字符串里面的`%`是一个普通字符怎么办？这个时候就需要转义，用`%%`来表示一个`%`：

    >>> 'growth rate: %d %%' % 7
    'growth rate: 7 %'

```python
#小明的成绩从去年的72分提升到了今年的85分，请计算小明成绩提升的百分点
s1 = 72
s2 = 85
r = (s2-s1)/s1*100 #多出的部分除去增长前。
r = (s2/s1-1)*100 #自己琢磨的。两个结果都一样。
print('小明成绩提升的百分点 %f %%' % r) #只保留小数点后1位，进行了四舍五入。
```

### 使用list和tuple
**list**  
Python内置的一种数据类型是列表：list。list是一种有序的集合，可以随时添加和删除其中的元素。  
比如，列出班里所有同学的名字，就可以用一个list表示：

    >>> classmates = ['Michael', 'Bob', 'Tracy']
    >>> classmates
    ['Michael', 'Bob', 'Tracy']
变量`classmates`就是一个list。用`len()`函数可以获得list元素的个数：

    >>> len(classmates)
    3
用索引来访问list中每一个位置的元素，记得索引是从`0`开始的：

    >>> classmates[0]
    'Michael'
    >>> classmates[1]
    'Bob'
    >>> classmates[2]
    'Tracy'
    >>> classmates[3]
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    IndexError: list index out of range
当索引超出了范围时，Python会报一个IndexError错误，所以，要确保索引不要越界，记得最后一个元素的索引是`len(classmates) - 1`。  
如果要取最后一个元素，除了计算索引位置外，还可以用`-1`做索引，直接获取最后一个元素：

    >>> classmates[-1]
    'Tracy'
以此类推，可以获取倒数第2个、倒数第3个：

    >>> classmates[-2]
    'Bob'
    >>> classmates[-3]
    'Michael'
    >>> classmates[-4]
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    IndexError: list index out of range
当然，倒数第4个就越界了。

list是一个可变的有序表，所以，可以往list中追加元素到末尾：

    >>> classmates.append('Adam')
    >>> classmates
    ['Michael', 'Bob', 'Tracy', 'Adam']
也可以把元素插入到指定的位置，比如索引号为`1`的位置：

    >>> classmates.insert(1, 'Jack')
    >>> classmates
    ['Michael', 'Jack', 'Bob', 'Tracy', 'Adam']
要删除list末尾的元素，用`pop()`方法：

    >>> classmates.pop()
    'Adam'
    >>> classmates
    ['Michael', 'Jack', 'Bob', 'Tracy']
要删除指定位置的元素，用`pop(i)`方法，其中`i`是索引位置：

    >>> classmates.pop(1)
    'Jack'
    >>> classmates
    ['Michael', 'Bob', 'Tracy']
要把某个元素替换成别的元素，可以直接赋值给对应的索引位置：

    >>> classmates[1] = 'Sarah'
    >>> classmates
    ['Michael', 'Sarah', 'Tracy']
list里面的元素的数据类型也可以不同，比如：

    >>> L = ['Apple', 123, True]
list元素也可以是另一个list，比如：

    >>> s = ['python', 'java', ['asp', 'php'], 'scheme']
    >>> len(s)
    4
要注意`s`只有4个元素，其中`s[2]`又是一个list，如果拆开写就更容易理解了：

    >>> p = ['asp', 'php']
    >>> s = ['python', 'java', p, 'scheme']
要拿到`'php'`可以写`p[1]`或者`s[2][1]`，因此`s`可以看成是一个二维数组，类似的还有三维、四维……数组，不过很少用到。

如果一个list中一个元素也没有，就是一个空的list，它的长度为0：

    >>> L = []
    >>> len(L)
    0

**tuple**  
另一种有序列表叫元组：tuple。tuple和list非常类似，但是tuple一旦初始化就不能修改，比如同样是列出同学的名字：

    >>> classmates = ('Michael', 'Bob', 'Tracy')
现在，classmates这个tuple不能变了，它也没有append()，insert()这样的方法。其他获取元素的方法和list是一样的，你可以正常地使用`classmates[0]`，`classmates[-1]`，但不能赋值成另外的元素。

不可变的tuple有什么意义？因为tuple不可变，所以代码更安全。如果可能，能用tuple代替list就尽量用tuple。

tuple的陷阱：当你定义一个tuple时，在定义的时候，tuple的元素就必须被确定下来，比如：

    >>> t = (1, 2)
    >>> t
    (1, 2)
如果要定义一个空的tuple，可以写成`()`：

    >>> t = ()
    >>> t
    ()
但是，要定义一个只有1个元素的tuple，如果你这么定义：

    >>> t = (1)
    >>> t
    1
定义的不是tuple，是`1`这个数！这是因为括号`()`既可以表示tuple，又可以表示数学公式中的小括号，这就产生了歧义，因此，Python规定，这种情况下，按小括号进行计算，计算结果自然是`1`。

所以，只有1个元素的tuple定义时必须加一个逗号`,`，来消除歧义：

    >>> t = (1,)
    >>> t
    (1,)
Python在显示只有1个元素的tuple时，也会加一个逗号`,`，以免你误解成数学计算意义上的括号。

最后来看一个“可变的”tuple：

    >>> t = ('a', 'b', ['A', 'B'])
    >>> t[2][0] = 'X'
    >>> t[2][1] = 'Y'
    >>> t
    ('a', 'b', ['X', 'Y'])
这个tuple定义的时候有3个元素，分别是`'a'`，`'b'`和一个list。不是说tuple一旦定义后就不可变了吗？怎么后来又变了？  
表面上看，tuple的元素确实变了，但其实变的不是tuple的元素，而是list的元素。tuple一开始指向的list并没有改成别的list，所以，tuple所谓的“不变”是说，tuple的每个元素，指向永远不变。即指向'a'，就不能改成指向'b'，指向一个list，就不能改成指向其他对象，但指向的这个list本身是可变的！

理解了“指向不变”后，要创建一个内容也不变的tuple怎么做？那就必须保证tuple的每一个元素本身也不能变。

> `t`指向的三个元素`'a'`,`'b'`,`一个list`。`t`中的list底下有2个数据，`t`中只有list数据是可变的，没有改变指向别的list或别的对象。

    >>> s=[2,3]
    >>> t=(1,s)
    >>> t
    (1, [2, 3])
    >>> s[0]=4
    >>> t
    (1, [4, 3])

### 条件判断
**条件判断** 
注意不要少写了冒号`:`。

可以用`elif`做更细致的判断：

    age = 3
    if age >= 18:
        print('adult')
    elif age >= 6:
        print('teenager')
    else:
        print('kid')
`elif`是`else if`的缩写，完全可以有多个`elif`，所以`if`语句的完整形式就是：

    if <条件判断1>:
        <执行1>
    elif <条件判断2>:
        <执行2>
    elif <条件判断3>:
        <执行3>
    else:
        <执行4>
if判断条件还可以简写，比如写：

    if x:
        print('True')
只要`x`是非零数值、非空字符串、非空list等，就判断为`True`，否则为`False`。

**再议 input**  
`input()`返回的数据类型是`str`，`str`不能直接和整数比较，必须先把`str`转换成整数。Python提供了`int()`函数来完成这件事情：

    s = input('birth: ')
    birth = int(s)
    if birth < 2000:
        print('00前')
    else:
        print('00后')

如果输入的不是合法的数字时`int()`就会报错

### 循环
要计算1+2+3+...+10000，直接写表达式就不可能了。

为了让计算机能计算成千上万次的重复运算，我们就需要循环语句。

Python的循环有两种，一种是for...in循环，依次把list或tuple中的每个元素迭代出来，看例子：

    names = ['Michael', 'Bob', 'Tracy']
    for name in names:
        print(name)
执行这段代码，会依次打印`names`的每一个元素：

    Michael
    Bob
    Tracy
所以`for x in ...`循环就是把每个元素代入变量`x`，然后执行缩进块的语句。

再比如我们想计算1-10的整数之和，可以用一个`sum`变量做累加：

    sum = 0
    for x in [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]:
        sum = sum + x
    print(sum)
如果要计算1-100的整数之和，从1写到100有点困难，幸好Python提供一个`range()`函数，可以生成一个整数序列，再通过`list()`函数可以转换为list。比如`range(5)`生成的序列是从0开始小于5的整数：

    >>> list(range(5))
    [0, 1, 2, 3, 4]
`range(101)`就可以生成0-100的整数序列，计算如下：

    sum = 0
    for x in range(101):
    sum = sum + x
    print(sum)
请自行运行上述代码，看看结果是不是当年高斯同学心算出的5050。

第二种循环是while循环，只要条件满足，就不断循环，条件不满足时退出循环。比如我们要计算100以内所有奇数之和，可以用while循环实现：

    sum = 0
    n = 99
    while n > 0:
        sum = sum + n
        n = n - 2
    print(sum)
在循环内部变量`n`不断自减，直到变为`-1`时，不再满足while条件，循环退出。








### 使用dict和set
**dict**  
Python内置了字典：dict的支持，dict全称dictionary，在其他语言中也称为map，使用键-值（key-value）存储，具有极快的查找速度。

举个例子，假设要根据同学的名字查找对应的成绩，如果用list实现，需要两个list：

    names = ['Michael', 'Bob', 'Tracy']
    scores = [95, 75, 85]
给定一个名字，要查找对应的成绩，就先要在names中找到对应的位置，再从scores取出对应的成绩，list越长，耗时越长。

如果用dict实现，只需要一个“名字”-“成绩”的对照表，直接根据名字查找成绩，无论这个表有多大，查找速度都不会变慢。用Python写一个dict如下：

    >>> d = {'Michael': 95, 'Bob': 75, 'Tracy': 85}
    >>> d['Michael']
    95
为什么dict查找速度这么快？因为dict的实现原理和查字典是一样的。假设字典包含了1万个汉字，我们要查某一个字，一个办法是把字典从第一页往后翻，直到找到我们想要的字为止，这种方法就是在list中查找元素的方法，list越大，查找越慢。

第二种方法是先在字典的索引表里（比如部首表）查这个字对应的页码，然后直接翻到该页，找到这个字。无论找哪个字，这种查找速度都非常快，不会随着字典大小的增加而变慢。

dict就是第二种实现方式，给定一个名字，比如'Michael'，dict在内部就可以直接计算出Michael对应的存放成绩的“页码”，也就是95这个数字存放的内存地址，直接取出来，所以速度非常快。

你可以猜到，这种key-value存储方式，在放进去的时候，必须根据key算出value的存放位置，这样，取的时候才能根据key直接拿到value。

把数据放入dict的方法，除了初始化时指定外，还可以通过key放入：

    >>> d['Adam'] = 67
    >>> d['Adam']
    67
由于一个key只能对应一个value，所以，多次对一个key放入value，后面的值会把前面的值冲掉：

    >>> d['Jack'] = 90
    >>> d['Jack']
    90
    >>> d['Jack'] = 88
    >>> d['Jack']
    88
如果key不存在，dict就会报错：

    >>> d['Thomas']
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    KeyError: 'Thomas'
要避免key不存在的错误，有两种办法，一是通过in判断key是否存在：

    >>> 'Thomas' in d
    False
二是通过dict提供的get方法，如果key不存在，可以返回None，或者自己指定的value：

    >>> d.get('Thomas')
    >>> d.get('Thomas', -1)
    -1
注意：返回None的时候Python的交互式命令行不显示结果。

要删除一个key，用pop(key)方法，对应的value也会从dict中删除：

    >>> d.pop('Bob')
    75
    >>> d
    {'Michael': 95, 'Tracy': 85}
请务必注意，dict内部存放的顺序和key放入的顺序是没有关系的。

和list比较，dict有以下几个特点：

查找和插入的速度极快，不会随着key的增加而变慢；
需要占用大量的内存，内存浪费多。
而list相反：

查找和插入的时间随着元素的增加而增加；
占用空间小，浪费内存很少。
所以，dict是用空间来换取时间的一种方法。

dict可以用在需要高速查找的很多地方，在Python代码中几乎无处不在，正确使用dict非常重要，需要牢记的第一条就是dict的key必须是不可变对象。

这是因为dict根据key来计算value的存储位置，如果每次计算相同的key得出的结果不同，那dict内部就完全混乱了。这个通过key计算位置的算法称为哈希算法（Hash）。

要保证hash的正确性，作为key的对象就不能变。在Python中，字符串、整数等都是不可变的，因此，可以放心地作为key。而list是可变的，就不能作为key：

    >>> key = [1, 2, 3]
    >>> d[key] = 'a list'
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: unhashable type: 'list'
    set

set和dict类似，也是一组key的集合，但不存储value。由于key不能重复，所以，在set中，没有重复的key。

要创建一个set，需要提供一个list作为输入集合：

    >>> s = set([1, 2, 3])
    >>> s
    {1, 2, 3}
注意，传入的参数[1, 2, 3]是一个list，而显示的{1, 2, 3}只是告诉你这个set内部有1，2，3这3个元素，显示的顺序也不表示set是有序的。。

重复元素在set中自动被过滤：

    >>> s = set([1, 1, 2, 2, 3, 3])
    >>> s
    {1, 2, 3}
通过add(key)方法可以添加元素到set中，可以重复添加，但不会有效果：

    >>> s.add(4)
    >>> s
    {1, 2, 3, 4}
    >>> s.add(4)
    >>> s
    {1, 2, 3, 4}
通过remove(key)方法可以删除元素：

    >>> s.remove(4)
    >>> s
    {1, 2, 3}
set可以看成数学意义上的无序和无重复元素的集合，因此，两个set可以做数学意义上的交集、并集等操作：

    >>> s1 = set([1, 2, 3])
    >>> s2 = set([2, 3, 4])
    >>> s1 & s2
    {2, 3}
    >>> s1 | s2
    {1, 2, 3, 4}
set和dict的唯一区别仅在于没有存储对应的value，但是，set的原理和dict一样，所以，同样不可以放入可变对象，因为无法判断两个可变对象是否相等，也就无法保证set内部“不会有重复元素”。试试把list放入set，看看是否会报错。

再议不可变对象

上面我们讲了，str是不变对象，而list是可变对象。

对于可变对象，比如list，对list进行操作，list内部的内容是会变化的，比如：

    >>> a = ['c', 'b', 'a']
    >>> a.sort()
    >>> a
    ['a', 'b', 'c']
而对于不可变对象，比如str，对str进行操作呢：

    >>> a = 'abc'
    >>> a.replace('a', 'A')
    'Abc'
    >>> a
    'abc'
虽然字符串有个replace()方法，也确实变出了'Abc'，但变量a最后仍是'abc'，应该怎么理解呢？

我们先把代码改成下面这样：

    >>> a = 'abc'
    >>> b = a.replace('a', 'A')
    >>> b
    'Abc'
    >>> a
    'abc'
要始终牢记的是，a是变量，而'abc'才是字符串对象！有些时候，我们经常说，对象a的内容是'abc'，但其实是指，a本身是一个变量，它指向的对象的内容才是'abc'：

a-to-str

当我们调用a.replace('a', 'A')时，实际上调用方法replace是作用在字符串对象'abc'上的，而这个方法虽然名字叫replace，但却没有改变字符串'abc'的内容。相反，replace方法创建了一个新字符串'Abc'并返回，如果我们用变量b指向该新字符串，就容易理解了，变量a仍指向原有的字符串'abc'，但变量b却指向新字符串'Abc'了：

a-b-to-2-strs

所以，对于不变对象来说，调用对象自身的任意方法，也不会改变该对象自身的内容。相反，这些方法会创建新的对象并返回，这样，就保证了不可变对象本身永远是不可变的。

小结

使用key-value存储结构的dict在Python中非常有用，选择不可变对象作为key很重要，最常用的key是字符串。

tuple虽然是不变对象，但试试把(1, 2, 3)和(1, [2, 3])放入dict或set中，并解释结果。





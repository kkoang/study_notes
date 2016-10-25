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

dict就是第二种实现方式，给定一个名字，比如`'Michael'`，dict在内部就可以直接计算出`Michael`对应的存放成绩的“页码”，也就是`95`这个数字存放的内存地址，直接取出来，所以速度非常快。

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
要避免key不存在的错误，有两种办法，一是通过`in`判断key是否存在：

    >>> 'Thomas' in d
    False
二是通过dict提供的get方法，如果key不存在，可以返回None，或者自己指定的value：

    >>> d.get('Thomas')
    >>> d.get('Thomas', -1)
    -1
注意：返回`None`的时候Python的交互式命令行不显示结果。

要删除一个key，用`pop(key)`方法，对应的value也会从dict中删除：

    >>> d.pop('Bob')
    75
    >>> d
    {'Michael': 95, 'Tracy': 85}

> 请务必注意，dict内部存放的顺序和key放入的顺序是没有关系的。

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

**set**

set和dict类似，也是一组key的集合，但不存储value。由于key不能重复，所以，在set中，没有重复的key。

要创建一个set，需要提供一个list作为输入集合：

    >>> s = set([1, 2, 3])
    >>> s
    {1, 2, 3}
注意，传入的参数`[1, 2, 3]`是一个list，而显示的`{1, 2, 3}`只是告诉你这个set内部有1，2，3这3个元素，显示的顺序也不表示set是有序的。。

重复元素在set中自动被过滤：

    >>> s = set([1, 1, 2, 2, 3, 3])
    >>> s
    {1, 2, 3}
通过`add(key)`方法可以添加元素到set中，可以重复添加，但不会有效果：

    >>> s.add(4)
    >>> s
    {1, 2, 3, 4}
    >>> s.add(4)
    >>> s
    {1, 2, 3, 4}
通过`remove(key)`方法可以删除元素：

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

**再议不可变对象**

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
虽然字符串有个`replace()`方法，也确实变出了`'Abc'`，但变量`a`最后仍是`'abc'`，应该怎么理解呢？

我们先把代码改成下面这样：

    >>> a = 'abc'
    >>> b = a.replace('a', 'A')
    >>> b
    'Abc'
    >>> a
    'abc'
要始终牢记的是，`a`是变量，而`'abc'`才是字符串对象！有些时候，我们经常说，对象`a`的内容是`'abc'`，但其实是指，`a`本身是一个变量，它指向的对象的内容才是`'abc'`：

> 所以，对于不变对象来说，调用对象自身的任意方法，也不会改变该对象自身的内容。相反，这些方法会创建新的对象并返回，这样，就保证了不可变对象本身永远是不可变的。

小结

使用key-value存储结构的dict在Python中非常有用，选择不可变对象作为key很重要，最常用的key是字符串。

tuple虽然是不变对象，但试试把(1, 2, 3)和(1, [2, 3])放入dict或set中，并解释结果。

## 函数
函数就是最基本的一种代码抽象的方式。

### 调用函数
Python内置了很多有用的函数，我们可以直接调用。

要调用一个函数，需要知道函数的名称和参数，比如求绝对值的函数`abs`，只有一个参数。可以直接从Python的官方网站查看文档：

<http://docs.python.org/3/library/functions.html#abs>

也可以在交互式命令行通过`help(abs)`查看`abs`函数的帮助信息。

调用`abs`函数：

    >>> abs(100)
    100
    >>> abs(-20)
    20
    >>> abs(12.34)
    12.34
调用函数的时候，如果传入的参数数量不对，会报`TypeError`的错误，并且Python会明确地告诉你：`abs()`有且仅有1个参数，但给出了两个：

    >>> abs(1, 2)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: abs() takes exactly one argument (2 given)
如果传入的参数数量是对的，但参数类型不能被函数所接受，也会报`TypeError`的错误，并且给出错误信息：`str`是错误的参数类型：

    >>> abs('a')
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: bad operand type for abs(): 'str'
而`max`函数`max()`可以接收任意多个参数，并返回最大的那个：

    >>> max(1, 2)
    2
    >>> max(2, 3, 1, -5)
    3
**数据类型转换**

Python内置的常用函数还包括数据类型转换函数，比如`int()`函数可以把其他数据类型转换为整数：

    >>> int('123')
    123
    >>> int(12.34)
    12
    >>> float('12.34')
    12.34
    >>> str(1.23)
    '1.23'
    >>> str(100)
    '100'
    >>> bool(1)
    True
    >>> bool('')
    False
函数名其实就是指向一个函数对象的引用，完全可以把函数名赋给一个变量，相当于给这个函数起了一个“别名”：

    >>> a = abs # 变量a指向abs函数
    >>> a(-1) # 所以也可以通过a调用abs函数
    1

> 起别名很有用，Linux的指令也可以取别名。

### 定义函数
在Python中，定义一个函数要使用`def`语句，依次写出函数名、括号、括号中的参数和冒号:，然后，在缩进块中编写函数体，函数的返回值用`return`语句返回。

我们以自定义一个求绝对值的`my_abs`函数为例：

    def my_abs(x):
        if x >= 0:
            return x
        else:
            return -x
请自行测试并调用`my_abs`看看返回结果是否正确。

请注意，函数体内部的语句在执行时，一旦执行到`return`时，函数就执行完毕，并将结果返回。因此，函数内部通过条件判断和循环可以实现非常复杂的逻辑。

如果没有`return`语句，函数执行完毕后也会返回结果，只是结果为`None`。

`return None`可以简写为`return`。

如果你已经把`my_abs()`的函数定义保存为`abstest.py`文件了，那么，可以在该文件的当前目录下启动Python解释器，用`from abstest import my_abs`来导入`my_abs()`函数，注意`abstest`是文件名（不含`.py`扩展名）：

**空函数**

如果想定义一个什么事也不做的空函数，可以用`pass`语句：

    def nop():
        pass
`pass`语句什么都不做，那有什么用？实际上`pass`可以用来作为占位符，比如现在还没想好怎么写函数的代码，就可以先放一个`pass`，让代码能运行起来。

`pass`还可以用在其他语句里，比如：

    if age >= 18:
        pass
缺少了`pass`，代码运行就会有语法错误。

**参数检查**

调用函数时，如果参数个数不对，Python解释器会自动检查出来，并抛出`TypeError`：

    >>> my_abs(1, 2)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: my_abs() takes 1 positional argument but 2 were given
但是如果参数类型不对，Python解释器就无法帮我们检查。试试`my_abs`和内置函数`abs`的差别：

    >>> my_abs('A')
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
      File "<stdin>", line 2, in my_abs
    TypeError: unorderable types: str() >= int()
    >>> abs('A')
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: bad operand type for abs(): 'str'
当传入了不恰当的参数时，内置函数`abs`会检查出参数错误，而我们定义的`my_abs`没有参数检查，会导致`if`语句出错，出错信息和`abs`不一样。所以，这个函数定义不够完善。

让我们修改一下`my_abs`的定义，对参数类型做检查，只允许整数和浮点数类型的参数。数据类型检查可以用内置函数`isinstance()`实现：

    def my_abs(x):
        if not isinstance(x, (int, float)):
            raise TypeError('bad operand type')
        if x >= 0:
            return x
        else:
            return -x
添加了参数检查后，如果传入错误的参数类型，函数就可以抛出一个错误：

    >>> my_abs('A')
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
      File "<stdin>", line 3, in my_abs
    TypeError: bad operand type
错误和异常处理将在后续讲到。

**返回多个值**

函数可以返回多个值吗？答案是肯定的。

比如在游戏中经常需要从一个点移动到另一个点，给出坐标、位移和角度，就可以计算出新的新的坐标：

    import math

    def move(x, y, step, angle=0):
        nx = x + step * math.cos(angle)
        ny = y - step * math.sin(angle)
        return nx, ny
`import math`语句表示导入`math`包，并允许后续代码引用`math`包里的`sin`、`cos`等函数。

然后，我们就可以同时获得返回值：

    >>> x, y = move(100, 100, 60, math.pi / 6)
    >>> print(x, y)
    151.96152422706632 70.0
但其实这只是一种假象，Python函数返回的仍然是单一值：

    >>> r = move(100, 100, 60, math.pi / 6)
    >>> print(r)
    (151.96152422706632, 70.0)
原来返回值是一个tuple！但是，在语法上，返回一个tuple可以省略括号，而多个变量可以同时接收一个tuple，按位置赋给对应的值，所以，Python的函数返回多值其实就是返回一个tuple，但写起来更方便。

小结

定义函数时，需要确定函数名和参数个数；

如果有必要，可以先对参数的数据类型做检查；

函数体内部可以用`return`随时返回函数结果；

函数执行完毕也没有`return`语句时，自动`return None`。

函数可以同时返回多个值，但其实就是一个tuple。

提示：计算平方根可以调用`math.sqrt()`

    >>> import math
    >>> math.sqrt(2)
    1.4142135623730951

### 函数的参数
定义函数的时候，我们把参数的名字和位置确定下来，函数的接口定义就完成了。对于函数的调用者来说，只需要知道如何传递正确的参数，以及函数将返回什么样的值就够了，函数内部的复杂逻辑被封装起来，调用者无需了解。

Python的函数定义非常简单，但灵活度却非常大。除了正常定义的必选参数外，还可以使用默认参数、可变参数和关键字参数，使得函数定义出来的接口，不但能处理复杂的参数，还可以简化调用者的代码。

**位置参数**

我们先写一个计算x^2的函数：

    def power(x):
        return x * x
对于`power(x)`函数，参数`x`就是一个位置参数。

当我们调用`power`函数时，必须传入有且仅有的一个参数x：

    >>> power(5)
    25
    >>> power(15)
    225
现在，如果我们要计算x3怎么办？可以再定义一个`power3`函数，但是如果要计算x4、x5……怎么办？我们不可能定义无限多个函数。

你也许想到了，可以把`power(x)`修改为`power(x, n)`，用来计算x^n，说干就干：

    def power(x, n):
        s = 1
        while n > 0:
            n = n - 1
            s = s * x
        return s
对于这个修改后的`power(x, n)`函数，可以计算任意n次方：

    >>> power(5, 2)
    25
    >>> power(5, 3)
    125
修改后的`power(x, n)`函数有两个参数：`x`和`n`，这两个参数都是位置参数，调用函数时，传入的两个值按照位置顺序依次赋给参数`x`和`n`。

**默认参数**

新的`power(x, n)`函数定义没有问题，但是，旧的调用代码失败了，原因是我们增加了一个参数，导致旧的代码因为缺少一个参数而无法正常调用：

    >>> power(5)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: power() missing 1 required positional argument: 'n'
Python的错误信息很明确：调用函数`power()`缺少了一个位置参数`n`。

这个时候，默认参数就排上用场了。由于我们经常计算x^2，所以，完全可以把第二个参数n的默认值设定为2：

    def power(x, n=2):
        s = 1
        while n > 0:
            n = n - 1
            s = s * x
        return s
这样，当我们调用`power(5)`时，相当于调用`power(5, 2)`：

    >>> power(5)
    25
    >>> power(5, 2)
    25
而对于`n > 2`的其他情况，就必须明确地传入n，比如`power(5, 3)`。

从上面的例子可以看出，默认参数可以简化函数的调用。设置默认参数时，有几点要注意：

一是必选参数在前，默认参数在后，否则Python的解释器会报错（思考一下为什么默认参数不能放在必选参数前面）；

二是如何设置默认参数。

当函数有多个参数时，把变化大的参数放前面，变化小的参数放后面。变化小的参数就可以作为默认参数。

使用默认参数有什么好处？最大的好处是能降低调用函数的难度。

举个例子，我们写个一年级小学生注册的函数，需要传入`name`和`gender`两个参数：

    def enroll(name, gender):
        print('name:', name)
        print('gender:', gender)
这样，调用`enroll()`函数只需要传入两个参数：

    >>> enroll('Sarah', 'F')
    name: Sarah
    gender: F
如果要继续传入年龄、城市等信息怎么办？这样会使得调用函数的复杂度大大增加。

我们可以把年龄和城市设为默认参数：

    def enroll(name, gender, age=6, city='Beijing'):
        print('name:', name)
        print('gender:', gender)
        print('age:', age)
        print('city:', city)
这样，大多数学生注册时不需要提供年龄和城市，只提供`必须的两个参数`：

    >>> enroll('Sarah', 'F')
    name: Sarah
    gender: F
    age: 6
    city: Beijing
只有与默认参数不符的学生才需要提供额外的信息：

    enroll('Bob', 'M', 7)
    enroll('Adam', 'M', city='Tianjin')
可见，默认参数降低了函数调用的难度，而一旦需要更复杂的调用时，又可以传递更多的参数来实现。无论是简单调用还是复杂调用，函数只需要定义一个。

有多个默认参数时，调用的时候，既可以按顺序提供默认参数，比如调用`enroll('Bob', 'M', 7)`，意思是，除了`name`，`gender`这两个参数外，最后1个参数应用在参数`age`上，`city`参数由于没有提供，仍然使用默认值。

也可以不按顺序提供部分默认参数。当不按顺序提供部分默认参数时，需要把参数名写上。比如调用`enroll('Adam', 'M', city='Tianjin')`，意思是，`city`参数用传进去的值，其他默认参数继续使用默认值。

默认参数很有用，但使用不当，也会掉坑里。默认参数有个最大的坑，演示如下：

先定义一个函数，传入一个list，添加一个`END`再返回：

    def add_end(L=[]):
        L.append('END')
        return L
当你正常调用时，结果似乎不错：

    >>> add_end([1, 2, 3])
    [1, 2, 3, 'END']
    >>> add_end(['x', 'y', 'z'])
    ['x', 'y', 'z', 'END']
当你使用默认参数调用时，一开始结果也是对的：

    >>> add_end()
    ['END']
但是，再次调用`add_end()`时，结果就不对了：

    >>> add_end()
    ['END', 'END']
    >>> add_end()
    ['END', 'END', 'END']
很多初学者很疑惑，默认参数是`[]`，但是函数似乎每次都“记住了”上次添加了`'END'`后的list。

原因解释如下：

Python函数在定义的时候，默认参数`L`的值就被计算出来了，即`[]`，因为默认参数`L`也是一个变量，它指向对象`[]`，每次调用该函数，如果改变了`L`的内容，则下次调用时，默认参数的内容就变了，不再是函数定义时的`[]`了。

所以，定义默认参数要牢记一点：默认参数必须指向不变对象！

> 默认参数必须指向不变对象！

要修改上面的例子，我们可以用`None`这个不变对象来实现：

    def add_end(L=None):
        if L is None:
            L = []
        L.append('END')
        return L
现在，无论调用多少次，都不会有问题：

    >>> add_end()
    ['END']
    >>> add_end()
    ['END']
为什么要设计`str`、`None`这样的不变对象呢？因为不变对象一旦创建，对象内部的数据就不能修改，这样就减少了由于修改数据导致的错误。此外，由于对象不变，多任务环境下同时读取对象不需要加锁，同时读一点问题都没有。我们在编写程序时，如果可以设计一个不变对象，那就尽量设计成不变对象。

**可变参数**

在Python函数中，还可以定义可变参数。顾名思义，可变参数就是传入的参数个数是可变的，可以是1个、2个到任意个，还可以是0个。我们以数学题为例子，给定一组数字a，b，c……，请计算a2 + b2 + c2 + ……。要定义出这个函数，我们必须确定输入的参数。由于参数个数不确定，我们首先想到可以把a，b，c……作为一个list或tuple传进来，这样，函数可以定义如下：

    def calc(numbers):
        sum = 0
        for n in numbers:
            sum = sum + n * n
        return sum
但是调用的时候，需要先组装出一个list或tuple：

    >>> calc([1, 2, 3])
    14
    >>> calc((1, 3, 5, 7))
    84
如果利用可变参数，调用函数的方式可以简化成这样：

    >>> calc(1, 2, 3)
    14
    >>> calc(1, 3, 5, 7)
    84
所以，我们把函数的参数改为可变参数：

    def calc(*numbers):
        sum = 0
        for n in numbers:
            sum = sum + n * n
        return sum
定义可变参数和定义一个list或tuple参数相比，仅仅在参数前面加了一个*号。在函数内部，参数numbers接收到的是一个tuple，因此，函数代码完全不变。但是，调用该函数时，可以传入任意个参数，包括0个参数：

    >>> calc(1, 2)
    5
    >>> calc()
    0
如果已经有一个list或者tuple，要调用一个可变参数怎么办？可以这样做：

    >>> nums = [1, 2, 3]
    >>> calc(nums[0], nums[1], nums[2])
    14
这种写法当然是可行的，问题是太繁琐，所以Python允许你在list或tuple前面加一个*号，把list或tuple的元素变成可变参数传进去：

    >>> nums = [1, 2, 3]
    >>> calc(*nums)
    14
`*nums`表示把`nums`这个list的所有元素作为可变参数传进去。这种写法相当有用，而且很常见。

**关键字参数**

可变参数允许你传入0个或任意个参数，这些可变参数在函数调用时自动组装为一个`tuple`。而关键字参数允许你传入0个或任意个含参数名的参数，这些关键字参数在函数内部自动组装为一个`dict`。请看示例：

    def person(name, age, **kw):
        print('name:', name, 'age:', age, 'other:', kw)
函数`person`除了必选参数`name`和`age`外，还接受关键字参数`kw`。在调用该函数时，可以只传入必选参数：

    >>> person('Michael', 30)
    name: Michael age: 30 other: {}
也可以传入任意个数的关键字参数：

    >>> person('Bob', 35, city='Beijing')
    name: Bob age: 35 other: {'city': 'Beijing'}
    >>> person('Adam', 45, gender='M', job='Engineer')
    name: Adam age: 45 other: {'gender': 'M', 'job': 'Engineer'}
关键字参数有什么用？它可以扩展函数的功能。比如，在`person`函数里，我们保证能接收到`name`和`age`这两个参数，但是，如果调用者愿意提供更多的参数，我们也能收到。试想你正在做一个用户注册的功能，除了用户名和年龄是必填项外，其他都是可选项，利用关键字参数来定义这个函数就能满足注册的需求。和可变参数类似，也可以先组装出一个dict，然后，把该dict转换为关键字参数传进去：

    >>> extra = {'city': 'Beijing', 'job': 'Engineer'}
    >>> person('Jack', 24, city=extra['city'], job=extra['job'])
    name: Jack age: 24 other: {'city': 'Beijing', 'job': 'Engineer'}
当然，上面复杂的调用可以用简化的写法：

    >>> extra = {'city': 'Beijing', 'job': 'Engineer'}
    >>> person('Jack', 24, **extra)
    name: Jack age: 24 other: {'city': 'Beijing', 'job': 'Engineer'}
`**extra表示`把`extra`这个dict的所有key-value用关键字参数传入到函数的`**kw`参数，`kw`将获得一个dict，注意`kw`获得的dict是`extra`的一份拷贝，对`kw`的改动不会影响到函数外的`extra`。

**命名关键字参数**

对于关键字参数，函数的调用者可以传入任意不受限制的关键字参数。至于到底传入了哪些，就需要在函数内部通过`kw`检查。

仍以`person()`函数为例，我们希望检查是否有`city`和`job`参数：

    def person(name, age, **kw):
        if 'city' in kw:
            # 有city参数
            pass
        if 'job' in kw:
            # 有job参数
            pass
        print('name:', name, 'age:', age, 'other:', kw)
但是调用者仍可以传入不受限制的关键字参数：

    >>> person('Jack', 24, city='Beijing', addr='Chaoyang', zipcode=123456)
如果要限制关键字参数的名字，就可以用命名关键字参数，例如，只接收city和job作为关键字参数。这种方式定义的函数如下：

    def person(name, age, *, city, job):
        print(name, age, city, job)
和关键字参数`**kw`不同，命名关键字参数需要一个特殊分隔符`*`，`*`后面的参数被视为命名关键字参数。

调用方式如下：

    >>> person('Jack', 24, city='Beijing', job='Engineer')
    Jack 24 Beijing Engineer
如果函数定义中已经有了一个可变参数，后面跟着的命名关键字参数就不再需要一个特殊分隔符`*`了：

    def person(name, age, *args, city, job):
        print(name, age, args, city, job)
命名关键字参数必须传入参数名，这和位置参数不同。如果没有传入参数名，调用将报错：

    >>> person('Jack', 24, 'Beijing', 'Engineer')
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: person() takes 2 positional arguments but 4 were given
由于调用时缺少参数名`city`和`job`，Python解释器把这4个参数均视为位置参数，但`person()`函数仅接受2个位置参数。

命名关键字参数可以有缺省值，从而简化调用：

    def person(name, age, *, city='Beijing', job):
        print(name, age, city, job)
由于命名关键字参数`city`具有默认值，调用时，可不传入`city`参数：

    >>> person('Jack', 24, job='Engineer')
    Jack 24 Beijing Engineer
使用命名关键字参数时，要特别注意，如果没有可变参数，就必须加一个`*`作为特殊分隔符。如果缺少`*`，Python解释器将无法识别位置参数和命名关键字参数：

    def person(name, age, city, job):
        # 缺少 *，city和job被视为位置参数
        pass

**参数组合**

在Python中定义函数，可以用必选参数、默认参数、可变参数、关键字参数和命名关键字参数，这5种参数都可以组合使用。但是请注意，参数定义的顺序必须是：必选参数、默认参数、可变参数、命名关键字参数和关键字参数。

比如定义一个函数，包含上述若干种参数：

    def f1(a, b, c=0, *args, **kw):
        print('a =', a, 'b =', b, 'c =', c, 'args =', args, 'kw =', kw)

    def f2(a, b, c=0, *, d, **kw):
        print('a =', a, 'b =', b, 'c =', c, 'd =', d, 'kw =', kw)
在函数调用的时候，Python解释器自动按照参数位置和参数名把对应的参数传进去。

    >>> f1(1, 2)
    a = 1 b = 2 c = 0 args = () kw = {}
    >>> f1(1, 2, c=3)
    a = 1 b = 2 c = 3 args = () kw = {}
    >>> f1(1, 2, 3, 'a', 'b')
    a = 1 b = 2 c = 3 args = ('a', 'b') kw = {}
    >>> f1(1, 2, 3, 'a', 'b', x=99)
    a = 1 b = 2 c = 3 args = ('a', 'b') kw = {'x': 99}
    >>> f2(1, 2, d=99, ext=None)
    a = 1 b = 2 c = 0 d = 99 kw = {'ext': None}
最神奇的是通过一个tuple和dict，你也可以调用上述函数：

    >>> args = (1, 2, 3, 4)
    >>> kw = {'d': 99, 'x': '#'}
    >>> f1(*args, **kw)
    a = 1 b = 2 c = 3 args = (4,) kw = {'d': 99, 'x': '#'}
    >>> args = (1, 2, 3)
    >>> kw = {'d': 88, 'x': '#'}
    >>> f2(*args, **kw)
    a = 1 b = 2 c = 3 d = 88 kw = {'x': '#'}
所以，对于任意函数，都可以通过类似`func(*args, **kw)`的形式调用它，无论它的参数是如何定义的。

小结

Python的函数具有非常灵活的参数形态，既可以实现简单的调用，又可以传入非常复杂的参数。

默认参数一定要用不可变对象，如果是可变对象，程序运行时会有逻辑错误！

要注意定义可变参数和关键字参数的语法：

`*args`是可变参数，args接收的是一个tuple；

`**kw`是关键字参数，kw接收的是一个dict。

以及调用函数时如何传入可变参数和关键字参数的语法：

可变参数既可以直接传入：`func(1, 2, 3)`，又可以先组装list或tuple，再通过`*args`传入：`func(*(1, 2, 3))`；

关键字参数既可以直接传入：`func(a=1, b=2)`，又可以先组装dict，再通过`**kw`传入：`func(**{'a': 1, 'b': 2})`。

使用`*args`和`**kw`是Python的习惯写法，当然也可以用其他参数名，但最好使用习惯用法。

命名的关键字参数是为了限制调用者可以传入的参数名，同时可以提供默认值。

定义命名的关键字参数在没有可变参数的情况下不要忘了写分隔符`*`，否则定义的将是位置参数。

### 递归函数

在函数内部，可以调用其他函数。如果一个函数在内部调用自身本身，这个函数就是递归函数。

举个例子，我们来计算阶乘`n! = 1 x 2 x 3 x ... x n`，用函数`fact(n)`表示，可以看出：

fact(n) = n! = 1 x 2 x 3 x ... x (n-1) x n = (n-1)! x n = fact(n-1) x n

所以，`fact(n)`可以表示为`n x fact(n-1)`，只有n=1时需要特殊处理。

于是，`fact(n)`用递归的方式写出来就是：

    def fact(n):
        if n==1:
            return 1
        return n * fact(n - 1)
上面就是一个递归函数。可以试试：

    >>> fact(1)
    1
    >>> fact(5)
    120
    >>> fact(100)
    93326215443944152681699238856266700490715968264381621468592963895217599993229915608941463976156518286253697920827223758251185210916864000000000000000000000000
如果我们计算`fact(5)`，可以根据函数定义看到计算过程如下：

    ===> fact(5)
    ===> 5 * fact(4)
    ===> 5 * (4 * fact(3))
    ===> 5 * (4 * (3 * fact(2)))
    ===> 5 * (4 * (3 * (2 * fact(1))))
    ===> 5 * (4 * (3 * (2 * 1)))
    ===> 5 * (4 * (3 * 2))
    ===> 5 * (4 * 6)
    ===> 5 * 24
    ===> 120
递归函数的优点是定义简单，逻辑清晰。理论上，所有的递归函数都可以写成循环的方式，但循环的逻辑不如递归清晰。

使用递归函数需要注意防止栈溢出。在计算机中，函数调用是通过栈（stack）这种数据结构实现的，每当进入一个函数调用，栈就会加一层栈帧，每当函数返回，栈就会减一层栈帧。由于栈的大小不是无限的，所以，递归调用的次数过多，会导致栈溢出。可以试试`fact(1000)`：

    >>> fact(1000)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
      File "<stdin>", line 4, in fact
      ...
      File "<stdin>", line 4, in fact
    RuntimeError: maximum recursion depth exceeded in comparison
解决递归调用栈溢出的方法是通过尾递归优化，事实上尾递归和循环的效果是一样的，所以，把循环看成是一种特殊的尾递归函数也是可以的。

尾递归是指，在函数返回的时候，调用自身本身，并且，return语句不能包含表达式。这样，编译器或者解释器就可以把尾递归做优化，使递归本身无论调用多少次，都只占用一个栈帧，不会出现栈溢出的情况。

上面的`fact(n)`函数由于`return n * fact(n - 1)`引入了乘法表达式，所以就不是尾递归了。要改成尾递归方式，需要多一点代码，主要是要把每一步的乘积传入到递归函数中：

    def fact(n):
        return fact_iter(n, 1)

    def fact_iter(num, product):
        if num == 1:
            return product
        return fact_iter(num - 1, num * product)
可以看到，`return fact_iter(num - 1, num * product)`仅返回递归函数本身，`num - 1`和`num * product`在函数调用前就会被计算，不影响函数调用。

`fact(5)`对应的`fact_iter(5, 1)`的调用如下：

    ===> fact_iter(5, 1)
    ===> fact_iter(4, 5)
    ===> fact_iter(3, 20)
    ===> fact_iter(2, 60)
    ===> fact_iter(1, 120)
    ===> 120
尾递归调用时，如果做了优化，栈不会增长，因此，无论多少次调用也不会导致栈溢出。

遗憾的是，大多数编程语言没有针对尾递归做优化，Python解释器也没有做优化，所以，即使把上面的fact(n)函数改成尾递归方式，也会导致栈溢出。

小结

使用递归函数的优点是逻辑简单清晰，缺点是过深的调用会导致栈溢出。

针对尾递归优化的语言可以通过尾递归防止栈溢出。尾递归事实上和循环是等价的，没有循环语句的编程语言只能通过尾递归实现循环。

Python标准的解释器没有针对尾递归做优化，任何递归函数都存在栈溢出的问题。

## 高级特性

掌握了Python的数据类型、语句和函数，基本上就可以编写出很多有用的程序了。

比如构造一个`1, 3, 5, 7, ..., 99`的列表，可以通过循环实现：

    L = []
    n = 1
    while n <= 99:
        L.append(n)
        n = n + 2
取list的前一半的元素，也可以通过循环实现。

但是在Python中，代码不是越多越好，而是越少越好。代码不是越复杂越好，而是越简单越好。

基于这一思想，我们来介绍Python中非常有用的高级特性，1行代码能实现的功能，决不写5行代码。请始终牢记，代码越少，开发效率越高。

### 切片

取一个list或tuple的部分元素是非常常见的操作。比如，一个list如下：

    >>> L = ['Michael', 'Sarah', 'Tracy', 'Bob', 'Jack']
取前3个元素，应该怎么做？

笨办法：

    >>> [L[0], L[1], L[2]]
    ['Michael', 'Sarah', 'Tracy']
之所以是笨办法是因为扩展一下，取前N个元素就没辙了。

取前N个元素，也就是索引为0-(N-1)的元素，可以用循环：

    >>> r = []
    >>> n = 3
    >>> for i in range(n):
    ...     r.append(L[i])
    ... 
    >>> r
    ['Michael', 'Sarah', 'Tracy']
对这种经常取指定索引范围的操作，用循环十分繁琐，因此，Python提供了切片（Slice）操作符，能大大简化这种操作。

对应上面的问题，取前3个元素，用一行代码就可以完成切片：

    >>> L[0:3]
    ['Michael', 'Sarah', 'Tracy']
`L[0:3]`表示，从索引`0`开始取，直到索引`3`为止，但不包括索引`3`。即索引`0`，`1`，`2`，正好是3个元素。

如果第一个索引是`0`，还可以省略：

    >>> L[:3]
    ['Michael', 'Sarah', 'Tracy']
也可以从索引1开始，取出2个元素出来：

    >>> L[1:3]
    ['Sarah', 'Tracy']
类似的，既然Python支持`L[-1]`取倒数第一个元素，那么它同样支持倒数切片，试试：

    >>> L[-2:]
    ['Bob', 'Jack']
    >>> L[-2:-1]
    ['Bob']
记住倒数第一个元素的索引是`-1`。

切片操作十分有用。我们先创建一个0-99的数列：

    >>> L = list(range(100))
    >>> L
    [0, 1, 2, 3, ..., 99]
可以通过切片轻松取出某一段数列。比如前10个数：

    >>> L[:10]
    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
后10个数：

    >>> L[-10:]
    [90, 91, 92, 93, 94, 95, 96, 97, 98, 99]
前11-20个数：

    >>> L[10:20]
    [10, 11, 12, 13, 14, 15, 16, 17, 18, 19]
前10个数，每两个取一个：

    >>> L[:10:2]
    [0, 2, 4, 6, 8]
所有数，每5个取一个：

    >>> L[::5]
    [0, 5, 10, 15, 20, 25, 30, 35, 40, 45, 50, 55, 60, 65, 70, 75, 80, 85, 90, 95]
甚至什么都不写，只写`[:]`就可以原样复制一个list：

    >>> L[:]
    [0, 1, 2, 3, ..., 99]
tuple也是一种list，唯一区别是tuple不可变。因此，tuple也可以用切片操作，只是操作的结果仍是tuple：

    >>> (0, 1, 2, 3, 4, 5)[:3]
    (0, 1, 2)
字符串`'xxx'`也可以看成是一种list，每个元素就是一个字符。因此，字符串也可以用切片操作，只是操作结果仍是字符串：

    >>> 'ABCDEFG'[:3]
    'ABC'
    >>> 'ABCDEFG'[::2]
    'ACEG'
在很多编程语言中，针对字符串提供了很多各种截取函数（例如，substring），其实目的就是对字符串切片。Python没有针对字符串的截取函数，只需要切片一个操作就可以完成，非常简单。

小结

有了切片操作，很多地方循环就不再需要了。Python的切片非常灵活，一行代码就可以实现很多行循环才能完成的操作。

    L = [1,2,3,4,5,6,7,8,9]
    print(L[::1])
    print(L[:8:1])
    print(L[-2::1])
    print(L[-2::-1])
    print(L[-2:0:-1])
    print(L[-2:0:-2])
    print(L[-2:1:-1])
结果分别是：

    [1, 2, 3, 4, 5, 6, 7, 8, 9]
    [1, 2, 3, 4, 5, 6, 7, 8]
    [8, 9]
    [8, 7, 6, 5, 4, 3, 2, 1]
    [8, 7, 6, 5, 4, 3, 2]
    [8, 6, 4, 2]
    [8, 7, 6, 5, 4, 3]

### 迭代

如果给定一个list或tuple，我们可以通过`for`循环来遍历这个list或tuple，这种遍历我们称为迭代（Iteration）。

在Python中，迭代是通过`for ... in`来完成的，而很多语言比如C或者Java，迭代list是通过下标完成的，比如Java代码：

    for (i=0; i<list.length; i++) {
        n = list[i];
    }
可以看出，Python的`for`循环抽象程度要高于Java的`for`循环，因为Python的`for`循环不仅可以用在list或tuple上，还可以作用在其他可迭代对象上。

list这种数据类型虽然有下标，但很多其他数据类型是没有下标的，但是，只要是可迭代对象，无论有无下标，都可以迭代，比如dict就可以迭代：

    >>> d = {'a': 1, 'b': 2, 'c': 3}
    >>> for key in d:
    ...     print(key)
    ...
    a
    c
    b
因为dict的存储不是按照list的方式顺序排列，所以，迭代出的结果顺序很可能不一样。

默认情况下，dict迭代的是key。如果要迭代value，可以用`for value in d.values()`，如果要同时迭代key和value，可以用`for k, v in d.items()`。

由于字符串也是可迭代对象，因此，也可以作用于`for`循环：

    >>> for ch in 'ABC':
    ...     print(ch)
    ...
    A
    B
    C
所以，当我们使用`for`循环时，只要作用于一个可迭代对象，`for`循环就可以正常运行，而我们不太关心该对象究竟是list还是其他数据类型。

那么，如何判断一个对象是可迭代对象呢？方法是通过collections模块的Iterable类型判断：

    >>> from collections import Iterable
    >>> isinstance('abc', Iterable) # str是否可迭代
    True
    >>> isinstance([1,2,3], Iterable) # list是否可迭代
    True
    >>> isinstance(123, Iterable) # 整数是否可迭代
    False
最后一个小问题，如果要对list实现类似Java那样的下标循环怎么办？Python内置的`enumerate`函数可以把一个list变成索引-元素对，这样就可以在`for`循环中同时迭代索引和元素本身：

    >>> for i, value in enumerate(['A', 'B', 'C']):
    ...     print(i, value)
    ...
    0 A
    1 B
    2 C
上面的`for`循环里，同时引用了两个变量，在Python里是很常见的，比如下面的代码：

    >>> for x, y in [(1, 1), (2, 4), (3, 9)]:
    ...     print(x, y)
    ...
    1 1
    2 4
    3 9
小结

任何可迭代对象都可以作用于`for`循环，包括我们自定义的数据类型，只要符合迭代条件，就可以使用`for`循环。

<https://github.com/michaelliao/learn-python3/blob/master/samples/advance/do_iter.py#L20>

    print('next():')
    it = iter([1, 2, 3, 4, 5])
    print(next(it))
    print(next(it))
    print(next(it))
    print(next(it))
    print(next(it))






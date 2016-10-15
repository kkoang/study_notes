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


















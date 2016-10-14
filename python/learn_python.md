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

直接运行py文件,在Mac和Linux上是可以的，方法是在.py文件的第一行加上一个特殊的注释：

    #!/usr/bin/env python3
    print('hello, world')

这是脚本语言共同遵守的规则：当第一行为 #!/path/to/script/interpreter时，指定了用来执行本脚本的解释器。

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












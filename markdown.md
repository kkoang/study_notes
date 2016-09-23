### 兼容 HTML

    <table>
        <tr>
            <td>Foo</td>
        </tr>
    </table>
    <br>标签等等

`&copy; ©`：&copy; © <br>
`AT&T AT&amp;T &amp;`：AT&T AT&amp;T &amp; <br>
`&lt; <`：&lt; < <br>
`4 < 5` Markdown 将会把它转换为：`4 &lt; 5` <br>
`<` 和 `&` 两个符号都一定会被转换成 HTML 实体，这项特性让你可以很容易地用 Markdown 写 HTML code

### 标题

Markdown 支持两种标题的语法

    This is an H1
    =============
    This is an H2
    -------------

任何数量的 = 和 - 都可以有效果。

行首插入 1 到 6 个 # ，对应到标题 1 到 6 阶，例如：

    # This is an H1
    ## This is an H2
    ###### This is an H6

你可以选择性地`「闭合」`，这纯粹只是美观用的，若是觉得这样看起来比较舒适，你就可以在行尾加上 #，而行尾的 # 数量也不用和开头一样（行首的井字数量决定标题的阶数）`或者在标题中加入#`：

    # 在标题中加入# #
    ## This is an H2 ##
    ### This is an H3 ######

### Blockquotes（引用）

Markdown 标记区块引用是使用类似 email 中用 > 的引用方式，然后在每行的最前面加上 > ：

> 这是一段被引用的例子文本
>
>>>可以叠加`>`
>
>换行可以入`空白行`或`> 行`
>
> 可以使用`` `小段代码引用` ``

* * *

引用的区块内也可以使用其他的 Markdown 语法，包括标题、列表、代码区块等：

> ### This is a header.
>
> 1.   This is the first list item.
> 1.   This is the second list item.
>
> 下面是代码区块案例`（加了4个空格或者2个Tab）`：
>
>     return shell_exec("echo $input | $markdown_script");

### 列表

Markdown 支持有序列表和无序列表。
无序清单使用`星号`、`加号`或是`减号`作为列表标记：

    * Red
    + Green
    - Blue

例子：

* 编程语言  
    * 脚本语言  
        * Python

有序列表则使用`数字接着一个英文句点`：

    1. Bird
    2. McHale
    9. Parish

一定要接着至少一个空格或制表符。  
要让列表看起来更漂亮，你可以把内容用固定的缩进整理好：

可以在列表项目内放进引用，`>` ：

* A list item with a blockquote:
> This is a blockquote

如果要放文本块的话：

* A list item with a code block:
      <放入列表的代码区块需要4个空格+\*（等于一个空格）+\*右边空格数到文本结束（最少1个最多3个空格）>

当然，项目列表很可能会不小心产生，像是下面这样的写法：

`1986. What a great season.`

换句话说，也就是在行首出现数字-句点-空白，要避免这样的状况，你可以在句点前面加上反斜杠。

`1986\. What a great season.`

### 程序代码区块

Markdown 会用 `<pre>` 和 `<code>` 标签来把代码区块包起来。
```
用```引起来的区块可以代码高亮
用 4 个空格或是 1 个制表符的是文本块
```
要在 Markdown 中建立代码区块很简单，只要简单地缩进 4 个空格或是 1 个制表符就可以，例如，下面的输入：

    This is a normal paragraph:
        This is a code block.

### 分隔线

你可以在一行中用三个或以上的星号、减号来建立一个分隔线，行内不能有其他东西。你也可以在星号中间插入空格。下面每种写法都可以建立分隔线：

    * * *
    ***
    *****
    - - -

### 链接

Markdown 支持两种形式的链接语法： **行内式**和**参考式**两种形式。

不管是哪一种，链接的文字都是用 `[方括号]` 来标记。

要建立一个行内式的链接，只要在方括号后面马上接着圆括号并插入网址链接即可，如果你还想要加上链接的 title 文字，只要在网址后面，用双引号把 title 文字包起来即可，例如：

    This is [an example](http://example.com/ "Title") inline link.
    [This link](http://example.net/) has no title attribute.

**参考式**的链接是在链接文字的括号后面再接上另一个方括号，而在第二个方括号里面要填入用以辨识链接的标记：

    This is [an example][id] reference-style link.

你也可以选择性地在两个方括号中间加上空格：

    This is [an example] [id] reference-style link.

接着，在文件的任意处，你可以把这个标签的链接内容定义出来：

    [id]: http://example.com/  "Optional Title Here"

链接内容定义的形式为：

* 方括号（前面可以选择性地加上至多三个空格来缩进），里面输入链接文字
* 接着一个冒号
* 接着一个以上的空格或制表符
* 接着链接的网址
* 选择性地接着 title 内容，可以用单引号、双引号或是圆括号包着
下面这三种连结的定义都是相同：

    [foo]: http://example.com/  "Optional Title Here"
    [foo]: http://example.com/  'Optional Title Here'
    [foo]: http://example.com/  (Optional Title Here)

**请注意**：有一个已知的问题是 Markdown.pl 1.0.1 会忽略单引号包起来的链接 title。
链接网址也可以用方括号包起来：

    [id]: <http://example.com/>  "Optional Title Here"

链接辨识标记可以有字母、数字、空白和标点符号，但是并不区分大小写，因此下面两个链接是一样的：

    [link text][a]
    [link text][A]

**隐式链接标记**功能让你可以省略指定链接标记，这种情形下，链接标记和链接文字会视为相同，要用隐式链接标记只要在链接文字后面加上一个空的方括号，如果你要让 "Google" 链接到 google.com，你可以简化成：

    [Google][]

然后定义链接内容：

    [Google]: http://google.com/

链接的定义可以放在文件中的任何一个地方，我比较偏好直接放在链接出现段落的后面，你也可以把它放在文件最后面，就像是注解一样。
下面是一个参考式链接的范例：

I get 10 times more traffic from [Google] [1] than from
[Yahoo] [2] or [MSN] [3].
  [1]: http://google.com/        "Google"
  [2]: http://search.yahoo.com/  "Yahoo Search"
  [3]: http://search.msn.com/    "MSN Search"

如果改成用链接名称的方式写：

    I get 10 times more traffic from [Google][] than from
    [Yahoo][] or [MSN][].
      [google]: http://google.com/        "Google"
      [yahoo]:  http://search.yahoo.com/  "Yahoo Search"
      [msn]:    http://search.msn.com/    "MSN Search"

### 自动链接

    <http://www.baidu.com/>

邮址的自动链接也很类似，只是 Markdown 会先做一个编码转换的过程，把文字字符转成 16 进位码的 HTML 实体，这样的格式可以糊弄一些不好的邮址收集机器人，例如：

    <address@example.com>

### 强调

#### 斜体、粗体、删除线

|语法|效果|
|:--:|:--:|
|`*斜体1*`|*斜体1*
|`_斜体2_`|_斜体2_
|`**粗体1**`|**粗体1**
|`__粗体2__`|__粗体2__
|`这是一个 ~~删除线~~`|这是一个 ~~删除线~~
|`***斜粗体1***`|***斜粗体1***
|`___斜粗体2___`|___斜粗体2___
|`***~~斜粗体删除线1~~***`|***~~斜粗体删除线1~~***
|`~~***斜粗体删除线2***~~`|~~***斜粗体删除线2***~~

斜体、粗体、删除线可混合使用

### 代码

如果要标记一小段行内代码，你可以用反引号把它包起来（`` ` ``），例如：

    Use the `printf()` function.

如果要在代码区段内插入反引号，你可以用多个反引号来开启和结束代码区段：

    ``There is a literal backtick (`) here.``

### 图片

很明显地，要在纯文本应用中设计一个 「自然」的语法来插入图片是有一定难度的。
Markdown 使用一种和链接很相似的语法来标记图片，同样也允许两种样式： 行内式和参考式。
行内式图片的语法看起来像是：

    ![Alt text](/path/to/img.jpg)
    ![Alt text](/path/to/img.jpg "Optional title")

例子：

    ![][foryou]
    [foryou]:https://github.com/guodongxiaren/ImageCache/raw/master/Logo/foryou.gif

详细叙述如下：

* 一个惊叹号 !
* 接着一对方括号，里面放上图片的替代文字
* 接着一对普通括号，里面放上图片的网址，最后还可以用引号包住并加上选择性的 'title' 文字。

参考式的图片语法则长得像这样：

    ![Alt text][id]

「id」是图片参考的名称，图片参考的定义方式则和链接参考一样：

    [id]: url/to/image  "Optional title attribute"

到目前为止， Markdown 还没有办法指定图片的宽高，如果你需要的话，你可以使用普通的 `<img>` 标签。

### 反斜杠
Markdown 可以利用反斜杠来插入一些在语法中有其它意义的符号，例如：如果你想要用星号加在文字旁边的方式来做出强调效果（但不用 `<em>` 标签），你可以在星号的前面加上反斜杠：

    \*literal asterisks\*

Markdown 支持在下面这些符号前面加上反斜杠来帮助插入普通的符号：

```
    \   反斜杠
    `   反引号
    *   星号
    _   底线
    {}  大括号
    []  方括号
    ()  括号
    #   井字号
    +    加号
    -    减号
    .   英文句点
    !   惊叹号
```

* * * *

    4个空格或者两个Tab >> 形成单行文本

### 复选框列表
- [x] 是
- [ ] 否

### 表格

左对齐 | 居中 | 右对齐
----|:----:|----:
foo  foofoo | foo foo foo  | foo foo foo
*bar* | ~~bar~~  | **bar**
baz | baz  | baz

### 代码高亮

在三个反引号后面加上编程语言的名字，另起一行开始写代码，最后一行再加上三个反引号。

```Java
public static void main(String[]args){} //Java
```

```c
int main(int argc, char * argv[]) //C
```

```Bash
echo "hello GitHub" #Bash
```

```javascript
document.getElementById("myH1").innerHTML="Welcome to my Homepage"; //javascipt
```

```cpp
string &operator+(const string& A,const string& B) //cpp
```

```python
@requires_authorization
class SomeClass:
    pass

if __name__ == '__main__':
    # A comment
    print 'hello world'
```

### 锚点

每一个标题都是一个锚点，和HTML的锚点（#）类似，github支持此格式
不过要注意，标题中的英文字母都被转化为小写字母了。
[回到顶部](#readme)

### 表情

Github的Markdown语法支持添加emoji表情，输入不同的符号码（两个冒号包围的字符）可以显示出不同的表情。  
比如:blush:，可以显示:blush:。  
具体每一个表情的符号码，可以查询GitHub的官方网页<http://www.emoji-cheat-sheet.com>。  
但是这个网页每次都打开奇慢。。所以我整理到了本repo中，大家可以直接在此查看[emoji](https://github.com/guodongxiaren/README/blob/master/emoji.md)。

### 换行

直接回车不能换行，  
可以`在上一行文本后面补两个空格`，  
这样下一行的文本就换行了。  

或者就是在两行文本`直接加一个空行`。

也能实现换行效果，不过这个行间距有点大。

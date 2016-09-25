### 安装Git
<http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/00137396287703354d8c6c01c904c7d9ff056ae23da865a000#0>
Gist:
$ git config --global user.name "填你的名字"
$ git config --global user.email "填你的email地址"

### 创建版本库
创建一个版本库非常简单，首先，选择一个合适的地方，创建一个空目录：

    $ mkdir learngit
    $ cd learngit
    $ pwd
    /Users/michael/learngit

pwd命令用于显示当前目录。在我的Mac上，这个仓库位于/Users/michael/learngit。

第二步，通过`git init`命令把这个目录变成Git可以管理的仓库：

    $ git init
    Initialized empty Git repository in /Users/michael/learngit/.git/

瞬间Git就把仓库建好了，而且告诉你是一个空的仓库（empty Git repository），`.git`的目录，这个目录是Git来跟踪管理版本库的，**没事千万不要手动修改这个目录里面的文件**，不然改乱了，就把Git仓库给破坏了。如果你没有看到`.git`目录，那是因为**这个目录默认是隐藏的**，用`ls -ah`命令就可以看见。

**如果你使用Windows系统，为了避免遇到各种莫名其妙的问题，请确保目录名（包括父目录）不包含中文。**

### 把文件添加到版本库
所有的版本控制系统，其实只能跟踪文本文件的改动，比如TXT文件，网页，所有的程序代码等等，Microsoft的Word格式是二进制格式，所以没法跟踪。
    
    因为文本是有编码的，强烈建议使用标准的UTF-8编码

现在我们编写一个`readme.txt`文件，内容如下：

    Git is a version control system.
    Git is free software.

一定要放到`learngit`目录下（子目录也行），因为这是一个Git仓库，放到其他地方Git再厉害也找不到这个文件。  
把一个文件放到Git仓库只需要两步。

第一步，用命令git add告诉Git，把文件添加到仓库：

    $ git add readme.txt

执行上面的命令，没有任何显示，这就对了，Unix的哲学是“没有消息就是好消息”，说明添加成功。

第二步，用命令git commit告诉Git，把文件提交到仓库：

    $ git commit -m "wrote a readme file"
    [master (root-commit) cb926e7] wrote a readme file
     1 file changed, 2 insertions(+)
     create mode 100644 readme.txt

简单解释一下`git commit`命令，`-m`后面输入的是本次提交的说明，可以输入任意内容，当然最好是有意义的，这样你就能从历史记录里方便地找到改动记录。

`git commit`命令执行成功后会告诉你，1个文件被改动（我们新添加的readme.txt文件），插入了两行内容（readme.txt有两行内容）。

为什么Git添加文件需要`add`，`commit`一共两步呢？因为`commit`可以一次提交很多文件，所以你可以多次`add`不同的文件，比如：

    $ git add file1.txt
    $ git add file2.txt file3.txt
    $ git commit -m "add 3 files."









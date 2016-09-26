## 创建版本库
版本库又名仓库，英文名repository

第一步，创建一个版本库非常简单，首先，选择一个合适的地方，创建一个空目录：

```bash
$ mkdir learngit //创建名叫learngit的文件夹
$ cd learngit //进入learngit文件夹
$ pwd //显示现在在哪里
```

第二步，通过git init命令把这个目录变成Git可以管理的仓库：

    $ git init //把当前目录变为git可管理仓库
    Initialized empty Git repository in /Users/michael/learngit/.git/

第一步，用命令`git add`告诉Git，把文件添加到仓库：

    $ git add readme.txt //添加名为readme的文件到

第二步，用命令`git commit`告诉Git，把文件提交到仓库,记得加`-m "本次提交的说明"`也可以不加，非强制，最好是加：

    $ git commit -m "wrote a readme file"

commit可以一次提交很多文件，所以你可以多次add不同的文件，比如：

    $ git add file1.txt
    $ git add file2.txt file3.txt
    $ git commit -m "add 3 files."

#### 创建版本库小结

现在总结一下今天学的两点内容：  
初始化一个Git仓库，使用`git init`命令。  
添加文件到Git仓库，分两步：
* 第一步，使用命令`git add <file>`，注意，可反复多次使用，添加多个文件；
* 第二步，使用命令`git commit`，完成。

## 时光机穿梭
修改readme.txt文件  
`git status`命令可以让我们时刻掌握仓库当前的状态，上面的命令告诉我们，readme.txt被修改过了，但还没有准备提交的修改。  
如果记不清上次怎么修改的readme.txt，所以，需要用git diff这个命令看看：

    $ git diff readme.txt 

`git diff`顾名思义就是查看difference，显示的格式正是Unix通用的diff格式，可以从上面的命令输出看到，我们在第一行添加了一个“distributed”单词。

提交修改和提交新文件是一样的两步，第一步是`git add`：

    $ git add readme.txt

同样没有任何输出。在执行第二步`git commit`之前，我们再运行`git status`看看当前仓库的状态：

`git status`告诉我们，将要被提交的修改包括readme.txt，下一步，就可以放心地提交了：

    $ git commit -m "add revise"

提交后，我们再用`git status`命令看看仓库的当前状态：

Git告诉我们当前没有需要提交的修改，而且，工作目录是干净（working directory clean）的。

* 要随时掌握工作区的状态，使用`git status`命令。
* 如果`git status`告诉你有文件被修改过，用`git diff`可以查看修改内容。











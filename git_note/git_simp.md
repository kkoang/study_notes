## 创建版本库
版本库又名仓库，英文名repository

所以，创建一个版本库非常简单，首先，选择一个合适的地方，创建一个空目录：

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



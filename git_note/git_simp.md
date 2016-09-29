## 创建版本库
版本库又名仓库，英文名repository

第一步，创建一个版本库非常简单，首先，选择一个合适的地方，创建一个空目录：

```bash
$ mkdir learngit //创建名叫learngit的文件夹
$ cd learngit //进入learngit文件夹
$ pwd //显示现在在哪里
```

第二步，通过`git init`命令把这个目录变成Git可以管理的仓库：

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
如果记不清上次怎么修改的readme.txt，所以，需要用`git diff`这个命令看看：

    $ git diff readme.txt 

`git diff`顾名思义就是查看difference，显示的格式正是Unix通用的diff格式，可以从上面的命令输出看到，我们在第一行添加了一个“distributed”单词。

提交修改和提交新文件是一样的两步，第一步是`git add`：

    $ git add readme.txt

同样没有任何输出。在执行第二步`git commit`之前，我们再运行`git status`看看当前仓库的状态：

`git status`告诉我们，将要被提交的修改包括readme.txt，下一步，就可以放心地提交了：

    $ git commit -m "add revise"

提交后，我们再用`git status`命令看看仓库的当前状态：

Git告诉我们当前没有需要提交的修改，而且，工作目录是干净（working directory clean）的。

#### 时光机穿梭小结
* 要随时掌握工作区的状态，使用`git status`命令。
* 如果`git status`告诉你有文件被修改过，用`git diff`可以查看修改内容。

### 版本回退
`git log`命令显示从**最近到最远**的提交日志

如果嫌输出信息太多，看得眼花缭乱的，可以试试加上`--pretty=oneline`参数：

    $ git log --pretty=oneline
    3628164fb26d48395383f8f31179f24e0882e1e0 append GPL

你看到的一大串类似`3628164...882e1e0`的是`commit id`（版本号），

我们要把当前版本“append GPL”回退到上一个版本“add distributed”，就可以使用`git reset`命令：

    $ git reset --hard HEAD^

`HEAD^`，上上一个版本就是`HEAD^^`，当然往上100个版本写100个`^`比较容易数不过来，所以写成`HEAD~100`

> `HEAD^`跟`HEAD~1`效果一样。

Git提供了一个命令`git reflog`用来记录你的每一次命令：

    $ git reflog

> `git reflog`看到记录，可以回到指定的`commit id`版本

#### 版本回退小结
* HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令`git reset --hard commit_id`。
* 穿梭前，用`git log`可以查看提交历史，以便确定要回退到哪个版本。
* 要重返未来，用`git reflog`查看命令历史，以便确定要回到未来的哪个版本。

### 工作区和暂存区
Git和其他版本控制系统如SVN的一个不同之处就是有暂存区的概念。先来看名词解释。

**工作区（Working Directory）** 就是你在电脑里能看到的目录，比如我的`learngit`文件夹就是一个工作区：

**版本库（Repository）** 工作区有一个隐藏目录`.git`，这个不算工作区，而是Git的版本库。

![](http://www.liaoxuefeng.com/files/attachments/001384907702917346729e9afbf4127b6dfbae9207af016000/0)

> 个人理解`stage`是暂存区

### 管理修改
> 提交后，用`git diff HEAD -- readme.txt`命令可以查看工作区和版本库里面最新版本的区别：
> 每次修改，如果不add到暂存区，那就不会加入到commit中。

### 撤销修改
场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令`git checkout -- file`。  
场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令`git reset HEAD file`，就回到了场景1，第二步按场景1操作。  
场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。
> `git reset HEAD file`可以把暂存区的修改撤销掉（unstage）。实测是删除对应暂存区的文件.

### 删除文件
> 命令git checkout -- file是把最近的版本覆盖到工作区，如果暂存区有文件用暂存区覆盖工作区的对应文件，没有看版本库有没有，版本库有就用版本库的覆盖工作区的对应文件

* 命令`git rm`用于删除一个文件。如果一个文件已经被提交到版本库，那么你永远不用担心误删，但是要小心，你只能恢复文件到最新版本，你会丢失最近一次提交后你修改的内容。

> 命令`git rm`用于删除一个文件,`git add`用于添加一个文件，两个命令都是把命令添加到stage（暂存区）。
> 用 git rm 来删除文件，同时还会将这个删除操作记录下来；
> 用 rm 来删除文件，仅仅是删除了物理文件，没有将其从 git 的记录中剔除。

## 远程仓库
第1步：创建SSH Key。在用户主目录下，看看有没有.ssh目录，如果有，再看看这个目录下有没有`id_rsa`和`id_rsa.pub`这两个文件，如果已经有了，可直接跳到下一步。如果没有，打开Shell（Windows下打开Git Bash），创建SSH Key：

    $ ssh-keygen -t rsa -C "youremail@example.com"

如果一切顺利的话，可以在用户主目录里找到`.ssh`目录，里面有`id_rsa`和`id_rsa.pub`两个文件，这两个就是SSH Key的秘钥对，`id_rsa`是私钥，不能泄露出去，`id_rsa.pub`是公钥，可以放心地告诉任何人。

第2步：登陆GitHub，打开“Account settings”，“SSH Keys”页面：

然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴`id_rsa.pub`文件的内容：

点“Add Key”，你就应该看到已经添加的Key：

为什么GitHub需要SSH Key呢？因为GitHub需要识别出你推送的提交确实是你推送的，而不是别人冒充的，而Git支持SSH协议，所以，GitHub只要知道了你的公钥，就可以确认只有你自己才能推送。

当然，GitHub允许你添加多个Key。假定你有若干电脑，你一会儿在公司提交，一会儿在家里提交，只要把每台电脑的Key都添加到GitHub，就可以在每台电脑上往GitHub推送了。

> 最后友情提示，在GitHub上免费托管的Git仓库，任何人都可以看到喔（但只有你自己才能改）。所以，不要把敏感信息放进去。

### 添加远程库
登陆GitHub，创建一个新的仓库，Repository name填入`learngit`，创建好仓库。  
这个时候的`learngit`仓库还是空的。

    $ git remote add origin git@github.com:michaelliao/learngit.git

请千万注意，把上面的`michaelliao`替换成你自己的GitHub账户名  
添加后，远程库的名字就是`origin`，这是Git默认的叫法，也可以改成别的。  
现在把本地库的所有内容推送到远程库上：

    $ git push -u origin master

把本地库的内容推送到远程，用`git push`命令，实际上是把当前分支`master`推送到远程。

我们第一次推送`master`分支时，加上了`-u`参数

现在起，只要本地作了提交，就可以通过命令：

    $ git push origin master

第一次使用Git的`clone`或者`push`命令连接GitHub时，会得到一个警告：

    The authenticity of host 'github.com (xx.xx.xx.xx)' can't be established.
    RSA key fingerprint is xx.xx.xx.xx.xx.
    Are you sure you want to continue connecting (yes/no)?

输入`yes`回车即可。

### 从远程库克隆
先用GitHub，创建一个新的仓库，名字叫`gitskills`。  
勾选`Initialize this repository with a README`，GitHub会自动为我们创建一个`README.md`文件

远程库已经准备好了，下一步是用命令`git clone`克隆一个本地库：

    $ git clone git@github.com:kkoang/gitskills.git

    $ cd gitskills
    $ ls
    README.md

> 要克隆一个仓库，首先必须知道仓库的地址，然后使用`git clone`命令克隆。
> Git支持多种协议，包括`https`，但通过`ssh`支持的原生`git`协议速度最快。

## 分支管理
> 其实就是在主分支分出来一段分支，这段分支可以等到开发完之后再合并到主分支。

### 创建与合并分支

创建`dev`分支，然后切换到`dev`分支：

    $ git checkout -b dev

`git checkout`命令加上`-b`参数表示创建并切换，相当于以下两条命令：

    $ git branch dev
    $ git checkout dev

> `git branch`命令会列出所有分支，查看当前指向哪个分支，当前分支前面会标一个`*`号。

把`dev`分支的工作成果合并到master分支上。

    $ git checkout master
    $ git merge dev

#### 创建与合并分支小结

Git鼓励大量使用分支：

查看分支：`git branch`

创建分支：`git branch <name>`

切换分支：`git checkout <name>`

创建+切换分支：`git checkout -b <name>`

合并某分支到当前分支：`git merge <name>`

删除分支：`git branch -d <name>`

### 解决冲突

创建一个新的分支叫`xx`

    git checkout -b xx

修改文件`readme.txt`然后提交到`xx`分支上：

    add>commit

切换到master分支：

    $ git checkout master

在`master`分支上把readme.txt文件的修改,然后提交：

`git checkout master`HEAD指向master再合并分支`git merge xx`

这种情况下，Git无法执行“快速合并”，只能试图把各自的修改合并起来（`<<<`,`+++`,`>>>`),需要人工合并之后再提交最终合并版本。

> 合并失败进`(xx|MERGING)`人工修改合并文件之后，add>commit（提交）后为最终修改版本，可以删除合并的分支`xx`

用`git log --graph`命令可以看到分支合并图。






.

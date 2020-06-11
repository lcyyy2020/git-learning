# 前导知识：一些基础的linux命令
```
cd 			进入某路径文件夹下
mkdir 		创建文件夹
pwd			查看当前路径
vi			进入文件
wq			退出文件
```
# 一、Git是什么？
Git是目前世界上最先进的分布式版本控制系统。

Workspace：工作区
Index / Stage：暂存区
Repository：仓库区（或本地仓库）
Remote：远程仓库

# 二、使用git之前的最小配置

首先对用户信息进行配置
注意 此处email需要真实能够收到信件，以便于项目出现问题是可以被通知到
user.name（此处是一个空格，必须有）’name’
``` 
$ git config --global  user.name ’name’
$ git config --global  user.email ’email’
``` 
以下是config的三个作用域，缺省等同于local
```
$ git config —-local			只对某一个仓库有效
$ git config --global			当前用户的所有仓库
$ git config —-system			对系统所有登录的用户有效
```
查看当前作用域下git的配置
```
$ git config --list —-local				只对某一个仓库有效
$ git config --list --global			当前用户的所有仓库
$ git config --list —-system			对系统所有登录的用户有效
```

# 三、创建git仓库对项目进行管理
1. 当项目文件已经存在时
```
$ cd 项目代码所在文件夹
$ git init 
```
2. 当项目文件还未创建
```
$ cd 某个文件夹
$ git init your_project  会自动创建一个同名并已经被git管理了的
$ cd your_project
```
这时候你当前testgit目录下会多了一个.git的目录，这个目录是Git来跟踪管理版本的，没事千万不要手动乱改这个目录里面的文件，否则，会把git仓库给破坏了

# 四、使用git对项目版本进行管理
当项目修改后，需要先将需要保存至仓库的项目文件添加至暂存区
```
$ git add 文件名
```
随后可将暂存区的文件提交至仓库
```
$ git commit -m '为此次修改备注的信息'
```
下面可以通过命令git status来查看是否还有文件未提交，如下：
```
$ git status
```
当发现有未被提交的修改，可以通过命令git diff来查看文件都做了哪些修改
```
$ git diff 要比对的文件名
```
## 简洁用法
如果我们很清晰的知道文件没有问题，想要一次性提交到仓库，省略掉中间添加到暂存区的环节可以直接通过以下命令实现
```
```
## 重命名文件
```
mv 需要重命名的文件 重命名的名字
$ git add 新的文件名
$ git rm 旧的文件名
```
简洁用法
```
$ git mv 需要重命名的文件 重命名的名字
```
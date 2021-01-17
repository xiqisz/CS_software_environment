## 前言

参考资料：

>[廖雪峰git教程](https://www.liaoxuefeng.com/wiki/896043488029600)
>
>[鱼C-小甲鱼git教程视频](https://www.bilibili.com/video/BV1bs411N7ny?from=search&seid=3395503626604857200)

## Git简介

Git是目前世界上最先进的分布式版本控制系统（没有之一）。

git工作区域

![image-20210117135149584](https://cdn.jsdelivr.net/gh/xiqisz/xiqisz-images/Typora/20210117135331.png)

## Git安装

### 在Windows上安装Git

在Windows上使用Git，可以从Git官网直接[下载安装程序](https://git-scm.com/downloads)，然后按默认选项安装即可。

安装完成后，在开始菜单里找到“Git”->“Git Bash”，蹦出一个类似命令行窗口的东西，就说明Git安装成功！

![image-20210117132243010](https://cdn.jsdelivr.net/gh/xiqisz/xiqisz-images/Typora/20210117134543.png)

安装完成后，还需要最后一步设置，在命令行输入：

```
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
```

因为Git是分布式版本控制系统，所以，每个机器都必须自报家门：你的名字和Email地址。你也许会担心，如果有人故意冒充别人怎么办？这个不必担心，首先我们相信大家都是善良无知的群众，其次，真的有冒充的也是有办法可查的。

注意`git config`命令的`--global`参数，用了这个参数，表示你这台机器上所有的Git仓库都会使用这个配置，当然也可以对某个仓库指定不同的用户名和Email地址。

## Git命令

```
git init
git add file.name
git commit -m "说明"
git diff
git checkout branch
git status
git log
...
```

![image-20210117135949500](https://cdn.jsdelivr.net/gh/xiqisz/xiqisz-images/Typora/20210117135949.png)



### 1.提交缓存到Git仓库

1.初始化一个空的仓库，用来跟踪管理版本迭代的，追踪这个文件夹里的文件来管理git项目的

```
git init
```

2.创建一个XX.md文件，让开发人员看到你的文档
3.将需要进行版本管理的文件放入暂存区域

```
git add XX.md
```

4.将暂存区域的文件提交到git仓库

```
git commit -m "the first commit"  //“”中间的信息是提交此次缓存的备注,方便应用
```

![image-20210117140557463](https://cdn.jsdelivr.net/gh/xiqisz/xiqisz-images/Typora/20210117140557.png)

### 2.查看工作状态和历史提交

1.查看状态（可查看到所处分支,未暂存以提交的更改,未跟踪的文件,有没有需要提交的更改）

```
git status 
//如果出现下图的红色文件 代表此文件没有加入到缓存去  可用 git add XX.js 加入缓存区，加入后就会变成绿色了
```

![image-20210117140806348](https://cdn.jsdelivr.net/gh/xiqisz/xiqisz-images/Typora/20210117141011.png)

2.最后提交的代码恢复回暂存区域

```
git reset HEAD <file>  
//不写<file>将回滚最后一次提交的所有文件，如果指定了<file>将只回滚选中的文件
```

3.删除暂存的更改(未commit前)

```
git checkout <file> 
//不写<file>将回滚所有更改文件，如果指定了<file>将只回滚选中的更改文件
```

4.查看历史提交记录

```
git log   
//进入查看log后 可用 q  退出
```

![image-20210117141050452](https://cdn.jsdelivr.net/gh/xiqisz/xiqisz-images/Typora/20210117141050.png)

### 3.回滚代码

1.回滚最后一次提交的记录到暂存区域(commit后的代码)

```
git reset HEAD~   
//～后面可加数字,如:(git reset HEAD~3),代表回滚最近3次的提交。
//本次命令写全是(git reset --mixed HEAD~)，执行后 再用git log也看不到回滚的提交记录了

```

2.回滚到指定位置,之前的提交会全部回滚到暂存区域

```
git reset bc124d4a1ca 
// 'bc124d4a1ca'是git log 后显示的黄色提交序号,不需要写全,但是要保证写的快照ID是唯一.
```

### 4.diff 对比找不同

1.比较暂存区域与工作目录不同的地方，也就是所更改的地方

```
git diff
```

2.比较两个历史快照

```
git diff 快照1ID 快照2ID
```

3.比较当前工作目录和Git仓库中的快照(还没有git add前的)

```
git diff 要对比的快照ID 
//因为当前工作目录的更改还没有提交，所以没有快照ID，故只需要写要对比的快照ID就可
```

```
git diff HEAD //比较当前工作目录和最新提交的快照
```

4.比较暂存目录和Git仓库中的快照(git add后的)

```
git diff --cached //比较的是暂存区域和最新提交的快照
```

```
git diff --cached 要对比的快照ID //暂存目前和指定的Git仓库中的快照的对比
```

### 5.修改最后一次提交

1.修改最后那次提交的备注信息

```
git commit --amend 
//输入后会进入到新的页面,输入i进入到修改，更改最上层的提交备注，
//修改后输入 :wq 保存并退出，并且不会多log日志。因说明是中文导致乱码
```

### 6.删除文件

1.如果不小心删除文件 可-> `git status`查看删除的是哪个文件 -> `git checkout -- 文件名`就可以恢复了,[注意: – 左右各有一个空格]
2.`git rm fileName //只是删除工作目录和暂存区域的文件` -> `git reset --soft HEAD~`因为删除后使用git status 依旧可以查看到被删除的信息,所以用–soft修改log的指针,把提交删除的记录去掉,但不会移动任何文件
3.`git rm -f fileName //强制删除，如果暂存区和当前目录都有此文件，将会两个文件一起删除`
4.`git rm --cached 文件名 //删除暂存区域的文件`

### 7.重命名文件

```
1.git mv fileName newFileName
```

### 8.分支

1.创建分支 `git branch 分支名`
2.切换分支

```
git checkout 分支名 
```

```
git checkout -b 分支名 //创建并切换到此分支
```

3.所有分支，包括远程分支`git branch -a`
4.图形化显示提交记录

```
git log --decorate --oneline --graph --all 
//‘oneline’精简化的显示 ‘graph’图形化显示 ‘all’显示所有的分支，decorate后的顺序可随意
```

5.合并分支

```
git merge 分支名 //把指定分支合并到当前分支
```

6.删除分支 `git branch -d 分支名 //-d 精简分支名，--delete 全名`

### 9.标签

1.新建标签

```
git tag <tagname>
//默认为HEAD 也可以指定一个commit id.
```

2.查看所有标签

```
git tag
```

3.指定标签信息

```
git tag -a <tagname> -m "blalallaa"
```

4.删除标签

```
git tag -d v0.1
```

```
git push origin :refs/tags/<tagname>
```



5.推送标签

```
git push origin --tags
```

```
git push origin <tagname>
```


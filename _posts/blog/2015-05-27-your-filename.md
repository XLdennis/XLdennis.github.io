---
published: true
---

---
layout:     post
title:      Git工作原理
category: blog
description: 觉得github很难，遂写一篇博客。
---

在 Git 内都只有三种状态：已提交（committed），已修改（modified）和已暂存（staged）。`已提交`表示该文件已经被安全地保存在本地数据库中了；`已修改`表示修改了某个文件，但还没有提交保存；`已暂存`表示把已修改的文件放在下次提交时要保存的清单中。

如下图所示
****
![](http://git-scm.com/figures/18333fig0106-tn.png =350x250)

Git配置
---

[用户信息]
	
	$ git config --global user.name "John Doe"
	$ git config --global user.email johndoe@example.com

如果用了 `--global` 选项，那么更改的配置文件就是位于你用户主目录下的那个，以后你所有的项目都会默认使用这里配置的用户信息。如果要在某个特定的项目中使用其他名字或者电邮，只要去掉 `--global` 选项重新配置即可，新的设定保存在当前项目的 `.git/config` 文件里(`git config --list 命令` 查看所有配置信息)。

[帮助]

	$ git help config

创建库
---

[在工作目录中初始化新仓库]

	$ git init	# 开始Git管理
	$ git add *.c 
	$ git add README # Git对哪些文件管理
	$ git commit -m 'initial project version'

[从现有库中提取]

	$ git clone git://github.com/schacon/grit.git #克隆 Ruby 语言的 Git 代码仓库 Grit, 这会在当前目录下创建一个名为grit的目录，其中包含一个 .git 的目录
	$ git clone git://github.com/schacon/grit.git mygrit #如果希望自己命名新的目录，则在.git后面加上名字
	
记录更新
---

[检查当前文件状态]

	$ git status #文件状态和分支名
	$ touch xxx
	$ open xxx
	$ git status #这个时候就会显示未跟踪的文件
	$ git add xxx #使用add命令来跟踪这些文件或者整个路径下的文件
	$ git status #这个时候文件xxx被跟踪，但是还没有同步commit
	$ git diff #工作目录中当前文件和暂存区域快照之间的差异
	
[忽略某些文件]

	$ cat .gitignore  #设置忽略文件
	*.[oa] #忽略所有以 .o 或 .a 结尾的文件
	!lib.a #但是不要忽略lib.a文件
	*~ #忽略所有以波浪符（~）结尾的文件
	/TODO #仅仅忽略项目根目录下的 TODO 文件，不包括 subdir/TODO
	build/ #忽略build/ 目录下的所有文件
	doc/*.txt #仅仅忽略doc文件根目录下的txt文件
	doc/**/*.txt #忽略全部txt文件
	
[提交暂存]

	$ git commit #提交add暂存的部分同步
	$ 一般是vim编辑器，可以使用 git config --global core.editor 命令设定你喜欢的编辑软件
	



		
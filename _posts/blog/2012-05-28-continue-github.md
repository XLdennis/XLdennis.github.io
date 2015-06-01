
                ---
                layout: post
                categories: [Tools]
                tags: [jekyll, github, git, markdown]
                ---

Git 基础
---
[历史记录]

	$ git clone git://github.com/schacon/simplegit-progit.git 
	$ git log -p -2 #-p 选项展开显示每次提交的内容差异, -2 则仅显示最近的两次更新
	$ git log -U1 --word-diff #单词层面的差异
	$ git log --stat #仅显示简要的增改行数统计
	$ git log --pretty=format:"%h - %an, %ar : %s" #定制要显示的记录格式，其中$h代表
	
	选项	 说明
	%H	提交对象（commit）的完整哈希字串
	%h	提交对象的简短哈希字串
	%T	树对象（tree）的完整哈希字串
	
	%t	树对象的简短哈希字串
	%P	父对象（parent）的完整哈希字串
	%p	父对象的简短哈希字串
	%an	作者（author）的名字
	%ae	作者的电子邮件地址
	%ad	作者修订日期（可以用 -date= 选项定制格式）
	%ar	作者修订日期，按多久以前的方式显示
	%cn	提交者(committer)的名字
	%ce	提交者的电子邮件地址
	%cd	提交日期
	%cr	提交日期，按多久以前的方式显示
	%s	提交说明

The keyboard shortcuts are `⌘+]` for indent and `⌘+[` for un-indent. 

	$ git log --pretty=format:"%h %s" --graph #形象地看到每个提交所在的分支及其分化衍合情况
	
	选项	说明
	-p	按补丁格式显示每个更新之间的差异。
	--word-diff	按 word diff 格式显示差异。
	--stat	显示每次更新的文件修改统计信息。
	--shortstat	只显示 --stat 中最后的行数修改添加移除统计。
	--name-only	仅在提交信息后显示已修改的文件清单。
	--name-status	显示新增、修改、删除的文件清单。
	--abbrev-commit	仅显示 SHA-1 的前几个字符，而非所有的 40 个字符。
	--relative-date	使用较短的相对时间显示（比如，“2 weeks ago”）。
	--graph	显示 ASCII 图形表示的分支合并历史，上面就是这个例子
	--pretty	使用其他格式显示历史提交信息。可用的选项包括 oneline，short，full，fuller 和 format（后跟指定格式）。
	--oneline	`--pretty=oneline --abbrev-commit` 的简化用法。

	$ git log --since=2.weeks #只输出最近两周的提交
你可以给出各种时间格式，比如说具体的某一天`2008-01-15`，或者是多久以前,`2 years 1 day 3 minutes ago`



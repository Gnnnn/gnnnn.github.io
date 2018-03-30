---
layout: post
title: "Common Git Command"
date: 2017-06-22
excerpt: "In case I fogot.Also,offer help to newbies."
tags: [list, git]
comments: true
---

## common git command

以下是一些常用的git命令，基本知道他们再结合--help就够用了。我把他们记录下来了以做参考。

### Tables

| number  | git command              | description                 |
|:--------|:------------------------:|----------------------------:|
| 0       | git init                 | init                        |
| 1       | git add .readme.txt      | add the file you want       |
| 2       | git add .readme.txt      | add the file you want       |
| 3       | git commit -a            | 'de'                        |
| 4       | git push origin maseter  | add the file you want       |
| 5       | git remote add origin url| 'de'                        |
| 6       | git push origin maseter  | add the file you want       |
|=====
| Foot1   | Foot2  | Foot3             
{: rules="groups"}


### 详细

* add
添加新文件到 Git 代码仓库的索引中
> $ git add filename

* mv
移动或重命名文件
> $ git mv old-filename new-filename

* rm
从工作目录和 Git 代码索引中删除文件
> $ git rm filename

* status
查看目前工作目录的代码状态，自上次提交以来的添加、修改和删除等
> $ git status

* diff
查看自上次提交以来，本地代码改动的具体情况
> $ git diff

* commit
提交修改的代码（只是提交到本地的代码库，不会推送到服务器）
> $ git commit -m '修改说明'

* push
local commit history->remote.将自上次 push 以来的，本地历次 commit，推送到服务器
> $ git push origin master:your-id
其中，master 是本地的分支名；your-id 填你在服务器上的 id，服务器的版本库里会有以你的 id 为名称的分支。

* pull
remote->local.将服务器上的代码拉到本地。
> $ git pull

* log
查看修改记录，含作者、时间、修改说明等
> $ git log

* show
显示具体的代码改动情况(最后一次commit）：
> $ git show

* branch
分支管理--列出所有分支（当前所在分支前会有“*”号）：
> $ git branch
新建分支：
> $ git branch 新分支名
删除分支：
> $ git branch -d 欲删除的分支名
###【注意！】不要把 ‘-d’ 写成了 ‘-D’，危险！

-d：要求：被删除分支的所有修改，已经合并到当前分支；
-D：直接删除，未合并的代码，将被丢弃！

* checkout
恢复某个已修改的文件（撤销未提交的修改）：
> $ git checkout file-name
切换到另外的分支，进行开发：
> $ git checkout branch-name

* merge
合并指定分支到当前分支：
$ git merge branch-name

* revert
还原已提交的修改（已经提交过的修改，可以反悔～）

* stash
先将未提交的修改暂存起来，接着清除所有改动，使之与没修改时一样。

若你正在开发功能 A，又需立即去开发功能 B。A 的代码正改到一半，未认真整理，你不想立即提交。此时……请呼叫 stash ～。

它会使你所有未提交的修改瞬间不见了：
$ git stash
它会使刚刚不见了的修改，瞬间又回来了：
$ git stash pop
【TIP】以上命令皆有更多参数，另有一些 Git 命令我们此处没有介绍。但是，这已足令你使用 Git 时游刃有余，你会觉得，Git 简直是一件神器！:-)

【TIP】’$ git help’ 与 ‘$ git help 命令名’ 会在你需要的时候，无私地帮助你。:-)


## 常见的git push 失败的解决办法

假设执行操作：

def solveErr():
	

1. 修改代码 2. git commit 3. git push
此时 push 失败（错误提示：! [rejected] master -> master (non-fast-forward) ）

解决办法：

$ git pull
若成功，则：

$ git push origin master:your-id
(* git pull origin master --allow-unrelated-histories)
完事。

若失败（提示：CONFLICT (content): Merge conflict in 文件名），则：

冲突的文件会有类似下面的代码块：

"<<<<HEAD 
你修改的代码 
============
 其他人修改的代码 
>>>>>commit id of others'"

考虑你和他人对代码的修改，更新成合适的内容，并删除 <<<、===、>>> 3行标记符号，保存文件。



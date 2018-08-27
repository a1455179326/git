# git
git 

Git 获取帮助
git help  <velp>  ;  git <velp> --help ;  man git-<verb>
例：git help config

在现有目录中初始化仓库
git init  创建一个名为 .git 的子目录
git add *.c
git add LICENSE
git commit -m 'initial project version'

克隆现有的仓库
git clone https://github.com/***/***
          user@server:path/to/repo.git 
          
  查看状态    
git status  
    git status -s  === git status --short 查看状态信息简便
    新添加的未跟踪文件前面有 ?? 标记
    新添加到暂存区中的文件前面有 A 标记
    修改过的文件前面有 M 标记--出现在右边的 M 表示该文件被修改了但是还没放入暂存区，出现在靠左边的 M 表示该文件被修改了并放入了暂存区
   
忽略文件
    例 cat .gitignore
        *.[oa]   第一行告诉 Git 忽略所有以 .o 或 .a 结尾的文件
        *~       第二行告诉 Git 忽略所有以波浪符（~）结尾的文件
        
查看尚未暂存的文件更新了哪些部分
   git diff
   git diff --cached 查看已暂存的将要添加到下次提交里的内容
   
提交更新
   git commit
   撤消操作 
   git commit --amend 
   
跳过使用暂存区域
   git commit -a
   
移除文件
     git rm
     git rm --cached
重命名文件
  git mv  
      相当于执行以下三部操作
            mv ll.js ll.txt
            git rm 11.js
            git add 11.txt

查看提交历史
  git log
  
    $ git log -p -2  一个常用的选项是 -p，用来显示每次提交的内容差异 也可以加上 -2 来仅显示最近两次提交
    git log --since=2.weeks    显示最近两周提交
    如果你想看到每次提交的简略的统计信息 git log --stat
    
-p

按补丁格式显示每个更新之间的差异。

--stat

显示每次更新的文件修改统计信息。

--shortstat

只显示 --stat 中最后的行数修改添加移除统计。

--name-only

仅在提交信息后显示已修改的文件清单。

--name-status

显示新增、修改、删除的文件清单。

--abbrev-commit

仅显示 SHA-1 的前几个字符，而非所有的 40 个字符。

--relative-date

使用较短的相对时间显示（比如，“2 weeks ago”）。

--graph

显示 ASCII 图形表示的分支合并历史。

--pretty

使用其他格式显示历史提交信息。可用的选项包括 oneline，short，full，fuller 和 format（后跟指定格式）。
    
取消暂存的文件
    git reset HEAD CONTRIBUTING.md
    
撤消对文件的修改
    git checkout 
《！------------------------------------------------------------------------------》
查看远程仓库
     git remote
     git remote -v  会显示需要读写远程仓库使用的 Git 保存的简写与其对应的 URL
添加远程仓库
    git remote add <shortname> <url>
    
从远程仓库中抓取与拉取
     git fetch [remote-name]
     
推送到远程仓库 
    git push origin master  
    
查看远程仓库
    git remote show origin  
    
远程仓库的移除与重命名
    重命名git remote rename one two
    
    移除git remote rm two
    
创建标签
    -附注标签  ||  Git 中创建一个附注标签是很简单的。 最简单的方式是当你在运行 tag 命令时指定 -a 选项     git tag -a v1.4 -m 'my version 1.4'  
     git show 命令可以看到标签信息与对应的提交信息
    -轻量标签  创建轻量标签，不需要使用 -a、-s 或 -m 选项，只需要提供标签名字 
    
    -后期打标签  git tag -a v -name
    
    -共享标签     git push origin [tagname]
    
    -把所有不在远程仓库服务器上的标签全部提交    git push origin --tags
    
    -检出标签  git checkout -b [branchname] [tagname]   
    《!---------------------------------------------------》
    

分支创建
    git branch test
分支切换
    git checkout test
删除分支
    git branch -d ***
分支的合并
    git merge <branchName>
分支的合并冲突
    git mergetool
分支管理
    如果要查看哪些分支已经合并到当前分支，可以运行 git branch --merged
    查看所有包含未合并工作的分支，可以运行 git branch --no-merged
    
远程分支
    git ls-remote (remote)
  
  
分支 - 变基 
    

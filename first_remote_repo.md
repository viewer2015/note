#在本地的note仓库下运行命令
本地关联远程库;远程库的名字就是origin，这是Git默认的叫法，也可以改成别的，但是origin这个名字一看就知道是远程库
```
git remote add origin git@github.com:viewer2015/note.git
```

#把本地库的所有内容推送到远程库上
把本地库的内容推送到远程，用git push命令，实际上是把当前分支master推送到远程。

由于远程库是空的，我们第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。


```
$ git push -u origin master
Counting objects: 19, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (19/19), done.
Writing objects: 100% (19/19), 13.73 KiB, done.
Total 23 (delta 6), reused 0 (delta 0)
To git@github.com:michaelliao/learngit.git
 * [new branch]      master -> master
Branch master set up to track remote branch master from origin.
```
推送成功后，可以立刻在GitHub页面中看到远程库的内容已经和本地一模一样：

#从现在起，只要本地作了提交，就可以通过命令：
```
$ git push origin master
```

#pull file from origin
```
git pull origin  master
```
#problem
when I first use the command, I met the problem
```
➜  note git:(master) git push -u origin master
To github.com:viewer2015/note.git
 ! [rejected]        master -> master (fetch first)
error: failed to push some refs to 'git@github.com:viewer2015/note.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```
出现错误的主要原因是github中的README.md文件不在本地代码目录中
可以通过如下命令进行代码合并【注：`pull=fetch+merge`]
```
git pull --rebase origin master
```

and there is another porblem, I write this with grammer markdown,but when I pull this file to github,
it did not deal this with a markdown file.why? 
because the file which end .md is treate as markdown
```
#在本地的note仓库下运行命令
本地关联远程库;远程库的名字就是origin，这是Git默认的叫法，也可以改成别的，但是origin这个名字一看就知道是远程库
```
git remote add origin git@github.com:viewer2015/note.git
```

#把本地库的所有内容推送到远程库上
把本地库的内容推送到远程，用git push命令，实际上是把当前分支master推送到远程。

由于远程库是空的，我们第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。
....
```

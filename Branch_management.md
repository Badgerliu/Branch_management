# Branch

![learn-branches](Branch_management.assets/0-20191030161753349.png)





## Create and merge branches

![git-br-initial](Branch_management.assets/0-20191030161858961.png)





![git-br-create](Branch_management.assets/0-20191030161907264.png)



```git
git checkout -b dev

or $ git branch dev
$ git checkout dev
```

![git-br-dev-fd](Branch_management.assets/0-20191030161914441.png)

```
$ git checkout master
$ git switch master #better than the previous one
```

![git-br-ff-merge](Branch_management.assets/0-20191030161920956.png)

```
git merge dev
```

![git-br-rm](Branch_management.assets/0-20191030161930678.png)

```
git branch -d dev
```



我们注意到切换分支使用`git checkout <branch>`，而前面讲过的撤销修改则是`git checkout -- <file>`，同一个命令，有两种作用，确实有点令人迷惑。

实际上，切换分支这个动作，用`switch`更科学。因此，最新版本的Git提供了新的`git switch`命令来切换分支：

创建并切换到新的`dev`分支，可以使用：

```
$ git switch -c dev
```





查看分支：`git branch`

创建分支：`git branch <name>`

切换分支：`git checkout <name>`或者`git switch <name>`

创建+切换分支：`git checkout -b <name>`或者`git switch -c <name>`

合并某分支到当前分支：`git merge <name>`

删除分支：`git branch -d <name>`



#### debug with remote existence



Huans-MacBook-Air:Branch_management liuhuan$ git status

On branch dev

Changes not staged for commit:

  (use "git add <file>..." to update what will be committed)

  (use "git checkout -- <file>..." to discard changes in working directory)



​	modified:   Branch_management.md



no changes added to commit (use "git add" and/or "git commit -a")

Huans-MacBook-Air:Branch_management liuhuan$ git add Branch_management.md

Huans-MacBook-Air:Branch_management liuhuan$ ls

Branch_management.assets	readme.txt

Branch_management.md

Huans-MacBook-Air:Branch_management liuhuan$ git commit -m 'finialized'

[dev 19642f5] finialized

 1 file changed, 42 insertions(+), 1 deletion(-)

Huans-MacBook-Air:Branch_management liuhuan$ git status

On branch dev

nothing to commit, working tree clean

Huans-MacBook-Air:Branch_management liuhuan$ git remote add origin git@github.com:Badgerliu/Branch_management.git

fatal: remote origin already exists.

Huans-MacBook-Air:Branch_management liuhuan$ git remot rm origin

git: 'remot' is not a git command. See 'git --help'.



The most similar command is

​	remote

Huans-MacBook-Air:Branch_management liuhuan$ git remote rm origin 

Huans-MacBook-Air:Branch_management liuhuan$ git remote add origin git@github.com:Badgerliu/Branch_management.git

Huans-MacBook-Air:Branch_management liuhuan$ git push -u origin master

error: src refspec master does not match any.

error: failed to push some refs to 'git@github.com:Badgerliu/Branch_management.git'

Huans-MacBook-Air:Branch_management liuhuan$ git push -u origin dev   

Warning: Permanently added the RSA host key for IP address '52.74.223.119' to the list of known hosts.

Enumerating objects: 14, done.

Counting objects: 100% (14/14), done.

Delta compression using up to 4 threads

Compressing objects: 100% (13/13), done.

Writing objects: 100% (14/14), 43.70 KiB | 8.74 MiB/s, done.

Total 14 (delta 1), reused 0 (delta 0)

remote: Resolving deltas: 100% (1/1), done.

To github.com:Badgerliu/Branch_management.git

 \* [new branch]      dev -> dev

Branch 'dev' set up to track remote branch 'dev' from 'origin'.
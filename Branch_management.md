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
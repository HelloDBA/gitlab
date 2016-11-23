# gitlab

# git pull 和 git fetch 的区别

git clone 一个新项目（里面只有一个readme.md，建立项目时自动增加）观察本地 .git/refs/heads/master与 .git\refs\remotes\origin\master 最新版本号变化

1. git clone 不做任何操作（为了测试，clone了两个本地库A\B）

```
$ cat refs/heads/master
01ed31d989693b92664161f16944b4ac2f5fbb12

$ cat refs/remotes/origin/master
cat: refs/remotes/origin/master: No such file or directory

```

2. A库进行一次git commit 并 push 到远程库

```
$ cat refs/heads/master
db39bda75ddb5e8c8b594e4a170167d95d6d3e41

$ cat refs/remotes/origin/master
db39bda75ddb5e8c8b594e4a170167d95d6d3e41

```

3. B库执行 git fetch 观察库最新版本变化

```
$ cat refs/heads/master
01ed31d989693b92664161f16944b4ac2f5fbb12

$ cat refs/remotes/origin/master
db39bda75ddb5e8c8b594e4a170167d95d6d3e41

$ cat refs/FETCH_HEAD
db39bda75ddb5e8c8b594e4a170167d95d6d3e41		branch 'master' of github.com:HelloDBA/gitlab

```
git fetch 只是更新了本地库关联的远程库的最新版本指向，本地库文件版本并没有变化

*   git fetch：这将更新git remote中所有的远程repo所包含分支的最新commit-id, 将其记录到.git/FETCH_HEAD文件中
*   git fetch remote_repo：这将更新名称为remote_repo 的远程repo上的所有branch的最新commit-id，将其记录 
*   git fetch remote_repo remote_branch_name：这将这将更新名称为remote_repo 的远程repo上的分支： remote_branch_name
*   git fetch remote_repo remote_branch_name:local_branch_name：这将这将更新名称为remote_repo 的远程repo上的分支： remote_branch_name ，并在本地创建local_branch_name 本地分支保存远端分支的所有数据。

4. B库执行 git commit 观察最新版本变化

```


```


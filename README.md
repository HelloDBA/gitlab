# gitlab

# git pull 和 git fetch 的区别

## git clone 一个新项目（里面只有一个readme.md，建立项目时自动增加）观察本地 .git/refs/heads/master与 .git\refs\remotes\origin\master 最新版本号变化

1. git clone 不做任何操作

```
$ cat refs/heads/master
01ed31d989693b92664161f16944b4ac2f5fbb12

$ cat refs/remotes/origin/master
cat: refs/remotes/origin/master: No such file or directory

```

2. 本地进行一次git commit 

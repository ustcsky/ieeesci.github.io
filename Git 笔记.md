# Git 的基本流程如下：

1、创建或修改文件

2、使用 `git add` 命令添加新创建或修改的文件到本地的缓存区（Index）

3、使用 `git commit` 命令提交到本地代码库

4、（可选，有的时候并没有可以同步的远端代码库）使用`git push`命令将本地代码库同步到远端代码库

[Git 实战教程](https://www.shiyanlou.com/courses/4)

[Github 快速上手实战教程](https://www.shiyanlou.com/courses/868)

# 命令

**git config**：配置相关信息 

**git clone**：复制仓库 

**git init**：初始化仓库 

**git add**：添加更新内容到索引中 。

使用 `git add` 命令将新建的文件添加到缓存区，为 `commit` 做好准备。

再次执行 `git status` 就会发现新的变化。

可以使用 `git diff` 命令再加上 `--cached` 参数，看看缓存区中哪些文件被修改了。如果没有`--cached`参数，`git diff` 会显示当前你所有已做的但没有加入到缓存区里的修改。

**git diff**：比较内容 

**git status**：获取当前项目状况。使用 `git status` 命令查看当前 Git 仓库的状态

**git commit**：使用 `git commit` 提交修改 

当所有新建，修改的文件都被添加到了缓存区，我们就要使用 `git commit` 提交到本地仓库：

```shell
$ git commit -m "add 3 files"
```

需要使用 `-m` 添加本次修改的注释，完成后就会记录一个新的项目版本。除了用 `git add` 命令，我们还可以用下面的 `-a` 参数将所有没有加到缓存区的修改也一起提交，但 `-a` 命令不会添加新建的文件。

```shell
$ git commit -a -m "add 3 files"
```

再次输入 `git status` 查看状态，会发现当前的代码库已经没有待提交的文件了，缓存区已经被清空。

**git branch**：分支相关

**git checkout**：切换分支

**git merge**：合并分支

**git reset**：恢复版本

**git log**：查看日志 。`git log` 命令可以显示所有的提交（commit）

**git push**：将修改推到一个公共仓库。

通过 http 或是 git 协议，其它维护者可以通过远程访问的方式抓取（fetch）你最近的修改，但是他们没有写权限。如何将本地私有仓库的最近修改主动上传到公共仓库中呢？

最简单的办法就是用 `git push` 命令，推送本地的修改到远程 Git 仓库，执行下面的命令:

```shell
$ git push ssh://服务器仓库地址 master:master
```

或者：

```shell
$ git push ssh://服务器仓库地址 master
```

`git push` 命令的目地仓库可以是 `ssh` 或 `http/https` 协议访问。




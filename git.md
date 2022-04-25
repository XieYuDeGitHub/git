# Git命令

设置用户签名

```git
git config --global user.name <用户名>
git config --global user.email <邮箱>
```



## 创建仓库

在当前目录初始化一个仓库

```git
git init
```



克隆远程仓库

```git
git clone [url]
```





## 提交与修改

## git add

添加一个或多个文件到暂存区

```git
git add [file] [file]...
```



添加指定目录到暂存区

```git
git add [dir]
```



添加当前目录下的所有文件到暂存区

```git
git add .
```



## git status

查看仓库状态，显示有变更的文件

```git
git status
```





## git diff

git diff 命令比较文件的不同，即比较文件在暂存区和工作区的差异。

git diff 命令显示已写入暂存区和已经被修改但尚未写入暂存区文件的区别。

git diff 有两个主要的应用场景。

- 尚未缓存的改动：**git diff**
- 查看已缓存的改动： **git diff --cached**
- 查看已缓存的与未缓存的所有改动：**git diff HEAD**
- 显示摘要而非整个 diff：**git diff --stat**

显示暂存区和工作区的差异:

```git
git diff [file]
```

显示暂存区和上一次提交(commit)的差异:

```git
git diff --cached [file]
或
git diff --staged [file]
```

显示两次提交之间的差异:

```git
git diff [first-branch]...[second-branch]
```





## git commit

`git commit`命令将暂存区内容添加到本地仓库



将暂存区内的文件全部提交到仓库

```git
git commit -m [message]
```

[message]可以是备注信息



提交暂存区的指定文件到仓库

```git
git commit [file] [file]... -m [message]
```



直接提交到仓库

```git
git commit -a
```





## git reset

git reset用于回退版本，可以指定退回某一次提交的版本

语法格式

```git
git reset [--soft | --mixed | --hard] [HEAD]
```



**--mixed** 为默认，可以不用带该参数，用于重置暂存区的文件与上一次的提交(commit)保持一致，工作区文件内容保持不变。

```git
git reset [HEAD]
```

```git
git reset HEAD^            # 回退所有内容到上一个版本  
git reset HEAD^ hello.php  # 回退 hello.php 文件的版本到上一个版本  
git  reset  052e           # 回退到指定版本
```



**-soft** 参数用于回退到某个版本：

```git
git reset --soft HEAD
```



**--hard** 参数撤销工作区中所有未提交的修改内容，将暂存区与工作区都回到上一次版本，并删除之前的所有信息提交：

```git
git reset --hard HEAD
```





## git rm

将文件从暂存区和工作区中删除

```git
git rm <file>
```



如果删除之前修改过并且已经放到暂存区域的话，则必须要用强制删除选项 **-f**。

```git
git rm -f <file>
```



如果想把文件从暂存区域移除，但仍然希望保留在当前工作目录中，换句话说，仅是从跟踪清单中删除，使用 **--cached** 选项即可：

```git
git rm --cached <file>
```





## git mv

git mv 命令用于移动或重命名一个文件、目录或软连接。

```git
git mv [file] [newfile]
```



如果新文件名已经存在，但还是要重命名它，可以使用 **-f** 参数：

```git
git mv -f [file] [newfile]
```





## 提交日志

### git log

语法格式（常用）

```git
git log [--oneline | --graph | --reverse | --author]
```

--oneline：查看历史记录的简洁的版本

--graph：查看历史中什么时候出现分支、合并

--reverse：逆向显示所有日志

--author：查看指定用户的提交日志

```git
git log --authro=<user>
```



### git blame

查看指定文件的修改记录

```git
git blame <file>
```



## 远程操作

### git remote

显示所有远程仓库

```git
git remote -v
```



显示某个远程库的信息

```git
git remote show [remote]
```



添加远程版本库：

```git
git remote add [shortname] [url]
```

shortname 为本地的版本库，例如：

```git
# 提交到 Github
$ git remote add origin git@github.com:tianqixin/runoob-git-test.git
$ git push -u origin master
```



删除远程仓库

```git
git remote rm <仓库链接 | 别名>
```



修改仓库名

```git
git remote rename <old_name> <new_name>
```


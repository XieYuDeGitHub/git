# Git命令



# 设置用户签名

```git
git config --global user.name <用户名>
git config --global user.email <邮箱>
```





## 添加到暂存区

**git add** 命令可将该文件添加到暂存区



添加一个或多个文件到暂存区

```git
git add [file_name] [file_name]...
```



添加指定文件夹到暂存区，包括子目录

```git
git add [dir_name]
```



添加当前目录到暂存区

```git
git add .
```





## 初始化本地库

```git
git init
```





## 查看本地库状态

```git
git status
```



## 查看日志

查看日志

```git
git reflog
```

```git
git log
```





## 版本穿梭

```git
git reset --hard <版本号>
```





## 分支相关

创建分支

```git
git branch <分支名>
```



查看分支

```git
git branch -v
```



切换分支

```git
git checkout <分支>
```



合并分支（将指定分支合并到当前分支）

```git
git merge <分支>
```





## 远程库相关

查看远程库

```git
git remote -v
```



为远程库添加别名

```git
git remote add <别名> <远程地址>
```



推送当前分支到远程库

```git
git push <别名>|<远程地址> <分支>
```



克隆远程库

```git
git clone <远程库地址>
```



拉去远程库指定分支最新的代码（会与本地分支合并）

```git
git pull <远程库地址>|<别名> <分支>
```


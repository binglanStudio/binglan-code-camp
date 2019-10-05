# Git学习笔记

## 1.Git是什么

Git是一个开源的分布式版本控制系统，可以有效、高速地处理从很小到非常大的项目版本管理。

## 2. 相关概念

- 仓库：存放代码，文档等文件的目录
	- 本地仓库
	- 远程仓库
	可以通过 git remote add 建立关联
- 工作区 (Working Directory): 编辑代码修改内容的地方
- 暂存区 (Stage or Index): 数据暂时存放的区域，可以在工作区和版本库之间进行转换
- 版本库 (Commit History): 存放已经提交的数据，push 的时候就是把这个区域的数据推送到远程仓库

![Git生命周期](https://img-blog.csdnimg.cn/20191005183511526.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ1NjkzNTg3,size_16,color_FFFFFF,t_70)

## 3.Git基本操作

```shell
git init # 在当前目录下初始化一个本地 git 仓库
git status # 检查当前文件状态
git add <filename> # 将 <filename> 添加到暂存区
git add -A # 将所有文件添加到暂存区
git add . # 将当前目录下的所有文件添加到暂存区
git commit # 提交更改（将暂存区的文件提交到 Commit History）
git commit -m <message> # 修改 commit 信息
git clone <repository> [<directory>] # 克隆远程分支到本地，repository 可以由 schema 为 http[s], ssh, git, ftp[s], file 等各种 uri 表示，也可以是 scp 风格的路径表示。directory 表示克隆下来的仓库目录名
git config [--global|--local] user.name "<username>" # 设置用户名，用户名会出现在 commit 信息里，加了--local参数只影响当前仓库的配置，加--global参数会影响本机上所有仓库的配置，默认是--local
git config [--global|--local] user.email "<email>" # 设置用户邮箱，邮箱会出现在 commit 信息里
git remote add origin <repository> # 添加一个远程分支，命名为 origin
git log [--oneline] # 查看 commit 信息
git log --oneline --graph # 查看 commit 节点树
```

## 4.Git实践操作

![具体如何操作实操流程](https://img-blog.csdnimg.cn/20191005212837836.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ1NjkzNTg3,size_16,color_FFFFFF,t_70)

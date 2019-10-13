## 对Git的认识
 1. Git是目前一款分布式版本控制系统。
 2. Git是免费、开源的。
 3. 官网： https://git-scm.com/

## 下载及配置Git

 1. 官网下载，选项默认安装即可
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191013105024509.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3ZlZ2FzbGlhcg==,size_16,color_FFFFFF,t_70)
 2. Git的本地配置及相关指令
右键 git bush,在弹出的命令框中执行一下语句
 git config --global user.name "#用户名"
 git config --global user.email #用户邮箱
git config -global -list        查看详细环境配置
## 部分基础执行语句
从远程主机克隆一个版本库:
 git clone <版本库的网址> 
取回远程主机某个分支的更新，再与本地的指定分支合并：
git pull <远程主机名> <远程分支名>:<本地分支名> 
列出所有分支（含本地及远程）：
git branch -a
新建一个分支，并停留在当前分支：
 git branch [branch-name]
新建一个分支，并切换到该分支：
 git checkout -b [branch]
新建一个分支，指向指定commit：
 git branch [branch] [commit]
 切换到指定分支，并更新工作区：
  git checkout [branch-name]
合并指定分支到当前分支： 
git merge [branch]
删除分支：
git branch -d [branch-name]
将文件修改添加到暂存区：
git add <file>

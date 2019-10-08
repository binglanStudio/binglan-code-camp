# 一、 使用Git的前期工作
不仅仅是Git，想要使用任何软件，都需要一些前期准备，否则，很容易事倍功半，并且耗费时间，前期工作并不是特别简单，毕竟再怎么说也是万事开头难。
## 1、Git的下载与安装
 在[git官网](https://git-scm.com/)找到适合自己的版本，下载，并进行安装，git有多个版本，可以在Windows，Linux，等等，在这里，我使用的是Windows版本。
进入安装界面后，按默认选项即可，安装完成后，在自己所安装的位置找到“Git”->“Git Bash”，蹦出一个类似命令行窗口的东西，就说明Git安装成功！
## 2、Git使用之前配置
当你安装完Git后首先要做的事情是设置你的用户名称和e-mail地址。这是非常重要的，因为若是想使用Git提交，首先需要自报家门。命令语句：
 git config --global user.name yanyuhang #你的名称
 git config --global user.email youname@example.com   #你的邮箱

还可以使用
git config -l 查看详细环境配置项。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191007230235155.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2hpYWhpYWhpYTIzMzM=,size_16,color_FFFFFF,t_70)
## 3、Github
如果你想更加方便的使用Git，一个GitHub的账号是必不可少的，远程库可以帮助一个团队之间的合作，使合作效率更加快速，并且这个账户是免费的，直接进入[git官网](https://git-scm.com/)注册就行了。
# 二、Git克隆文件到本地
1. 输入命令ssh-keygen -t rsa -C "your_email@youremail.com"   
2. 显示路径，我们在路径中可以找到公钥文件，用记事本打开复制里面的内容到github中的ssh and gpg keys里面
3. 过程:点击头像/settings/左边列表,双击进入ssh keys,复制进去即可,最后形成如下形式:
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191007230448564.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2hpYWhpYWhpYTIzMzM=,size_16,color_FFFFFF,t_70)


# 三、Git分支创建与切换
## Git分支基础知识
分支这个词原本表示指从总体或一个系统中分出的部分，但在Git里面，原本的意思无法很好的表示Git分支的意思，Git的分支更像是主支的镜像，就像我在进行某种实验，当我可以同时进行两个相同的实验，但是在某个步骤时，我发现这个实验可以有一些其他的选择，于是我的两个实验便走向了不同方向，当我实验完成之后，我就可以把实验结果合并，double happiness，既使某个方向的实验出问题，我也可以再次分出分支，进行其他方向的实验，Git的分支比这个奇怪的实验更加高效，它将这个实验快进了，而且复制出一个镜像实验只需要git branch branch-name（创建一个分支）这么一个语句，用这个实验做比喻可能还是无法阐述完整，需要在Git的学习与使用中慢慢体会。
## 基本分支操作语句
使用上述新建分支语句列所有本地分支：git branch

列出所有远程分支：git branch -r

列出所有本地分支和远程分支：git branch -a

新建一个分支，但依然停留在当前分支：
git branch [branch-name]

新建一个分支，并切换到该分支：
git checkout -b [branch]

新建一个分支，指向指定commit：
git branch [branch] [commit]

新建一个分支，与指定的远程分支建立追踪关系：
git branch --track [branch] [remote-branch]

切换到指定分支，并更新工作区：
git checkout [branch-name]

切换到上一个分支：git checkout -

建立追踪关系，在现有分支与指定的远程分支之间：
git branch --set-upstream [branch] [remote-branch]

合并指定分支到当前分支：
git merge [branch]

选择一个commit，合并进当前分支：git cherry-pick [commit]

删除分支：git branch -d [branch-name]

删除远程分支：
git push origin --delete [branch-name]
git branch -dr [remote/branch]

可以使用上述的新建与切换语句创建或者切换分支。![在这里插入图片描述](https://img-blog.csdnimg.cn/2019100723075411.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2hpYWhpYWhpYTIzMzM=,size_16,color_FFFFFF,t_70)
# 四、学习感想
初学时总是会觉得比较难，还是老话，万事开头难。写这篇博客的我只是一只菜鸟，也遇到不少问题，比方说将远程库克隆到本地，就卡住我了一会，克隆一直失败，我通过网上查资料才知道前期准备没有做好，没有创建生成SSH key；解决问题的过程远比结果更重要，拥有解决问题的思维，才有了通往答案的万能钥匙。

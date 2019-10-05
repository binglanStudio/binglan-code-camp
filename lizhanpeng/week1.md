# 1.GIT的学习笔记
## 1.配置所有仓库的用户名和Email地址
下载安装好Git后，打开Git bash，利用`git config --global user.name "your name"`和`git config --global user.email "Your email"`来配置所有仓库的用户名和email地址，配置完后，可以用`git config --global --list`查看是否配置成功.

## 2.创建一个仓库
选择合适的位置打开Git bash使用`git init 仓库名`来新建一个仓库，此时仓库里面会生成一个隐藏的`.git`目录。

## 3.把文件添加到仓库并提交
使用`cd 仓库名`进入到仓库目录，将文件拷贝到仓库后，利用`git add 文件名`来添加文件，添加后可使用`git status`查看状态，最后使用`git commit`将文件提交。ps（`git add`是把文件从工作区提交到暂存区，`git commit`是把文件从暂存区提交到版本库）

## 4.将本地仓库和github仓库进行同步
首先创建SSH Key：在git bash中使用指令ssh-keygen -t rsa -C "youremail@example.com"，创建后，找到创建的id_rsa.pub文件，将其内容复制到github账户里的ssh key这一块里面，添加后再使用`git remote add origin git@github.com:用户名/仓库名.git`指令来吧本地仓库与github上的仓库进行关联，关联成功后就可以使用` git push -u origin master`命令对本地仓库内容进行推送同步了。

## 5.git clone和pull requests
在github里面fork别人的仓库，然后再到本地仓库使用`git clone git@github.com:用户名/仓库名.git`指令对github的仓库进行克隆出一个本地的仓库，在本地对克隆的仓库文件进行修改并同步到github后，可通过`pull request`对原仓库作者进行拉取请求，如果原仓库作者接受拉取请求的话，你的修改内容就会合并到他的项目之中。

## 6.在仓库本地切一个分支，并在这个分支进行修改
使用`git switch -c 分支名`来切换分支，也可以使用`git checkout -b 分支名`来切分支，切换分支后，可以用`git branch`来查看当前分支，分支的工作完成后，就可以用` git switch master`指令切换回主分支，再利用`git merge 分支名`将分支的工作成果合并到主分支上，合并完成后就可以删掉副分支了。

# 2学习中遇到的问题及解决方法
在git push这一块中，出现了push失败的情况，上面显示`git@github.com: Permission denied (publickey)`，百度到的解决办法是 给文件起名字的时候使用 ‘ id_rsa ’ 这个名字，之后再用` ssh -T git@github.com`指令查看是否成功，试过之后出现了`Hi Patarw! You've successfully authenticated, but GitHub does not provide shell access.`
终于解决了这个问题。


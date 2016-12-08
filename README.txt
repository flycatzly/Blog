如何用git将项目代码上传到github http://blog.csdn.net/laozitianxia/article/details/50682100

配置Git

1）选择本地磁盘一个位置本地仓库建立 在本地仓库里右键选择Git Init Here，会多出来一个.git文件夹，这就表示本地git创建成功。 右键Git Bash进入git命令行 $ git init

2）在本地创建ssh key $ ssh-keygen -t rsa -C "your_email@youremail.com"

然后我们进入提示的地址下查看ssh key文件。 打开id_rsa.pub，复制里面的key。里面的key是一对看不懂的字符数字组合，不用管它，直接复制。 回到github网站，进入Account Settings，左边选择SSH Keys，Add SSH Key,

title随便填，粘贴key。

3）验证是否成功，在git bash下输入 $ ssh -T git@github.com

回车就会看到： You’ve successfully authenticated, but GitHub does not provide shell access 这就表示已成功连上github。

4）接下来我们要做的就是把本地仓库传到github上去，在此之前还需要设置username和email，因为github每次commit都会记录他们 $ git config --global user.name "your name" $ git config --global user.email "your_email@youremail.com"

提交上传

1）接下来在本地仓库里添加一些文件，比如README

在本地新建一个README文件，然后在命令行输入一下命令 $ git add README $ git commit -m "first commit"

2）上传到github $ git push origin master

git push命令会将本地仓库推送到远程服务器。 git pull命令则相反。

注：首次提交，先git pull下，修改完代码后，使用git status可以查看文件的差别，使用git add 添加要commit的文件。
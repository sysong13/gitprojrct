1.初始化仓库 git init
2.添加各种文件 例如 readme.txt
3.提交文件，分为两步：
	1） 添加需要被提交的文件 git add readme.txt  （可添加多个）
	2） 提交文件 git commit -m "description"  
4.查看当前状态 git status 会显示修改记录/待提交等等
5.每次提交相当于更新版本，版本之间可以回退和前进：
	1）HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令git reset --hard commit_id。

	2）穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。

	3）要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。
6.工作区和暂存区
	1）修改但尚未add的部分存在于工作区（working directory）,处于这一阶段时，想要撤回修改，可以使用 git checkout --file 
	2）修改并已经add的部分在 暂存区（stage）， 处于这一阶段时，想要撤回修改，
使用git reset HEAD <file> 回到工作区，再次 git checkout --file
	3)commit之后可以使用5中的版本回退方法

7.添加远程仓库
	1）生成当前PC的SSH密钥 ssh-keygen -t rsa -C "youremail@example.com"
	2）打开/.ssh/id_rsa.pub
	3) 在github仓库中打开账户setting，添加SSH KEY，将上面的密钥复制进去
	4）将本地仓库与github仓库同步，在本地文件夹中输入
		  git remote add origin git@github.com:sysong13/gitprojrct.git  
	5）将本地库的所有内容推送到远程库：
		  git push -u origin master
	6）今后提交作业通过命令：
		  git push origin master

8.创建分支
	1）创建分支 git branch dev
	2) 切换到dev分支 git checkout dev  (1和2可以用一条命令代替： git checkout -b dev)
	3) 查看当前分支  git branch
9.合并分支
	1）在dev分支修改内容后，提交修改
	2）切回master分支  git checkout master
	3）合并dev分支 git merge dev
	4) 删除dev分支 git branch -d dev
如果需要提交本地分支到远程分支，git push origin dev

10.多人合作
	小王：
	1）git clone项目到本地
	2）此时只能看到master分支，创建新的分支 git checkout -b dev
	3) 提交修改到远程origin dev分支

	小红：
	1）在本地创建dev分支，并设置跟踪origin  git checkout -b dev origin/dev
	2）获取origin/dev的更新 git pull


	

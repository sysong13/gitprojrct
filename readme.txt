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

	

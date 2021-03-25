初始号仓库：git init 

查看仓库文件状态：git status

将文件添加到暂存区：git add 文件名  //添加到暂存区会变绿 (使用git status查看)
		 git add . 	         //所有文件添加到暂存区
添加到暂存区后悔了撤回(commit提交前生效):git  reset 文件名

提交文件 		  git commit -m 描述名字  //m是message意思 
提交后悔了，想要本地返回指定版本():git  reset commitID值 --hard (不写--hard不会改变)

查看日志(谁,什么时间提交了什么)		  git log

查看所有所有操作记录：git reflog

注意：红色文件代表有新的变更

git是对比仓库和现有文件差异

alias 自定义
-----------------------------------------------
#reset 三种模式
###hard:不保存所有变更(选择提交的版本，拉到工作区，删除最后一次提交)	
总结：commit到你指定版本，文件也会改变
###soft:保留变更且变更内容处于暂存区（不保留自己提交的版本，写别的也是当前自己）
总结：commit到你指定的版本，后面都删除，本地文件不会变化
###mixed：包留变更内容处于当前工作区也就是本地(默认) 

git reset –-soft：回退到某个版本，只回退了commit的信息，不会恢复到index file一级。如果还要提交，直接commit即可；
git reset -–hard：彻底回退到某个版本，本地的源码也会变为上一个版本的内容，撤销的commit中所包含的更改被冲掉；
-----------------------------------------------
branch(分支
查看分支：git branch
创建新分支：git checkout -b <name><template> 
//<template> 哪个分支为模板，不写就是当前
切换分支：git checkout 分支名
------------------------------
合并分支(慎用)
git merge 分支名
出现冲突：手动保留等等

-----------------------
远程仓库
克隆远程仓库 git clone url 

查看远程分支 git branch -a

远程如果没有则 git push --set-upstream orgin 分支名

orgin远程仓库
set-upstream新分支
set-upstream orgin设置上流分支

将远程分支与本地联系起来git checkout -b 分支名 origin/分支名

git push 推送
git fetch 拉取（可以修改远程）
相当于是从远程获取最新版本到本地，不会自动merge
git pull 拉取(无法对远程跟踪)
相当于fetch+merge（合并）
------------
创建分支和远程联系流程
git remote add origin https://github.com/Jin676/test_324.git

远程创建分支
git branch -M main
git push -u origin main

查看分支

	$ git branch

	结果（带*表示当前所在的分支）：

	* dev 
	  master

	


显示目录

`ls` 

查看状态

`$ git status`

加入暂存区

`$ git add 文件名.后缀`

删除

`$ rm 文件名.后缀`

提交版本库

`$ git commit -m "提交的描述信息"`


推送到远程仓库

`$ git push origin master `


	创建并切换分支dev

	$ git checkout -b dev

	或者写作以下两句：

	$ git branch dev 

	$ git checkout dev  




合并dev分支

`$ git merge dev`

删除分支

`$ git branch -d dev`



> 查看分支：git branch



>创建分支：git branch name



> 切换分支：git checkout name



> 创建+切换分支：git checkout -b name



> 合并某分支到当前分支：git merge name



> 删除分支：git branch -d name



---
#流程
1.用cd命令切换到当前目录

2.运行git init

3.在gitHub创建仓库，取个名字（不一定要与本地相同），之后复制其生成的SSH key
	
	例如：
	 
	git@github.com:mixinan/shareApk.git

4.运行 git remote add origin git@github.com:mixinan/shareApk.git

5.添加所有文件到暂存区，运行（注意最后的“.”，表示所有）：git add .

6.提交，运行：git commit -m"版本描述"

7.推送到远程仓库，运行：git push -u origin master
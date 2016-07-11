#流程

首先去[百度云链接](http://pan.baidu.com/s/1skFLrMt#path=%252Fpub%252Fgit)下载可执行文件，安装到电脑上。

再按以下流程操作。它是我根据[别人写的教程](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/00137396287703354d8c6c01c904c7d9ff056ae23da865a000)精简的。

---


1. 用cd命令切换到当前目录，比如：cd E:/software/day01

2. 运行git init


3. 创建SSH Key
	
	在用户主目录下，看看有没有.ssh目录，如果有，再看看这个目录下有没有id_rsa和id_rsa.pub这两个文件，如果有，可直接跳到下一步。如果没有，运行：	$ ssh-keygen -t rsa -C "你的邮箱"

	然后一路回车，使用默认值即可。

	如果一切顺利的话，可以在用户主目录里找到.ssh目录，里面有id_rsa和id_rsa.pub两个文件，这两个就是SSH Key的秘钥对，id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人。


	登陆GitHub，打开“Account settings”，“SSH Keys”页面：

	然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容：


	点“Add Key”，你就应该看到已经添加的Key。






4. 在gitHub创建仓库，取个名字（不一定要与本地相同），之后复制其生成的SSH key
	
	例如：
	 
	git@github.com:mixinan/shareApk.git

5. 运行 git remote add origin git@github.com:mixinan/shareApk.git

6. 添加所有文件到暂存区，运行（注意最后的“.”，表示所有）：git add .
 
7. 提交，运行：git commit -m"版本描述"

8. 推送到远程仓库，运行：git push -u origin master




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


查看分支

	$ git branch

	结果（带*表示当前所在的分支）：

	* dev 
	  master

	


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

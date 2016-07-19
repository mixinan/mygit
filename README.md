#流程

首先去 [百度云链接](http://pan.baidu.com/s/1skFLrMt#path=%252Fpub%252Fgit) 下载可执行文件，安装到你的电脑上。

再按以下流程操作。它是我根据 [别人写的教程](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/00137396287703354d8c6c01c904c7d9ff056ae23da865a000) 精简的。

---


1. 打开Git Bash，也就是刚刚安装的软件。用cd 命令切换到你要上传至GitHub的文件夹，比如：
	
	>cd E:/software/day01

	>指的是：切换到E盘software文件夹里的day01文件夹


2. 输入命令：
	>git init

	>该文件夹下会生成一个.git的隐藏文件


3. 创建SSH Key
	
	>在用户主目录下（比如 C:\Users\你的用户名），看看有没有.ssh 目录，如果有，看看该目录下有没有id_rsa 和id_rsa.pub 这两个文件，如果有，可直接跳到下一步。如果没有，运行：	
	
	$ ssh-keygen -t rsa -C "你的邮箱"

	>然后一路回车，使用默认值即可。如果顺利，可以在用户主目录里找到.ssh 目录，里面有id_rsa 和id_rsa.pub 两个文件，它们是SSH Key 的秘钥对，id_rsa 是私钥，id_rsa.pub 是公钥。


	登陆GitHub，打开“Account settings”，“SSH Keys”页面，然后点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub 文件的内容，点“Add Key”，之后可看到已添加的Key。


4. 顺便接着上一步，在GitHub 创建一个空仓库（取名不一定要与本地相同），在空仓库的页面上找到并复制这行代码： 
 
    >git remote add origin git@github.com:xxx/xxx.git


5. 在Git 命令行窗口运行它


6. 为了防止提交内容以后，小方块不变绿（绿块越多，表示提交代码越频繁，有装X功能），配置邮箱和名字，分别运行：

    >git config user.email "你的邮箱
    
    >git config user.name "你的名字"
    
    如果还是不变绿，参考: [不变绿](http://blog.csdn.net/elloop/article/details/50564858)


7. 添加本地所有文件到暂存区，运行（注意最后的“.”，表示所有）：
	>git add .
 

8. 提交，运行：
	>git commit -m "版本描述"


9. 推送到远程仓库，运行：
	>git push -u origin master
	
	第一次推送，需要加“-u”，以后不用。

---
#扩展

克隆（下载）

>$ git clone <版本库的网址>

比如，克隆当前所在的这个仓库：

>$ git clone git@github.com:mixinan/mygit.git

该命令会在本地主机生成一个目录，与远程主机的版本库同名。

如果要指定不同的目录名，可以将目录名作为git clone命令的第二个参数（不需要尖括号）：

>$ git clone <版本库的网址> <本地目录名>



显示目录

>ls 

查看状态

>$ git status

加入暂存区(单个文件，如果后面换为一个点“.” ，可加入所有文件)

>$ git add 文件名.后缀

删除

>$ rm 文件名.后缀

提交版本库

>$ git commit -m "提交的描述信息"


推送到远程仓库

>$ git push origin master


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

>$ git merge dev

删除分支

>$ git branch -d dev



> 查看分支：git branch



>创建分支：git branch name



> 切换分支：git checkout name



> 创建+切换分支：git checkout -b name



> 合并某分支到当前分支：git merge name



> 删除分支：git branch -d name




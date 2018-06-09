总结下今天的情况:

首先早晨的时候又学习了git,之所以说又,是因为之前已经学过一遍,这次学的话,大体上还是听的懂的.然后自以为很容易,结果在下午学习vue的时候,想要试试,结果就给跪了. 其中有个443的端口一直链接不上.然后查了好长一段时间,试了各种办法都不行.最后找到了一个方法.

在项目下,git bush中 `git config --global http.proxy "localhost:1080"`输入这一段,然后就解决了......

感觉还是又点僵硬的. 不过好在解决了.现在已经12点半了.六一儿童节....哒哒.



## 贴一下今天git学到的一些命令

git下载站 https://git-scm.com/

### 安装后第一步执行配置

git config --global user.name "blue"                             //配置名称
git config --global user.email "wzzyy@msn.cn"	    //配置联系邮箱
git config --list				 //查看配置信息
git init 					 //创建一个仓库
git init test   				 //创建目录为test的仓库名称,并创建test文件夹

### 克隆仓库

git clone url  				 //克隆github上的项目到本地,自动创建项目文件夹 url为克隆网址
git clone url abc  			//同上,但是会重新命名项目文件及文件夹名称为abc

git status 						//查看仓库状态
git add .  				  	 	//将所有修改 添加到暂存区
git add abc.txt 					//只将abc.txt添加到暂存区
git commit -m "提交说明,可无" 	//提交修改
git log  						//查看提交记录
git log --all 					//查看所有提交记录
git log --oneline --all --graph  		//类图形化查看提交记录(包括分支)
git log -p 						//查看具体修改内容, 对比不同
git log --oneline 				//单行显示

### 添加标签

git tag -a 标签名称 -m "标签说明"   //给版本添加标签.如果没有-a,则不能显示详细信息包括提交人等.
git tag -a 标签名称 -m "标签说明" 版本号 	//给指定版本号添加标签
git show 标签名称  						//查询标签详细信息

### 版本查看及拉回

git checkout 版本号  			//拉回相同版本号的提交记录
git checkout 标签名称 			//拉回标签名称的提交记录
git checkout -	     				//拉回上个版本

### 分支

git branch 分支名称  		//创建分支
git checkout 分支名称  		//切换分支
git checkout -b 分支名称 	//创建分支并且换到分支

### 合并分支

git merge 分支名称  //将分支名称 合并到当前分支下

### 远程仓库操作  github

1.在github先创建一个仓库 并记录仓库地址 url
2.在本地输入git remote add 远程名称  远程地址url
git remote  				//查询远程仓库
git remote -v  				//查询远程仓库详细信息
git push -u 远程名 分支名  	//上传代码
git pull 					//获取远程服务器最新代码

### 其他一些常用命令

ls			//列出当前文件目录
cd abc		//跳转到abc文件夹
cd ..			//返回上一级目录
j			//光标向下
k			//光标向上
q			//退出
ctrl+L		//清屏
touch abc.txt   //创建abc.txt文件

## 本地分支版本回退的方法

https://blog.csdn.net/fuchaosz/article/details/52170105

如果你在本地做了错误提交，那么回退版本的方法很简单 
先用下面命令找到要回退的版本的commit id：

```
git reflog 1
```

接着回退版本:

```
git reset --hard Obfafd1
```

0bfafd就是你要回退的版本的commit id的前面几位

## 自己的远程分支版本回退的方法

如果你的错误提交已经推送到自己的远程分支了，那么就需要回滚远程分支了。 
首先要回退本地分支：

```
git reflog
git reset --hard Obfafd12
```

紧接着强制推送到远程分支：

```
git push -f1
```

**注意：本地分支回滚后，版本将落后远程分支，必须使用强制推送覆盖远程分支，否则无法推送到远程分支**


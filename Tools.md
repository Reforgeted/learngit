# Git

*常用命令*

- git add
- git commit -m
- git push
- git clone git@github.com:githubUsername/repositoryName.git
- git checkout -b [branchName]

## 本地操作

*创建版本库*

```shell
#	Linux
mkdir [dirname]
pwd

git init
#	ls -ah   Linux下查看隐藏文件  .git

git add [fileName ...] 
	#	此时文件置于暂存区
git commit -m ["message"]
#	-m 即声明后面是本次提交的备注说明
#	可add多个文件后再提交
```

## 版本回退

*状态*

```shell
git status
git diff [fileName] #	git diff readme.txt

```

*回退*

```shell
git log
	#	查看提交历史
	--graph
	--pretty=oneline
	#	将每次的提交记录变为一行   显示版本号及备注信息
	--abbrev-commit
git reset --hard HEAD^
	#	--hard 
	#	HEAD^ 中的^代表上一个版本   有几个^代表回退多少次    并且也可将HEAD^替换为指定版本号
```

### 撤销修改

```shell
git checkout -- [fileName]
	#	将fileName在工作区的操作全部撤销   不过分两种情况
	#		fileName还未被添加到暂存区	那么将会回到最初版本库的状态
	#		fileName提交到了暂存区且修改了	将回退到添加入暂存区后的状态  即回到最近一次add或者commit时的状态
	
	
git reset HEAD fileName
```

### 删除文件

```shell
git rm [fileName]

```

## 远程仓库

### 配置用户信息

```shell
git config --global user.name ""
git config --global user.email ""

#	查看配置是否成功
git config --list

git reflog
	#	记录每一次的命令
	#	后悔之前的回退操作  可以查找到之前每次操作的版本号	
```

#### 生成密匙

```shell
ssh-keygen -t rsa -C "email@example.com"
#	连续回车（如果需要覆盖之前生成输入 y 回车）
```

生成密匙及公匙的位置

- C:\Users\\[username]\\.ssh

#### Github添加公匙

### 操作

```bash
git remote add origin git@github.com:githubUsername/repositoryName.git
	#	origin相当于是后面仓库位置的别名
git remote -v
	#	查看添加过的远程仓库

git push -u origin master
	#	master指添加的分支

git clone git@github.com:githubUsername/repositoryName.git

```

## 分支管理

```bash
git checkout -b [branchName]
	#	-b 指创建并切换到指定的分支上
	#	相当于	
		git branch [brancdName]	
			#	创建
		git checkout [branchName]
			#	切换
		
git branch
	# 查看当前分支
	#	会列出所有分支	并在当前分支前加一个 *
	
git merge [otherBranchName]
	#	合并其他分支到当前分支
	-m
		#	备注信息
	--no-off
		#	禁用Fast-forward模式
git branch -d [brancdName]
	#	删除
	-D	[name]
		#	强行删除
```

### 合并

#### 模式

- Fast-forward    快进模式
  - 删除分支后  会丢掉分支信息

#### 冲突

> 超前提交
>
> 两个分支对同一个文件存在不同的修改
>
> 需手动解决冲突才能继续合并

### 分支策略

#### 错误处理分支

> 修复bug
>
> ​	创建新的bug分支并修复
>
> ​	然后合并 删除

*保存工作现场 转而去处理其他问题*

```bash
git stash
	#	把当前工作现场储存  使得可以快速转义到存在bug的分支进行工作
	
	list
		#	查看当前分支保存的工作现场
		
git stash apply [stash@{n}]
	#	恢复 但是不删除
git stash pop
	#	恢复并删除
```



## SourceTree





# SVN
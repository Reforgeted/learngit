# Git

*常用命令*

- 

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
	--pretty=oneline
	#	将每次的提交记录变为一行   显示版本号及备注信息
	
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

git push -u origin master
```



# SVN
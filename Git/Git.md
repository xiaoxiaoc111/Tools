# Git 

> git 是目前世界上最先进的分布式版本控制系统。 

## Reference

* [git官网](http://git-scm.com/)
* [git教程](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)



## Point


* `弄懂暂存区概念`
* `Git鼓励大量使用分支`
* `弄懂master head概念`

	* ![master](Git.assets/master-1525547199133.png)



## github和本地仓库管理

* 第一步 安装git以及创建版本库

    * [下载git ](https://git-scm.com/downloads)

    * ```bash
        # 设置 git
        git config --global user.name "Your Name"
        git config --global user.email "<email@example.com>"
        
        #初始化 git
        git init
        
        #添加文件和提交文件
        git add <filename>   
        git commit -m "write something or some function"
        ```

* 第二步 修改文档增删改查

    * ```bash
        #查看仓库当前状态
        git status
        
        #查看修改内容
        git diff  --pretty=oneline
        #查看工作区和版本库里面最新版本的区别
        git diff HEAD -- <filename>
        
        #查看命令历史
        git reflog
        
        #版本回退
        git reset --hard commit_id
        
        #丢弃工作区的修改
        git checkout -- <filename>
        
        #删除文件
        git rm <filename>
        ```


* 第三步 创建SHH密钥


	* ```bash
		#创建ssh密钥:
		ssh-keygen -t rsa -C "youremail@example.com"
		
		#密钥默认保存位置:
		#dic：user/.ssh   
		#file: id_rsa and id_rsa.pub
		
		#添加密钥 
		web端操作:github->Account settings->SSH Keys
		```

* 第四步 添加远程库


	* ```bash
		#创建新库：   
		web端操作:github -> Create a new repo-> file
		
		#提交主线：    
		git remote add origin  git@github.com:path/<githubname/file.git>
		
		#推送主线:
		git push -u origin master
		```

* 第五步 克隆远程库

	* ```bash
		#创建新库：   
		web端操作:github -> Create a new repo-> file
		
		#克隆远程库到本地：
		git clone git@github.com:path/<githubname/file.git>
		```



## 分支管理

* 第一步 创建分支

	* ```bash
		#查看分支
		git branch
		
		#创建分支
		git brach <name>
		
		#切换分支：
		git checkout <name>
		
		#创建+切换分支：
		git checkout -b <name>
		
		#合并某分支到mater：
		git merge <name>
		
		#删除分支：
		git branch -d <name>
		```


* 第二步 解决冲突


	* ```bash
		#分支合并图 
		git log --graph
		```

* 第三步 分支策略管理

	* ```bash
		#合并分支时，加上--no-ff参数就可以用普通模式合并，
		#合并后的历史有分支，能看出来曾经做过合并
		git merge --no-ff -m "write something" branch-name
		```

* 第四步 bug分支

	* ```bash
		#储藏工作现场
		git stash
		
		#查看工作现场
		git stash list
		
		#恢复工作现场
		git stash pop    
		```

* 第五步 feature分支

	* ```bash
		#丢弃分支
		it branch -D <branch-name> 
		```

* 第六步 多人协作

	* ```bash
		#查看远程库信息
		git remote -v
		
		#推送分支
		git push origin <branch-name>
		
		#在本地创建和远程分支对应的分支
		git checkout -b branch-name origin/branch-name
		
		#建立本地分支和远程分支的关联
		git branch --set-upstream branch-name 
		
		#从远程抓取分支
		git pull
		```



## 标签管理

* 第一步 创建标签

	* ```bash
		#创建新标签
		git tag tag-name
		
		#查看标签
		git log --pretty=oneline --abbrev-commit
		git log tag-name commit-id
		git tag -a tag-name -m "write something " commit-id
		
		#查看PGP签名信息&签名
		git show 
		git tag -s  
		```

* 第二步 操作标签

	* ```bash
		#删除标签
		git tag -d tag-name
		git push origin :refs/tags/tag-name
		
		#推送标签
		git push origin tag-name
		git push origin --tags
		```

		

## 使用github&码云

*    Omission



## 自定义Git

* 第一步 忽略特殊文件
    * 创建.gitignore文件 到 https://www.gitignore.io

* 第二步 配置别名

    * ```bash
        #use  git config --global alias.<something> <something>
        git config --global alias.co checkout
        git config --global alias.ci commit
        git config --global alias.br branch
        git config --global alias.st status
        git config --global alias.unstage 'reset HEAD'
        git config --global alias.last 'log -1'
        ```

* 第三步 搭建git服务器

	* ```bash
		#use linux/ubuntu
		sudo apt-get install git
		sudo adduser git
		sudo git init --bare <filename>.git
		sudo chown -R git:git <filename>.git
		git clone git@server:/srv/<filename>.git
		```

		

		

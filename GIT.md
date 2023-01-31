pwd (print working directory)

cd (change directory)
mkdir project (make directory named project)
cd .. (返回上一级)

ls == dir （git里面的ls相当于CMD里面的dir）

touch index.html (create file)
rm （delete file）

rmdir （delete directory）
rm -rf 【styles】  （）


工作区，暂存区， 本地仓库，云仓库


git init (创建git仓库)
git --version
git config --global user.name "YIFAN ZHANG"
git config --global user.email "mitchellzhang0527@gmail.com"


git status //查看文件状态
git log // 查看之前的commit
git diff // 查看该文件的改动状态

git add 【files's name】
git add .  （添加所有文件到暂存区）

git commit -m "解释一下做了什么事情"
// stage and unstage
add 是把内容加进 stage
git rm --cached "index.html" 是把内容移除 stage

// local repo
git rm "index.html"是直接删除commit后的文件

## stash
---
// git stash temporary ( 在commit 之前) 中间暂时存储
git stash save 'feature3' 
git stash list //查看储存区所有的stash 
gti stash apply 0(或者其他数字)
git stash pop 取最后一个并且删除
git stash drop 0
git stash clear
### git undo change
---
- 1
git checkout . (点代表当前的分支)（修改文件之后用checkout，在add前， 那么就会回滚到修改之前的状态）

- 2
git clean -f (新建文件后回滚到之前新建的文件之前)

- 3 (反向操作某一次commit内所作的所有动作)
git revert 后面跟一个commit id

- 4 
//！！使用需谨慎， 从历史记录中删除commit, 删除回滚到某一个commit之前的状态
git reset [commit id]
git reset HEAD^   //回退所有内容到上一个版本，内容回到上个版本的工作区
git reset --soft HEAD^1 //回退所有内容到上一个版本， 内容回到暂存区
git reset --hard HEAD^1 //回退所有内容到上面一个版本，这个版本就会删除



## branch
---
git branch 会告诉你有哪些branch
git branch login 制作分支名字叫login

git checkout login 到名字叫login的分支里面
git branch -d [name] 删除merge 完全的branch
git branch  -D （name）删除branch
//branch 命名方式
<type>/<ticket-number>-<title>
feature/JR-101-creater-header-for-home-page
//切换分支
git checkout [branchname]
git checkout -b [branchname] 建立本地分支切换到新分支

git branch -a 表示



## merge
---
// rebase 和 merge 很像 
git merge login 把login 合并进来 

//如果不想解决冲突，那么就以某一个branch为基准
git merge <branch name> --abort
git merge <branch name> --overwrite-ignore
git merge <branch name>--no-overwrite-ignore

## rebase
// 不要在公共分支上执行rebase操作

git checkout master
git pull //从 master分支跟新下载
git checkout feature1
git rebase master //在feature branch上rebase master
git checkout master
git merge feature1


## remote repo
---
# 第一次上传整个repo到GitHub
https://docs.github.com/en/get-started/importing-your-projects-to-github/importing-source-code-to-github/adding-locally-hosted-code-to-github


- git init -b main (naming the default branch name as main)
- ![[copy-remote-repository-url-quick-setup.png]]
- ```shell
$ git remote add origin <REMOTE_URL>
# Sets the new remote
$ git remote -v
# Verifies the new remote URL
```
- ```shell
$ git push origin main
# Pushes the changes in your local repository up to the remote repository you specified as the origin
```

//查看链接的远程仓库地址
git remote -v
//删除链接的远程仓库
git remote rm origin
//重新链接本地仓库到新远程仓库
git remote origin set-url [giturl]



# 第一次下载 repo 到本地
git clone https://github.com/simplypa/firstGitTest.git


//更新上传
git push https://github.com/simplypa/firstGitTest.git

//更新下载
git pull

//更改master branch 为main
git branch -m master main
$ git branch -m master main
https://www.git-tower.com/learn/git/faq/git-rename-master-to-main








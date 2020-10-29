# Git_基础
版本控制、
## 1.基本概念
    仓库 Re
    收藏 Star
    复制克隆 Fork
    发起请求 Request
    事物 Issue
## 2.Git原理
    Git使用hash来进行验证文件完整性
### 2.1Git 版本管理机制
    快照，得到哈希值，将个版本hash做成一个树，记录版本变化
### 2.2Git管理分支

## 3.Git 安装和使用
    https://www.git-scm.com/
### 区域
    工作区 Working Directory：doing
    Git仓库 Git Repository：done（历史信息）
    暂存区：暂存
### 对象
#### Git对象
    文件快照
```x
git init test
cd test 
find .git/objects
find .git/objects -type f
echo 'test content' | git hash-object -w --stdin
```
#### 树对象:参考数据结构-树 记录目录结构和Git对象索引 
#### 提交对象:包含指向前面树的指针和所有提交对象
### 3.1 基本命令
#### 基本信息设置
    设置用户名 git config --global user.name 'eg.Xpo'
    设置邮箱 git config --global user.email 'xxx@gmail.com' 
    查看设置 git config --list
    --global:当前用户
    --system:当前系统
    啥也没有:当前项目
#### Linux 命令
    clear
    echo 'xxx'>text.txt ==cout==printf
    ll
    find
    rm
    mv
    cat 文件名:查看文件内容
    mkdir：创建文件
    
#### Git
    git init 初始化git仓库
        hooks:提交前预处理，提交后处理
        info:全局排除文件
        logs:日志
        objects:主存
        refs:分支
        confg:配置文件
        description:描述
        HEAD:头文件
        index:暂存区
```x
    echo "text content" | git hash-object --stdin //生成哈希码
```
```
```
    git专属命令:
    git help
    git status:查看工作区、暂存区的变化
    git add xxx 添加到暂存区
    git rm --cached 文件名:从暂存区拿出来
    git commit xxx:提交文件到仓库
    git commit -m "添加的提示信息" xxx
```
    git clone[url]:克隆Git仓库
    git status -s:short显示跟踪状态
    git add xxx:将xxx放入暂存区
    cat .gitignore:忽略
    git diff :查看未暂存的文件更新
    git diff --cached:查看暂存文件更新
    git commit:提交
    git rm
    git mv
    
```
## 2.3版本前进、回退、找回删除文件
    git log
    git log --pretty=oneline
    git log --oneline
    git log reflog:显示部分索引值+变化
    commit 347ec52eb5d8ece1884ba96a78d10a2eb9e96b51 (HEAD -> master):HEAD是个指针，当前指向master，通过操作该指针
    1.基于索引值操作
        git reset --hard 索引值：回退到索引值时的版本
    2.回退符号 ^
        git reset --hard HEAD^ ：回退到HEAD指针所指向版本的前一个（几个^退几个版本）
    3.前进符号 ~
        git reset --hard HEAD~：前进到HEAD 指针所指向版本的后一个
    git reset +参数
        --soft 本地库移动HEAD指针
        --mixed 本地库移动HEAD指针，重置暂存区指针
        --hard 本地库移动HEAD指针，重置暂存区指针，重置工作区
## 2.4比较文件差异
    git diff xxx：比较工作区与暂存区差别
    git diff [本地库历史版本][文件名]：工作区与本地库历史版本差别
## 2.5远程仓库使用
    git remote add <shortname><url>
    git fetch
    git push [remote-name] [branch-name]:推送到远程仓库
    git remote show/rename/rm [remote-name]:查看/重命名/移除
## 2.6打标签
    git tag
    git tag
## 2.7别名
    git config A B
## 2.8分支
| master |           |           |          |
| :----: | :-------: | :-------: | :------: |
|        | feature_1 | feature_2 |          |
|        |           | branch_3  |          |
|        |           |           | branch_5 |
|        |           |           | branch_N |
    类似一棵树，对不同树枝进行操作
    git branch xxx:创建分支
    git branch -v:查看分支
    git checkout xxx:切换分支
    合并分支
        1.git checkout A先切换到所要合并的分支上
        2.git merge [新分支名字B] 将A合并
# 3.Git 本地库与远程库
            远程库
    pull push clone push
    本地库
## 3.1创建远程库
    github、码云 创建
## 3.2本地库push到远程库
    ！一定得是本地库，而不能是工作区的
    1.给远程库地址一个别名并保存
    git remote add A [url]:将url别名为A
    git remote -v 查看已存在的地址别名
    eg git remote add Hi_C git@github.com:xpo0a/Vnote.git
    2.推送本地库
    git push A B
## 3.3远程库clone到本地库
    git clone [url]
    完整地下载、默认创建地址别名、初始化本地库
## 3.3分支管理
## 3.4分支开发工作流
## 3.5远程分支
## 3.6变基
    整合来自不同分支的修改
# 4.服务器上的Git
## 4.1协议
    本地协议(Local)+HTTP+SHH(secure shell)+Git
## 4.2服务器上搭建Git
## 4.3生成SSH公钥
## 4.4配置服务器
## 4.5守护进程
## 4.6Smart HTTP
## 4.7GitWeb
## 4.8GitHub Lol
# 5.分布式Git
# 6.GitHub
# 7.Useful Tool
## 7.1
## 7.2交互式暂存
## 7.3储藏与清理
## 7.4签署工作
## 7.5搜搜
## 7.6重写历史
## 7.7重置解密
## 7.8高级合并
## 7.9Rerere
# 8.自定义Git
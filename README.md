# Git 常用操作

### 1. 初始化仓库

```
git init
```

### 2. 提交

```
# 将待提交内容放到暂存区
git add xxxx
# 保存仓库的历史记录
git commit [-m message]
# 修改上一条提交信息
git commit --amend
【git commit -am ""可以同时实现add，commit功能】
# 提交至仓库
git pull
```

### 3. 查看状态

```
git status
```

### 4. 查看日志

```
【1. 以当前状态为终点】
# 查看完整日志
git log
# 只查看每个日志的一行
git log --pretty=short
# 只显示指定目录、文件的日志
git log xxxx
# 显示文件的改动
git log -p xxxx
# 以图表的形式查看分支
git log --graph
【2. 查看当前仓库的操作日志】
git reflog
```

### 5. 查看更改前后的差别

```
# 查看当前工作树和暂存区的差别
git diff
# 查看工作树和最新提交之间的差别
git diff HEAD
```

### 6. 分支操作

```
# 显示分支表
git branch
git branch -a:添加 -a参数可以同时显示本地仓库和远程仓库的分支信息
# 创建分支
git branch xxxx
# 切换分支
git checkout xxxx
[git checkout -b xxxx 创建并切换分支]
# 切换到上一个分支
git checkout -
# 合并分支
1. 首先切换到master分支：git checkout master
2. 然后合并分支：git merge --no-ff xxxx
```

### 7. 回溯历史版本

```
git reset --hard xxxx(哈希值)
```

### 8. 压缩历史

```
选定当前分支中包含HEAD（最新提交）在内的两个最新历史记录为对象，并在编辑器中打开，然后进行修改。
git rebase -i HEAD~2
```

### 9. 推送至远程仓库

```
# 添加远程仓库
git remote add xxxx
example:git remote add origin git@github.com:Ustinian-J/git-tutorial.git
[按照上述格式执行git remote add命令之后，Git 会自动将git@github.com:Ustinian-J/git-tutorial.git远程仓库的名称设置为 origin（标识符）]
# 推送至远程仓库
git push
example:git push -u origin master
[推送至master分支]
【当然，也可以切换至其他分支，然后将该分支推送到远程仓库】
```

### 10. 获取远程仓库

```
# 获取远程仓库
git clone xxxx
example:git clone git@github.com:Ustinian-J/git-tutorial.git
# 获取远程分支
git checkout -b feature-D origin/feature-D
[- b 参数的后面是本地仓库中新建分支的名称。新建分支名称后面是获取来源的分支名称。例子中指定了 origin/feature-D，就是说以名为 origin 的仓库（这里指 GitHub 端的仓库）的 feature-D 分支为来源，在本地仓库中创建 feature-D 分支。]
# 获取最新的远程仓库分支
git pull
```






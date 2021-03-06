# Git使用

## 本地方法

### 1. 安装及普通使用

1. 官网下载

2. 配置用户名和邮箱

   ```
   git config --username
   git config --mail@mail
   ```

3. 初始化文件夹，新、增文件，提交到暂存区

   ```
   git init
   git add file_addr
   ```

4. 生成版本

   ```
   git commit -m 'message'
   ```

5. 查看版本

   ```
   git log
   ```

   

### 2. 高级使用

1. 回滚：返回到某一版本去，需要知道返回版本的版本号。

   ```
   git reset --hard 版本号
   ```

2. 回回滚：返回到上一个版本去，需要知道返回版本的版本号。

   ```
   git reflog
   git reset --hard 版本号
   ```

### 3. 分支

默认在master线上，当进行开发时，根据功能的不同与协作，可能需要分出不同线来进行开发，因此需要使用分支。当分支开发完成之后，需要将分支再合并到主干上。

1. 创建分支

   ```
   git branch 分支名
   ```

2. 切换到分支上

   ```
   git checkout 分支名
   ```

3. 合并分支

   ```
   # 切换到主干上
   git checkout master
   
   # 合并分支
   git merge 分支名
   ```

## 联机方法

之前介绍的方法都是本地就可以使用的方法，当进行实际开发时，往往需要将本地代码提交到服务器上，因此需要其他操作。

### 1. 克隆仓库

```
git clone url
```

### 2. 给远程仓库起名

```
git remote 仓库名 地址
```

### 3. 向远程仓库推送代码

```
git push -u 仓库名
```





## 3. 命令总结

```
git init
git add
git commit
git log
git reflog
git reset --hard 版本号
# 查看分支
git branch

# 创建分支
git branch 名字

# 删除分支
git branch -d 名字

# 切换分支
git checkout 名字

# 合并分支
git merge 名字

# 克隆代码
git clone url

# 给远程仓库起名
git remote add origin url

# 向远程推送代码
git push -u origin 分支

# 从远程拉代码下来
git pull origin 分支名

git fetch origin 分支名
git merge origin/分支名

git fetch origin 分支名
git rebase origin/分支名

# 查看记录
git log --graph 
```



## 

## 5. 工作流

至少两个分支，一个master，一个dev。

在另一个dev分支上开发前，应该保证自己的版本是最新的。

## 6. 多地开发

第一次获取代码

```
1. 克隆远程仓库代码
git clone 远程仓库地址

2. 切换分支
git checkout 分支名
```

在公司进行开发

```
1. 切换到dev分支开发
git checkout dev

2. 把master分支合并到dev
git merge master

3. 修改代码

4. 提交代码
git add .
git commit -m 'xx'
git push origin dev
```

出现冲突，手动解决冲突。

## 变基

使git记录变的简洁。

1. 将多个记录整合成一个记录。

```
git rebase -i HEAD~3(从HEAD开始往后合并)
```

注意：合并记录时，不要和push到仓库的记录进行合并。

2. 

注意：git rebase冲突，需要解决冲突，git add ...，git rebase --continue
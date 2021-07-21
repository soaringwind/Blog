# Git使用

## 1. 安装及普通使用

1. 官网下载

2. 配置用户名和邮箱

   ```
   git config --username
   git config --mail@mail
   ```

3. 新、增文件，提交到暂存区

   ```
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

   

## 2. 高级使用

1. 回滚

   ```
   git reset --hard commit_num
   ```

2. 回回滚

   ```
   git reflog
   git reset --hard commit_num
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
git branck 名字

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

```



## 4. 分支

## 5. 工作流

至少两个分支，一个master，一个dev。
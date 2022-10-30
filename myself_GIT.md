# GIT



## Git与SVN



## Git简单操作

### 添加至暂存区

```bash
git add .
```

```bash
git add fileName
```



### 撤销添加

```//bash
git reset head fileName//指定
git reset head HEAD//所有
```





### 查看暂存区

```bash
git status		
```



### 添加至分支

```base
git commit -m "tip"
```



### 撤销commit

```bash
git reset --soft head^^//不取消add
git reset --mixed/ head^^ //取消add.
git reset --hard head^^//回到上一次commit状态
```





### 创建分支

```bash
git branch dev
```

```bash
git switch -c dev
```

### 切换分支

```bash
git checkout (-b) dev
```

```bash
git switch dev
```

### 创建并切换分支

```bash
git checkout -b dev
```



### 推送到仓库

```bash
git push -u origin master
```





### 查看分支

```bash
git branch 
```

```bash
git branch -a
```



### 分支合并

```bash
git merge dev
```



### 删除分支

```bash
git branch -d dev
```

```bash
git branch -D dev (强制删除)
```



### 分支合并冲突

#### 查看冲突

```bash
git diff
```

### Fast forward模式

通常情况下，Git在合并分支时，会使用Fast forward模式。这种模式下，删除分支后，会丢掉分支信息。如下图所示，删除dev分支之后，分支的信息也就就丢失了

![image-20220625105226284](C:\Users\27472\AppData\Roaming\Typora\typora-user-images\image-20220625105226284.png)

![image-20220625105251749](C:\Users\27472\AppData\Roaming\Typora\typora-user-images\image-20220625105251749.png)

### 禁用Fast forward模式

```bash
git merge --no-ff -m "tip" dev
```

其中`--no-ff`参数，表示禁用Fast forward,因为本次合并要创建一个新的commit，所以加上`-m`参数。把commit描述写进去。



## BUG分支

修改bug

### 保存工作现场

```bash
git stash
```

![image-20220625105823570](C:\Users\27472\AppData\Roaming\Typora\typora-user-images\image-20220625105823570.png)

### 查看保存的工作现场

```bash
git stash lsit
```

![image-20220625105835263](C:\Users\27472\AppData\Roaming\Typora\typora-user-images\image-20220625105835263.png)

### 恢复工作现场

并不会删除保存的工作现场

```bash
git stash apply id
```

![image-20220625110434501](C:\Users\27472\AppData\Roaming\Typora\typora-user-images\image-20220625110434501.png)

### 删除工作现场

```bash
git satsh drop id
```

![image-20220625110907310](C:\Users\27472\AppData\Roaming\Typora\typora-user-images\image-20220625110907310.png)

### 恢复并删除工作现场

```bash
git stash pop id
```

### 提交A分支的一些commit到B分支

```bash
git checkout B
git cherry-pick commit_id
```

**commit_id**:![commit_id](C:\Users\27472\AppData\Roaming\Typora\typora-user-images\image-20220625115629767.png)

## feature分支

新功能分支



## 远程仓库(多人协作)

### 关联远程仓库

```bash
git remote add origin http/ssh
```

### 删除远程仓库

```bash
git remote rm origin
```

### 克隆仓库

```bash
git clone http/ssh
```

### 查看远程分支

```bash
git remote 
```

![image-20220625183956994](C:\Users\27472\AppData\Roaming\Typora\typora-user-images\image-20220625183956994.png)

```bash
git remote -v
```

![image-20220625184019224](C:\Users\27472\AppData\Roaming\Typora\typora-user-images\image-20220625184019224.png)

### 推送分支

```
git push -u origin master
```



### 创建远程分支

```bash
git push origin dev #没有dev分支则创建dev分支，只能从dev分支到dev分支
```



可以使用 **git reset --hard HEAD^ **来回退到上一次commit的状态。 此命令可以用来回退到任意版本：**git reset --hard commitid **

你可以使用 **git log **命令来查看git的提交历史。

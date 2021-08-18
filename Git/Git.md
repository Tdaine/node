Git

###### 删除远程仓库文件

```
git rm -r -n --cached 文件/文件名称
加上-n参数，执行命令时，是不会删除任何文件，而是展示此命令要删除的文件列表预览

删除文件
git rm -r --cached 文件/文件夹名称

提交到本地并推送到远程服务器
git commit 
git push origin master

想要回滚本地代码
git stash -p    //保存想要保存的文件
git reset --hard 版本   //回退到某个版本
git stash pop   //将保存的文件取出
```

###### 配置ssh

```git
ssh-keygen -t rsa -C "这里换上你的邮箱"
在下面路径生成id_rsa和id_rsa.pub两个文件

C:\Users\user\.ssh
复制id_rsa.pub文件的内容
添加到github的ssh中
```

##### 解决本地代码和远程代码不同步问题
```git
git stash //将本地已修改代码先进行保存
git pull  远程 指定分支 //拉取远程指定分支的代码
git stash pop //将刚才保存的代码进行恢复
git push 远程 指定分支 // 将本地代码提交到远程
```

**查看远程仓库地址**

```git
git remote -v
```


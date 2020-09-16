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


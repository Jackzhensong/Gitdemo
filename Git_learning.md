### Git Learning 

![img](https://img-blog.csdnimg.cn/20190604193324344.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2JlbmJlbl8yMDE1,size_16,color_FFFFFF,t_70)

- workspace：工作区，idea里写的代码，保存了就在workspace。
- index/stage：暂存区，git add命令执行后，会将代码存入stage/index。
- repository：仓库区（或本地仓库），git commit命令执行后，代码会存入repository中。
- remote：远程仓库，git push之后，代码会存入remote。	

1. 从远程库克隆

   GitHub给出的地址不止一个，可用 ：

   git clone git@github.com:accountername/repository name .git (速度最快)

   或者：git clone  https://github.com/accountname/repositoryname .git  (速度慢)

2. 分支管理

   - 创建分支：git branch  `name`
   - 查看分支：git branch 
   - 创建并切换分支：git checkout -b `branchname`   或    git switch -c `branchname`
   - 切换分支：git checkout `branchname`      或  git switch `branchname`
   - 合并分支：git checkout master            git merge `branchname`  
   - 删除分支：git branch -d `branchname` 

3. 第一次从本地上传文件到GitHub： git push --set-upstream origin `branchname`

3. 常用git命令    http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html



#### git operation

1. 删除

   - 删除远程文件/文件夹，保留本地的不删除

     ```
     git rm -r --cached filename
     git commit -m 'delete filename'
     git push
     ```

   -  直接在本地删除文件，commit 和 push 后远程文件也会同样被删除

   - 删除远程仓库：

     ```
     git remote // 查看远程仓库名
     git remote rm 仓库名
     
     还需在GitHub上把仓库手动删除掉，才能完全删除
     ```

   - 删除本地仓库
   
     ```
     ls -a   #列出仓库下的所有文件，包括隐藏的文件
     
     rm -rf .git  #删除本地仓库，可以看到仓库末尾的master已经没有
     
     rm -rf filenane  #删除本地的库文件夹
     ```
   
     



##### git handle error

1. Failed to connect to github.com port 443: Timed out

   ```
   // 取消代理
   git config --global --unset http.proxy
   git config --global --unset https.proxy
   ```

2. OpenSSL SSL_read: Connection was reset, errno 10054

   ```
   git config --list
   git config --global http.sslVerify "false"
   
   在项目目录下打开命令行工具，输入：git init 
   
   在cmd中输入：ipconfig /flushdns  #更新dns缓存
   ```

   


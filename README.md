# github

[Git Cheat Sheet](https://blog.igevin.info/posts/git-cheat-sheet/)  
Tipes：在github上看源碼的時候將github改為`github1s`，github秒變vscode

## 退版

```bash
# 從目前的 HEAD 倒退一個 Commit
git reset HEAD^

# 查看 Git 記錄
git log --oneline

# 強制推送至遠端 master 分支
git push origin main --force
```
這樣遠端 master 分支上面的錯誤 commit 就會不見了。


``

# windows ssh

PS C:\Users\jacob\Documents> `ssh-keygen`  
Generating public/private rsa key pair.  
Enter file in which to save the key (C:\Users\jacob/.ssh/id_rsa):  
Enter passphrase (empty for no passphrase):  
Enter same passphrase again:  
Your identification has been saved in C:\Users\jacob/.ssh/`id_rsa`.  
Your public key has been saved in C:\Users\jacob/.ssh/`id_rsa.pub`.  


https://github.com/settings/ssh/new

copy `id_rsa.pub`

# mac

[mac下已安裝的ssh的id_rsa.pub文件位置](https://blog.csdn.net/Cloudox_/article/details/50284131)
默認路徑的，因此要找到ssh文件夾下的id_rsa.pub文件，只需要：

打開終端輸入 `$ open ~/.ssh`

# git 

[從過去的某個 Commit 再長一個新的分支出來](https://gitbook.tw/chapters/branch/branch-from-old-commit.html)

`$ git checkout 657fce7`  (dev branch)  
`$ git checkout -b release`    
`$ git checkout master`  
`$ git merge release`  
`$ git push`  

The current branch release has no upstream branch.
To push the current branch and set the remote as upstream, use
`git push --set-upstream origin release`  

【狀況題】[手邊的工作做到一半，臨時要切換到別的任務](https://gitbook.tw/chapters/faq/stash.html)


 `$git reset -soft HEAD^`  
 `$git stash`  
 `$git checkout -b HotFix`  
 `$git branch`  
 `$git stash pop`  
 `$git add .`  
 `$git commit -m "hotfix"`  


### IDE
[CodePen](https://codepen.io/) - Front End Developer Playground & Code Editor  
[Repl.it](https://repl.it/languages/python3) - Online Python3 Editor and IDE - Fast, Powerful, Free  

### projects
[Asana](https://app.asana.com/) Use Asana to manage your team's work, projects, & tasks online

### hexo 

[hexo-theme-next](https://theme-next.org)  
[精于心，简于形](https://theme-next.iissnan.com/)  


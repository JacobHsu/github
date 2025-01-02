# github

[Git Cheat Sheet](https://blog.igevin.info/posts/git-cheat-sheet/)  
Tipes：在github上看源碼的時候將github改為`github1s`，github秒變vscode


你的電腦無法使用你的 SSH 金鑰連接到 GitHub。以下是解決問題的步驟：

---

### 1. **檢查是否已生成 SSH 金鑰**
在終端機輸入以下命令，檢查是否已經生成了 SSH 金鑰：

```bash
ls ~/.ssh
```

如果看到了類似 `id_rsa` 和 `id_rsa.pub` 的文件，表示你已經有 SSH 金鑰。如果沒有，則需要生成一個。

#### 如果需要生成 SSH 金鑰：
執行以下命令：

```bash
ssh-keygen -t rsa -b 4096 -C "你的GitHub郵箱地址"
```

然後按下 `Enter` 鍵，並按照提示完成。

---

### 2. **添加 SSH 金鑰到 ssh-agent**
啟動 `ssh-agent` 並添加金鑰：

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```

---

### 3. **將 SSH 公鑰添加到 GitHub**
將 `id_rsa.pub` 的內容添加到你的 GitHub 帳戶：

#### 查看公鑰內容：
```bash
cat ~/.ssh/id_rsa.pub
```

複製輸出的內容。

#### 添加到 GitHub：
1. 登錄到 [GitHub](https://github.com)。
2. 點擊右上角的個人資料圖片，選擇 **Settings**。
3. 在側邊欄選擇 **SSH and GPG keys**。
4. 點擊 **New SSH key**，將複製的公鑰內容貼上，然後保存。

---

### 4. **測試連接**
執行以下命令測試 SSH 是否正確連接到 GitHub：

```bash
ssh -T git@github.com
```

如果出現以下訊息，表示成功：

```plaintext
Hi <username>! You've successfully authenticated, but GitHub does not provide shell access.
```

---

### 5. **重試 git clone**
確認一切設置正確後，重新嘗試克隆：

```bash
git clone git@github.com:JacobHsu/nuxt-json-server.git
```

## 撤銷

`git revert` 是一個用於創建新提交以撤銷之前提交更改的 Git 命令。當您需要保留完整的提交歷史並回退更改時，這是一個很有用的方法。以下是使用 `git revert` 創建新提交的步驟：

1. **查找要撤銷的提交：** 使用 `git log` 命令查找您想要回退的特定提交的哈希值。複製該哈希值以供稍後使用。

2. **使用 `git revert` 命令：** 使用 `git revert` 命令並指定您想要回退的提交的哈希值。假設您的特定提交哈希值為 `<commit-hash>`：

   ```bash
   git revert <commit-hash>
   ```

   這會創建一個新的提交，該提交將撤銷選定的提交 `<commit-hash>` 所做的更改。Git 會打開一個文本編輯器以允許您編輯撤銷提交的提交消息，然後保存並關閉編輯器。

3. **保存撤銷提交：** 當編輯器打開時，您可以編輯提交消息，然後保存該文件並關閉編輯器。提交消息應該描述您正在撤銷的更改。

4. **推送撤銷提交：** 當您滿意撤銷提交的消息時，您可以將該提交推送到 GitHub 或您的遠程存儲庫：

   ```bash
   git push origin <branch-name>
   ```

   `<branch-name>` 是您的分支名稱，這會將新的撤銷提交推送到遠程存儲庫。

這樣，您就可以使用 `git revert` 創建一個新的提交，以撤銷之前的更改，同時保留完整的提交歷史。這對於在團隊協作中或保持版本控制歷史的完整性非常有用。

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

[使用 ssh-keygen 產生 publich key](https://www.maxlist.xyz/2022/12/22/github-ssh-setting/)  
將 publish key 貼到 [Github](https://github.com/settings/keys) 上  
`ssh -T git@github.com`  

# mac

[mac下已安裝的ssh的id_rsa.pub文件位置](https://blog.csdn.net/Cloudox_/article/details/50284131)
默認路徑的，因此要找到ssh文件夾下的id_rsa.pub文件，只需要：

打開終端輸入 `$ open ~/.ssh`

# git 

# 從目前的 HEAD 倒退一個 Commit  
`git reset HEAD^`

# 從目前的 HEAD 倒退三個 Commit  
`git reset HEAD~3`

# 強制推送至遠端分支  
`git push origin main --force`

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


## Frontend 

[leetcode](https://leetcode.com/) [studyplan](https://leetcode.com/studyplan/)  
[lintcode](https://www.lintcode.com/)  [course](https://www.lintcode.com/course/list/?tagId=1267&chargeStatus=1)  

### IDE
[CodePen](https://codepen.io/) - Front End Developer Playground & Code Editor  
[Repl.it](https://repl.it/languages/python3) - Online Python3 Editor and IDE - Fast, Powerful, Free  

### projects
[Asana](https://app.asana.com/) Use Asana to manage your team's work, projects, & tasks online

### hexo 

[hexo-theme-next](https://theme-next.org)  
[精于心，简于形](https://theme-next.iissnan.com/)  


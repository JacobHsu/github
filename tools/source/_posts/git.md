---
title: git
---

[GitLab and SSH keys](https://docs.gitlab.com/ee/ssh/)  

### Git for Windows  

The easiest way to install Git and the SSH client on Windows 8.1 and Windows 7 is [Git for Windows](https://gitforwindows.org/). It provides a Bash emulation (Git Bash) used for running Git from the command line and the ssh-keygen command that is useful to create SSH keys as you’ll learn below. 

### RSA SSH keys  

首先你需要在github上或者gitlab上有一個自己的賬戶

打開git bash，輸入命令`ls -al ~/.ssh`。檢查是否顯示有`id_rsa.pub`存在   

在`git bash`中鍵入
`$ ssh-keygen -t rsa -C "your_email@example.com"`
注意將這裡的郵箱地址替換成你自己的郵箱地址。之後一直按回車就可以了。在這裡可以看到`id_rsa`和`id_rsa.pub`文件已經生成。並且生成的路徑也已顯示。

用記事本之類的軟件打開`id_rsa.pub`文件，並且複製全部內容。這裡記錄的是公鑰信息。
在你的gitlab或者github的賬戶，打開SSH key標籤。
然後選擇`Add SSH key`按鈕，將剛剛複製的內容粘貼進去即可，然後點擊`add key`。   
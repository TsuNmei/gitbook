# Git

## Git 基本指令

```
# git 基礎指令

$ git init                 # 將目錄 init設定 
$ git status               # 查看 git狀態
$ git log                  # 查看 git logs 
$ git log --oneline        # 加上prettier 介面
$ git add -a / .           # 將更改內容加入 stage暫存區
$ git commit -m            # 將這次修改 commit 提交出去 (sha256 code)
$ git commit --amend       # 此次改動加入上一個 commit (*)

# github push
$ git push origin master   # 將 local端 code 推上 github
$ git pull origin master   # 將 github repository code 拉下來比對

$ git clone https://github.com/[user.name]/[repo.name]


```

```text
# 先確定目前遠端位置
git remote -v

# 如果出現這樣，代表前人用的是 SSH 連線方式
origin	git@github.com:{username}/{repo}.git (fetch)
origin	git@github.com:{username}/{repo}.git (push)
```


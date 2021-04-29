---
description: clone 指定 branch
---

# Clone 專案

## Git clone https://github...

第一次下載 repository 要使用 git clone 下載到指定目錄中。

```bash
$ git clone [repo_name]
```

### ＊ 指定要clone 哪個分支

```
$ git clone -b [branch_name] https://github.com/[user_name]/[repo_name].git
```

### ＊ Upload local branch to origin

```text
# create a new branch
$ git branch feat/new_feature

$ git checkout feat/new_feature

... do something & commit it

# 設定 upstream 可以使分支開始追蹤指定的遠端分支
$ git push --set-upstream origin feat/new_feature
                    or 
$ git push -u origin feat/new_feature

# 設定好 upstream 後，第二次以後要上傳分支時，就只需要透過 git push 就可以了
# 不必再帶 <remote name> 跟 <branch name> 等參數
```


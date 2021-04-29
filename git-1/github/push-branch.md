# Push Branch

Github 從 local push 另一個 branch 到 remote

1. 先下指令 git branch -a \(--all\)

   1. 查看現在有的所有 branch \(local / remote\)

```text
$ git branch -a 

*master (現在位置)
prod

```

1. 再來下 git remote -v

   1. 查看是否已經遠端連線到對應得 repository \(repo\)

```text
$ git remote -v 

# 不一定是 origin
origin  https://github.com/your_account/<branch_name>.git (fetch)
origin  https://github.com/your_account/<branch_name>.git (push)
```

1.  直接 push &lt;remote\_name&gt; &lt;local branch name&gt;

```text
# production
$ git push origin prod 

# staging
$ git push origin staging
```


# SSH 金鑰

## Github 建立一個新的 repository

### **＊ 設定 ssh 金鑰**

```
$ ssh-keygen                                   # 產生金鑰
Generating public/private rsa key pair.
Enter file in which to save the key (/users/[local].ssh/id_rsa):   # 金鑰存放路徑，直接按 Enter
Created directory '/home/jaycelin/.ssh'.
Enter passphrase (empty for no passphrase):    # 密碼，可設定可不設定，設定的話每次上傳會多需要輸入一次密碼
Enter same passphrase again:                   # 再輸入一次密碼
The key fingerprint is:                        # 之後會顯示你的 fingerprinˇ
```

### ＊ 讀取 ssh-rsa key

```bash
cat /users/[local].ssh/id_rsa.pub           # 讀取檔案內容
ssh-rsa ~一連串金鑰~username@pc-name         # 從 ssh-rsa 複製到 username@pc-name
```

### ＊ 將本機端的 git 推到 Github

```bash
git remote add origin git@URL  # 設定repo連到github repo
git push origin master         # 推到github repo上  
git push -u origin master      # -u代表推送時同時設定 upstream，也就是預設的追蹤遠端。
git pull origin master         # 當遠端版本庫有更新時，可以使用 git pull 將更新拉下來。
git clone git@URL              # 將local沒有的repo pull下來
```

[https://blog.jaycetyle.com/2018/02/github-ssh/](https://blog.jaycetyle.com/2018/02/github-ssh/)


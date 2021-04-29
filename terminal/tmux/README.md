---
description: Linux plugins
---

# TMUX

## What is TMUX ?

**`tmux`** 是一個 **`Terminal Multiplexer`**`，`是多視窗管理的 Terminal。簡單來說它就是在一個終端機（一個 Console）下可以開**多個視窗**或是**分割視窗**達到視覺化的介面。

> `tmux` 中我們會有視窗 \(window\) 和視窗區塊 \(panel\)

每一個 **`panel`** 各自有各自獨立執行一個 **`Terminal Instance`** （各自輸入輸出的介面實例）讓我們可以同時執行多個指令，而不需要開啟多個 Terminal 視窗。

### ⁍ What's used for ?

`tmux` 會在同一個 `session` （連線狀態下的執行環境）保存這些視窗和視窗區塊，我們可以在任何時間離開這個連線，這被稱為 `detaching`。離開後並不會像Terminal一樣 **離開即關閉**，而是在背景執行。

### ⁍ TMUX command

#### &gt; 開啟一個 tmux session

```
$ tmux new -s [session name] # e.g. tmux new -s todolist
```

#### &gt; 確認是否有成功建立sessiom

```text
$ ubuntu@ip-172-31-45-2:~$ tmux ls
0: 1 windows (created Tue Nov 17 03:39:14 2020) # 預設name= 0
1: 1 windows (created Wed Nov 18 01:33:23 2020)
```

####  &gt; 進入 tmux session

```text
$ tmux a -t [session name]
```

#### &gt; 進入後啟動 tmux 指令 \(prefix: ctrl + b\)，否則為 Linux 

{% hint style="info" %}
下方有 `bash 0` 紅色線為進入 tmux 內部 
{% endhint %}

```bash
$ (ctrl + b) + 指令
ctrl + b + c # create a new window
ctrl + b + n # go to next window
ctrl + b + ' # 平行 create a panel (shift+")
crtl + b + % # 垂直 create a panel (shift+%)
ctrl + b + (↑/↓/←/→) # 轉移 panel
```

#### &gt;  進入 tmux 啟動 server : python3 manage.py runserver 0.0.0.0:8000 \(對外的port\)

```bash
$ python3 manage.py runserver 0.0.0.0:8000
# if using 127.0.0.1 is for localhost run
$ ctrl + b + d (detaching leave) 
```


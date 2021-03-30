# Poetry

## 你還再用 pip 嗎，試試 Poetry 吧！

Poetry 其實跟 pip 一樣是個 python 套件管理系統，之於 MacOS 的 brew。

Poetry 強大的地方在於文件管理，可以多面向的設定 configuration，比方說 decouple `dev` 的 環境 及 `prod` 的環境，或是 `global` 的環境。

Poetry doc file 格式採用 .**toml**，可以把它想像成 **.json** 即可。

## 如何在專用開發使用 Poetry :

> 首先必須先在 Local 安裝 [POETRY](https://python-poetry.org/docs/)

{% hint style="info" %}
如果你是 macOS 使用者，請參考 [system預設python2.7 更改為python3](https://dev.to/malwarebo/how-to-set-python3-as-a-default-python-version-on-mac-4jjf)
{% endhint %}

```text
$ poetry new [project name]


# if need to create a virtual environment
$ touch poetry.toml
[virtualenvs]
in-project = true

# create a virtual env command
$ touch poetry shell
-> will help to create a .venv

$ source .venv/bin/activate
$ poetry install

```




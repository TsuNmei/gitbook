---
description: An excellent python IDE
---

# Jupyter notebook

## Jupyter Notebook 

> Jupyter Notebook 是一個具互動性高的開發環境

它提供 **單元式** 執行區塊、**Markdown** 語法以及 **Web Console** 的性質。「JUPYTER」它的名字主要是來自於 "Julia & Python & R"， 當然並非只有支援以上三種語言，其實 Juypter 也提供許多其他的 Kernels，例如： Go, Ruby 等等...

### ＊Install jupyter notebook

```bash
$ pip3 install jupyter

# 如果你用 zsh 的話，需要先將 local python bin 加入 .zshrc 裡面
# 請參考 https://medium.com/%E7%A8%8B%E5%BC%8F%E4%B9%BE%E8%B2%A8/jupyter-notebook-%E5%95%8F%E9%A1%8C-jupyter-command-not-found-a0764d253c65
```

### ＊ Install extension

```bash
Jupyter extension

# Installation
$ pip install jupyter_contrib_nbextensions
$ jupyter contrib nbextension install --user

# Enable extension
$ jupyter nbextension enable varInspector/main

# Configuration
$ sudo jupyter nbextensions_configurator enable --user

# Install themes
$ pip install --upgrade jupyterthemes

# Manage theme
$ jt -t onedork -f roboto

# Close theme
jt -r

# Close theme
"""
jt -t + [Themes] -N -T
Available Themes:
   chesterish
   grade3
   monokai
   oceans16
   onedork
   solarizedd
   solarizedl
"""
```


# Closure 閉包

## First-class function

第一層級函式是指 function 可以作為 argument 使用：

> Python中的每個 function 都屬於 First-class function。

```
def squre(x):
    return x**2
    
def square_list(func, list):
    _list = []
    for item in list:
        _list.append(func(item))
        
    return _list
```

{% hint style="info" %}
 Super-powers are granted randomly so please submit an issue if you're not happy with yours.
{% endhint %}

Once you're strong enough, save the world:

{% code title="hello.sh" %}
```bash
# Ain't no code for that yet, sorry
echo 'You got to trust me on this, I saved the world'
```
{% endcode %}




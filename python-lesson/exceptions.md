---
description: try / exception
---

# Exceptions

## Python Exception Example

如果程式執行發生錯誤時，列下錯誤原因：

```python
# exceptions example
def Error(a):
    try:
        b = 10 / a
        return b
    except Exception as e:
        print("There is an errror occur!")
        return repr(e)


Error(10)
# Output: 1.0
Error(0)
# Output[1]: There is an errror occur!
# Output[2]: ZeroDivisionError('division by zero')
```

{% hint style="info" %}
 Super-powers are granted randomly so please submit an issue if you're not happy with yours.
{% endhint %}

```python
# exceptions example
def Error(a):
    try:
        b = 10 / a
        return b
    except IntegrateError:
        raise IntegrateError
    except TypeError:
        raise TypeError
    except:
        raise exception

```


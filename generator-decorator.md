# Generator / Decorator

## Generator

```

```

## Decorator

> Decorator 是 Python 特殊語法 -語法糖（Syntax Candy\)

### \* When function call another functions:

```python
# print function for example

def print_func_name(func):
    def wrapped():
        print("Now is using the function **{}".format(func.__name__))
        func()
    return wrapped

def dog():
    print("Woof woof")

def cat():
    print("Mioew mioew")


print_func_name(dog)()
# Output: Now is using the function **dog
# Output: Woof woof

print_func_name(cat)()
# Output: Now is using the function **cat
# Output: Mieow mieow
```

{% hint style="success" %}
ㄋㄟㄋㄟ 補給站：**syntax candy**（語法糖）就是簡化的語法，可以將數十行的 code，寫個幾行或是寫個符號上去，就可以省略許多重複的過程。這是為什麼可以讓 code 「甜」一點，讓語言更貼近自然語言一點！且這在多數語言中都有類似的語法～
{% endhint %}



```python
# User decorator implement

def print_func_name(func):
    def wrapped():
        print("Now is using the function **{}".format(func.__name__))
        func()
    return wrapped

@print_func_name  # python decorator syntax
def dog():
    print("Woof woof")

@print_func_name
def cat():
    print("Mioew mioew")


dog()
# Output: Now is using the function **dog
# Output: Woof woof

cat()
# Output: Now is using the function **cat
# Output: Mieow mieow
```

### \* Function Runtime decorator 

```python
# Calcuate the function runtime

def calc_time(func):
   from time import time
   def wrapper():
      s = time()
      func() 
      e = time()
      print("The func takes {} second".format(round(e-s, 7)))
   
   return wrapper
   

@calc_time
def forloop():
   res = 0
   for i in range(100000):
      res+=i
   print(res)


forloop()
# Output: 4999950000
# Output: The func takes 0.0062823 second
```


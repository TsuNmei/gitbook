# Python Class 類別

## Python class

Python 為物件導向的語言，什麼是物件導向\(OOP\) 這裡不多加贅述，可以自行 GOOGLE。

OOP 有一個重要的特性就是 `class` ，他可以將實體的 **物件** 集合成 **類別。**

顧名思義 就是將 狗、貓、雞、羊 這些動物，賦予一個大類別 為 **動物類。**

{% code title="class\_tutorial.py" %}
```python
""" python class 不成文規定 “字首大寫其且不能有底線” """

class Animal(object):                          #動物的類別
    def __init__(self, name, sexual, mammal):  #動物的屬性
        self.name = name
        self.sexual = sexual
        self.mammal = mammal

cat = Animal(name="cat", sexual="male", mammal=True)

cat.name    #output "cat"
cat.sexual  #output "male"
cat.mammal  #output "True"

dog = Animal(name="dog", ....)

＝＝以此類推＝＝
    ...
```
{% endcode %}

{% hint style="info" %}
 補充說明 \_\_init\_\_ 的作用：
{% endhint %}

{% hint style="success" %}
* initial 即 \*\*初始化\*\*
* 當類別指向物件時，會初始化以下參數的設定。
* 例如上述的 name, sexual, mammal ...
{% endhint %}

以下範例示範直接賦予參數的例子:

{% code title="class\_Init.py" %}
```python
class Student(object):
    
    def __init__(self):         #不加參數即直接賦予參數
        self.name = "jamie"
        self.age = 24
        self.job = "python engineer"
        
        
jamie = Student()               #此處就不用賦予參數值
jamie.name  #output "jamie"
jamie.age   #output "24"
jamie.job   #output "python engineer"
```
{% endcode %}




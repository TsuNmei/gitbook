---
description: python 處理 datetime packages
---

# Import datetime

## Packages installation

```
$ pip install datetime
```

Once you're install already, you can follow the tutorial down bellow : 

> date / time / datetime

<table>
  <thead>
    <tr>
      <th style="text-align:left"></th>
      <th style="text-align:left">&#x985E;&#x5225;</th>
      <th style="text-align:left">&#x5E38;&#x7528;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">date</td>
      <td style="text-align:left">&lt; class date &gt;</td>
      <td style="text-align:left"><code>date.today()</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">time</td>
      <td style="text-align:left">&lt;class time&gt;</td>
      <td style="text-align:left"><code>time.time() </code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">datetime</td>
      <td style="text-align:left">&lt;class datetime&gt;</td>
      <td style="text-align:left">
        <p><code>datetime.now()  </code>
        </p>
        <p><code>datetime.today()</code>
        </p>
      </td>
    </tr>
  </tbody>
</table>

### Datetime - date

```python
# 引用套件
import datetime


# 今日日期
today = datetime.date.today()
print(today)
# Output: datetime.date(2020, 11, 24)

print(today.year, today.month, today.day, sep='\n')
# Year: 2020 
# Month: 11
# Day: 24

print(today.isoweekday())
# Output: 2 (Tuesday 11/24)
# 週一: 1 ; 週二:2 ...; 週日:7

today.ctime()
# Output: 'Tue Nov 24 00:00:00 2020'

```

### Datetime - time

```python
# import 
from datetime import time

print(time.hour, time.minute, time.second)

time.max
# Output: datetime.time(23, 59, 59, 999999)
time.min
# Output: datetime.time(0, 0)
```

### Datetime - datetime

```python
import datetime

datetime.datetime.now()
# Output: datetime.datetime(2020, 11, 24, 0, 42, 52, 515630)

datetime.datetime.today()
# Output: datetime.datetime(2020, 11, 24, 0, 43, 45, 680482)

today = datetime.datetime.today()
print(today.date())
# Output: datetime.date(2020, 11, 24)

datetime.today.timestamp()
# Output: 1606149859.589663

datetime.today.strftime("%Y-%m-%d %H:%M:%S")
# Output: '2020-11-23 23:51:47'

date = "2020/11/24"
datetime.datetime.strptime(date, "%Y/%m/%d")
# Output: datetime.datetime(2020, 11, 24, 0, 0)

# Yesterday
today = datetime.datetime.today()
oneday = datetime.delta(days=1)
yesterday = today - oneday
print(yesterday)
# Output: datetime.date(2020, 11, 23)


dt1 = datetime.datetime(2020, 1, 1, 10, 30, 20) 
dt2 = datetime.datetime(2021, 1, 1, 10, 30, 20) 
delta = dt2 - dt1
print(delta)
# Output: datetime.timedelta(days=366)
print(delta.days)
# Output: 366
```

### Formatting 

| 功能 | 描述 |
| :--- | :--- |
| `datetime.strftime` | 將 `<class: datetime.datetime>` 轉為字串  |
| `datetime.strptime` | 將 字串 轉為  `<class: datetime.datetime>` |

#### Example : 

```python
# "12:30"
datetime.datetime(2020, 12, 23, 12, 30).strftime("%H:%M")
# datetime.datetime(2020, 12, 23, 12, 30)
datetime.strptime("12:30", "%H:%M")   
```

[https://www.delftstack.com/zh-tw/howto/python/how-to-convert-string-to-datetime/](https://www.delftstack.com/zh-tw/howto/python/how-to-convert-string-to-datetime/)


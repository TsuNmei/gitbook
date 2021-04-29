---
description: － 獲取資料
---

# Get item

## Get Item

> 取得  table 內 的 item

### ＊ 取得一個 item

```python
import boto3

# Make sure credential setup already

dynamodb = boto3.resource('dynamodb')

try:        
    table = dynamodb.Table("TableName")
        
    item = {
            'Author': "Jamie",
            'Title': "Holly Mommy",
            'Score': 666,
            }

    resp = table.get_item(Key={
                "Author": "John Grisham", 
                "Title": "The Rainmaker"
                })
                    
    print(resp['Item'])
    
    
except Exception as e:
    print("There's a error occurs!")
    print(repr(e))    

        
# Output:   
{
  'Title': 'The Rainmaker', 
  'Formats': {
      'Audiobook': '8WE3KPTP', 
      'Hardcover': 'J4SUKVGU', 
      'Paperback': 'D7YF4FCX'
      }, 
  'Author': 'John Grisham', 
  'Category': 'Suspense'
}
          
```

### ＊Query Items

```python
import boto3
from boto3.dynamodb.conditions import Key, Attr

"""
省略 credentials 部分
      ...
      ..
"""

table = dynamodb.Table('Books')

# Key是指 partition Key , eq='equal' 
resp = table.query(
    KeyConditionExpression=Key('Author').eq('John Grisham')
    )


for item in resp['Items']:
    print(item)

# print出 author是 "John Grisham" 的 items
{'Title': 'The Firm', 'Formats': {'Hardcover': 'Q7QWE3U2', 'Paperback': 'ZVZAYY4F', 'Audiobook': 'DJ9KS9NM'}, 'Author': 'John Grisham', 'Category': 'Suspense'}
{'Title': 'The Rainmaker', 'Formats': {'Audiobook': '8WE3KPTP', 'Hardcover': 'J4SUKVGU', 'Paperback': 'D7YF4FCX'}, 'Author': 'John Grisham', 'Category': 'Suspense'}

# Use filterexpression to extract more specific target data 
resp = table.query(
    KeyConditionExpression=Key("Author").eq("John Grisham"),
    FilterExpression=Attr("Title").begins_with("The")
    )

for item in resp['Items']:
    print(item)

```

{% hint style="success" %}
* KeyConditionExpression     \# Key 搜索表示法
* FilterExpression                    \# Attribute 表示法
* AttributeDefinition \([REF](https://boto3.amazonaws.com/v1/documentation/api/latest/reference/customizations/dynamodb.html#dynamodb-conditions)\)
  * "eq" -&gt; equal
  * "lt" -&gt; less than
  * "gt" -&gt; greater than ...
{% endhint %}

### ＊Scan Items \(避免使用: cost 計費較多\)  

```python
import boto3
from boto3.dynamodb.conditions import Key, Attr

"""
省略 credentials 部分
      ...
      ..
"""

table = dynamodb.Table('Books')

# Key是指 partition Key , eq='equal' 
resp = table.scan()


for item in resp['Items']:
    print(item)

# print出所有books內的 items
```


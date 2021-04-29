---
description: － 更新資料
---

# Update\_item

## Update Items

> 透過 boto3 api 建立 更新 items：

### ＊ update items

```python
import boto3

# Make sure credential setup already

# Need attr: service_name, region_name, access_token, secret_token
dynamodb = boto3.resource('dynamodb')

try:        
    table = dynamodb.Table("TableName")
        
    item = {
            'Author': "Jamie",
            'Title': "Holly Mommy",
            'Score': 666,
            }
    table.put_item(
         Item=item
    )
        
    print("Item insert into the table succesfully!")
        
except Exception as e:
    print("There's a error occurs!")
    print(repr(e))    
        
```

### ＊批次建立 Items

```python
import boto3

"""
省略 credentials 部分
      ...
      ..
"""

table = dynamodb.Table('Books')

try:
    with table.batch_writer() as batch:
        batch.put_item(
            Item={
                "Author": "John Grisham",
                "Title": "The Rainmaker",
                "Category": "Suspense",
                "Formats": {
                    "Hardcover": "J4SUKVGU",
                    "Paperback": "D7YF4FCX"
                }
            }
        )
        batch.put_item(
            Item={
                "Author": "John Grisham",
                "Title": "The Firm",
                "Category": "Suspense",
                "Formats": {
                    "Hardcover": "Q7QWE3U2",
                    "Paperback": "ZVZAYY4F",
                    "Audiobook": "DJ9KS9NM"
                }
            }
        )
        batch.put_item(
            Item={
                "Author": "James Patterson",
                "Title": "Wonder Girl",
                "Category": "Romantics",
                "Formats": {
                    "Hardcover": "C9NR6RJ7",
                    "Paperback": "37JVGDZG",
                }
            }
        )
        
    print("Item created successfully!")

except Exception as e:
    print("Occur Error!!")
    print(repr(e))

```




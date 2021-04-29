---
description: － 建立資料表
---

# Create\_table

## Create A Table

> 透過 client 或是 resource 來建立 table :

{% hint style="success" %}
* Client 為 **`low-level`**，是指 client 限制為 dynamodb 使用的 method。
* Resource 為 **`high-level`**，是指 resource 可定義其他 AWS service。
  * 例如： `boto3.resource('s3', region_name='tokyo')` 
{% endhint %}

### ＊ Client example : 

```python
# Import first
import boto3

# Make sure credientials setup already

# Need attr: service_name, region_name, access_token, secret_token
client = boto3.client('dynamodb')

# Attr: TableName, AttributeDefinitions, KeySchema, ProvisionedThroughput
resp = client.create_table(
        TableName="Books",
        # 定義 Keyschema: 1) HASH->主鍵.  2)RANGE->排序鍵.
        # 以下為 複合鍵 (HASH+RANGE)
        KeySchema=[
            {
                "AttributeName": "Author",
                "KeyType": "HASH"
            },
            {
                "AttributeName": "Title",
                "KeyType": "RANGE"
            }
        ],
        # 定義鍵屬性: "S"->string / "B"->int / "N":number
        AttributeDefinitions=[
            {
                "AttributeName": "Author",
                "AttributeType": "S"
            },
            {
                "AttributeName": "Title",
                "AttributeType": "S"
            }
        ],
    
        # 控制「讀取」與「寫入」的量
        # Dynamodb 限制 每次讀取最大限量為 1MB (Filter前)
        ProvisionedThroughput={
            "ReadCapacityUnits": 1,   #1kb
            "WriteCapacityUnits": 1   #1kb
        }
    )
```

### ＊ Resource example : 

```python
# Import first
import boto3

credientials = {
    "ACCESS_KEY": "Paste Your access key from AWS account",
    "SECRET_KEY": "Paste Your secret key from AWS account"
}

# Need attr: service_name, region_name, access_token, secret_token
dynamodb = boto3.resource(
        'dynamodb', 
        region_name='us-east-1', 
        aws_access_key_id=ACCESS_KEY, 
        aws_secret_access_key=SECRET_KEY
        )

# Attr: TableName, AttributeDefinitions, KeySchema, ProvisionedThroughput
resp = dynamodb.create_table(
        TableName="Books",
        # 定義 Keyschema: 1) HASH->主鍵.  2)RANGE->排序鍵.
        # 以下為 複合鍵 (HASH+RANGE)
        KeySchema=[
            {
                "AttributeName": "Author",
                "KeyType": "HASH"
            },
            {
                "AttributeName": "Title",
                "KeyType": "RANGE"
            }
        ],
        # 定義鍵屬性: "S"->string / "B"->int / "N":number
        AttributeDefinitions=[
            {
                "AttributeName": "Author",
                "AttributeType": "S"
            },
            {
                "AttributeName": "Title",
                "AttributeType": "S"
            }
        ],
    
        # 控制「讀取」與「寫入」的量
        # Dynamodb 限制 每次讀取最大限量為 1MB (Filter前)
        ProvisionedThroughput={
            "ReadCapacityUnits": 1,   #1kb
            "WriteCapacityUnits": 1   #1kb
        }
    )
```




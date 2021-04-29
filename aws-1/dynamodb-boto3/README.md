---
description: NoSQL database from AWS
---

# Dynamodb

## Dynamo DB

DynamoDB 有 Python SDK 可以用叫 **`boto3`**。DynamoDB 為「**非關聯式資料庫**」與傳統的「關聯式資料庫」有所不同。也因為 DynamoDB 是 **NoSQL 資料庫**，因此可打造隨應用程式發展的彈性結構描述設計。

DynamoDB 利用近乎**無限的擴展**來提供**低延遲效能**，所以無需擔心因為應用程式成長而產生的效能瓶頸。DynamoDB 可透過 HTTP API 或 HTTPS 端點加以存取，而可為您的資料庫提供簡單、安全的互動模型。

### NoSQL / SQL 比較圖

![&amp;lt;From AWS website&amp;gt;](../../.gitbook/assets/image%20%281%29.png)

| \* | NoSQL \(Dynamo\) | SQL\(RDS\) |
| :--- | :--- | :--- |
| 資料表 | Table | Table |
| 資料 | **Item** | Data |
| 欄位 | **Attribute** | Column |
| 索引 | **Partition key** | Primary key |
| Method | Create/Get/Update/Delete | Create/Get/Update/Delete |

### boto3 實作

> 本次主題是透過 python3 SDK - boto3 實作：

```bash
# Install First
$ pip install boto3
 
# Install setup.py file
$ curl -sL https://s3.amazonaws.com/ddb-deep-dive/dynamodb.tar | tar -xv
```

{% hint style="info" %}
首先你要先有 AWS account \(IAM / Normal\)
{% endhint %}

AWS 提供的 tutorial 來練習 dynamodb API CRUD 的實際操作 \(boto3\)

![&amp;lt;DynamoDB preview&amp;gt;](../../.gitbook/assets/image%20%284%29.png)

[https://aws.amazon.com/tw/getting-started/hands-on/create-manage-nonrelational-database-dynamodb/2/](https://aws.amazon.com/tw/getting-started/hands-on/create-manage-nonrelational-database-dynamodb/2/)


# Setup Credentials

## Credential setup in MacOS

> 當使用 boto3 時，遠端連線到 AWS dynamodb\(ddb\) 需要設定 credential 。

### ＊ Methods One

```
$ pip install awscli
$ aws configure

# AWS Access Key ID [None]: 請輸入你的 aws access-token-key
# AWS Secret Access Key [None]: 請輸入你的 aws sercet-token-key
# Default region name [None]: 輸入region地區(預設ap-northeast-1)
# Default output format [None]: json
```

### ＊ Methods Two

{% code title="/Users/jmdev/.aws/credentials" %}
```bash
# 創建路徑在上方 (本機端的user/.aws)

$ cd /Users/jmdev/.aws/credentials
$ vi credentials
[default]
aws_access_key_id=AKIAIOSFODNN7EXAMPLE
aws_secret_access_key=wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY

$ vi config
[default]
region=ap-northeat-1
output=json


$ your_boto3.py 
# 執行看看是否work already
client = boto3.client()
```
{% endcode %}

### Reference :

> [https://boto3.amazonaws.com/v1/documentation/api/latest/guide/credentials.html](https://boto3.amazonaws.com/v1/documentation/api/latest/guide/credentials.html)


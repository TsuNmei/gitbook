# Simple Notification Service

## SNS

![](../.gitbook/assets/image%20%285%29.png)

```
$ give me super-powers
```

### \* 訂閱 Subscription

{% hint style="info" %}
Need to edit zappa\_settings.json
{% endhint %}

```text
events: [
      {
         function: callback.profile_callback,
         event_source: {
         arn:  arn:aws:sns:ap-northeast-1:407141366849:hwh-stg-profile,
         events: [
            sns:Publish
         ]
         }
      }
   ]
```




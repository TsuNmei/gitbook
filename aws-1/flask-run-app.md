# Flask Run App

## 如何在 Flask 跑 python app.py

```
$ AWS_PROFILE=revtel-dev python3 app.py
```

## 自動寄信 \(auth-v3\)

### AWS- DDB \(dev.auth.issuer\)

```text
{
   "client":"hwh",
   "method":"email",
   "name":"interview",
   "redirect_url":"https://hwh-api-dev.revtel2.com/interview/confirm",
   "sender":"send-interview",
   "title":"面試通知",
   "type":"redirect"
}
```


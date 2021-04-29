# Request & Response

## Request from client

> REST framework's `Request` class extends the standard `HttpRequest`, adding support for REST framework's flexible request parsing and request authentication.

#### How To Use ?

```python
from rest_framework import response, views

# classifiy a List view
class VideoListView(views.APIView):
    permissions_classes = [permissions.IsAuthenticated, ]
    serializer_class = ChannelSerializer
    
    def post(self, request):
        # get the request post_data
        data = request.data
        serializer = self.serializer_class(data=data)
        # check the data mapping database or not 
        serializers.is_valid(raise_exception=True)
        # real_data means the data is verified 
        real_data = serializers.validated_data
        # request.user is mean for sender (user profile)
        instance = serializers.save(owner=self.request.user)
        return response.Response(
            self.serializer_class(instance).data,  # response data 
            201 # status code response (create success)
            )
```

| Methods | Explanation | Example |
| :--- | :--- | :--- |
| Request.data | Get all of post data **\(json\)** | {"name":"admin"} |
| Request.query\_params | Get all of the query behind urls **\(query\_set\)** | Q\[{"name":"jamie"}\] |
| Request.user | Get the sender user data  | &lt;user: admin&gt; |
| Request.auth | Get the user token of the sender | &lt;token ......&gt; |

## Response from request

#### How To Use ?

```python
from rest_framework import response, views

class VideoListView(views.APIView):
    permissions_classes = [permissions.IsAuthenticated, ]
    serializer_class = ChannelSerializer
    
    def get(self):
        # sender user profile
        user = self.request.user
        channels = user.channels.all()
        serializer = self.serializer_class(channels, many=True)
        return response.Response(serializer.data, 200)
```

| Attribute | Explanation | Example |
| :--- | :--- | :--- |
| data | 需要經過 serialized 的 data | serializer.data |
| status\_code | 回應狀態 code | status\_code=200 |


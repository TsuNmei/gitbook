---
description: export the database data to csv
---

# Export CSV

## How to user Django framework to export CSV

> 如何用 Django 輸出 csv 檔案 或是其他文書檔

### 一、安裝套件

```text
pip install django-import-export
```

### 二、settings.py 加上

```text
INSTALLED_APPS = [    
    'django.contrib.admin',    
    'django.contrib.auth',    
       ...
       ..
    'import_export', ]    #<--這個

# Admin import-export       
STATIC_URL = '/static/'
STATIC_ROOT = os.path.join(BASE_DIR, 'static')
IMPORT_EXPORT_USE_TRANSACTIONS = True
```

###  三、Run setting config 設定

```bash
$ python3 manage.py collectstatic
```

### 四、Admin.py

```python
from django.contrib import admin

# Register your models here.
from import_export import resources
from api.models import Item #Your models 
from import_export.admin import ImportExportModelAdmin

# Your model Resource (Inherit ModelResource)
class ItemResource(resources.ModelResource):
    class Meta:
        model = Item

# Your ItemAdmin display
class ItemAdmin(ImportExportModelAdmin):
    resource_class = ItemResource


admin.site.register(Item, ItemAdmin)

```

### 五、啟動 server

```python
$ python3 manage.py runserver
```

### 六、Admin 畫面

![](../../.gitbook/assets/jie-tu-20201119-shang-wu-11.34.55%20%281%29.png)

### Official Getting Started

```python
# from django official

import csv
from django.http import HttpResponse

def some_view(request):
    # Create the HttpResponse object with the appropriate CSV header.
    response = HttpResponse(content_type='text/csv')
    response['Content-Disposition'] = 'attachment; filename="somefilename.csv"'

    writer = csv.writer(response)
    writer.writerow(['First row', 'Foo', 'Bar', 'Baz'])
    writer.writerow(['Second row', 'A', 'B', 'C', '"Testing"', "Here's a quote"])

    return response
```

> #### REF： [https://django-import-export.readthedocs.io/en/stable/getting\_started.html](https://django-import-export.readthedocs.io/en/stable/getting_started.html)


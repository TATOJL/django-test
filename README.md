# django(windows)

 下載django
 ---

 __Anaconda虛擬環境下載:__
```shell

conda install -c anaconda django

```

 __pip下載:__
```shell

py -m pip install Django

```

 查看django版本
 ---


在終端機輸入:
```shell 

python -m django --version 

```

 創建django專案
 ---

 在終端機輸入:
```shell

django-admin startproject project

```

 ![projecct](images/project.png)

 測試django
 ---

 cd到專案的資料夾中，然後在終端機輸入:
```shell

python manage.py runserver

```
 
瀏覽器輸入127.0.0.1:8000在本機測試django:
![django](images/django.png)

在專案中新增views.py，並在此輸入以下程式碼:
```py

from django.http import HttpResponse

def hello(request):
    return HttpResponse("hello world")

```
![views](/images/views.png)

url.py中新增以下程式碼:  
```py
 
from django.urls import re_path as urls 
from . import views

```
```py
 
url(r'^$',views.hello)

```
![urlspy](/images/urls.py.png)

瀏覽器輸入127.0.0.1:8000在本機測試頁面:
![hellowworld](/images/helloworld.png)

新增django app
---

cd到專案的資料夾中，然後在終端機輸入:
```shell

python manage.py startapp app

```
 ![app](images/app.png)

把app加到設定黨(settings.py)裡:
![settings](images/app-settings.png)

在app的views.py中加入以下程式碼:
```py

from django.http import HttpResponse

def index(request):
      return HttpResponse("hello app")

```
![settings](images/app-views.png)

最後在url.py加入以下程式碼:    
```py

from app.views import index

```
```py

url(r'^app/',index)

```
![settings](images/app-views.png)

瀏覽器輸入127.0.0.1:8000/app在本機測試頁面:
![test](images/app-test.png)

新增模板與靜態文件
---

在專案資料夾中，新增以下文件:  
![app-statics](images/statics.png)








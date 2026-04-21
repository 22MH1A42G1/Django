### day-02

### Document Notes : https://docs.djangoproject.com/en/6.0/

### Steps 

> **step1**  : create virtual environment with python and django
```
conda create --name env1 python==3.13 django==5.2
```
> **step2** : activate environment
```
conda activate env1
```
> **step3** : go to the location where you want create django project
    
> **step4** : create project
```
django-admin startproject proj1
```
it creates 5 files inside project directory and also manage.py in base directory
```
proj1 # base directory
  proj1  # project directory
    -> __init__.py
    -> asgi.py
    -> settings.py
    -> urls.py
    -> wsgi.py
```

> **step5** : cd project_name
> **step6** : open project inside vscode
```
code .
```
> **step7** : start project
```
python manage.py runserver
```
> **step8** : access project in browser 
- copy url which is generated and paste on browser address bar
- after server running their a file created that is --> db.sqlite3


## URLs 

#### URL configuration for proj1 project.

> The `urlpatterns` list routes URLs to views. For more information please see:
- https://docs.djangoproject.com/en/5.2/topics/http/urls/

*Examples*:
- Function views
    1. Add an import:  from my_app import views
    2. Add a URL to urlpatterns:  path('', views.home, name='home')
- Class-based views
    1. Add an import:  from other_app.views import Home
    2. Add a URL to urlpatterns:  path('', Home.as_view(), name='home')
- Including another URLconf
    1. Import the include() function: from django.urls import include, path
    2. Add a URL to urlpatterns:  path('blog/', include('blog.urls'))

## Fuction Based steps
> step 01: import libraries HttpResponse or render
- HttpResponse : inline code linker
```
from django.http import HttpResponse
```
- render : external code linker
```
from django.shortcuts import render
```
> step 02: write your code that connection in functions. here sample code for urls.py
```
from django.contrib import admin
from django.urls import path
from django.http import HttpResponse
from django.shortcuts import render
def home(request):
    return HttpResponse("<h1>Hello, World!</h1>")
def about(request):
    return HttpResponse("<h1>About Page</h1>")
def contact(request):
    return render(request, 'contact.html')

urlpatterns = [                       # 127.0.0.1:8000 --> base URL
    path('admin/', admin.site.urls),  # 127.0.0.1:8000/admin --> admin page
    path('', home),                   # 127.0.0.1:8000 --> home page  (base URL)
    path('about/', about),            # 127.0.0.1:8000/about --> about page
    path('contact/', contact),        # 127.0.0.1:8000/contact --> contact page
]

```
> step03: Add file path *temp* in **settings.py** for templates linking (contact.html inside this file) 
- we can just add [BASE_DIR / 'templates'] this path.
- and templates folder shoud be in outside project directory.
```
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [BASE_DIR / 'templates'],  # Add this line to specify the templates directory
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]
```
> step 04:  access project in browser 
- copy url which is generated and paste on browser address bar
- 127.0.0.1:8000 --> home page  (base URL)
- 127.0.0.1:8000/about --> about page
- 127.0.0.1:8000/contact --> contact page 











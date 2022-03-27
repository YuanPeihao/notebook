# DjangoNote

# 1. Setup Django project

# check Django version

`python -m django --version`

# establish a Django project

`django-admin startproject mysite`

# start the Django development server

`python manage.py runserver`

# change the server’s port

`python manage.py runserver 8080`

# change the server’s IP

`python manage.py runserver 0:8000`

# create your app

`python manage.py startapp polls`

# projects vs. apps

An app is a web application that does something – e.g., a blog system, a database of public records or a small poll app. A project is a collection of configuration and apps for a particular website. A project can contain multiple apps. An app can be in multiple projects.

# 2. View

# write your first view

polls/views.py
```
from django.http import HttpResponse


def index(request):
    return HttpResponse("Hello, world. You're at the polls index.")
```

polls/urls.py
```
from django.urls import path
from . import views


urlpatterns = [
    path('', views.index, name='index'),
]
```

mysite/urls.py
```
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('polls/', include('polls.urls')),
    path('admin/', admin.site.urls),
]
```

# 3. Datebase

# create the tables in the database

`python manage.py migrate`

The migrate command looks at the INSTALLED_APPS setting and creates any necessary database tables according to the database settings in your mysite/settings.py file and the database migrations shipped with the app.

# create data models

polls/models.py
```
from django.db import models


class Question(models.Model):
    question_text = models.CharField(max_length=200)
    pub_date = models.DateTimeField('date published')


class Choice(models.Model):
    question = models.ForeignKey(Question, on_delete=models.CASCADE)
    choice_text = models.CharField(max_length=200)
    votes = models.IntegerField(default=0)
```

# install app

mysite/settings.py
```
INSTALLED_APPS = [
    'polls.apps.PollsConfig',
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
]
```

# after update models.py

`python manage.py makemigrations polls`

By running makemigrations, you’re telling Django that you’ve made some changes to your models (in this case, you’ve made new ones) and that you’d like the changes to be stored as a migration.

`python manage.py migrate`

run migrate again to create those model tables in your database



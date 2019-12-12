# Django-Hello-World
Step 1: Installing Django 

1)Open Terminal. Install Python Virtual Environment (if not already installed) using 'pip install virtualenv' (ignore the single quotes)

2)Create and enter a root directory for all your projects:

>mkdir myprojects

>cd myprojects

3)Create a virtual environment:

>myprojects>virtual django

4) Install Django:

>myprojects>pip install django

Step 2: Creating a Django Project

1) Create your django project:

>myprojects>django-admin startproject GCI

2)Test the development server:

>myprojects>GCI>python manage.py runserver

You should get the following output:

Performing system checks...

System check identified no issues (0 silenced).

You have unapplied migrations; your app may not work properly until they are applied.
Run 'python manage.py migrate' to apply them.

December 11, 2019 - 15:50:53
Django version 2.2, using settings 'mysite.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CONTROL-C.


3)Creating the polls app:

>myprojects>GCI>python manage.py startapp polls

4)Edit polls/views.py:

from django.http import HttpResponse


def index(request):
    return HttpResponse("Hello, world.")
    
    
5) Create a urls.py in the polls directory, and edit it:

from django.urls import path

from . import views

urlpatterns = [
    path('', views.index, name='index'),
]


6) Edit the GCI/urls.py (NOT THE POLLS VIEWS.PY):

from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('polls/', include('polls.urls')),
    path('admin/', admin.site.urls),
]

7) Run the server and go to  http://localhost:8000/polls/

You will see the 'Hello world' message printed.



## This Django app is build for Custom Authentication, build by [Abhijith KR](https://github.com/abhi7745).

### Authentication Views
It provides several views that you can handle ( index, signup, login, logout ) and all are written using function-based views.

### Contents :-

#### app
- accounts/views.py (index, signup, login, logout)
- accounts/models.py (User_Account)
- accounts/urls.py (login, signup, logout)

#### static
- accounts/dashboard/assets/(css, js, etc..)

#### templates
- accounts/(signup.html,login.html)
- admin/(dashboard.html, sidebar.html)
- /base.html
- /index.html

### Requirements
- django

Quick start
-----------

#### 1. How to use the resuable app
#### Case -1 ( Using git clone command, then follow these steps ) :
- Create a fresh folder for your project 
- Make sure your working directory (cloning folder) doesn't have these file names ['accounts', 'static', 'templates', 'readme.md'], it will raise error.
- Clone this repository into your project directory
- Make sure the git clone 'url' ends with a period '.' 

```bash
  git clone https://github.com/abhi7745/reusable_django_app-with_custom_authentication_pack.git .
```
- Alert : Delete the repository .git and readme.md file and make your own.

#### Case - 2 ( Downloading file from github, then follow these steps ) :
If you want to download this repository as zip file, follow these steps:
- Download the repository from github
- Unzip the file
- Copy the files ['accounts', 'static', 'templates'] from "reusable_django_app-with_custom_authentication_pack" folder and paste it in the project root folder. 
- Alert : Don't copy the repository .git and readme.md file, make your own.

#### 3. Create your own django project :
- Make sure you have Django installed on your machine or virtual environment.
- If you are using virtual environment, then activate it.

```django-admin startproject projectname```

#### 4. Add "accounts" to your INSTALLED_APPS setting like this::

``` bash
    INSTALLED_APPS = [
        ...
        'accounts',
    ]
```


#### 5. Include the accounts URLconf in your project urls.py like this::

```bash

from django.urls import path, include
from accounts.views import index

urlpatterns = [
    path('', index, name='index'),
    path('accounts/', include('accounts.urls')),
]
```

#### This will include the following URL patterns
```bash
urlpatterns = [
    path('login/', login_page, name='login'),
    path('signup/', signup, name='signup'),
    path('logout/', logout_page, name='logout'),
]
```
#### 6. Add ```import os``` at the top of setting.py file

#### 7. Add "[os.path.join(BASE_DIR,'templates')]" to your TEMPLATES setting like this::

```bash
TEMPLATES = [
    {
        ...
        'DIRS': [os.path.join(BASE_DIR,'templates')],
        ...
       
    },
]
```
#### 8. Add these lines in your setting::
```bash
# static folder setup
STATIC_URL = 'static/'
STATICFILES_DIRS= [os.path.join(BASE_DIR,'static')]
```

#### 9. Run ``python manage.py migrate`` to create the accounts models.

#### 10. Start the development server ``python manage.py runserver`` and visit
- http://127.0.0.1:8000/
- http://127.0.0.1:8000/login
- http://127.0.0.1:8000/signup
- http://127.0.0.1:8000/logout
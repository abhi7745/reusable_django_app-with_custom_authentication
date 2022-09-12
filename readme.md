## This Django app is build for Custom Authentication, build by [Abhijith KR](https://github.com/abhi7745).

### Authentication Views
It provides several views that you can handle ( index, signup, login, logout )

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

#### 1. Clone this repository into your project root directory

```bash
  git clone https://github.com/abhi7745/reusable_django_app-with_custom_authentication_pack.git
```
#### 2. Add "accounts" to your INSTALLED_APPS setting like this::

``` bash
    INSTALLED_APPS = [
        ...
        'accounts',
    ]
```

#### 3. Include the accounts URLconf in your project urls.py like this::

```bash
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
#### 4. Add ```import os``` at the top of setting.py file

#### 5. Add "[os.path.join(BASE_DIR,'templates')]" to your TEMPLATES setting like this::

```bash
TEMPLATES = [
    {
        ...
        'DIRS': [os.path.join(BASE_DIR,'templates')],
        ...
       
    },
]
```
#### 6. Add these lines in your setting::
```bash
# static folder setup
STATIC_URL = 'static/'
STATICFILES_DIRS= [os.path.join(BASE_DIR,'static')]
```

#### 7. Run ``python manage.py migrate`` to create the accounts models.

#### 8. Start the development server ``python manage.py runserver`` and visit 
- http://127.0.0.1:8000/
- http://127.0.0.1:8000/login
- http://127.0.0.1:8000/signup
- http://127.0.0.1:8000/logout
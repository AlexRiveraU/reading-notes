# Django Custom User

This topic matters as it relates to learning best practices to implement the Django Custom User Model, and using DjangoX. 

---

### Django Custom User Model

#### Setup

We need to create a new Django project and an app called `account`. Do not run migrate to configure the database yet. It's important to wait until after we've created our new custom user model.

#### AbstractUser vs AbstractBaseUser

There are two modern ways to create a custom user model: 
* `AbstractUser`
* `AbstractBaseUser` (requires much more work)

>Required fields
* email
* username
* date_joined
* last_login
* is_admin
* is_active
* is_staff
* is_superuser

#### Custom User Model

* update django_project/settings.py
* create a new `CustomUser` model
* create new `UserCreation` and `UserChangeForm`
* update the admin

We need to create a `forms.py` file in the app, and write the code to subclass the existing forms.

```python
from django import forms
from django.contrib.auth.forms import UserCreationForm, UserChangeForm
from .models import CustomUser

class CustomUserCreationForm(UserCreationForm):
    class Meta:
        model = CustomUser
        fields = ("username", "email")

class CustomUserChangeForm(UserChangeForm):
    class Meta:
        model = CustomUser
        fields = ("username", "email")
```

#### Templates/Views/URLs

The goal is to have a homepage with links to `log in`, `log out`, and `sign up`. To set the redirect links for log in and log out, we need to add the following lines at the bottom of `settings.py`:

```python
LOGIN_REDIRECT_URL = "home"
LOGOUT_REDIRECT_URL = "home"
```

We also need to create a registration folder within templates. Here is where Django will look for the log in template. We will also put our `signup.html` template in there.

* [*source*](https://learndjango.com/tutorials/django-custom-user-model)
* [*source*](https://www.youtube.com/watch?v=eCeRC7E8Z7Y&t=59s)

---

### DjangoX

DjangoX can be installed via Pip, Pipenv, or Docker. Clone following repo:

```commandline
$ git clone https://github.com/wsvincent/djangox.git
```

[*source*](https://github.com/wsvincent/djangox)

### Things I want to know more about

* I would like to know more about how to implement Django Custom User Model efficiently.

---

[-back](https://alexriverau.github.io/reading-notes/code401)

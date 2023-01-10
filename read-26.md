# Intro to Django

This topic matters as it relates to getting started with Django.

---

## Getting started with Django

### Intro to Django

**Object-relational mapper**

Django allows us to define our data models entirely in Python. We get a rich, dynamic database-access API for free, but we can still write SQL if needed. (e.g.)

```python
from django.db import models

class Person(models.Model):
    first_name = models.CharField(max_length=30)
    last_name = models.CharField(max_length=30)
```

**URLs and views**

Django encourages beautiful URL design and does not put any cruft in URLs, like .php or .asp. To design URLs for an app, we create a Python module called a URLconf. It contains a simple mapping between URL patterns and your views. (e.g.)

```python
from django.urls import path
from . import views

urlpatterns = [
    path('articles/2003/', views.special_case_2003),
    path('articles/<int:year>/', views.year_archive),
    path('articles/<int:year>/<int:month>/', views.month_archive)
]
```

**Templates**

Django’s templates are designed to feel comfortable and easy-to-learn to those used to working with HTML, like designers and front-end developers. But it is also flexible and highly extensible, allowing developers to augment the template language as needed.

**Forms**

Django provides a powerful form library that handles rendering forms as HTML, validating user-submitted data, and converting that data to native Python types. Django also provides a way to generate forms from our existing models and use those forms to create and update data. (e.g.)

```python
from django import forms

class BandContactForm(forms.Form):
    subject = forms.CharField(max_length=100)
    message = forms.CharField()
    sender = forms.EmailField()
    cc_myself = forms.BooleanField(required=False)
```

**Authentication**

It comes with a full-featured and secure authentication system. It handles user accounts, groups, permissions and cookie-based user sessions. This lets us easily build sites that allow users to create accounts and safely log in/out. (e.g.)

```python
from django.contrib.auth.decorators import login_required
from django.shortcuts import render

@login_required
def my_protected_view(request):
    return render(request, 'protected.html', {'user': request.user})
```

**Admin**

One of the most powerful parts of Django is its automatic admin interface. It reads metadata in your models to provide a powerful and production-ready interface that content producers can immediately use to start managing content on your site. It’s easy to set up and provides many hooks for customization. (e.g.)

```python
from django.contrib import admin
from bands.models import Band, Member

class MemberAdmin(admin.ModelAdmin):
    list_display = ('name', 'instrument')
    list_filter = ('band',)
admin.site.register(Band)
admin.site.register(Member, MemberAdmin)
```

**Internationalization**

Django offers full support for translating text into different languages, plus locale-specific formatting of dates, times, numbers, and time zones. It lets developers and template authors specify which parts of their apps should be translated or formatted for local languages and cultures, and it uses these hooks to localize web applications for particular users according to their preferences.

**Security**

Django provides multiple protections against:

* Clickjacking
* Cross-site scripting
* Cross Site Request Forgery (CSRF)
* SQL injection
* Remote code execution

[*source*](https://www.djangoproject.com/start/)

---


### How Django Works Behind the Scenes

Django is an open source Python-based web framework. It was originally developed at the Lawrence Journal-World newspaper by Adrian Holovaty, Simon Willison, and Jacob Kaplan-Moss.

**Django Software Foundation**

The DSF supports and maintains Django in a number of capacities. The largest expense, by far, is the Fellows Program, paid contractors who triage tickets, manage releases, and generally perform the unsexy but necessary work needed to keep Django on track.

**Technical Organization**

Django has a small, core team of trusted volunteers who work alongside the Django Fellows to manage technical side of the Django Project. Django Core members are divided into teams that have authority over the Django Project infrastructure, including the Django Project website itself, the official issue tracker, official mailing lists, IRC channels, and more.

[*source*](https://wsvincent.com/how-django-works-behind-the-scenes/)

---

### Things I want to know more about

* I would like to know more about how to write applications efficiently using Django. 

---

[-back](https://alexriverau.github.io/reading-notes/code401)

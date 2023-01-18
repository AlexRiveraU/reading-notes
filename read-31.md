# Django REST Framework & Docker

This topic matters as it relates to learning how to implement the Django REST framework, and Docker. 

---

### Beginner’s Guide to Docker

 Docker is a way to isolate and run entire applications, regardless of the type of system we're using, whether is a Mac, Windows, or Linux computer. The entire development environment is isolated: programming language, software packages, databases, and more. We don't have to deal with virtual environments anymore.

### Linux Containers

Docker is basically a way to implement Linux containers.

* **Containers:** A type of virtualization, also known as "containerization". They're a lightweight alternative to Virtual Machines.

To better explain this, an analogy we can use here is that of homes and apartments. Virtual Machines are like homes: stand-alone buildings with their own infrastructure including plumbing and heating, as well as a kitchen, bathrooms, bedrooms, and so on. Docker containers are like apartments: they share common infrastructure like plumbing and heating, but come in various sizes that match the exact needs of an owner.

### Containers vs Virtual Environments

* Virtual environments are used to isolate Python software packages locally, but they still rely on a global, system-level installation of Python albeit they can refer to the proper version, and can’t run a production database or other services. 
* Docker containers don't have any of those limitations.

### Install Docker

* We need to download the desktop app on our computer and create a free account.
* We use the command below to confirm we have the correct version:

```commandline
$ docker --version
Docker version 19.03.5, build 633a0ea
```

### Images and Containers

* An image is a snapshot in time of what a project contains. They're made up of one or more image layers
  * `Dockerfile` used to create custom images.
* A container is a running instance of the image.
  * `docker-compose.yml` we use these type of files to control how to run containers.

[*source*](https://wsvincent.com/beginners-guide-to-docker/)

---

### Django for APIs - Library Website

To transform a Django Library Website into a web API, we need to install Django REST framework and create a new URL that acts as an API endpoint.


### Django REST Framework

* To install we run:

```commandline
python -m pip install djangorestframework~=3.13.0
```
* We also need to add our newly installed framework to our project's `settings.py`

```python
INSTALLED_APPS = [
    "rest_framework",
]
```
There are multiple ways to organize these files. We just include API logic in the related app while putting URLs under an `/api/` prefix. We can also create a dedicated apis app for our project using `startapp` and add it to `INSTALLED_APPS` in our local section.

#### URLs

Like configuring a traditional Django URL route. In the project-level django_project/urls.py file include the apis app and configure its URL route.

```python
urlpatterns = [
    path("api/", include("apis.urls")),
]
```

#### Views

Django REST Framework views are similar than traditional Django views, except the end result is serialized data in JSON format. They rely on a model, a URL, and a new file called a `serializer`. A common views to use in these cases is `ListAPIView`.

#### Serializers

The most important–action is to create our serializer. It translates complex data like querysets and model instances into a format that is easy to consume over the internet, typically JSON. It is also possible to “deserialize” data, literally the same process in reverse, whereby JSON data is first validated and then transformed into a dictionary. To create a serializer:

* Create a new file called `apis/serializers.py` and update it as follows:

```python
from rest_framework import serializers

from books.models import Book


class BookSerializer(serializers.ModelSerializer):
    class Meta:
        model = Book
        fields = ("title", "subtitle", "author")
```

#### Deployment and Static Files

Deploying a web API is almost identical to deploying a traditional website. We can use Heroku or any other platform for this purpose.

There are static files included in the Django admin and Django REST Framework browsable API. In order for those to deploy properly we must configure all static files:

* Create a `static` directory.
* Add a `.keep` file so the static directory in included in source control.
* Install the `WhiteNoise` package.

```commandline
python -m pip install whitenoise==6.0.0
```

* Add `WhiteNoise` to the project via `settings.py`. 
  * `whitenoise` above `django.contrib.staticfiles` in `INSTALLED_APPS`. 
  * `WhiteNoiseMiddleware` above `CommonMiddleware`. 
  * `STATICFILES_STORAGE` configuration pointing to WhiteNoise
* Run the `collectstatic` command for the first time to compile all the static file directories and files into one self-contained unit suitable for deployment.

```commandline
python manage.py collectstatic
```

[*source*](https://djangoforapis.com/library-website-and-api/)

### Things I want to know more about

* I would like to know more about how to implement Django REST framework efficiently.

---

[-back](https://alexriverau.github.io/reading-notes/code401)

# Authentication & Production Server

This topic matters as it relates to learning about JSON Web Tokens and Authentication using the DRF. 

---

### JSON Web Tokens

JSON Web Token (JWT) is an open standard (RFC 7519) that defines a compact and self-contained way for securely transmitting information between parties as a JSON object. This information can be verified and trusted because it is digitally signed.

#### JSON Web Token structure

* **Header -** Consists of the type of the token, and the signing algorithm being used.
* **Payload -** Contains the claims, which are statements about an entity and additional data. 
  * Types of claims: 
    * Registered. 
    * Public
    * Private claims.
* **Signature -** We take the encoded header, the encoded payload, a secret, the algorithm specified in the header, and sign that.

[*source*](https://jwt.io/introduction/)

---

### DRF JWT Authentication

The JWT is just an authorization token that should be included in all requests. It's acquired by exchanging a username and a password for an `access token` and a `refresh token`.

* **access token -** Short-lived, expires in about 5 min. Can be customized.
* **refresh token -** Lives a little longer, expires in 24 hours. Can be customized.

In order to use JWT in the DRF, we need to install its library, and update `settings.py` abd `urls.py`:

```commandline
pip install djangorestframework_simplejwt
```

```python
REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': [
        'rest_framework_simplejwt.authentication.JWTAuthentication',
    ],
}
```

```python
from django.urls import path
from rest_framework_simplejwt import views as jwt_views

urlpatterns = [
    path('api/token/', jwt_views.TokenObtainPairView.as_view(), name='token_obtain_pair'),
    path('api/token/refresh/', jwt_views.TokenRefreshView.as_view(), name='token_refresh'),
]
```

[*source*](https://simpleisbetterthancomplex.com/tutorial/2018/12/19/how-to-use-jwt-authentication-with-django-rest-framework.html)

---

### Django Runserver Is Not Your Production Server

`python manage.py runserver` is not meant to be used as part of a production setup. It's not guaranteed to be performant, and it isn't built with security concerns in mind.

#### The right approach

* When a request arrives at our server, it should be passed to a dedicated **web server**. Like Nginx for example.
* We also need a WSGI (Web Server Gateway Interface) **application server**. Like Gunicorn for example.

[*source*](https://vsupalov.com/django-runserver-in-production/)

### Things I want to know more about

* I would like to know more about how to implement JWT with the Django REST framework efficiently.

---

[-back](https://alexriverau.github.io/reading-notes/code401)

# Permissions & Postgresql

This topic matters as it relates to learning about permissions and postgresql. 

---

### Permissions

* Permissions determine whether a request should be granted or denied access. 
* Permission checks are always run at the very start of the view, before any other code is allowed to proceed. 
* Permission checks will typically use the authentication information in the `request.user` and `request.auth` properties to determine if the incoming request should be permitted.
* Permissions are used to grant or deny access for different classes of users to different parts of the API.

### How permissions are determined

* Permissions are defined as a list of permission classes.
* Each permission in the list is checked before running the main body of the view 
* If checks fail, `exceptions.PermissionDenied` or `exceptions.NotAuthenticated` are raised, and the main body of the view will not run.
* Returns a `403 Forbidden` or `401 Unauthorized` response.

### Object level permissions

Object level permissions are used to determine if a user should be allowed to act on a particular object, typically a model instance. They're run in generic views by calling `.get_object()`. Raises`exceptions.PermissionDenied` if the user is not allowed to act on the object.

### Setting the permission policy

The default setting allows unrestricted access `.AllowAny`. We can change it by setting the permission policy globally ourselves:

```python
REST_FRAMEWORK = {
    'DEFAULT_PERMISSION_CLASSES': [
        'rest_framework.permissions.IsAuthenticated',
    ]
}
```

We can also set the authentication policy on a per-view, or per-viewset basis, using the `APIView` class-based views, or with the `@api_view` decorator.

```python
from rest_framework.permissions import IsAuthenticated
from rest_framework.views import APIView

class ExampleView(APIView):
    permission_classes = [IsAuthenticated]
```

```python
from rest_framework.decorators import api_view, permission_classes
from rest_framework.permissions import IsAuthenticated

@api_view(['GET'])
@permission_classes([IsAuthenticated])
```

### API Reference

* `AllowAny` - Permission class that allows unrestricted access, regardless of whether the request was authenticated or unauthenticated.
* `IsAuthenticated` - Permission class that denies permission to any unauthenticated user, and allows permission otherwise.
* `IsAdminUser` - Permission class that denies permission to any user, unless `user.is_staff` is True in which case permission will be allowed.
* `IsAuthenticatedOrReadOnly` - Permission class that allows authenticated users to perform any request. Requests for unauthorised users will only be permitted if the request method is either `GET`, `HEAD` or `OPTIONS`.
* `DjangoModelPermissions` - Permission class that must only be applied to views that have a `.queryset` property or `get_queryset()` method. Authorization is granted if the user is authenticated and has the relevant model permissions assigned.
* `DjangoModelPermissionsOrAnonReadOnly` - Similar to `DjangoModelPermissions`, but also allows unauthenticated users to have read-only access to the API.
* `DjangoObjectPermissions` - Permission class that allows per-object permissions on models. We need to add a permission backend that supports object-level permissions, like django-guardian. It must only be applied to views that have a `.queryset` property or `get_queryset()` method. Authorization is granted if the user is authenticated and has the relevant per-object permissions and relevant model permissions assigned.
* `Custom permissions` - In order to implement custom permissions we need override `BasePermission` and implement either, or both, of the following methods:
  * ```.has_permission(self, request, view)```
  * ```.has_object_permission(self, request, view, obj)```
    * They return True for granted access, and False otherwise.

### Overview of access restriction methods

Three different methods to customize access restrictions on a case-by-case basis:

* `queryset/get_queryset()` - Limits the general visibility of existing objects from the database. The queryset limits which objects will be listed and which objects can be modified or deleted. The get_queryset() method can apply different querysets based on the current action.
* `permission_classes/get_permissions()` - General permission checks based on the current action, request and targeted object. Object level permissions can only be applied to retrieve, modify and deletion actions. Permission checks for list and create will be applied to the entire object type.
* `serializer_class/get_serializer()` - Instance level restrictions that apply to all objects on input and output. The serializer may have access to the request context. The get_serializer() method can apply different serializers based on the current action.

[*source*](https://www.django-rest-framework.org/api-guide/permissions/#permissions)

---

### SQL Practice

* [Review SQL Prework](https://alexriverau.github.io/reading-notes/prep401_read03)


### Things I want to know more about

* I would like to know more about how to implement Django REST framework permissions efficiently, and learn about Postgresql.

---

[-back](https://alexriverau.github.io/reading-notes/code401)

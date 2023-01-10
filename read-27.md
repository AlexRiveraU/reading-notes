# Django Models

This topic matters as it relates to learning about Django models and how to implement them. 

---

## Using models

### Overview

* **Models:** Python objects used by Django applications to access and manage data. They define the structure of stored data. 

When designing models, it makes sense to have separate models for every object, for example: books, books instances and authors.

### Model definition

Models are usually defined in an application's `models.py` file. Implemented as subclasses of `django.db.models.Model`, and can include fields, methods and metadata. (e.g.)

```python
from django.db import models
from django.urls import reverse

class MyModelName(models.Model):
    my_field_name = models.CharField(max_length=20, help_text='Enter field documentation')
    
    class Meta:
        ordering = ['-my_field_name']
        
    def get_absolute_url(self):
        return reverse('model-detail-view', args=[str(self.id)])
        
    def __str__(self):
        return self.my_field_name
```

### Fields

Models can have an arbitrary number of fields, of any type. Each one represents a column of data that we want to store in one of our database tables. Each database record (row) will consist of one of each field value. (e.g.)

```python
my_field_name = models.CharField(max_length=20, help_text='Enter field documentation')
```

### Metadata

We can declare model-level metadata for our Models by declaring class Meta. One of the most useful features of this metadata is to control the default ordering of records returned when you query the model type. (e.g.)

```python
class Meta:
    ordering = ['-my_field_name']
```
```python
ordering = ['title', '-pubdate']
```

### Methods

In every model we should define the standard Python class method `__str__()` to return a human-readable string for each object. This string is used to represent individual records in the administration site. (e.g.)

```python
def __str__(self):
    return self.my_field_name
```

Another common method is `get_absolute_url()`, which returns a URL for displaying individual model records on the website. (e.g.)

```python
def get_absolute_url(self):
    return reverse('model-detail-view', args=[str(self.id)])
```

### Creating and modifying records

To create a record we can define an instance of the model and then call `save()`. We can access the fields in this new record using the dot syntax, and change the values, by calling `save()` to store modified values to the database.

```python
# Create a new record using the model's constructor.
record = MyModelName(my_field_name="Instance #1")

# Save the object into the database.
record.save()

# Access model field values using Python attributes.
print(record.id) # should return 1 for the first record.
print(record.my_field_name) # should print 'Instance #1'

# Change record by modifying the fields, then calling save().
record.my_field_name = "New Instance Name"
record.save()
```

### Searching for records

We can search for records that match certain criteria using the model's objects attribute. We can get all records for a model as a `QuerySet`, using `objects.all()`. The QuerySet is an iterable object, meaning that it contains a number of objects that we can iterate/loop through. The `filter()` method allows us to filter the returned `QuerySet` to match a specified text or numeric field against particular criteria.

```python
all_books = Book.objects.all()
```

```python
wild_books = Book.objects.filter(title__contains='wild')
number_wild_books = wild_books.count()
```

### Re-run the database migrations

After all our models have been created we need to re-run our database migrations to add them to our database.

[*source*](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Models)

---

## Django Admin

### Overview

The Django admin application can use our models to automatically build a site area that you can use to `create`, `view`, `update`, and `delete` records.

### Registering models

In the `admin.py` file in the catalog application we need register the models by importing the models and then calling `admin.site.register` to register each of them. (e.g.)

```python
from .models import Author, Genre, Book, BookInstance

admin.site.register(Book)
admin.site.register(Author)
admin.site.register(Genre)
admin.site.register(BookInstance)
```

### Creating a superuser

To log into the admin site, we need a user account with Staff status enabled. With permissions to manage all objects, to view and create records, and with full access to the site. We create this `superuser` account in `manage.py` using the following command:

```python
python3 manage.py createsuperuser
```

### Logging in and using the site

To log into the site, we open the /admin URL and enter our `superuser` credentials. Here we can see our models, grouped by installed application. We can access and edit all of their associated records.

[*source*](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Admin_site)

---

### Things I want to know more about

* I would like to know more about how to implement Django models efficiently, and how to create a superuser to utilize the admin site. 

---

[-back](https://alexriverau.github.io/reading-notes/code401)

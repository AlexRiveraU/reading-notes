# Django CRUD and Forms

This topic matters as it relates to learning how to implement Django Forms and CRUD (Create, Read, Update and Delete). 

---

## Django Forms

### Overview

An HTML Form is a group of one or more fields/widgets on a web page, which can be used to collect information from users for submission to a server. Forms are a flexible mechanism for collecting user input because there are suitable widgets for entering many different types of data, including text boxes, checkboxes, radio buttons, date pickers and so on. Forms are also a relatively secure way of sharing data with the server, as they allow us to send data in POST requests with cross-site request forgery protection.

### Django form handling process

* Display the default form the first time it is requested by the user.
  * The form may contain blank fields, or it may be pre-populated with initial values.
  * The form is referred to as `unbound` at this point, because it isn't associated with any user-entered data.
* Receive data from a submit request and bind it to the form. 
  * Binding data to the form means that the user-entered data and any errors are available when we need to redisplay the form.
* Clean and validate the data.
  * Cleaning the data performs sanitization of the input fields, such as removing invalid characters that might be used to send malicious content to the server, and converts them into consistent Python types.
  * Validation checks that the values are appropriate for the field.
* If any data is invalid, re-display the form, this time with any user populated values and error messages for the problem fields.
* If all data is valid, perform required actions.
* Once all actions are complete, redirect the user to another page.

#### Form

The `Form` class is the heart of Django's form handling system. It specifies the fields in the form, their layout, display widgets, labels, initial values, valid values, and the error messages associated with invalid fields. It also provides methods for rendering itself in templates using predefined formats or for getting the value of any element.

#### Declaring a Form

Form data is stored in the application's `forms.py` file. We have import the `forms` library, derive from the `Form` class, and declare the form's fields.

```python
from django import forms

class RenewBookForm(forms.Form):
  renewal_date = forms.DateField(help_text="Enter a date")
  ```

* There are many types of form fields, very similar to the model field classes.

#### Validation

The easiest way to validate a single field is to override the method `clean_<fieldname>()` for the field we want to check.

```python
class RenewBookForm(forms.Form):
  renewal_date = forms.DateField(help_text="Enter a date")
  
  def clean_renewal_date(self):
    data = self.cleaned_data['renewal_date']
    
    if data < datetime.date.today():
      raise ValidationError(_('Invalid date'))
    
    if data > datetime.date.today() + datetime.timedelta(weeks=4):
      raise ValidationError(_('Invalid date'))
      
    return data
```

#### URL configuration

```python
urlpatterns += [
  path('book/<uuid:pk>/renew/', views.renew_book_librarian, name='renew-book')
]
```

#### View

* The view has to render the default form when it is first called and then either re-render it with error messages if the data is invalid, or process the data and redirect to a new page if the data is valid. 
* The view has to be able to know whether it is being called for the first time to render the default form, or a subsequent time to validate data.
* We use a `POST` request to submit information to the server to identify form validation requests.
* We can use `GET` to identify the initial form creation request or to submit the data.

```python
def renew_book_librarian(request, pk):
  book_instance = get_object_or_404(BookInstance, pk=pk)
  
  if request.method == 'POST':
    form = RenewBookForm(request.POST)
    
    if form.is_valid():
      book_instance.due_back = form.cleaned_data['renewal_date']
      book_instance.save()
      
      return HttpResponseRedirect(reverse('all-borrowed'))
      
    else:
      prop_renewal = datetime.date.today() + datetime.timedelta(weeks=3)
      form = RenewBookForm(initial={'renewal_date': prop_renewal})
      
    context = {
      'form': form,
      'book_instance': book_instance,
    }
    
    return render(request, 'catalog/book_renew_librarian.html', context)
```

#### The template

* `form.as_table` renders each field as a table row.
* `form.as_ul` renders each field as a list item. 
* `form.as_p` renders each field as a paragraph.


We can also render each part of the form using dot notation.

### ModelForms

We can also use `ModelForm` helper class to create a form from a model already created, instead of recreating the model definitions in the form. It is used within views just like an ordinary `Form`.

```python
from django.forms import ModelForm
from catalog.models import BookInstance

class RenewBookModelForm(ModelForm):
  
  class Meta:
    model = BookInstance
    fields = ['due_back']
```

[*source*](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Forms)

---

### Things I want to know more about

* I would like to know more about how to implement Django Forms and ModelForm efficiently.

---

[-back](https://alexriverau.github.io/reading-notes/code401)

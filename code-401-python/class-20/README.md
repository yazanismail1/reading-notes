# Django Models

# Using models

Django web applications access and manage data through Python objects referred to as models. Models define the structure of stored data, including the field types and possibly also their maximum size, default values, selection list options, help text for documentation, label text for forms, etc. The definition of the model is independent of the underlying database — you can choose one of several as part of your project settings.

Once you've chosen what database you want to use, you don't need to talk to it directly at all — you just write your model structure and other code, and Django handles all the dirty work of communicating with the database for you.

## Designing the LocalLibrary models

Assume you want to make a bookstore...

We know that we need to store information about books (title, summary, author, written language, category, ISBN) and that we might have multiple copies available (with globally unique id, availability status, etc.). We might need to store more information about the author than just their name, and there might be multiple authors with the same or similar names. We want to be able to sort information based on book title, author, written language, and category.

**Types of Relationships**

Django allows you to define relationships that are one to one (OneToOneField), one to many (ForeignKey) and many to many (ManyToManyField).

## Model primer

This section provides a brief overview of how a model is defined and some of the more important fields and field arguments.

**Model definition**

Models are usually defined in an application's models.py file. They are implemented as subclasses of django.db.models.Model, and can include fields, methods and metadata.

**Fields**

A model can have an arbitrary number of fields, of any type — each one represents a column of data that we want to store in one of our database tables. Each database record (row) will consist of one of each field value.

**Common field types**

- **CharField:** is used to define short-to-mid sized fixed-length strings. You must specify the max_length of the data to be stored.

- **TextField:** is used for large arbitrary-length strings. You may specify a max_length for the field, but this is used only when the field is displayed in forms (it is not enforced at the database level).

- **IntegerField:** is a field for storing integer (whole number) values, and for validating entered values as integers in forms.

- **DateField and DateTimeField:** are used for storing/representing dates and date/time information (as Python datetime.date and datetime.datetime objects, respectively). 

- **EmailField:** is used to store and validate email addresses.

- **FileField and ImageField:** are used to upload files and images respectively (the ImageField adds additional validation that the uploaded file is an image).

- **AutoField:** is a special type of IntegerField that automatically increments. A primary key of this type is automatically added to your model if you don't explicitly specify one.

- **ForeignKey:** is used to specify a one-to-many relationship to another database model.

- **ManyToManyField:** is used to specify a many-to-many relationship.

**Metadata**

One of the most useful features of this metadata is to control the default ordering of records returned when you query the model type.

**Methods**

A model can also have methods.

Minimally, in every model you should define the standard Python class method __ _str_ __( ) to return a human-rea able string for each object. This string is used to represent individual records in the administration site.

Another common method to include in Django models is get_absolute_url(), which returns a URL for displaying individual model records on the website.

**Model management**

Once you've defined your model classes you can use them to create, update, or delete records, and to run queries to get all records or particular subsets of records.

**Creating and modifying records**

To create a record you can define an instance of the model and then call save().

**Dearching for records**

We can get all records for a model as a QuerySet, using objects.all().

Django's filter() method allows us to filter the returned QuerySet to match a specified text or numeric field against particular criteria.


# Django admin site

The Django admin application can use your models to automatically build a site area that you can use to create, view, update, and delete records. This can save you a lot of time during development, making it very easy to test your models and get a feel for whether you have the right data. The admin application can also be useful for managing data in production, depending on the type of website.

## Registering models

By simply importing the models and register them...

```
from django.contrib import admin
from .models import Author, Genre, Book, BookInstance

admin.site.register(Book)
admin.site.register(Author)
admin.site.register(Genre)
admin.site.register(BookInstance)
```
## Creating a superuser

```
$ python manage.py createsuperuser
```

**Logging in**

redirect to the following url <http://127.0.0.1:8000/admin> and enter the username.and password

## Things I want to know more about

- Django
- Flask
- DBs

## References

[1] <https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Models>

[2] <https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Admin_site>

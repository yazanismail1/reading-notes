# Django Custom User

Django ships with a built-in User model for authentication. for a real-world project, the official Django documentation highly recommends using a custom user model instead. This provides far more flexibility down the line so, as a general rule, always use a custom user model for all new Django projects.

### Setup

- Install Django

- Make a new Django project called django_project

- Make a new app accounts

- Start the local web server

> Note that we did not run migrate to configure our database. It's important to wait until after we've created our new custom user model before doing so.

### AbstractUser vs AbstractBaseUser

There are two modern ways to create a custom user model in Django: AbstractUser and AbstractBaseUser. In both cases we can subclass them to extend existing functionality however AbstractBaseUser requires much, much more work.

### Custom User Model

Creating our initial custom user model requires four steps:

- update django_project/settings.py

- create a new CustomUser model

- create new UserCreation and UserChangeForm

- update the admin

In settings.py we'll add the accounts app and use the AUTH_USER_MODEL config to tell Django to use our new custom user model in place of the built-in User model. We'll call our custom user model CustomUser.

Within INSTALLED_APPS add accounts at the bottom. Then at the bottom of the entire file, add the AUTH_USER_MODEL config.

Now update accounts/models.py with a new User model which we'll call CustomUser.

Create a new file in the accounts app called forms.py.

### Superuser

It's helpful to create a superuser that we can use to log in to the admin and test out log in/log out. On the command line type the following command and go through the prompts.

```
python manage.py createsuperuser
```

### Templates/Views/URLs

**project/settings.py**
```
TEMPLATES = [
    {
        ...
        "DIRS": [BASE_DIR / "templates"],  # new
        ...
    },
]

LOGIN_REDIRECT_URL = "home"
LOGOUT_REDIRECT_URL = "home"
```
**Create the HTML files**

templates/base.html
```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>{% block title %}Django Auth Tutorial{% endblock %}</title>
</head>
<body>
  <main>
    {% block content %}
    {% endblock %}
  </main>
</body>
</html>
```
templates/home.html
```
{% extends "base.html" %}

{% block title %}Home{% endblock %}

{% block content %}
{% if user.is_authenticated %}
  Hi {{ user.username }}!
  <p><a href="{% url 'logout' %}">Log Out</a></p>
{% else %}
  <p>You are not logged in</p>
  <a href="{% url 'login' %}">Log In</a> |
  <a href="{% url 'signup' %}">Sign Up</a>
{% endif %}
{% endblock %}
```
templates/registration/login.html
```
{% extends "base.html" %}

{% block title %}Log In{% endblock %}

{% block content %}
<h2>Log In</h2>
<form method="post">
  {% csrf_token %}
  {{ form.as_p }}
  <button type="submit">Log In</button>
</form>
{% endblock %}
```
templates/registration/signup.html
```
{% extends "base.html" %}

{% block title %}Sign Up{% endblock %}

{% block content %}
<h2>Sign Up</h2>
<form method="post">
  {% csrf_token %}
  {{ form.as_p }}
  <button type="submit">Sign Up</button>
</form>
{% endblock %}
```
**project/urls.py**
```
from django.contrib import admin
from django.urls import path, include
from django.views.generic.base import TemplateView

urlpatterns = [
    path("", TemplateView.as_view(template_name="home.html"), name="home"),
    path("admin/", admin.site.urls),
    path("accounts/", include("accounts.urls")),
    path("accounts/", include("django.contrib.auth.urls")),
]
```
**app/urls.py**
```
from django.urls import path

from .views import SignUpView

urlpatterns = [
    path("signup/", SignUpView.as_view(), name="signup"),
]
```
**app/views.py**
```
from django.urls import reverse_lazy
from django.views.generic.edit import CreateView

from .forms import CustomUserCreationForm

class SignUpView(CreateView):
    form_class = CustomUserCreationForm
    success_url = reverse_lazy("login")
    template_name = "registration/signup.html"
```
## Things I want to know more about

- Django
- Flask
- DBs

## References

[1] <https://learndjango.com/tutorials/django-custom-user-model>

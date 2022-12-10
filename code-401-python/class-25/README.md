# Django REST Framework & Docker

With Docker we now longer have to mess around with virtual environments. We can faithfully reproduce a production environment locally. And Docker can be shared among team members so everyone is working on the same setup.

Docker is really just Linux containers which are a type of virtualization.

Virtualization has its roots at the beginning of computer science when large, expensive mainframe computers were the norm. How could multiple programmers use the same single machine? The answer was virtualization and specifically virtual machines which are complete copies of a computer system from the operating system on up.

What’s the downside to a virtual machine? Size and speed. A typical guest operating system can easily take up 700MB of size. So if one physical server supports three virtual machines, that’s at least 2.1GB of disk space taken up along with separate needs for CPU and memory resources.

### Containers vs Virtual Environments

Virtual environments are used to isolate Python software packages locally. We can create an isolated box for individual projects so one can use Python 2.7 and Django 1.5 while another can use Python 3.5 and Django 2.1 on the same computer. Virtual environments are great.

But…virtual environments can only isolate Python packages. They still rely on a global, system-level installation of Python albeit they can refer to the proper version. So when we use Python 2.7 in a project, we’re pointing to an installation of Python 2.7 on the computer itself, not actually within the virtual environment.

### Install Docker

To install Docker we need to download the desktop app on our computer and create a free account.

### Images and Containers

Images and containers are the two fundamental concepts to grasp when you start with Docker. An image is a snapshot in time of what a project contains. A container is a running instance of the image.

**A baking analogy we can use here is as follows:**

- A Dockerfile is the recipe for a cake

- An image is a snapshot of the recipe at a given time

- A docker-compose.yml says how to make the cake

- And the container is the actual, baked cake

### Image Layers

Every image is made up of one or more image layers. The base layer is often a flavor of Linux, like alpine. When we built the image for python:3.7-alpine this image had the id b2c276538711. But that image depended on five other images which were visible while building it

### Containers

Now that we have our Python image how do we run it? Well just as a Dockerfile is a list of image instructions there is also a docker-compose.yml file that is a list of container instructions.

To demonstrate a real-world image and container example we will now “Dockerize” a basic Django web app.

## Dockerized Django

We’ll now create a Dockerfile for our image which will completely replace our local dev environment, so this will have Python 3 and Django. Then we’ll add a docker-compose.yml for the container instructions.

# Django for APIs

Django REST Framework works alongside the Django web framework to create web APIs. We cannot build a web API with only Django Rest Framework. It always must be added to a project after Django itself has been installed and configured.

### Traditional Django

A traditional Django website consists of a single project with multiple apps representing discrete functionality.

### Django APIs

The main difference is how the data is presented, we need to make it as Json so that users can apply api logic.

**Serializers**

A serializer translates complex data like querysets and model instances into a format that is easy to consume over the internet, typically JSON. It is also possible to “deserialize” data, literally the same process in reverse, whereby JSON data is first validated and then transformed into a dictionary.

The real beauty of Django REST Framework lies in its serializers which abstracts away most of the complexity for us.

```
# apis/serializers.py
from rest_framework import serializers

from books.models import Book


class BookSerializer(serializers.ModelSerializer):
    class Meta:
        model = Book
        fields = ("title", "subtitle", "author", "isbn")
```

After completing the project as a normal django project we need to create a new route for the api and add the previous code in apis app in a file called serializers.py

And that’s it! We’re done. By creating a new URL route, a new view, and a serializer class we have created an API endpoint for our Library website that will display all existing books in list format.

## Things I want to know more about

- Docker
- Django
- Flask
- SQL

## References

[1] <https://wsvincent.com/beginners-guide-to-docker/>

[2] <https://djangoforapis.com/library-website-and-api/>

[3] <https://djangoforapis.com/library-api/>

# API Deployment

## Configuring Django Settings: Best Practices

### Managing Django Settings: Issues

**Different environments**

Usually, you have several environments: local, dev, ci, qa, staging, production, etc. Each environment can have its own specific settings (for example: DEBUG = True, more verbose logging, additional apps, some mocked data, etc). You need an approach that allows you to keep all these Django setting configurations.

**Sensitive data**

You have SECRET_KEY in each Django project. On top of this there can be DB passwords and tokens for third-party APIs like Amazon or Twitter. This data cannot be stored in VCS.

**Sharing settings between team members**

You need a general approach to eliminate human error when working with the settings. For example, a developer may add a third-party app or some API integration and fail to add specific settings. On large (or even mid-size) projects, this can cause real issues.

**Django settings are a Python code**

This is a curse and a blessing at the same time. It gives you a lot of flexibility, but can also be a problem – instead of key-value pairs, settings.py can have a very tricky logic.

### Setting Django Configurations

There is no built-in universal way to configure Django settings without hardcoding them. But books, open-source and work projects provide a lot of recommendations and approaches on how to do it best.

**<u>settings_local.py</u>**

The basic idea of this method is to extend all environment-specific settings in the settings_local.py file, which is ignored by VCS.

_settings.py_

```
ALLOWED_HOSTS = ['example.com']
DEBUG = False
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'production_db',
        'USER': 'user',
        'PASSWORD': 'password',
        'HOST': 'db.example.com',
        'PORT': '5432',
        'OPTIONS': {
            'sslmode': 'require'
        }
    }
}

...

from .settings_local import *
```

_settings_local.py_

```
ALLOWED_HOSTS = ['localhost']
DEBUG = True
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'local_db',
        'HOST': '127.0.0.1',
        'PORT': '5432',
    }
}
```

**Pros:**

- Secrets not in VCS.

**Cons:**

- settings_local.py is not in VCS, so you can lose some of your Django environment settings.

- The Django settings file is a Python code, so settings_local.py can have some non-obvious logic.

- You need to have settings_local.example (in VCS) to share the default Django configurations for developers.

**<u>Separate settings file for each environment</u>**

This is an extension of the previous approach. It allows you to keep all configurations in VCS and to share default settings between developers.

In this case, there are multiple files from which projects on Django get settings, and you make a settings package with the following file structure:

```
settings/
   ├── __init__.py
   ├── base.py
   ├── ci.py
   ├── local.py
   ├── staging.py
   ├── production.py
   └── qa.py
```

_settings/local.py_

```
from .base import *


ALLOWED_HOSTS = ['localhost']
DEBUG = True
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'local_db',
        'HOST': '127.0.0.1',
        'PORT': '5432',
    }
}
```

To specify for a project you run which Django configuration to use, you need to set an additional parameter:

```
python manage.py runserver --settings=settings.local
```

**Pros:**

- All environments are in VCS.

- It’s easy to share settings between developers.

**Cons:**

- You need to find a way to handle secret passwords and tokens.
“Inheritance” of settings can be hard to trace and maintain.

**<u>Environment variables</u>**

To solve the issue with sensitive data, you can use environment variables in Django

We will face a KeyError, to handle it...

**Pros:**

- Django config is separated from code.

- Environment parity – you have the same code for all environments.

- No inheritance in settings, and cleaner and more consistent code.

- There is a theoretical grounding for using Django environment 
variables – 12 Factors.

**Cons:**

- You need to handle sharing default config between developers

### 12 Factors

12 Factors is a collection of recommendations on how to build distributed web-apps that will be easy to deploy and scale in the Cloud. It was created by Heroku, a well-known Cloud hosting provider.

As the name suggests, the collection consists of twelve parts:

1. Codebase

2. Dependencies

3. Config

4. Backing services

5. Build, release, run

6. Processes

7. Port binding

8. Concurrency

9. Disposability

10. Dev/prod parity

11. Logs

12. Admin processes

Each point describes a recommended way to implement a specific aspect of the project. Some of these points are covered by instruments like Django, Python, pip. Some are covered by design patterns or the infrastructure setup. In the context of this article, we are interested in one part: Configuration.

Its main rule is to store configuration in the environment. Following this recommendation will give us strict separation of config from code.

### django-environ

Writing code using os.environ could be tricky sometimes and require additional effort to handle errors. It’s better to use django-environ instead.

Technically it’s a merge of:

- envparse

- honcho

- dj-database-url

- dj-search-url

- dj-config-url

- django-cache-url

This app gives a well-functioning API for reading values from environment variables or text files, handful type conversion, etc. Let’s look at some examples.

_settings.py_ before.

```
import os


SITE_ROOT = os.path.dirname(os.path.dirname(os.path.dirname(os.path.realpath(__file__))))

DEBUG = True
TEMPLATE_DEBUG = DEBUG

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'production_db',
        'USER': 'user',
        'PASSWORD': 'password',
        'HOST': 'db.example.com',
        'PORT': '5432',
        'OPTIONS': {
            'sslmode': 'require'
        }
    }
}

MEDIA_ROOT = os.path.join(SITE_ROOT, 'assets')
MEDIA_URL = 'media/'
STATIC_ROOT = os.path.join(SITE_ROOT, 'static')
STATIC_URL = 'static/'

SECRET_KEY = 'Some-Autogenerated-Secret-Key'

CACHES = {
    'default': {
        'BACKEND': 'django_redis.cache.RedisCache',
        'LOCATION': '127.0.0.1:6379/1',
    }
}
```

_settings.py_ after.

```
import environ


root = environ.Path(__file__) - 3  # get root of the project
env = environ.Env()
environ.Env.read_env()  # reading .env file

SITE_ROOT = root()

DEBUG = env.bool('DEBUG', default=False)
TEMPLATE_DEBUG = DEBUG

DATABASES = {'default': env.db('DATABASE_URL')}

public_root = root.path('public/')
MEDIA_ROOT = public_root('media')
MEDIA_URL = env.str('MEDIA_URL', default='media/')
STATIC_ROOT = public_root('static')
STATIC_URL = env.str('STATIC_URL', default='static/')

SECRET_KEY = env.str('SECRET_KEY')

CACHES = {'default': env.cache('REDIS_CACHE_URL')}
```

_.env_ file.

```
DEBUG=True
DATABASE_URL=postgres://user:password@db.example.com:5432/production_db?sslmode=require
REDIS_CACHE_URL=redis://user:password@cache.example.com:6379/1
SECRET_KEY=Some-Autogenerated-Secret-Key
```

### Naming Conventions

Naming of variables is one of the most complex parts of development. So is naming of settings. We can’t imply on Django or third-party applications, but we can follow these simple rules for our custom (project) settings:

- Give meaningful names to your settings.

- Always use the prefix with the project name for your custom  (project) settings.

- Write descriptions for your settings in comments.

### Django Settings: Best practices

- Keep settings in environment variables.

- Write default values for production configuration (excluding secret keys and tokens).

- Don’t hardcode sensitive settings, and don’t put them in VCS.

- Split settings into groups: Django, third-party, project.

- Follow naming conventions for custom (project) settings.

## What Is SSH: Understanding Encryption, Ports and Connection

### What Is SSH?

SSH, or Secure Shell Protocol, is a remote administration protocol that allows users to access, control, and modify their remote servers over the internet.

SSH service was created as a secure replacement for the unencrypted Telnet and uses cryptographic techniques to ensure that all communication to and from the remote server happens in an encrypted manner.

### How Does SSH Work

If you’re using Linux or Mac, then using SSH is very simple. If you use Windows, you will need to utilize an SSH client to open SSH connections. The most popular SSH client is PuTTY.

### Understanding Different Encryption Techniques

The significant advantage offered by SSH over its predecessors is the use of encryption to ensure a secure transfer of information between the host and the client. Host refers to the remote server you are trying to access, while the client is the computer you are using to access the host. There are three different encryption technologies used by SSH:

1. Symmetrical encryption

2. Asymmetrical encryption

3. Hashing

**Symmetric Encryption**

Symmetric encryption is a form of encryption where a secret key is used for both encryption and decryption of a message by both the client and the host. Effectively, anyone possessing the key can decrypt the message being transferred.

Symmetrical encryption is often called shared key or shared secret encryption. There is usually only one key that is used, or sometimes a pair of keys, where one key can easily be calculated using the other key.

**Asymmetric Encryption**

Unlike symmetrical encryption, asymmetrical encryption uses two separate keys for encryption and decryption. These two keys are known as the public key and the private key. Together, both these keys form a public-private key pair.

A public key can be used by any individual to encrypt a message and can only be decrypted by the recipient who possesses their particular private key, and vice versa.

**Hashing**

One-way hashing is another form of cryptography used in Secure Shell Connections. One-way-hash functions differ from the above two forms of encryption in the sense that they are never meant to be decrypted. They generate a unique value of a fixed length for each input that shows no clear trend which can be exploited. This makes them practically impossible to reverse.

It is easy to generate a cryptographic hash from a given input, but impossible to generate the input from the hash. This means that if a client holds the correct input, they can generate the cryptographic hash and compare its value to verify whether they possess the correct input.

SSH uses hashes to verify the authenticity of messages. This is done using HMACs, or Hash-based Message Authentication Codes. This ensures that the command received is not tampered with in any way.

### How Does SSH Work With These Encryption Techniqueس

The way SSH works is by making use of a client-server model to allow for authentication of two remote systems and encryption of the data that passes between them.

SSH operates on TCP port 22 by default (though SSH port can be changed if needed). The host (server) listens on port 22 (or any other SSH assigned port) for incoming connections. It organizes the secure connection by authenticating the client and opening the correct shell environment if the verification is successful.

The client must begin the SSH connection by initiating the TCP handshake with the server, ensuring a secured symmetric connection, verifying whether the identity displayed by the server match previous records (typically recorded in an RSA key store file), and presenting the required user credentials to authenticate the connection.

There are two stages to establishing a connection – first, both the systems must agree upon encryption standards to protect future communications, and second, the user must authenticate themselves. If the credentials match, then the user is granted access.

## Session Encryption Negotiation

When a client tries to connect to the server via TCP, the server presents the encryption protocols and respective versions that it supports. If the client has a similar matching pair of a protocol and version, an agreement is reached and the connection is started with the accepted protocol. The server also uses an asymmetric public key which the client can use to verify the authenticity of the host.

Once this is established, the two parties use what is known as a Diffie-Hellman Key Exchange Algorithm to create a symmetrical key. This algorithm allows both the client and the server to arrive at a shared encryption key which will be used henceforth to encrypt the entire communication session.

### Authenticating the User

The final stage before the user is granted access to the server is authenticating his/her credentials. For this, most SSH users use a password. The user is asked to enter the username, followed by the password. These credentials securely pass through the symmetrically encrypted tunnel, so there is no chance of them being captured by a third party.

Although passwords are encrypted, it is still not recommended to use passwords for secure connections. This is because many bots can simply brute force easy or default passwords and gain access to your account. Instead, the recommended alternative is SSH Key Pairs.

# Things I want to know more about

- Deploying
- How to use Django for freelancing

# References

[1] <https://djangostars.com/blog/configuring-django-settings-best-practices/>

[2] <https://www.hostinger.com/tutorials/ssh-tutorial-how-does-ssh-work>



# Adding google login to a django app

Follow this video: https://www.youtube.com/watch?v=ZTBexYIIOP8

OK in this video we do the following:

Add these lines to the INSTALLED_APPS list in `settings.py`
```
    'django.contrib.sites',
    'allauth',
    'allauth.account',
    'allauth.socialaccount',
    'allauth.socialaccount.providers.google',
```

Add this to the end of the `settings.py` file
```
AUTHENTICATION_BACKENDS = (
    'django.contrib.auth.backends.ModelBackend',
    'allauth.account.auth_backends.AuthenticationBackend',
)

SITE_ID = 1
```

Add this to your `url_patterns` list in `urls.py`
```
    path('accounts', include('allauth.urls')),
```

You might also have to add `include` to your imports from `django.urls`
```
from django.urls import path, include
```

Run `pip install django-allauth` to make that line work.

Now run `python manage.py migrate`.

Now run the app `python manage.py runserver`.

Go to localhost:8000/admin. Click on add social application.

Go to [GCP console](https://console.cloud.google.com/) and open your project.

And you know what just follow the youtbe vid linked at the top of this doc for the rest of it.


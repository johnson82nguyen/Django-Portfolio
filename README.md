# Personal website

This is my django website that I hosted on Heroku. This is the domain that is hosting my website. 

www.johnson-nguyen.com

## The purpose of this Repository

The purpose of this repository isn't to give you my functioning website. I didn't put the entireity of my source code into this repository just because I don't want a mere copy but I put a lot of it in. This is to show you the base steps to start your own personal Django application if you are ever feel like starting one. 



## Installing Django

First off if you want to run a Django application, you need to install Django. To do so, you run the following command in your terminal

```bash
python -m pip install Django
```

You will now have Django installed onto your device. This will give you access to django packages. Now once you have django on your system, let's create a virtual environment.

To do so, run the following commands in your command line
```bash
$ python3 -m venv venv 
```
and 
```
$ source venv/bin/activate
```

This will create your virtual environment, and allow you to develope your web application.

## To start your first Django application 

To start your first Django application, you need to run the server. Since Django Framework uses python, you use the following command.
```bash
python manage.py runserver 
```

What this line does is it runs the server. If you check local:host8000 you should have a server running. However, You shouldn't be able to see anything because the server isn't connecting to any applications yet.

To start your first Django application you run the following command.

```bash
python manage.py startapp "new application name" 
```

This creates a directory with the new application name.



1. Once u create an app, you will need to add it in settings.py

2. This settings.py file will be location in your newly created application directory

3. There will be a function called installed_apps within your settings.py file

4. In installed apps, you just add the name of your newly created app. A little something like this


```bash
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'new application name'
]
```


6. 2. After that, you need to create a views function. I.e

from django.shortcuts import render

def hello_world(request): 

return render(request, 'hello_world.html', {})

Need to make an HTML template to display to the user. render() looks for HTML templates inside directory called templates inside app directory.
i.e mkdir hello_world/templates/ touch hello_world/templates/hello_world.html

4.To hookup to the url, u need to visit urls.py and add the following lines to display to the server,

From django.urls import path, include path('',include('hello_world.urls')),

The urls.py doesn't exist in hello_world yet so we'll create it.
Touch hello_world/urls.py

And add the following to urls.py in your hello_world directory

from django.urls import path from hello_world import views

urlpatterns = [ path('', views.hello_world, name='hello_world'), ]

Now when u run localhost:8000 u should see "hello, world" or whatever you added in the HTML file.

This is for adding bootstrap. Go to personal_portfolio/templates/ And make a base.html file This should be where your CSS is.
Add

{% block page_content %}{% endblock %}

To ur base.html file

sets virtual environment to run website

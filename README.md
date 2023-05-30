# Personal website

This is my django website that I hosted on Heroku. This is the domain that is hosting my website. 

www.johnson-nguyen.com (DEPRICATED)

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



1. Once you create an app, you will need to add it in settings.py

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

 After that, you need to create a views function.
 A views function will take a request and display it to the server.
 If the request is valid, then you should be able to see your website when you test out local:host8000
 
 To add to your views function, copy the following code 
 
 
```bash
from django.shortcuts import render

def new_application_name(request): 

return render(request, 'new_application_name.html', {})
```

This will make a request to your 'new_application_name.html' file and display it on local host. 

```bash
The render() looks for html templates inside the directory called templates inside the app directory.
```

However, this won't display anything yet since we haven't created a new_application_name.html file.

To do this we can use some linux commands to make a folder and a html file.

```bash
mkdir new_application_name/templates/
```
This will make a new directory, and another directory within new_application_name

Now we want to make the html file. To do so, you can run

```bash
touch new_application_name.html
```
There is one more step we need to do. 
So far we installed the app, added it into our settings, and also created a view for it to display. One more thing we need to do is hook it up to a url. This will allow us to display to the server. The views only displays to the user, but this will display to the server.

To hookup to the url, You need to visit urls.py and add the following lines to display to the server,

```bash
From django.urls import path, include path('',include('new_application_name.urls')),
```

The urls.py doesn't exist in new_application_name yet so we'll create it.

```bash
touch new_application_name/urls.py
```
This goes into your application directory and creates a urls.py file.


Add the following to urls.py in your new_applications_name directory

```bash
from django.urls import path from new_application_name import views

urlpatterns = [ path('', views.new_application_name, name='new_application_name'), ]
```

Now when you run localhost:8000 You should see whatever you added in the HTML file.

## Conclusion

In conclusion, these are the basic steps you need to follow in order to get your Django applications up and running for yourself.
This isn't an in depth guide to show you how everything works in django as I've just started learning Django myself recently.
Ever time you want to create a new application to add to your project, just follow these steps and you're good to go :)
Hopefully this has helped you!


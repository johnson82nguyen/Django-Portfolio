# personal website
https://tranquil-garden-02710.herokuapp.com/landing_page/

## Installing Django

First off if you want to run a Django application, you need to install Django. To do so, you run the following command,
'''bash
python -m pip install Django
'''
python3 -m venv venv $ source venv/bin/activate

Python manage.py runserver Python manage.py startalp "new application name" I.e hello_world

1.Once u create an app, u need to add it in settings.py in installed_apps 2. After that, you need to create a views function. I.e

from django.shortcuts import render

def hello_world(request): return render(request, 'hello_world.html', {})

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

https://tranquil-garden-02710.herokuapp.com/landing_page/


python3 -m venv venv
$ source venv/bin/activate


Python manage.py runserver
Python manage.py startalp "new application name" I.e hello_world

1.Once u create an app, u need to add it in settings.py in installed_apps
2. After that, you need to create a views function. I.e

from django.shortcuts import render

def hello_world(request):
    return render(request, 'hello_world.html', {})

3. Need to make an HTML template to display to the user. render() looks for HTML templates inside directory called templates inside app directory.

i.e mkdir hello_world/templates/
    touch hello_world/templates/hello_world.html

4.To hookup to the url, u need to visit urls.py and add the following lines to display to the server,

From django.urls import path, include
path('',include('hello_world.urls')),

5. The urls.py doesn't exist in hello_world yet so we'll create it.

Touch hello_world/urls.py

And add the following to urls.py in your hello_world directory

from django.urls import path
from hello_world import views

urlpatterns = [
    path('', views.hello_world, name='hello_world'),
]

Now when u run localhost:8000 u should see "hello, world" or whatever you added in the HTML file. 

6. This is for adding bootstrap.
Go to personal_portfolio/templates/
And make a base.html file
This should be where your CSS is.

Add 

{% block page_content %}{% endblock %}

To ur base.html file


sets virtual environment to run website


<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css" integrity="sha384-MCw98/SFnGE8fJT3GXwEOngsV7Zt27NXFoaoApmYm81iuXoPkFOJwJ8ERdknLPMO" crossorigin="anonymous">


<script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.3/umd/popper.min.js" integrity="sha384-ZMP7rVo3mIykV+2+9J3UJ46jBk0WLaUAdn689aCwoqbBJiSnjAK/l8WvCWPIPm49" crossorigin="anonymous"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/js/bootstrap.min.js" integrity="sha384-ChfqqxuZUCnJSK3+MXmPNIyE6ZbWh2IMqE241rYiqJxyMiZ6OW/JmZQ5stwEULTy" crossorigin="anonymous"></script> 



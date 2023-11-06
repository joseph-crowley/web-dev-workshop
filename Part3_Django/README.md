# Part 3: Django Project Setup

This section will guide you through setting up a basic Django project and app, and integrating the HTML from Part 1 into a Django view.

## Setting up the Django Project

Ensure you have Docker running, then build and run the container with the following commands from the `Part2_Docker` directory:

```sh
docker-compose build
docker-compose up -d # Run in detached mode so you can use the terminal
```

Once the container is running, use the following command to create a Django project:

```sh
docker-compose exec web-workshop django-admin startproject hello_world_project .
```

This will create the necessary project structure within the `Part3_Django` directory.

Migrations are how django creates the database `db.sqlite3` and tables for your project. Run the following command to create the database and tables:

```sh
docker-compose exec web-workshop python manage.py migrate
```

Use your text editor to modify `../Part3_Django/hello_world_project/settings.py` to include the following:

```python
ALLOWED_HOSTS = ['*']
```

This makes the application accessible from any host, which is useful for development.

## Running the Development Server

Use this command to run the Django development server:

```sh
docker-compose exec web-workshop python manage.py runserver 0.0.0.0:8000
```

Open your web browser and navigate to `http://localhost:8000` to see your Django project in action.


## Django App Integration using existing HTML

In this part, we'll integrate the `complete.html` page from Part 1 into a new Django app within our project. Follow these steps to set up your `hello_world_app` and serve the HTML page as the main page of the app.

### Create the Django App

Within the running container, use the Django management command to create a new app called `hello_world_app` by running the following command from the `Part2_Docker` directory:

```sh
docker-compose exec web-workshop python manage.py startapp hello_world_app
```

### Register the App

Update the `settings.py` file in the `hello_world_project` to include the new app in the `INSTALLED_APPS` list:

```python
# hello_world_project/settings.py

INSTALLED_APPS = [
    # ...
    'hello_world_app',
]
```

### Set Up the View

Define a view in `hello_world_app/views.py` that will render the `complete.html`:

```python
# hello_world_app/views.py

from django.shortcuts import render

def home_page(request):
    return render(request, 'complete.html')
```

### Configure URLs

Create a `urls.py` in the `hello_world_app` directory and define the URL pattern for the home page:

```python
# hello_world_app/urls.py

from django.urls import path
from .views import home_page

urlpatterns = [
    path('', home_page, name='home'),
]
```

Include the app URLs in the main `urls.py` of the `hello_world_project`:

```python
# hello_world_project/urls.py

# ...
from django.urls import include, path

urlpatterns = [
    # ...
    path('', include('hello_world_app.urls')),
]
```

### Move HTML Template

Move your `complete.html` from Part 1 into the `templates` directory of your new app by running the following commands from the `Part3_Django` directory:

```sh
mkdir -p hello_world_app/templates
cp ../Part1_Basic_HTML_CSS_JS/complete.html hello_world_app/templates
```

### Run the Development Server

Run the development server to see your page in action by running the following command from the `Part2_Docker` directory:

```sh
docker-compose exec web-workshop python manage.py runserver 0.0.0.0:8000
```

Navigate to `http://localhost:8000` in your browser to view the "Hello, World" page served by Django.

# django-cheatsheet

## How to create a new Django project
```bash
django-admin startproject projectname
```

 ## How to start the Django development server
 (in the new project dir)
 ```bash
 python3 manage.py runserver
 ```
 
 ## How to STOP it?
  ```bash
 CTRL + C
 ```
 
 ## How to create a new application in the project
 (Don't name same as project)
 ```bash
 python3 manage.py startapp main_app
 ```
 
 ## Django Directory Structure
 ```
 djangoproject
 |
 | - djangoproject
 |   |
 |   | - settings.py : Main settings for our project (db, apps, config, etc.)
 |   | - urls.py : Main URLs for the entire project
 |  
 | - application_name
 |   |
 |   | - static : (dir) Holds all static files (CSS, JS, IMGs, AUX, FORMS)
 |   | - templates : (dir) Holds all HTML template files
 |   | - migrations : (dir) This holds all data migration files
 |   | - admin.py : Where we register data models
 |   | - models.py : This is where all the models are put
 |   | - views.py : Where the functions that run our routes are places (crucial file)
 |   | - urls.py : Every URL for our site is defined here
 |
 | - manage.py : Let's us manage everything about our project
 
 ```

## How to make URL with the path() function:
```python
urlpatterns = [
 path('route/', views.route_function, name='route_name'),
 path('route/<string_variable>', views.string_function, name='string_name'),
 path('route/<int:variable_name>', views.int_function, name='int_name'),
]
```

## How to make a view() function:
```python
def route_function(request):
    return render(request, 'template.html')

def string_function(request, string_variable):
    return render(request, 'string_variable_template.html', { 'data': string_variable })
    
def int_function(request, variable_name):
    return render(request, 'int_variable_template.html', { 'data': variable_name })
```

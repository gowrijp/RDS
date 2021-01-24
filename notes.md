- Install postman(used to test api methods)
- Install node.js
- You can open Node.js cmd to check the version (npm -v)
- open cmd in the desired folder and make a virtual env to download django
- python -m venv myenv (here myenv is the name of the environment)
- myenv\Scripts\activate (type this to activate the venv)
- pip install django
- pip install djangorestframework
- django-admin startproject DjangoAPI
- cd DjangoAPI
- code . (To open vs code)
- python manage.py runserver 
- create db.sqlite3 in the main folder alongside manage.py (if its not created by default)
- Download SQLite Studio 
- You can directly use the executable file present in the folder downloaded
- Click on Database menu -> add a database -> choose the file location (to visualise the database)
- pip install django-cors-headers
- By default all django projects comes with a security feature that blocks the api requests coming from different domains.
- Now in settings.py add 'corsheaders' in INSTALLED_APPS
- CORS_ORIGIN_ALLOW_ALL = True (add this after INSTALLED_APPS)
- In MIDDLEWARE add 'corsheaders.middleware.CorsMiddleware',
- Now lets create an app inside the project
- python manage.py startapp EmployeeApp
- Next we need to register our app in settings.py  
- In settings.py in the section INSTALLED_APPS add 'EmployeeApp.apps.EmployeeappConfig', 'rest_framework'

### Creating models
- In models.py of the app add the classes as required
- python manage.py makemigrations EmployeeApp
- python manage.py migrate EmployeeApp

- Create serializers in a separate file serializers.py
- Then add api in views.py
- Put method is used to update an existing record
- Then create urls.py in the EmployeeApp folder
- We also need to include these urls in the main urls.py of DjangoAPI project
- Then in cmd type in - python manage.py runserver
- Now copy the url and lets test the api methods in postman
- 


#### If you are getting a pylint error (getting a 404 error in postman while testing) check this -> https://www.youtube.com/watch?v=llrYpQGNq3w

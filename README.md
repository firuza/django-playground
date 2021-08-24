# django-playground

## python pip

* Install: <br>
   ```python3 -m pip install --user --upgrade pip```
* Check version: <br>
  ```python3 -m pip --version```

## Virtual environment

* Install: <br>
   ```python3 -m pip install --user virtualenv```
* Create: <br>
   ```python3 -m venv env```
* Activate: <br>
   ```source env/bin/activate```
* Deactivate: <br>
   ```deactivate```

## Install Django
* Create requirements.txt  <br>
  ```django==3.2```
* Install <br>
  ```pip install -r requirements.txt```
* Check packages and versions installed in the virtual environment <br>
  ```pip freeze```
* Create Django Project <br>
  ```django-admin startproject playground```
* Migrate and Start <br>
  * ```python manage.py migrate```
  * ```python manage.py runserver```
* Create superuser <br>
  * ```python manage.py createsuperuser```
* Browse  
  * Site: ```http://localhost:8000```
  * Django admin: ```http://localhost:8000/admin/``` <br>
    Login with the credentials created for superuser
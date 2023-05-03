# Getting Started with Apis in Django

Please ensure you have followed the steps on the Django Notes ReadMe as this will continue on using that as a baseline.

## Next Steps

1. Create an app for your Api, this will be done in the mysitenamehere directory: 
`python manage.py startapp myapi`

2. Next you will edit the settings.py file found in the mysitenamehere directory:
```
INSTALLED_APPS = [
    'myapi.apps.MyapiConfig',
    ... # Leave all the other INSTALLED_APPS
]
```

3. Now you will migrate the database:
`python manage.py migrate`

4. We will now create a super user, this will make it easier to handle models and data, not a necessary step:
` pyhton manage.py createsuperuser`

5. Navigate to `localhost:8000/admin` and ensure you can log into the admin portal


   

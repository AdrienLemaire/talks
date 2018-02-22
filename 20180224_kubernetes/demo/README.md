https://docs.docker.com/compose/django/

1. Go through pages:
    - Dockerfile
    - requirements.txt
    - docker-compose.yml

2. Run docker-compose

    $ sudo docker-compose run web django-admin.py startproject composeexample .
    $ sudo chown -R $USER:$USER .

3. Modify DATABASES in `composeexample/settings.py`

    DATABASES = {
        'default': {
            'ENGINE': 'django.db.backends.postgresql',
            'NAME': 'postgres',
            'USER': 'postgres',
            'HOST': 'db',
            'PORT': 5432,
        }
    }

  For demo purposes, also set

    ALLOWED_HOSTS = ['*']

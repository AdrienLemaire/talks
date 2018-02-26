# DEMO 1

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

4. Go to http://localhost:8000/

# DEMO 2

```
$ docker build -f ./Dockerfile . -t "gcr.io/miraidenshi-142903/web:v0.1"
$ gcloud docker -- push gcr.io/miraidenshi-142903/web:v0.1;

$ gcloud config list
$ gcloud config set project miraidenshi-142903
$ gcloud container clusters create owddm --zone asia-east1-a
$ kubectl config get-clusters
$ kubectl config set-cluster gke_miraidenshi-142903_asia-east1-a_owddm
$ kubectl apply -f deployment.yaml
$ kubectl get pods
```

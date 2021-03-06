## Django Development With Docker Compose and Machine

Featuring:

- Docker v1.10.3
- Docker Compose v1.6.2
- Docker Machine v0.6.0
- Python 3.5

Blog post -> https://realpython.com/blog/python/django-development-with-docker-compose-and-machine/

### OS X Instructions

1. Start new machine - `docker-machine create -d virtualbox dev;`
1. Build images - `docker-compose build`
1. Start services - `docker-compose up -d`
1. Create migrations - `docker-compose run web /usr/local/bin/python manage.py migrate`
1. Grab IP - `docker-machine ip dev` - and view in your browser

### Run Migration (Tested on Ubuntu)
-----------------------
$ sudo docker-compose up
------------------------
In new terminal
$ docker ps

copy container id for webapp image
$ docker exec -t -i <container id> bash

$ cd <path/to/dangoapp>
$ python3 manage.py makemigrations
$ python manage.py migrate

### collect static files
$ python3 manage.py collectstatic

You get the following message
---
You have requested to collect static files at the destination
location as specified in your settings:

    /usr/src/app/static

This will overwrite existing files!
Are you sure you want to do this?

Type 'yes' to continue, or 'no' to cancel: yes
---
type yes and press enter.



Ctrl + D to exit interactive bash
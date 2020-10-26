# REST API for YaMDb

![YaMDb workflow](https://github.com/MuggleSkin/yamdb_final/workflows/YaMDb_workflow/badge.svg)

YaMDb is a database which contains reviews about movies, books and music.

## Getting Started

Install docker:

[Install docker engine](https://docs.docker.com/engine/install/)

and docker-engine:

[Install docker-compose](https://docs.docker.com/compose/install/)

Download this github project on your local machine or remote server. 

Create ".env" file in the root directory of your project and fill it with required environment variables:

```
DB_ENGINE=django.db.backends.postgresql
POSTGRES_DB=your_db_name
POSTGRES_USER=your_postgres_user
POSTGRES_PASSWORD=your_postgres_password
DB_HOST=db
DB_PORT=5432
```

### Deploying

Open terminal to create and start new containers with docker-compose:

```
sudo docker-compose up -d
```

(Optionally) Fill your database with test data from fixtures.json:

```
sudo docker-compose exec web python manage.py loaddata fixtures.json
```

Create superuser to be able to moderate resources:

```
sudo docker-compose exec web python manage.py createsuperuser
```

and follow the further instructions.



## Testing the service

Your service is available on

```
http://127.0.0.1/api/v1/
```

try to fetch some data from resources.

Admin page is available at

```
http://127.0.0.1/admin/
```

You can inspect database using db service:

```
sudo docker-compose exec db psql your_db_name your_postgres_user
```

## Built With

[Yandex Praktikum](https://praktikum.yandex.ru) - Online educational service

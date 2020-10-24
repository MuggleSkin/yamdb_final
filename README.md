# REST API for YaMDb

![YaMDb workflow](https://github.com/MuggleSkin/yamdb_final/workflows/YaMDb_workflow/badge.svg)

YaMDb is a database which contains reviews about movies, books and music.

## Getting Started

Download this project on your local machine or remote server. 

Create ".env" file in the root directory of your project and fill it with required environment variables:

```
DB_ENGINE=django.db.backends.postgresql
DB_NAME=your_db_name
POSTGRES_USER=your_postgres_user
POSTGRES_PASSWORD=your_postgres_password
DB_HOST=db
DB_PORT=5432
```
but make sure DB_NAME and POSTGRES_USER are the same to avoid excessive database creation.

Open terminal to create and start new containers with docker-compose:

```
docker-compose up
```

If something goes wrong with deploying of containers - restart them:

```
docker-compose restart
```

### Installing

(Optionally) Fill your database with test data from fixtures.json:

```
docker-compose exec web python manage.py loaddata fixtures.json
```

Create superuser to be able to moderate resources:

```
docker-compose exec web python manage.py createsuperuser
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
docker-compose exec db psql --username=your_username --dbname=your_dbname
```

## Built With

[Yandex Praktikum](https://praktikum.yandex.ru) - Online educational service

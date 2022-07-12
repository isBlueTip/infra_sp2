# Проект API via Docker

## Описание проекта

Проект по контейнеризации API проект Yatube с использованием Docker, Nginx и Gunicorn

## Установка проекта локально

В папке склонированного репозитория выполните:

```bash
cd infra
docker-compose up -d
docker exec infra_web_1 python3 manage.py makemigrations
docker exec infra_web_1 python3 manage.py migrate
docker exec -it infra_web_1 python3 manage.py createsuperuser --email root@root.com --username root -v 3
```
Задайте пароль для суперпользователя. Логин суперпользователя - root.  
Для проверки работоспособности, перейдите на localhost/admin


## Заполнение БД тестовыми данными

```bash
docker exec infra_web_1 python3 manage.py loaddata fixtures/fixtures.json
```

## Пример .env файла
```Python
DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=pass
DB_HOST=db
DB_PORT=5432
```
## Документация API

доступна по адресу localhost/redoc при развёрнутом проекте

## Стек

Django, Django REST framework, JWT, Docker, Postgres, Nginx, Gunicorn

## Автор

Семён Егоров  


[LinkedIn](https://www.linkedin.com/in/simonegorov/)  
[Email](rhinorofl@gmail.com)  
[Telegram](https://t.me/SamePersoon)
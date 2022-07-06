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
docker exec -it infra_web_1 python3 manage.py createsuperuser --email root@root.ru --username root -v 3
```
Задайте пароль для суперпользователя. Логин суперпользователя - root.  
Для проверки работоспособности, перейдите на localhost/admin

## Пример .env файла

DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=pass
DB_HOST=db
DB_PORT=5432

## Заполнение БД тестовыми данными

## Документация API

доступна по адресу localhost/redoc при развёрнутом проекте

## Стек

Django, Django REST framework, JWT, Docker, Postgres, Nginx, Gunicorn

## Авторы

+
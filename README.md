![example workflow](https://github.com/github/docs/actions/workflows/main.yml/badge.svg)

Дaнный проект разворачивает образ приложения api_yamdb (проект по сбору отзывов о музыкальных произведениях) на своём сервере. Принцип подключения следующий:

11
Подготовка и зaпyск проекта:
Клонировать репозиторий:

git clоne https://github.com/Patron322/yamdb_final

Запустить docker-compose:

docker-compose up -d --build

Выполнить миграции, создать суперпользователя, собрать статику.

docker-compose exec web python manage.py migrate

docker-compose exec web python manage.py createsuperuser

docker-compose exec web python manage.py collectstatic --no-input

Создать файл .env из директории infra/ и внестите в него данные:

DB_ENGINE=django.db.backends.postgresql

DB_NAME=postgres

POSTGRES_USER=postgres

POSTGRES_PASSWORD= # установите свой пароль

DB_HOST=db

DB_PORT=5432

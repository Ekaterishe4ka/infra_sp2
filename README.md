# Описание

Учебный проект 15 спринта курса Python-разработик в Яндекс.Практикум

http://127.0.0.1:8000/redoc/ Документация для YaMDb

Проект YaMDb собирает отзывы пользователей на произведения. Сами произведения в YaMDb не хранятся, здесь нельзя посмотреть фильм или послушать музыку.

# Системные требования
- Python 3.7+
- Works on Linux, Windows, macOS

# Стек технологий

- Python

- Django

- Docker

- Nginx

# Установка

Клонировать репозиторий и перейти в него в командной строке:

```
https://github.com/Ekaterishe4ka/infra_sp2.git
```

```
cd infra/
```

Запустить приложение в контейнерах:

```
docker-compose up -d --build
```

Выполнить миграции:

```
docker-compose exec web python manage.py migrate
```

Создать суперпользователя:

```
docker-compose exec web python manage.py createsuperuser
```

Собрать статику:

```
docker-compose exec web python manage.py collectstatic --no-input
```

Остановить приложение в контейнерах:

```
docker-compose down -v
```

## Шаблон наполнения env-файла

```
DB_ENGINE=django.db.backends.postgresql # указываем, что работаем с postgresql
DB_NAME=postgres # имя базы данных
POSTGRES_USER=postgres # логин для подключения к базе данных
POSTGRES_PASSWORD=postgres # пароль для подключения к БД (установите свой)
DB_HOST=db # название сервиса (контейнера)
DB_PORT=5432 # порт для подключения к БД
```

## Описание команды для заполнения базы данными

Копируем файл с базами данных из /infra в папку app:

```
docker cp fixtures.json <id контенера>:/app
```

Запускаем команду для загрузки баз:

```
docker-compose exec web python manage.py loaddata fixtures.json
```

# Автор проекта

Екатерина Богомолова

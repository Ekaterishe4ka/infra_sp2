## Описание

Учебный проект 15 спринта курса Python-разработик в Яндекс.Практикум

http://127.0.0.1:8000/redoc/ Документация для YaMDb

Проект YaMDb собирает отзывы пользователей на произведения. Сами произведения в YaMDb не хранятся, здесь нельзя посмотреть фильм или послушать музыку.

## Стек

- Python
- Django
- Docker
- Nginx

## Установка

Клонировать репозиторий и перейти в него в командной строке:

```
https://github.com/Ekaterishe4ka/infra_sp2.git
```

```
cd api_yamdb/
```

Cоздать и активировать виртуальное окружение:

```
python -m venv venv
```

```
source venv/Scripts/activate
```

Установить зависимости из файла requirements.txt:

```
python -m pip install --upgrade pip
```

```
pip install -r requirements.txt
```

Запустить приложение в контейнерах:

*из директории infra/
```
docker-compose up -d --build
```

Выполнить миграции:

*из директории infra/
```
docker-compose exec web python manage.py migrate
```

Создать суперпользователя:

*из директории infra/
```
docker-compose exec web python manage.py createsuperuser
```

Собрать статику:

*из директории infra/
```
docker-compose exec web python manage.py collectstatic --no-input
```

Остановить приложение в контейнерах:

*из директории infra/
```
docker-compose down -v
```

## Шаблон наполнения env-файла

```
infra/.env
```

## Описание команды для заполнения базы данными
```
cd api_yamdb && python manage.py loaddata ../infra/fixtures.json
```

# Автор проекта

Екатерина Богомолова

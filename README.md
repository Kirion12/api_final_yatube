# Описание

Данный проект представляет собой API для проекта Yatube - социальной сети, в которой можно публиковать и комментировать записи, подписываться на авторов и отписываться от их публикаций.

Стек технологий:
Python 3.11, Django 3.2, DRF, JWT + Djoser

Ключевые моменты:
Применены вьюсеты;
Для аутентификации использованы JWT-токены;
У неаутентифицированных пользователей доступ к API только на чтение. Исключение — эндпоинт /follow/;
Аутентифицированным пользователям разрешено изменение и удаление своего контента; в остальных случаях доступ предоставляется только для чтения;

# Как установить проект:

1) Клонируем репозиторий:

git@github.com:Kirion12/api_final_yatube.git

2) Перейти в него в командной строке:

cd api_final_yatube

3) Cоздать и активировать виртуальное окружение:

python -m venv venv
```
source venv/scripts/activate
```
4) Установить зависимости из файла requirements.txt:
```
python -m pip install --upgrade pip
```
pip install -r requirements.txt
```
5) Выполнить миграции:
```
python3 manage.py migrate
```
6) Запустить проект:
```
python3 manage.py runserver

# Примеры:

Доступ авторизованным пользователем доступен по JWT-токену (Joser), который можно получить выполнив POST запрос по адресу:
```
POST /api/v1/jwt/create/
```
Обновление JWT токена
```
POST /api/v1/jwt/refresh/ - обновление JWT-токена
```
Примеры работы с API для всех пользователей только для чтения:
```
GET api/v1/posts/ - получить список всех публикаций.
GET api/v1/posts/{id}/ - получение публикации по id

GET api/v1/groups/ - получение списка доступных групп
GET api/v1/groups/{id}/ - получение информации о группах по id

GET api/v1/{post_id}/comments/ - получение всех комментариев к публикации
GET api/v1/{post_id}/comments/{id}/ - Получение комментария к публикации по id
```
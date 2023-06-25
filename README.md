# API Yatube

## Описание
CRUD для Yatube.

API доступен только аутентифицированным пользователям.
Аутентификация реализована по токену TokenAuthentication.
Аутентифицированный пользователь авторизован на изменение и удаление своего контента,
в остальных случаях доступ предоставляется только для чтения.

## Функционал

- Получение токенов доступа.
- Чтение/Публикация/Редакция/Удаление записей и комментариев.

### Endpoints

`api/v1/api-token-auth/` - (POST): передаём логин и пароль, получаем токен.

`api/v1/posts/` -  (GET, POST): получаем список всех постов или создаём новый пост.

`api/v1/posts/{post_id}/` - (GET, PUT, PATCH, DELETE): получаем, редактируем или удаляем пост по id.

`api/v1/groups/` - (GET): получаем список всех групп.

`api/v1/groups/{group_id}/` - (GET): получаем информацию о группе по id.

`api/v1/posts/{post_id}/comments/` - (GET, POST): получаем список всех комментариев поста с id=post_id или создаём 
новый, указав id поста, который хотим прокомментировать.

`api/v1/posts/{post_id}/comments/{comment_id}/` - (GET, PUT, PATCH, DELETE): получаем, редактируем или удаляем 
комментарий по id у поста с id=post_id.

## Установка и запуск

**💡 ВЕРСИЯ Python3.9**

Клонировать репозиторий:
```
git clone <https or SSH URL>
```

Перейти в папку проекта:
```
cd api_yatube
```

Создать и активировать виртуальное окружение:
```
python3 -m venv venv
source venv/bin/activate
```

Обновить pip:
```
python3 -m pip install --upgrade pip
```

Установить зависимости:
```
pip install -r requirements.txt
```

Выполнить миграции:
```
python3 yatube_api/manage.py migrate
```

Запустить сервер:
```
python3 yatube_api/manage.py runserver
```

**Проект «API для Yatube»**
===========
Этот API предоставляет доступ к своим данным клиенту по определенному URL и позволяет использовать следующий функционал:

1. **Пост**

- Получить список всех постов

- Создать новый пост

- Полностью или частично отредактировать пост

- Удалить пост

2. **Группы**

- Получить список всех групп

- Получить информацию о доступной группе

3. **Комментарии**

- Получить все комментарии к посту

- Получить конкретный комментарий к посту

- Добавить новый комментарий к посту

- Полностью или частично отредактировать комментарий

- Удалить комментарий

4. **Подписка**

- Получить список своих подписчиков

- Оформить подписку на других пользователей
  
- Осуществить поиск по подпискам по параметру search

**Доступ к API**
-----------
Для аутентификации используются JWT-токены.

Информация доступна как для незарегистрированных пользователей (доступ к API только на чтение), так и для зарегистрированных.

Исключение — эндпоинт /follow/: доступ к нему возможен только аутентифицированным пользователям.

Аутентифицированным пользователям разрешено изменение и удаление своего контента, в остальных случаях доступ предоставляется только на чтение.

Добавление новых пользователей в данном API не предусмотрено.
____
**Как запустить проект:**
-----------
Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/TatianaSharova/api_final_yatube.git
```
```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:
```
python -m venv env
```
```
source env/Scripts/activate
```
Установить зависимости из файла requirements.txt:
```
python3 -m pip install --upgrade pip
```
```
pip install -r requirements.txt
```
Выполнить миграции:
```
python3 manage.py migrate
```
Запустить проект:
```
python3 manage.py runserver
```

**Примеры запросов:**
-----------
- Чтобы получить список всех постов отправьте GET-запрос, в качестве целевого URL укажите:
```
http://localhost:8000/api/v1/posts/
```
- Чтобы получить определенную публикацию, отправьте GET-запрос, в качестве целевого URL укажите:
```
http://localhost:8000/api/v1/posts/{id}/
```
- Чтобы получить список из 5 постов, начиная со второго, отправьте GET-запрос, в качестве целевого URL укажите:
```
http://localhost:8000/api/v1/posts/?limit=5&offset=1
```
- Чтобы создать публикацию, отправьте POST-запрос, в качестве целевого URL укажите:
```
http://localhost:8000/api/v1/posts/
```
- Чтобы полностью переписать, частично изменить или удалить пост, отправьте PUT, PATCH или DELETE-запрос соответственно. В качестве целевого URL укажите:
```
http://localhost:8000/api/v1/posts/{id}/
```
- Чтобы осуществить поиск по подпискам, отправьте GET-запрос, в качестве целевого URL укажите:
```
http://localhost:8000/api/v1/follow/?search={username}
```
____

Более подробно ознакомиться с документацией API можно по ссылке после запуска проекта:

http://127.0.0.1:8000/redoc/

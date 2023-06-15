# yamdb_final for sprint16

![My workflow status](https://github.com/DariaZhbanova/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg?event=push)

### Описание

Проект YaMDb собирает отзывы пользователей на различные произведения.

<!-- ### Алгоритм регистрации пользователей

1. Пользователь отправляет POST-запрос на добавление нового пользователя с параметрами email и username на эндпоинт:
```
/api/v1/auth/signup/
```
2. YaMDB отправляет письмо с кодом подтверждения (confirmation_code) на адрес email.
3. Пользователь отправляет POST-запрос с параметрами username и confirmation_code на эндпоинт 
```
/api/v1/auth/token/
```
, в ответе на запрос ему приходит token (JWT-токен).
4. При желании пользователь отправляет PATCH-запрос на эндпоинт
```
/api/v1/users/me/
```
и заполняет поля в своём профайле (описание полей — в документации). -->

<!-- ### Создание файла .env с переменными окружения для работы с базой данных:

Рекомендуется использовать шаблон .env.dist или же .env.sample. Например:
```
https://github.com/bheisig/i-doit-docker/blob/main/.env.dist
``` -->

### Как запустить проект:

Клонировать репозиторий:

```
git clone git@github.com:DariaZhbanova/yamdb_final.git
```
Добавить следующие необходимые ключи (Secrets) в своем профиле GitHub по ссылке:
'https://github.com/<your_github_username>/yamdb_final/settings/secrets/actions'

1. Секретный ключ Вашего проекта для settings.py (установите свой, используя кавычки).  
SECRET_KEY = "some_funky_key"

2. Режим разработки или отладки (по умолчанию False).  
DEBUG = False

3. Параметр с указанием на используемый движок для доступа к базе данных.  
По умолчанию используется Postgres.  
DB_ENGINE = django.db.backends.postgresql

4. Имя базы данных.  
DB_NAME = postgres

5. Логин для подключения к базе данных.  
POSTGRES_USER = postgres

6. Пароль для подключения к базе данных (установите свой).  
POSTGRES_PASSWORD = "new_key"

7. Название сервиса (контейнера).  
DB_HOST = db

8. Порт для подключения к базе данных (принять как 5432).  
DB_PORT = 5432

## В качестве аддона для получения уведомлений в свой телеграм-бот добавьте следующие ключи:

9. ID своего аккаунта в телеграм. Получить его можно у @userinfobot.
TELEGRAM_TO = <your_telegram_id>

10. Токен вашего бота в телеграм. Получить его можно у @BotFather.
TELEGRAM_TOKEN = <your_telegram_bot_token>

## Данный проект сам запускается по адресу 51.250.27.209 при активации команд из корневой директории проекта:

```
git add .
git commit -m <your_commit>
git push
```

Заходим на указанный выше боевой сервер и далее выполняем команды:


Для создания и применения миграций:
```
sudo docker-compose exec web python manage.py makemigrations --noinput
sudo docker-compose exec web python manage.py migrate --noinput
```

Создаем супер-пользователя:
```
sudo docker-compose exec web python manage.py createsuperuser
```

Собрать статику:
```
sudo docker-compose exec web python manage.py collectstatic --no-input
```

Следующим шагом создайте дамп (резервную копию) базы:
```
sudo docker-compose exec web python manage.py dumpdata > fixtures.json
```

Проверьте работоспособность приложения, для этого перейдите на страницу:
```
 http://51.250.27.209/admin/
```

***Документация*** (запросы для работа с API):

```
 http://51.250.27.209/redoc/
```

Автор проекта:
```
Дарья Жбанова
```

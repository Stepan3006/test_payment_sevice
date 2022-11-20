# test_payment_service
Тестовое задание для компании 'Ришат'

Текст задания находится в файле task.txt

## Как запустить проект:
Клонировать репозиторий на свой компьютер
https://github.com/Stepan3006/test_payment_sevice

Перейти в папку stripe_project:
cd payment_sevice/

Создать .env файл, с параметрами:
``` 
    echo 'STRIPE_PUBLIC_KEY=<your_stripe_public_key>
    STRIPE_SECRET_KEY=<your_stripe_secret_key>
    DB_ENGINE=django.db.backends.postgresql
    DB_NAME=postgres
    POSTGRES_USER=<your postgres_username>
    POSTGRES_PASSWORD=<your postgres_password>
    DB_HOST=db
    DB_PORT=5432
    ' >.env
```
Запустить docker-compose:

```docker-compose up -d```

Выполнить миграции:

```docker-compose exec web python manage.py migrate```

Собрать staticfiles:

```docker-compose exec web python manage.py collectstatic --no-input```

Создать пользователя с правами администратора:

```docker-compose exec web python manage.py createsuperuser```

Перейдите на страницу http://localhost/admin/ для доступа к админ-зоне проекта,

Перейдите на страницу http://localhost/item/<int:id>/, действуйте!

http://localhost/check_order/<int:id>/ аналогична предыдущей, но для оплаты заказа.

API Эндпойнты 
http://localhost/buy/<int:id>/ 

http://localhost/pay_for_order/<int:id>/ 

возвращают id платежной сессии.

_Tech_stack:_
Django, Stripe, Docker


_Author:_
Kalinin Stepan https://github.com/Stepan3006

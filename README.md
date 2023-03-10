# **Infra_sp2**
### **Описание:**

Сделал инфраструктуру для запуска командного проекта [api_yamdb-1](https://github.com/Stas767/api_yamdb-1) состоящую из 3 docker-контейнеров (docker-compose):
+ Django-проект "api_yamdb-1" и сервер Gunicorn;
+ База данных Postgres;
+ Сервер nginx, для раздачи статики.
___

### **Технологии:**
+ python 3.7.16;
+ django 2.2;
+ unnittest django;
+ docker;
+ docker-compose;
+ nginx;
+ postgreSQL;
+ gunicorn.
___

### **Как запустить проект в docker конейнере:**

Клонировать репозиторий:

```
git clone git@github.com:Stas767/infra_sp2.git
```
Перейти в папку с docker-compose:

```
cd infra_sp2/infra
```
Запустить docker-compose командой:
```
docker-compose up -d
```

Выполнить миграции:

```
docker-compose exec web python manage.py migrate
```

Создать суперпользователя:

```
docker-compose exec web python manage.py createsuperuser
```
Наполнить базу данных тестовыми записями:

```
docker-compose exec web python manage.py add_csv
```

Собрать статику:

```
docker-compose exec web python manage.py collectstatic --no-input
```
Проект доступен по адресу http://localhost/
___
### **Шаблон наполнения env-файла**
```
DB_ENGINE = указываем, что работаем с postgresql
DB_NAME= имя базы данных
POSTGRES_USER= логин для подключения к базе данных
POSTGRES_PASSWORD= пароль для подключения к БД (установите свой)
DB_HOST= название сервиса (контейнера)
DB_PORT= 
```

___
### **Автор:**
Станислав Балджи
___



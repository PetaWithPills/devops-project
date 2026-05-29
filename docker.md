Docker
Что было сделано

Я добавил в проект Docker для контейнеризации приложения.

Используемые технологии

1) Docker

2) Docker Compose

3) PostgreSQL

4) Node.js

Созданные файлы

Dockerfile

docker-compose.yml

Что  было реализовано

1) контейнеризирован backend на Node.js

2) контейнеризирован PostgreSQL

3) настроены Docker volumes

4) настроены environment variables

5) создан init.sql

6) реализован запуск проекта через Docker Compose

Команда запуска

docker compose up --build


Результат

Backend и PostgreSQL успешно запускаются внутри Docker контейнеров.

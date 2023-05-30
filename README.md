# praktikum_new_diplom
# Foodrgam

[![Django-app workflow](https://github.com/Konyahinzhenya/foodgram-project-react/actions/workflows/main.yml/badge.svg)](https://github.com/Konyahinzhenya/foodgram-project-react/actions/workflows/main.yml)


Проект развернут на сервере - http://158.160.7.66/recipes
http://158.160.7.66/

 Продуктовый помощник - дипломный проект курса Backend-разработки Яндекс.Практикум. Проект представляет собой онлайн-сервис и API для него. На этом сервисе пользователи могут публиковать рецепты, подписываться на публикации других пользователей, добавлять понравившиеся рецепты в список «Избранное», а перед походом в магазин скачивать сводный список продуктов, необходимых для приготовления одного или нескольких выбранных блюд.

Проект реализован на `Django` и `DjangoRestFramework`. Доступ к данным реализован через API-интерфейс. Документация к API написана с использованием `Redoc`.

## Особенности реализации

- Проект завернут в Docker-контейнеры;
- Образы foodgram-frontend и foodgram-backend на DockerHub;
- Реализован workflow c автодеплоем на удаленный сервер и отправкой сообщения в Telegram;


## Развертывание проекта

### Развертывание на локальном сервере

1. Установите на сервере `docker` и `docker-compose`.
2. Создайте файл `/infra/.env`. Шаблон для заполнения файла нахоится в `/infra/.env.example`.
3. Выполните команду `docker-compose up -d --buld`.
4. Выполните миграции `docker-compose exec backend python manage.py migrate`.
5. Создайте суперюзера `docker-compose exec backend python manage.py createsuperuser`.
6. Соберите статику `docker-compose exec backend python manage.py collectstatic --no-input`.
7. Заполните базу ингредиентами `docker-compose exec backend python manage.py load_ingredients`.
8. Документация к API находится по адресу: <http://localhost/api/docs/redoc.html>.

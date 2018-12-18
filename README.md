# Разворачивание Битрикса

## Подготовка
Для разворачивания понадобится установленный Docker и docker-compose. Как их установить, можно посмотреть по ссылке.
https://docs.docker.com/install/linux/docker-ce/ubuntu/
https://docs.docker.com/compose/install/

Поскольку название папки проекта является префиксом для контейнеров, созданных docker-compose, рекомендую называть папку понятно. 

Неправильно: `/proj1/`, `/proj2/`

Правильно: `/docsfera/`, `/petrovich/`

В папку с проектом необходимо склонировать данный репозиторий

## Вариант 1 (если архив битрикса нормальный)

В корневой папке проекта запускаем команду `docker-compose up -d`

После этого должны запуститься 3 контейнера: fpm, apache, db

Набираем команду:
`docker ps`

В выводе должно быть что-то такое:
```
60d8be2ab596        spprlocal_fpm               "docker-php-entrypoi…"   2 months ago        Up 6 hours          9000/tcp                         spprlocal_fpm_1
359af136d39b        spprlocal_db                "docker-entrypoint.s…"   2 months ago        Up 6 hours          3306/tcp                         spprlocal_db_1
10f40ec41126        webdevops/apache:alpine-3   "/entrypoint supervi…"   2 months ago        Up 6 hours          443/tcp, 0.0.0.0:32768->80/tcp   spprlocal_apache_1
```
Видим у контейнера `_apache_1` порт 32768 (или любой другой похожий). Это порт, по которому ваш сайт будет доступен из браузера.

Попробуем развернуть битрикс из резервной копии. Для этого в браузере открываем следующий путь:

`127.0.0.1:32768`

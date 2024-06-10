## Настройка докера
- скопируйте файл .env.example в .env, управление докером ведется через него
- скопируйте docker-compose.yml.example в docker-compose.yml, вносить изменения в файл примера запрещено
- укажите название проекта в значении `APP_CODE_PATH_HOST`, в дальнейшем вам нужно будет развернуть проект внутри этой папки
- в значение `COMPOSE_PROJECT_NAME` обязательно укажите название проекта, он повлияет на названия контейнеров, образов и сетей
- в значение `PHP_VERSION` укажите требуемую версию php
- остальные значения меняйте на свой страх и риск
- по умолчанию включена установка следующих пакетов: composer, xdebug, redis

## Настройка nginx
- в папке nginx/conf.d скопируйте файл app.conf.example в app.conf
- обновите значение `server_name` на то которое хотите использовать

## Настройка php.ini
- в папке скопируйте или создайте новый ini файл с шаблоном по следующему примеру `php-${PHP_VERSION}-${APP_ENV}.ini`, например php-8.2-local.ini

## FAQ
- если вам НЕ нужен редис:  закомментируйте его в docker-compose.yml
- если хотите добавить новых сервисов: добавьте какие хотите, главное не docker-compose.yml.example
- у меня уже есть образ: используйте второй пример app, а первый закомментируйте
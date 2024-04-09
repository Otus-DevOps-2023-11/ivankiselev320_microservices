# ivankiselev320_microservices
ivankiselev320 microservices repository

### ДЗ №13

- Установка Docker и зависимостей
- Протестированы типовые команды Docker
- Вывод docker images в файл [docker-1.log](docker/docker-monolith/docker-1.log)
- Установлен и настроен docker-machine, протестирована установка и запуска контейнера на удаленном хосте
- Создан каталог docker-monolith, [Dockerfile](docker/docker-monolith/Dockerfile), [db_config](docker/docker-monolith/db_config), [mongod.conf](docker/docker-monolith/mongod.conf), [start.sh](docker/docker-monolith/start.sh)
- Собран контейнер с помощью команды docker build .
- Зарегистрирован аккаунт в DockerHub, образ загружен и протестирован

### ДЗ №14

- Создан каталог src и Dockerfile для сборки контейнеров
- [comment](src/comment/Dockerfile), [post-py](src/post-py/Dockerfile), [ui](src/ui/Dockerfile)
- Исправлены ошибки с зависимостями, подобраны другие базовые образы т.к. дефолтные были deprecated и так же выбраны slim версии для уменьшения размера
- Создан volume для mongo
- Создана bridge сеть для контейнеров
- Контейнеры запущены протетсированы, при удалении контейнеров и запуске повторно данные сохраняются т.к. volume хранит состояние базы

### ДЗ №15

- Изучил и попрактиковался с сетями докера
- Создан [docker-compose.yml](docker/docker-compose.yml) с соблюдением всех условий, контейнеры в корректных сетях, переменные вынесены в [.env](docker/.env.example)
- Так же создан [docker-compose.override.yml](docker/docker-compose.override.yml) для запуска в dev режиме
- Добавил в [README.md](src/README.md) описание как формируется имя проекта

### ДЗ №17

- Запустил prometheus и ознакомился с функционалом
- Собрал свой образ [prometheus](monitoring/prometheus/Dockerfile), добавив в контейнер конфиг [prometheus.yml](monitoring/prometheus/prometheus.yml)
- Так же добавил сборщик метрик и сам prometheus в [docker-compose.yml](docker/docker-compose.yml), прописал им сети
- Ознакомился с метриками, провел тестирование
- Собранные контейнеры запушены в docker hub https://hub.docker.com/u/ivankiselev320

### ДЗ №18

- Подготовлено окружение для тестирования логирования и трейсинга
- Созданы [docker-compose-logging.yml](docker/docker-compose-logging.yml), подготовлен контейнер [Dockerfile](logging/fluentd/Dockerfile)
- Протестирован сбор структурированных и неструктурировнных логов, визуализация логов
- Добавлен zipkin в [docker-compose-logging.yml](docker/docker-compose-logging.yml) и протестирован

### ДЗ №19

- Установлен и настроен кластер k8s
- Добавлены ноды ссылкой которую сгенерировал kubectl init
- Установлен плагин calico
- Созданы манифесты для запуска контейнеров в кластере: [comment-deployment.yml](kubernetes/reddit/comment-deployment.yml), [mongo-deployment.yml](kubernetes/reddit/mongo-deployment.yml), [post-deployment.yml](kubernetes/reddit/post-deployment.yml), [ui-deployment.yml](kubernetes/reddit/ui-deployment.yml)
- Поды запущены

### ДЗ №20

- 
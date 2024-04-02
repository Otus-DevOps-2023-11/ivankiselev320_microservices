# ivankiselev320_microservices
ivankiselev320 microservices repository

### ДЗ №13

- Установка Docker и зависимостей
- Протестированы типовые команды Docker
- Вывод docker images в файл [docker-1.log](docker-monolith/docker-1.log)
- Установлен и настроен docker-machine, протестирована установка и запуска контейнера на удаленном хосте
- Создан каталог docker-monolith, [Dockerfile](docker-monolith/Dockerfile), [db_config](docker-monolith/db_config), [mongod.conf](docker-monolith/mongod.conf), [start.sh](docker-monolith/start.sh)
- Собран контейнер с помощью команды docker build .
- Зарегистрирован аккаунт в DockerHub, образ загружен и протестирован

### ДЗ №14

- Создан каталог src и Dockerfile для сборки контейнеров
- [comment](src/comment/Dockerfile), [post-py](src/post-py/Dockerfile), [ui](src/ui/Dockerfile)
- Исправлены ошибки с зависимостями, подобраны другие базовые образы т.к. дефолтные были deprecated и так же выбраны slim версии для уменьшения размера
- Создан volume для mongo
- Создана bridge сеть для контейнеров
- Контейнеры запущены протетсированы, при удалении контейнеров и запуске повторно данные сохраняются т.к. volume хранит состояние базы

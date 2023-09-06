# media-holder-CICD
media holder docker compose repository

Микросервис хранения файлов


Для установки и работы работы с микросервисом Media-holder на Вашем компьтере
должны быть установлены следующие программы:

- Docker - инструмент для работы с контейнерами

- Docker compose - инструмент для запуска мультиконтейнерного приложения,
которое не зависит от платформы и содержит все необходимые для работы
технологии и библиотеки.


# Создание и запуск приложения media-holder с использованием Docker конетейнера

1. Загрузите docker-образ с Docker Hub.
(Docker Hub - хранилище всех доступных Docker-образов).
Для этого в консоли выполните команду от имени администратора
(для OS Linux используйте префикс sudo):

docker pull fldslf/media-holder:latest

В случае отсутствия, одновременно с образом микросервиса, будет автоматически
загружен образ SQL-сервера Postgres.


2. Проконтролируйте наличие докер-образа микросервиса и необходимого SQL-сервера
в локальном репозитории с помощью команды: 

sudo docker image ls

- Список образов должен включать в себя:

REPOSITORY            TAG       IMAGE ID       CREATED       SIZE
...
fldslf/media-holder   latest    ...
...
postgres              15        ...
...


- Для дальнейшего создания и запуска контейнеров docker и observationdata создайте 
на диске директорию postgres. В ней создайте еще одну директорию postgres, а также 
скопируйте и поместите файл docker-compose.yml из данного репозитория.

- Для создания и запуска контейнеров в консоли перейдите в директорию 'postgres', 
в которой находится файл docker-compose.yml и выполните команду: 

sudo docker-compose up

- После завершения процесса сборки и запуска контейнеров при необходимости просмотреть список 
работающих контейнеров docker используйте команду:

sudo docker ps

- При успешном запуске сервиса в списке контейнеров должен присутствовать данный 
контейнер с именем:

postgres_observationdata-service_1

- После запуска контейнеров используйте программу DBeaver. Создайте новое подключение PostgreSQL с 
именем 'postgres' и паролем 'password'. В подключении 'postgres' уже будет присутствовать 
созданная база данных 'postgres-observation' со всеми таблицами.




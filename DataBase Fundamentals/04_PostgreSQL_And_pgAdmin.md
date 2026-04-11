# 04. PostgreSQL and pgAdmin

## Зачем нужен этот модуль

Этот модуль нужен, чтобы участник понимал, что именно он разворачивает локально и как связаны между собой сервер БД, база данных, клиент и инструмент администрирования.

## Что нужно понять

### 1. PostgreSQL server

`PostgreSQL` — это сервер СУБД.

Он:
- хранит базы данных;
- принимает подключения;
- выполняет SQL-запросы;
- управляет пользователями, транзакциями и ограничениями.

### 2. Database

Внутри одного экземпляра `PostgreSQL` можно создавать несколько баз данных.

Это важно понимать, потому что:
- сервер и база данных — не одно и то же;
- сначала работает сервер;
- потом внутри него создается конкретная база.

### 3. Client

Клиент — это программа, через которую пользователь подключается к БД.

Клиентом может быть:
- `psql`;
- `pgAdmin`;
- приложение;
- скрипт.

### 4. pgAdmin

`pgAdmin` — это графический клиент и административный инструмент для `PostgreSQL`.

Он помогает:
- подключаться к серверу;
- создавать базы;
- создавать таблицы;
- выполнять SQL;
- смотреть схему и данные.

### 5. Connection

Чтобы подключиться к БД, обычно нужны:
- host;
- port;
- database;
- username;
- password.

Даже если все работает локально, эти сущности все равно полезно различать.

### 6. Локальная установка

Для учебного задания важно понимать простую картину:
- `PostgreSQL` установлен локально;
- `pgAdmin` подключается к нему как клиент;
- участник руками создает БД и таблицы;
- никакие контейнеры и orchestration не используются.

## Что нужно уметь после модуля

После этого модуля участник должен уметь:
- объяснить, что такое сервер `PostgreSQL`;
- объяснить разницу между сервером и базой данных;
- объяснить, чем `pgAdmin` отличается от самой СУБД;
- показать, какие параметры нужны для подключения;
- объяснить, что именно происходит при локальном развертывании БД.

## Ресурсы

- PostgreSQL Tutorial:
  [https://www.postgresql.org/docs/current/tutorial.html](https://www.postgresql.org/docs/current/tutorial.html)
- PostgreSQL Architectural Fundamentals:
  [https://www.postgresql.org/docs/current/tutorial-arch.html](https://www.postgresql.org/docs/current/tutorial-arch.html)
- PostgreSQL Creating a Database:
  [https://www.postgresql.org/docs/current/manage-ag-createdb.html](https://www.postgresql.org/docs/current/manage-ag-createdb.html)
- PostgreSQL createdb utility:
  [https://www.postgresql.org/docs/current/app-createdb.html](https://www.postgresql.org/docs/current/app-createdb.html)
- pgAdmin Documentation:
  [https://www.pgadmin.org/docs/pgadmin4/latest/index.html](https://www.pgadmin.org/docs/pgadmin4/latest/index.html)
- pgAdmin Getting Started:
  [https://www.pgadmin.org/docs/pgadmin4/latest/getting_started.html](https://www.pgadmin.org/docs/pgadmin4/latest/getting_started.html)

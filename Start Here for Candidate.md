# Start Here for Candidate

Этот файл — стартовая точка для кандидата, стажера или джуна.

Если вам выдали этот репозиторий для прохождения программы, начинайте отсюда.

## Полная карта прохождения

```mermaid
flowchart TB
    S["Start Here for Candidate"]
    M["Main Route: INF Learning Program"]
    B1["Block 1\nEnvironment and Core Processes"]
    B2["Block 2\nCMDB Test Data"]
    B3["Block 3\nCMDB Data Model and Advanced ITSM"]
    B4["Block 4\nAvailability and Integration Design"]
    DB["Parallel Track\nDataBase Fundamentals"]
    DEV["Parallel Track\nDevelopers Theory Fundamentals"]
    KB["Reference Track\nKnowledge Base"]

    S --> M
    M --> B1
    B1 --> B2
    B2 --> B3
    B3 --> B4

    B1 -. "use as glossary and reference" .-> KB
    B2 -. "use as glossary and reference" .-> KB
    B3 -. "required if SQL / PostgreSQL / ER-model base is weak" .-> DB
    B3 -. "use as glossary and reference" .-> KB
    B4 -. "required if client-server / HTTP / DOM base is weak" .-> DEV
    B4 -. "use as glossary and reference" .-> KB

    click S "https://github.com/nadirakpayev/INF-Jira-Learning-Program/blob/main/Start%20Here%20for%20Candidate.md" "Open start file"
    click M "https://github.com/nadirakpayev/INF-Jira-Learning-Program/blob/main/INF%20Learning%20Program/README.md" "Open main route"
    click B1 "https://github.com/nadirakpayev/INF-Jira-Learning-Program/blob/main/INF%20Learning%20Program/Block%201/01_Setup_Atlassian_Cloud.md" "Open Block 1"
    click B2 "https://github.com/nadirakpayev/INF-Jira-Learning-Program/blob/main/INF%20Learning%20Program/Block%202/07_CMDB_Test_Data_Practice.md" "Open Block 2"
    click B3 "https://github.com/nadirakpayev/INF-Jira-Learning-Program/blob/main/INF%20Learning%20Program/Block%203/08_CMDB_Data_Modeling_Practice.md" "Open Block 3"
    click B4 "https://github.com/nadirakpayev/INF-Jira-Learning-Program/blob/main/INF%20Learning%20Program/Block%204/15_Availability_Management_Practice.md" "Open Block 4"
    click DB "https://github.com/nadirakpayev/INF-Jira-Learning-Program/blob/main/DataBase%20Fundamentals/README.md" "Open DataBase Fundamentals"
    click DEV "https://github.com/nadirakpayev/INF-Jira-Learning-Program/blob/main/Developers%20Theory%20Fundamentals/README.md" "Open Developers Theory Fundamentals"
    click KB "https://github.com/nadirakpayev/INF-Jira-Learning-Program/blob/main/Knowledge%20Base/README.md" "Open Knowledge Base"
```

Если ваш просмотрщик Markdown не делает узлы диаграммы кликабельными, используйте ссылки ниже.

## Нажимаемая карта маршрута

### Основной маршрут

- [INF Learning Program/README.md](INF%20Learning%20Program/README.md) — главный маршрут программы.
- [Block 1](INF%20Learning%20Program/Block%201/01_Setup_Atlassian_Cloud.md) — создание среды и базовые процессы.
- [Block 2](INF%20Learning%20Program/Block%202/07_CMDB_Test_Data_Practice.md) — тестовые данные CMDB.
- [Block 3](INF%20Learning%20Program/Block%203/08_CMDB_Data_Modeling_Practice.md) — модель данных CMDB, PostgreSQL и расширенные ITSM-процессы.
- [Block 4](INF%20Learning%20Program/Block%204/15_Availability_Management_Practice.md) — доступность и проектирование интеграций.

### Параллельные треки

- [DataBase Fundamentals/README.md](DataBase%20Fundamentals/README.md) — открывайте перед блоком 3, если не хватает базы по РБД, SQL, `JOIN`, подзапросам, `PostgreSQL` и `pgAdmin`.
- [Developers Theory Fundamentals/README.md](Developers%20Theory%20Fundamentals/README.md) — открывайте перед блоком 4, если не хватает базы по клиент-серверной архитектуре, `HTTP`, `HTML` и `DOM`.
- [Knowledge Base/README.md](Knowledge%20Base/README.md) — используйте по ходу всей программы как словарь и справочный слой.

## Что является основным маршрутом

Основной трек:
- [INF Learning Program/README.md](INF%20Learning%20Program/README.md)

Именно этот трек нужно проходить как главный.

## Рекомендуемый порядок

1. Откройте [INF Learning Program/README.md](INF%20Learning%20Program/README.md).
2. Идите по блокам строго по порядку.
3. Если на каком-то этапе не хватает базы по данным, откройте [DataBase Fundamentals/README.md](DataBase%20Fundamentals/README.md).
4. Если не хватает базовой веб-теории, откройте [Developers Theory Fundamentals/README.md](Developers%20Theory%20Fundamentals/README.md).
5. Если нужен дополнительный словарь и внешние ссылки, используйте [Knowledge Base/README.md](Knowledge%20Base/README.md).

## Что не является стартовой точкой для кандидата

На старте не нужно ориентироваться на внутренние материалы.

Их можно игнорировать, если вам отдельно не сказали обратное:
- `Internal Materials/`

## Коротко

Если нужно выбрать один файл для старта:
- начните с [INF Learning Program/README.md](INF%20Learning%20Program/README.md)

# Формат сдачи

Сдача идет по блокам.

Для screening обязательны:
- `Блок 1`
- `Блок 2`

`Блок 3` и `Блок 4` добавляются только после `PASS`.

## Структура пакета

```text
submission/
  README.md
  decision_log.md
  block_1/
    README.md
    jira/
      screenshots/
      automation_summary.md
      sla_summary.md
      queues_summary.md
      catalog_summary.md
  block_2/
    README.md
    data/
      data_model.md
      schema.sql
      seed.sql
      validation_queries.sql
      query_results.md
      pgadmin_setup_notes.md
    jira/
      screenshots/
      process_linkage_summary.md
      sla_summary.md
      queues_summary.md
  block_3/
    README.md
    availability_summary.md
    screenshots/
  block_4/
    README.md
    integration_model.md
    screenshots/
```

## Что обязательно для screening

### Корень пакета

- `submission/README.md`
  - что реализовано;
  - что не реализовано;
  - список ограничений;
  - краткая карта содержимого.
- `submission/decision_log.md`
  - 5-15 решений;
  - формат: решение / причина / компромисс.

### Блок 1

- `submission/block_1/README.md`
- `submission/block_1/jira/catalog_summary.md`
- `submission/block_1/jira/automation_summary.md`
- `submission/block_1/jira/sla_summary.md`
- `submission/block_1/jira/queues_summary.md`
- evidence-скриншоты

### Блок 2

- `submission/block_2/README.md`
- `submission/block_2/data/data_model.md`
- `submission/block_2/data/schema.sql`
- `submission/block_2/data/seed.sql`
- `submission/block_2/data/validation_queries.sql`
- `submission/block_2/data/query_results.md`
- `submission/block_2/data/pgadmin_setup_notes.md`
- `submission/block_2/jira/process_linkage_summary.md`
- `submission/block_2/jira/sla_summary.md`
- `submission/block_2/jira/queues_summary.md`
- evidence-скриншоты

## Обязательные скриншоты для Блока 1

Минимум:
- экран cloud-site или проекта;
- список `Components`;
- request types или портал;
- пример маршрутизации или default assignee;
- очередь инцидентов;
- очередь сервисных запросов;
- `SLA` инцидентов;
- `SLA` сервисных запросов.

## Обязательные скриншоты для Блока 2

Минимум:
- схема таблиц в `pgAdmin`;
- пример данных в таблицах;
- результат минимум `2` SQL-запросов;
- пример `Major Incident`;
- пример `Problem`;
- пример `Change`;
- evidence их связки;
- `SLA` второго блока;
- `Queues` второго блока.

## Правила

- один файл = одно понятное доказательство;
- названия файлов должны быть читаемыми;
- скриншоты должны содержать данные, а не только общий экран;
- текст должен ссылаться на конкретные evidence-файлы;
- `Source Docs` не нужно включать в submission.

## Что не считается сдачей

Не принимается:
- только ссылка на Jira;
- только устная демонстрация;
- только narrative без SQL и evidence;
- только SQL без Jira-части;
- только Jira без модели данных.

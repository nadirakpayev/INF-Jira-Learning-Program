# Raw Code Fragments Extracted from DOCX XML

## Что это

В этом файле собраны не пересказы, а буквальные кодоподобные фрагменты, которые удалось извлечь из XML внутри исходных `.docx`.

Важно:
- это не полные исходники `.groovy`;
- в документах не обнаружены цельные script bodies, готовые к исполнению;
- ниже перечислены реальные токены, вызовы API, идентификаторы полей и фрагменты логики, которые присутствуют в тексте документа.

Основной источник:
- `Source Docs/Forte-J-ITSM25+Руководство+администратора_v1.0.docx`

## HAPI / ScriptRunner / Jira API Fragments

Найдены буквальные фрагменты:

```text
Issues.
Issues.getByKey()
Users.
Users.getByName(assigneeName)
Assets.*
Assets.search
Assets.search(...)
issue.update()
issueManager.updateIssue
DO_NOT_DISPATCH
RUN_AS_USER
```

Что это подтверждает:
- исходные описания действительно опирались на `HAPI` и ScriptRunner-логику;
- часть скриптов использовала обновление задач без диспатча событий;
- назначение исполнителя и поиск задач/объектов шли через Jira/Assets API.

## Custom Field IDs and Workflow Tokens

Найдены буквальные идентификаторы:

```text
customfield_12401
customfield_12600
customfield_12329
```

Найдены буквальные логические маркеры:

```text
return false
```

Интерпретация:
- `customfield_12401` фигурирует в логике группы `Problem Manager`;
- `customfield_12600` используется в логике обходного решения;
- `customfield_12329` упоминается как числовой счетчик откатов;
- `return false` подтверждает наличие condition-логики с блокировкой перехода.

## Date / Time Logic

Найдены буквальные фрагменты:

```text
LocalDateTime.now()
ZoneId.systemDefault()
```

Что это значит:
- пост-функции дат опирались на серверное локальное время;
- часть логики зависела от часового пояса сервера Jira, а не бизнес-таймзоны.

## GLPI Integration Tokens

Найдены буквальные интеграционные токены:

```text
sessionToken
appToken
userToken
Config
GLPIAuth
GLPIService
Mailer
```

Найдены буквальные имена таблиц:

```text
glpi_computers
glpi_softwares
glpi_softwareversions
glpi_items_softwareversions
```

Что это подтверждает:
- интеграция была завязана и на REST API GLPI, и на прямое чтение таблиц через datasource;
- в документах действительно присутствуют признаки job-логики, а не только бизнес-описания.

## Performance / Background Processing Fragments

Найдены буквальные фрагменты:

```text
Thread.sleep
LIMIT N
```

Интерпретация:
- job-скрипты предполагали ретраи или паузы между вызовами;
- для тестовых запусков рекомендовалось ограничивать объем обрабатываемых данных.

## Assets Query and Filtering Fragments

Найдены буквальные фрагменты:

```text
startOfDay(0d)
"Updated" >= startOfDay(0d)
```

Что это означает:
- в скрипте профиля замещения использовалась фильтрация объектов, обновленных за текущий день;
- фильтрация явно опиралась на синтаксис запросов Assets.

## Ограничения восстановления

Что не удалось извлечь в виде полного кода:
- блоки `import ...`;
- complete class bodies;
- полные Groovy closures;
- готовые SQL-запросы целиком;
- HTTP payloads и полноценные REST-вызовы.

Итог:
- из `Source Docs` удалось извлечь реальные буквальные фрагменты кода и идентификаторы;
- полноценный комплект исходников в документах отсутствует;
- для практического использования эти фрагменты нужно рассматривать как forensic-слой поверх файлов с описанием логики:
  - `01_Problem_Management_Scripts.md`
  - `02_Availability_Scripts.md`
  - `03_Change_Management_Scripts.md`
  - `04_GLPI_Integration_Jobs.md`
  - `05_Substitution_Profile_Script.md`

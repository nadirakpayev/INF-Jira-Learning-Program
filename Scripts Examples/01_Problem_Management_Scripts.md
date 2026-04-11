# Problem Management Scripts

Источник:
- `Source Docs/Forte-J-ITSM25+Руководство+администратора_v1.0.docx`

Ниже собраны все найденные скрипты по workflow conditions, listeners, post-functions и behaviours для problem management.

## Workflow Conditions

### `1_conditionOnPRBManagersGrup`

- Тип: workflow condition
- Назначение: показывать переход только участникам Assets-группы из поля `Группа Problem Manager`
- Ключевая зависимость: Insight/Assets API
- Основная логика:
  - прочитать Assets-группу из custom field;
  - извлечь участников Jira;
  - сравнить с текущим пользователем;
  - вернуть `true/false`

### `1_simpleConditionDiagTeam`

- Тип: workflow condition
- Назначение: разрешить переход участникам команды диагностики PRB
- Основная логика:
  - прочитать Assets-объект команды;
  - получить связанных сотрудников;
  - извлечь их `Jira Пользователь`;
  - сравнить с текущим пользователем

### `1_simpleConditionPRBCoord`

- Тип: workflow condition
- Назначение: разрешить переход только координатору проблемы
- Основная логика:
  - взять объект сотрудника из поля `Координатор проблемы`;
  - извлечь его `Jira Пользователь`;
  - сравнить с текущим пользователем

### `KnownError_condition_available`

- Тип: workflow condition
- Назначение: разрешить fast-track transition для инцидента, если связанная проблема и обходное решение удовлетворяют условиям
- Основная логика:
  - взять объект `Известная Ошибка`;
  - найти связанную проблему по JQL;
  - проверить статус проблемы;
  - проверить флаг обходного решения;
  - вернуть `true/false`

### `KnownError_condition_limited`

- Тип: workflow condition
- Назначение: инвертированная логика доступности перехода по известной ошибке
- Отличие: при "недопустимом" статусе или `Нет` по обходному решению возвращает `true`

## Listeners

### `1_ListenerAutomaticPriorityPRB_script`

- Тип: listener
- Событие: `IssueLinkCreatedEvent`
- Назначение: повышать приоритет проблемы по количеству связанных инцидентов
- Дополнительно:
  - добавляет комментарий;
  - отправляет email уведомления Problem Manager и команде диагностики

### `1_ListenerLinkCreatedTransitionINC_script`

- Тип: listener
- Событие: `IssueLinkCreatedEvent`
- Назначение: при связывании инцидента с проблемой автоматически переводить инцидент в нужный статус
- Основная логика:
  - определить пару `Инцидент` / `Проблема`;
  - прочитать статус проблемы и значения полей решения;
  - перевести инцидент в один из целевых статусов;
  - при необходимости отправить уведомление

## Problem / KEDB Post-Functions

### `1_CreateLinkedIssue_Problem`

- Тип: post-function / automation
- Назначение: создать `Проблему` при переходе из значительного инцидента и обработать связанные инциденты
- Делает:
  - проверяет флаг `Кандидат в проблему`;
  - вычисляет ИТ-владельца и приоритет;
  - копирует поля;
  - создает новую задачу `Проблема`;
  - связывает объекты;
  - переводит связанные инциденты

### `1_notificationOnProblemManagerRFCclosed_script`

- Тип: post-function
- Назначение: уведомить Problem Manager о закрытии связанного RFC

### `1_problemCreateUpdateKEDB_script`

- Тип: post-function / sync script
- Назначение: создать или обновить объект `Известная ошибка` в KEDB на основе задачи `Проблема`

### `1_problemNotifyChangedDesc_script`

- Тип: post-function
- Назначение: отправить уведомление при изменении описания проблемы

### `1_problemPermanentResolution_script`

- Тип: post-function
- Назначение: при постоянном решении обработать связанные инциденты, проставить поля и разослать уведомления

### `1_ProblemSetManager_script (Deprecated)`

- Тип: deprecated helper script
- Назначение: подобрать `Problem Manager` и группу по выбранной системе
- Особенность: жесткая зависимость от формата `KE-...` и `AD-...`

### `1_problemWorkaroundlogic_script`

- Тип: post-function
- Назначение: применить workaround ко всем связанным инцидентам

### `1_transitionIncidentProblemDeclined_script`

- Тип: post-function
- Назначение: вернуть связанные инциденты на нужную линию поддержки при отклонении проблемы

### `KnownError_function_available`

- Тип: post-function
- Назначение: связать инцидент с проблемой по объекту `Известная ошибка` и сразу заполнить решение / резолюцию / комментарий

### `KnownError_function_limited`

- Тип: post-function
- Назначение: ограниченная версия, создающая только issue link с проблемой

## Date Setting Post-Functions

### `1_setDateonTransition_onVendor`

- Тип: date post-function
- Назначение: записать дату отправки на вендора

### `1_setDateonTransition_workaround`

- Тип: date post-function
- Назначение: записать дату применения обходного решения

### `1_setDateonTransition_close`

- Тип: date post-function
- Назначение: записать дату фактического закрытия

Во всех трех случаях общая логика одинаковая:
- выполнить код от `RUN_AS_USER`;
- записать `LocalDateTime.now()` в целевое поле;
- сохранить задачу без дополнительных проверок

## Behaviours

### `FORTE: Restrict Issue Types for Linking Issues`

- Тип: Behaviour
- Назначение: на create-экране проблемы принудительно выставить link type и проверить наличие хотя бы одного связанного инцидента

### `FORTE SM: Ограничение создания проблем для группы менеджеров`

- Тип: Behaviour
- Назначение: автоматически подставить группу Problem Manager по системе и запретить создание проблемы неавторизованному пользователю

### `FORTE SM: Скрытия подзадач в зависимости от типа запроса`

- Тип: Behaviour
- Назначение:
  - фильтровать типы подзадач;
  - скрывать типы задач на create;
  - ограничивать видимость типа `Событие недоступности`

### `FORTE: Логика перехода в известную ошибку`

- Тип: Behaviour
- Назначение: делать текст обходного решения обязательным, если выбран флаг `Да`

## Что важно

- В документе найдено описание логики, а не исходные `.groovy` файлы.
- Почти все скрипты завязаны на `Insight/Assets`, `RUN_AS_USER`, числовые `customfield_*` и Jira Data Center / ScriptRunner.
- Это описания серверной логики, а не Cloud-ready реализация.

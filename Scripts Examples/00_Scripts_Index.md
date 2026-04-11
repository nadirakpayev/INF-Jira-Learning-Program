# Индекс найденных скриптов

## Источники

Основной источник:
- `Source Docs/Forte-J-ITSM25+Руководство+администратора_v1.0.docx`

Косвенные упоминания без детализации:
- `Source Docs/FORTE-J-ITSM25+Регламент+процесса+Управления+конфигурациями+и+активами+v03.docx`
- `Source Docs/FORTE-J-ITSM25+Руководство+пользователя+процесса+Управления+конфигурациями+и+активами+v03.docx`
- `Source Docs/Forte-J-ITSM25+Техническое+задание+процесса+Управления+конфигурациями+и+активами+v03.docx`

Во вторичных источниках найдено только упоминание `automation rule`, без самих скриптов.

## Workflow Conditions

- `1_conditionOnPRBManagersGrup`
- `1_simpleConditionDiagTeam`
- `1_simpleConditionPRBCoord`
- `KnownError_condition_available`
- `KnownError_condition_limited`

## Listeners

- `1_ListenerAutomaticPriorityPRB_script`
- `1_ListenerLinkCreatedTransitionINC_script`

## Problem / KEDB Post-Functions

- `1_CreateLinkedIssue_Problem`
- `1_notificationOnProblemManagerRFCclosed_script`
- `1_problemCreateUpdateKEDB_script`
- `1_problemNotifyChangedDesc_script`
- `1_problemPermanentResolution_script`
- `1_ProblemSetManager_script (Deprecated)`
- `1_problemWorkaroundlogic_script`
- `1_transitionIncidentProblemDeclined_script`
- `KnownError_function_available`
- `KnownError_function_limited`

## Date Setting Post-Functions

- `1_setDateonTransition_onVendor`
- `1_setDateonTransition_workaround`
- `1_setDateonTransition_close`

## Behaviours

- `FORTE: Restrict Issue Types for Linking Issues`
- `FORTE SM: Ограничение создания проблем для группы менеджеров`
- `FORTE SM: Скрытия подзадач в зависимости от типа запроса`
- `FORTE: Логика перехода в известную ошибку`

## Availability Scripts

- `Назначение AM manager`
- `Назначение Исполнителя заявки`
- `Рассылка для ИТ-владельца`
- `Расчет плановой длительности простоя (в минутах)`
- `Расчет фактической длительности простоя (в минутах) для внеплановой`
- `Расчет фактической длительности простоя (в минутах)`
- `Создание события недоступности из ЗИ`
- `Условия поля AM manager`

## Change Management Scripts

- `Автоматическая подстановка группы Change manager`
- `Заполнение поля Автостарт по плановой дате`
- `Заполнение Тип запроса для портала`
- `Заполнение фактической даты`
- `Рассылка для согласующих`
- `Рассылка для участников группы Change manager`
- `Рассылка для участников группы исполнителей`
- `Создание связанной PIR задачи`
- `Создание связанной PIR-задачи_не успешно`
- `Создание связанной задачи PIR_условие`
- `Создание события недоступности из RFC`
- `Увеличение счетчика откатов на +1`

## GLPI Integration Jobs and Classes

- `Job: актуализация групп ПО`
- `Job: актуализация ПК`
- `Job: актуализация версионности`
- `Job: актуализация виртуальных машин (VM)`
- `Job: актуализация сетевого оборудования`
- `Job: актуализация Разрешенного ПО`
- `MappingComputer`
- `MappingSoftware`
- `MappingVersion`
- `MappingVM`
- `MappingNetwork`
- `GLPIAuth`
- `GLPIService`
- `Mailer`
- `Config`

## Substitution Profile

- `Профиль замены`

## Literally Extracted Code Fragments

- `HAPI / Assets / Issues / Users API tokens`
- `RUN_AS_USER`
- `LocalDateTime.now()`
- `DO_NOT_DISPATCH`
- `Users.getByName(...)`
- `Issues.getByKey(...)`
- `Assets.search(...)`
- `customfield_12401`
- `customfield_12600`
- `customfield_12329`
- `sessionToken`
- `appToken`
- `userToken`
- `glpi_computers`
- `glpi_softwares`
- `glpi_softwareversions`
- `glpi_items_softwareversions`
- `Thread.sleep`
- `LIMIT N`
- `startOfDay(0d)`

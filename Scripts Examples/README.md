# Scripts Examples

В этой папке собраны все найденные в `Source Docs` скрипты и скриптоподобные технические артефакты.

Важно:
- в исходных `.docx` в большинстве случаев найдено не тело исходного кода, а структурированные описания скриптов;
- основной источник скриптов: `Source Docs/Forte-J-ITSM25+Руководство+администратора_v1.0.docx`;
- остальные документы в основном содержат только упоминания `automation rule`, без детальной спецификации скриптов.

Что найдено:
- workflow conditions;
- listeners;
- post-functions;
- behaviours;
- расчетные и служебные скрипты по доступности;
- скрипты по change management;
- интеграционные groovy-job’ы GLPI -> Jira Assets;
- скрипт профиля замещения.

Структура:
- `00_Scripts_Index.md` — полный индекс найденных скриптов;
- `01_Problem_Management_Scripts.md` — conditions, listeners, post-functions, behaviours для problem flow;
- `02_Availability_Scripts.md` — скрипты по доступности;
- `03_Change_Management_Scripts.md` — скрипты и служебные функции RFC/PIR;
- `04_GLPI_Integration_Jobs.md` — job’ы и классы интеграции GLPI;
- `05_Substitution_Profile_Script.md` — логика замещения.
- `06_Raw_Code_Fragments.md` — буквальные кодовые фрагменты и токены, извлеченные из XML внутри `.docx`.

Не найдено:
- полноценные raw Groovy-файлы;
- отдельные `.groovy`, `.sql`, `.json`, `.sh` или `.py` в `Source Docs`;
- автономные script attachments вне текстового описания.

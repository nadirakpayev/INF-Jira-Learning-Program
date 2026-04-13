# CMDB Test Data Reference

Этот файл содержит единый учебный датасет для заданий по CMDB. Данные сгенерированы как реалистичные, но не относятся к реальным организациям.

## Сервисы

| service_code | service_name | service_owner | criticality |
| --- | --- | --- | --- |
| SRV-001 | Digital Workplace | A. Nurbekova | High |
| SRV-002 | Payments Hub | D. Kassenov | Critical |
| SRV-003 | CRM Operations | I. Sarsenbayev | High |
| SRV-004 | HR Self-Service | M. Bekturova | Medium |
| SRV-005 | Corporate Data Platform | E. Tulegenova | High |

## Рабочие группы

| workgroup_code | workgroup_name | lead_name | support_line |
| --- | --- | --- | --- |
| WG-APP | Application Support | Timur Zhakupov | L2 |
| WG-DB | Database Operations | Marina Kim | L2 |
| WG-INF | Infrastructure Operations | Rustem Sadykov | L3 |
| WG-SD | Service Desk | Aliya Omarova | L1 |
| WG-NET | Network Services | Daniyar Utebayev | L2 |

## Сотрудники

| employee_code | full_name | role_name | workgroup_code | email |
| --- | --- | --- | --- | --- |
| EMP-001 | Aliya Omarova | Service Desk Lead | WG-SD | aliya.omarova@example.local |
| EMP-002 | Timur Zhakupov | Application Support Lead | WG-APP | timur.zhakupov@example.local |
| EMP-003 | Marina Kim | DBA Lead | WG-DB | marina.kim@example.local |
| EMP-004 | Rustem Sadykov | Infrastructure Lead | WG-INF | rustem.sadykov@example.local |
| EMP-005 | Daniyar Utebayev | Network Lead | WG-NET | daniyar.utebayev@example.local |
| EMP-006 | Aigerim Nusupova | Service Owner | WG-APP | aigerim.nusupova@example.local |
| EMP-007 | Yerlan Kozybayev | Change Manager | WG-APP | yerlan.kozybayev@example.local |
| EMP-008 | Madina Bekturova | Problem Manager | WG-APP | madina.bekturova@example.local |
| EMP-009 | Arman Seidakhmet | System Analyst | WG-APP | arman.seidakhmet@example.local |
| EMP-010 | Elena Tulegenova | Data Platform Owner | WG-DB | elena.tulegenova@example.local |

## Системы

| system_code | system_name | service_code | owner_employee | support_workgroup | environment |
| --- | --- | --- | --- | --- | --- |
| SYS-001 | Workplace Portal | SRV-001 | EMP-006 | WG-APP | Production |
| SYS-002 | Payment Gateway | SRV-002 | EMP-007 | WG-APP | Production |
| SYS-003 | Client CRM | SRV-003 | EMP-009 | WG-APP | Production |
| SYS-004 | HR Portal | SRV-004 | EMP-006 | WG-APP | Production |
| SYS-005 | Data Warehouse Core | SRV-005 | EMP-010 | WG-DB | Production |

## Модули

| module_code | module_name | system_code | business_weight | module_type |
| --- | --- | --- | --- | --- |
| MOD-001 | Portal Authentication | SYS-001 | 5 | Web |
| MOD-002 | Portal Knowledge Base | SYS-001 | 3 | Web |
| MOD-003 | Card Payment Routing | SYS-002 | 5 | Integration |
| MOD-004 | Merchant Settlement | SYS-002 | 4 | Batch |
| MOD-005 | Client Profile | SYS-003 | 5 | Web |
| MOD-006 | Case Management | SYS-003 | 4 | Workflow |
| MOD-007 | Leave Requests | SYS-004 | 4 | Web |
| MOD-008 | Employee Profile | SYS-004 | 3 | Web |
| MOD-009 | ETL Scheduler | SYS-005 | 5 | Batch |
| MOD-010 | Data Mart Publishing | SYS-005 | 4 | Reporting |

## Конфигурационные единицы

| ci_code | ci_name | ci_type | system_code | module_code | hostname_or_id | status |
| --- | --- | --- | --- | --- | --- | --- |
| CI-001 | wp-app-01 | Application Server | SYS-001 | MOD-001 | wp-app-01.local | Active |
| CI-002 | wp-db-01 | Database Server | SYS-001 | MOD-002 | wp-db-01.local | Active |
| CI-003 | pay-int-01 | Integration Server | SYS-002 | MOD-003 | pay-int-01.local | Active |
| CI-004 | pay-batch-01 | Batch Server | SYS-002 | MOD-004 | pay-batch-01.local | Active |
| CI-005 | crm-app-01 | Application Server | SYS-003 | MOD-005 | crm-app-01.local | Active |
| CI-006 | crm-wf-01 | Workflow Server | SYS-003 | MOD-006 | crm-wf-01.local | Active |
| CI-007 | hr-web-01 | Web Server | SYS-004 | MOD-007 | hr-web-01.local | Active |
| CI-008 | hr-db-01 | Database Server | SYS-004 | MOD-008 | hr-db-01.local | Active |
| CI-009 | dwh-etl-01 | ETL Server | SYS-005 | MOD-009 | dwh-etl-01.local | Active |
| CI-010 | dwh-rpt-01 | Reporting Server | SYS-005 | MOD-010 | dwh-rpt-01.local | Active |
| CI-011 | net-fw-01 | Firewall | SYS-002 | MOD-003 | FW-EDGE-01 | Active |
| CI-012 | net-lb-01 | Load Balancer | SYS-001 | MOD-001 | LB-DMZ-01 | Active |

## Программное обеспечение

| software_code | software_name | software_version | vendor_name | linked_ci |
| --- | --- | --- | --- | --- |
| SW-001 | PostgreSQL | 16 | PostgreSQL Global Development Group | CI-002 |
| SW-002 | Nginx | 1.24 | F5 NGINX | CI-001 |
| SW-003 | Kafka Connect | 3.6 | Apache | CI-003 |
| SW-004 | Spring Boot Service | 3.2 | Internal Build | CI-005 |
| SW-005 | Airflow | 2.8 | Apache | CI-009 |

## Лицензии

| license_code | license_name | license_type | assigned_system | expiry_date |
| --- | --- | --- | --- | --- |
| LIC-001 | CRM Enterprise License | User-Based | SYS-003 | 2027-12-31 |
| LIC-002 | Reporting Suite License | Server-Based | SYS-005 | 2027-09-30 |
| LIC-003 | HR Portal Support License | Subscription | SYS-004 | 2027-06-30 |
| LIC-004 | Payment Gateway Security License | Subscription | SYS-002 | 2027-11-30 |

## Технологические окна

| window_code | system_code | weekday_name | start_time | end_time | comment_text |
| --- | --- | --- | --- | --- | --- |
| MW-001 | SYS-001 | Sunday | 01:00 | 03:00 | Monthly patching window |
| MW-002 | SYS-002 | Saturday | 02:00 | 04:00 | Restricted payment maintenance |
| MW-003 | SYS-003 | Sunday | 00:00 | 02:00 | CRM weekly deployment window |
| MW-004 | SYS-004 | Saturday | 22:00 | 23:30 | HR low-load window |
| MW-005 | SYS-005 | Sunday | 03:00 | 06:00 | DWH processing maintenance |

## Примеры связей для проверки модели

- `SRV-002` включает систему `SYS-002`.
- `SYS-002` содержит модули `MOD-003` и `MOD-004`.
- `MOD-003` связан с `CI-003` и `CI-011`.
- `SYS-002` поддерживается группой `WG-APP`.
- Владелец `SYS-005` это `EMP-010`.

## Как использовать датасет

1. В задании по моделированию CMDB используйте его как источник сущностей и связей.
2. В задании по PostgreSQL перенесите эти записи в свои таблицы.
3. В заданиях по major incident, problem и change используйте коды систем, модулей и рабочих групп из этого файла как основу для сценариев.

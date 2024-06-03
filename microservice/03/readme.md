# Домашнее задание к занятию «Микросервисы: подходы»

Вы работаете в крупной компании, которая строит систему на основе микросервисной архитектуры.
Вам как DevOps-специалисту необходимо выдвинуть предложение по организации инфраструктуры для разработки и эксплуатации.


## Задача 1: Обеспечить разработку

Предложите решение для обеспечения процесса разработки: хранение исходного кода, непрерывная интеграция и непрерывная поставка. 
Решение может состоять из одного или нескольких программных продуктов и должно описывать способы и принципы их взаимодействия.

Решение должно соответствовать следующим требованиям:
- облачная система;
- система контроля версий Git;
- репозиторий на каждый сервис;
- запуск сборки по событию из системы контроля версий;
- запуск сборки по кнопке с указанием параметров;
- возможность привязать настройки к каждой сборке;
- возможность создания шаблонов для различных конфигураций сборок;
- возможность безопасного хранения секретных данных (пароли, ключи доступа);
- несколько конфигураций для сборки из одного репозитория;
- кастомные шаги при сборке;
- собственные докер-образы для сборки проектов;
- возможность развернуть агентов сборки на собственных серверах;
- возможность параллельного запуска нескольких сборок;
- возможность параллельного запуска тестов.

Обоснуйте свой выбор.

## Решение 1:
Я бы выбрал инструменты GitLab для обеспечения процесса разработки, потому что они предоставляются одной компанией, что обеспечивает лучшую интеграцию и совместимость между инструментами. Это упрощает настройку и поддержку системы, а также позволяет избежать проблем с взаимодействием между инструментами от разных производителей. Кроме того, использование инструментов от одного поставщика позволяет снизить затраты на обучение персонала и поддержку системы. 


Ниже привёл таблицу с **Требованиями, решением и аналогами**
|     Требование     |     Решение     |      Аналоги      |
|--------------------|-----------------|-------------------|
| Облачная система   | GitLab  | GitHub, Bitbucket  |
| Система контроля версий Git  | Встроенная поддержка Git в GitLab  | GitHub, Bitbucket  |
| Репозиторий на каждый сервис  | Многорепозиторная архитектура в GitLab  | Монорепозиторий в GitHub, Bitbucket  |
| Запуск сборки по событию из системы контроля версий  | GitLab CI/CD  | Jenkins, Travis CI, CircleCI  |
| Запуск сборки по кнопке с указанием параметров  | Ручные запуски в GitLab CI/CD  | Ручные запуски в Jenkins, Travis CI, CircleCI  |
| Возможность привязать настройки к каждой сборке	  | Переменные среды и файлы конфигурации в GitLab CI/CD  | Переменные среды и файлы конфигурации в Jenkins, Travis CI, CircleCI  |
| Возможность создания шаблонов для различных конфигураций сборок  | Использование шаблонов в GitLab CI/CD  | Использование шаблонов в Jenkins, Travis CI, CircleCI  |
| Возможность безопасного хранения секретных данных (пароли, ключи доступа)  | Защищенные переменные среды в GitLab CI/CD  | Защищенные переменные среды в Jenkins, Travis CI, CircleCI  |
| Несколько конфигураций для сборки из одного репозитория  | Использование различных файлов конфигурации в GitLab CI/CD  | Использование различных файлов конфигурации в Jenkins, Travis CI, CircleCI  |
| Кастомные шаги при сборке  | 	Использование скриптов в GitLab CI/CD  | Использование скриптов в Jenkins, Travis CI, CircleCI  |
| Собственные докер-образы для сборки проектов  | Использование собственных докер-образов в GitLab CI/CD  | Использование собственных докер-образов в Jenkins, Travis CI, CircleCI  |
| Возможность развернуть агентов сборки на собственных серверах  | Использование GitLab Runner  | Использование агентов в Jenkins, Travis CI, CircleCI  |
| Возможность параллельного запуска нескольких сборок  | Параллельные задания в GitLab CI/CD  | Параллельные задания в Jenkins, Travis CI, CircleCI  |
| Возможность параллельного запуска тестов  | Параллельные тесты в GitLab CI/CD  | Параллельные тесты в Jenkins, Travis CI, CircleCI  |

## Задача 2: Логи

Предложите решение для обеспечения сбора и анализа логов сервисов в микросервисной архитектуре.
Решение может состоять из одного или нескольких программных продуктов и должно описывать способы и принципы их взаимодействия.

Решение должно соответствовать следующим требованиям:
- сбор логов в центральное хранилище со всех хостов, обслуживающих систему;
- минимальные требования к приложениям, сбор логов из stdout;
- гарантированная доставка логов до центрального хранилища;
- обеспечение поиска и фильтрации по записям логов;
- обеспечение пользовательского интерфейса с возможностью предоставления доступа разработчикам для поиска по записям логов;
- возможность дать ссылку на сохранённый поиск по записям логов.

Обоснуйте свой выбор.

## Решение 2:

Я предлагаю следующие программные продукты :

- **Elasticsearch** - это поисковая система, которая обеспечивает хранение и индексирование логов, а также предоставляет возможности поиска и фильтрации.
- **Logstash** - это инструмент для сбора и обработки логов, который может использоваться для доставки логов в Elasticsearch.
- **Filebeat** - это агент для сбора логов, который может быть установлен на каждом хосте и собирать лог-файлы или журналы stdout.
- **Kibana** - это веб-интерфейс для визуализации данных, хранящихся в Elasticsearch, который предоставляет возможности поиска и фильтрации логов, а также предоставляет пользовательский интерфейс для разработчиков.

|     Требование     |     Решение     |      Аналоги      |
|--------------------|-----------------|-------------------|
| Сбор логов в центральное хранилище со всех хостов, обслуживающих систему  | Elasticsearch + Logstash/Filebeat  | Graylog, Splunk, Sumo Logic  |
| Минимальные требования к приложениям, сбор логов из stdou  | 	Filebeat  | Fluentd, Logstash  |
| Гарантированная доставка логов до центрального хранилища  | Logstash + Elasticsearch  | Graylog, Splunk, Sumo Logic  |
| Обеспечение поиска и фильтрации по записям логов  | 	Elasticsearch + Kibana  | Graylog, Splunk, Sumo Logic  |
| Обеспечение пользовательского интерфейса с возможностью предоставления доступа разработчикам для поиска по записям логов  |  Kibana | Graylog, Splunk, Sumo Logic  |
| Возможность дать ссылку на сохранённый поиск по записям логов  | Kibana  | Graylog, Splunk, Sumo Logic  |

## Задача 3: Мониторинг

Предложите решение для обеспечения сбора и анализа состояния хостов и сервисов в микросервисной архитектуре.
Решение может состоять из одного или нескольких программных продуктов и должно описывать способы и принципы их взаимодействия.

Решение должно соответствовать следующим требованиям:
- сбор метрик со всех хостов, обслуживающих систему;
- сбор метрик состояния ресурсов хостов: CPU, RAM, HDD, Network;
- сбор метрик потребляемых ресурсов для каждого сервиса: CPU, RAM, HDD, Network;
- сбор метрик, специфичных для каждого сервиса;
- пользовательский интерфейс с возможностью делать запросы и агрегировать информацию;
- пользовательский интерфейс с возможностью настраивать различные панели для отслеживания состояния системы.

Обоснуйте свой выбор.

## Решение 3: 

Я предлагаю следующие программные продукты :

- **Prometheus** является широко используемой и проверенной системой мониторинга, которая подходит для сбора и анализа метрик в микросервисной архитектуре.
- **Node Exporter** и **cAdvisor** являются стандартными инструментами для сбора метрик состояния хостов и контейнеров, которые предоставляют необходимые метрики из коробки. 
- Программные клиенты **Prometheus** для различных языков программирования позволяют собирать метрики, специфичные для каждого сервиса, и предоставляют гибкие возможности для настройки.
- **Grafana** является гибкой и мощной системой визуализации данных, которая позволяет создавать различные панели мониторинга и настраивать их в соответствии с потребностями.

|     Требование     |     Решение     |      Аналоги      |
|--------------------|-----------------|-------------------|
| Сбор метрик со всех хостов, обслуживающих систему  | Prometheus  | InfluxDB, Graphite, OpenTSDB  |
| Сбор метрик состояния ресурсов хостов: CPU, RAM, HDD, Network | Node Exporter  | Collectd, Telegraf, Zabbix  |
| Сбор метрик потребляемых ресурсов для каждого сервиса: CPU, RAM, HDD, Network  | cAdvisor  | Prometheus Blackbox Exporter, Instana, Dynatrace  |
| Сбор метрик, специфичных для каждого сервиса  | Программные клиенты Prometheus для различных языков программирования	 | StatsD, OpenCensus, Micrometer |
| Пользовательский интерфейс с возможностью делать запросы и агрегировать информацию  | Grafana  | Kibana, Chronograf, Grafana Loki  |
| Пользовательский интерфейс с возможностью настраивать различные панели для отслеживания состояния системы  | Grafana  | Dashing, Netdata, Zabbix |
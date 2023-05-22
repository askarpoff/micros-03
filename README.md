# Домашнее задание к занятию «Микросервисы: подходы»

Вы работаете в крупной компании, которая строит систему на основе микросервисной архитектуры.
Вам как DevOps-специалисту необходимо выдвинуть предложение по организации инфраструктуры для разработки и эксплуатации.


## Задача 1: Обеспечить разработку

Предложите решение для обеспечения процесса разработки: хранение исходного кода, непрерывная интеграция и непрерывная поставка. 
Решение может состоять из одного или нескольких программных продуктов и должно описывать способы и принципы их взаимодействия.
## Ответ:
Для обеспечения процесса разработки, непрерывной интеграции и непрерывной поставки наиболее подходящим решением будет использование облачной CI/CD платформы GitLab CI/CD.

GitLab CI/CD включает в себя систему контроля версий Git, что соответствует требованию. Каждый сервис может иметь свой собственный репозиторий, а также настройки сборки могут быть привязаны к каждой сборке.

Сборка может быть запущена как по событию из системы контроля версий, так и по кнопке с указанием параметров. Это позволяет гибко настраивать процесс сборки и доставки.

GitLab CI/CD предоставляет возможность создания шаблонов для различных конфигураций сборок, что упрощает процесс настройки и повторного использования настроек.

Для безопасного хранения секретных данных GitLab CI/CD предоставляет функцию Variables, которая позволяет хранить пароли, ключи доступа и другие конфиденциальные данные. Эти переменные могут быть использованы в настройках сборки.

GitLab CI/CD позволяет настроить несколько конфигураций для сборки из одного репозитория и имеет возможность настройки кастомных шагов при сборке.

Для сборки проектов GitLab CI/CD использует Docker-образы, что позволяет создавать собственные образы для сборки проектов.

GitLab CI/CD поддерживает возможность развернуть агенты сборки на собственных серверах, что позволяет контролировать процесс сборки и доставки.

GitLab CI/CD поддерживает параллельный запуск нескольких сборок и тестов, что ускоряет процесс сборки и доставки.

В целом, использование GitLab CI/CD позволяет гибко настроить процесс разработки, непрерывной интеграции и непрерывной поставки, а также обеспечить безопасное хранение конфиденциальных данных.

## Задача 2: Логи

Предложите решение для обеспечения сбора и анализа логов сервисов в микросервисной архитектуре.
Решение может состоять из одного или нескольких программных продуктов и должно описывать способы и принципы их взаимодействия.

## Ответ:
Для обеспечения сбора и анализа логов сервисов в микросервисной архитектуре наиболее подходящим решением будет использование Elastic Stack (ранее известный как ELK Stack).

Elastic Stack включает в себя три основных компонента: Elasticsearch, Logstash и Kibana.

Logstash используется для сбора и обработки логов со всех хостов, обслуживающих систему. Он может принимать логи из различных источников, включая stdout приложений, и отправлять их в центральное хранилище Elasticsearch.

Elasticsearch используется для хранения и индексации логов. Он обеспечивает возможность поиска и фильтрации по записям логов.

Kibana используется для создания пользовательского интерфейса и предоставления доступа разработчикам для поиска по записям логов. Он также позволяет сохранять поисковые запросы и предоставлять ссылки на них.

Для гарантированной доставки логов до центрального хранилища можно использовать систему очередей сообщений.

В целом, использование Elastic Stack позволяет обеспечить сбор и анализ логов сервисов в микросервисной архитектуре, а также обеспечить поиск и фильтрацию по записям логов и пользовательский интерфейс для доступа к этим данным.


## Задача 3: Мониторинг

Предложите решение для обеспечения сбора и анализа состояния хостов и сервисов в микросервисной архитектуре.
Решение может состоять из одного или нескольких программных продуктов и должно описывать способы и принципы их взаимодействия.

## Ответ:
Для обеспечения сбора и анализа состояния хостов и сервисов в микросервисной архитектуре наиболее подходящим решением будет использование Prometheus и Grafana.

Prometheus используется для сбора метрик со всех хостов и сервисов. Он поддерживает множество протоколов для сбора метрик, включая HTTP, SNMP, JMX, и др. Prometheus также предоставляет возможность для создания пользовательских метрик с помощью языка PromQL.

Grafana используется для создания пользовательского интерфейса и предоставления доступа разработчикам для поиска по записям логов. Он также позволяет сохранять поисковые запросы и предоставлять ссылки на них. Grafana позволяет создавать различные панели для отслеживания состояния системы, включая графики, таблицы, и др.

Для сбора метрик состояния ресурсов хостов можно использовать экспортеры Prometheus, которые собирают метрики из системных интерфейсов, таких как /proc и /sys. Для сбора метрик потребляемых ресурсов для каждого сервиса можно использовать экспортеры Prometheus, специфичные для каждого сервиса. Эти экспортеры могут собирать метрики из различных источников, включая стандартные интерфейсы, такие как HTTP, или специфичные для сервиса.

Пользовательский интерфейс Grafana позволяет делать запросы и агрегировать информацию. Он также позволяет настраивать различные панели для отслеживания состояния системы.

В целом, использование Prometheus и Grafana позволяет обеспечить сбор и анализ состояния хостов и сервисов в микросервисной архитектуре, а также обеспечить пользовательский интерфейс для доступа к этим данным и настройку различных панелей для отслеживания состояния системы.

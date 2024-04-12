# Домашнее задание к занятию «Микросервисы: принципы»

Вы работаете в крупной компании, которая строит систему на основе микросервисной архитектуры.
Вам как DevOps-специалисту необходимо выдвинуть предложение по организации инфраструктуры для разработки и эксплуатации.

## Задача 1: API Gateway 

Предложите решение для обеспечения реализации API Gateway. Составьте сравнительную таблицу возможностей различных программных решений. На основе таблицы сделайте выбор решения.

Решение должно соответствовать следующим требованиям:
- маршрутизация запросов к нужному сервису на основе конфигурации,
- возможность проверки аутентификационной информации в запросах,
- обеспечение терминации HTTPS.

Обоснуйте свой выбор.

## Решение 1: 
 
#### **Среди подходящих решений, нам подходят следующие программные решения для реализации API Gateway:**
  
| Решение          | Маршрутизация запросов | Аутентификация | Терминация HTTPS | Стоимость/Бесплатность |
|------------------|------------------------|----------------|------------------|-------------------------|
| Kong             | Да                     | Да             | Да               | Бесплатно (Open Source)  |
| Traefik          | Да                     | Да             | Да               | Бесплатно (Open Source)  |
| NGINX Plus       | Да                     | Да             | Да               | Коммерческая            |
| Zuul (Netflix)   | Да                     | Да             | Да               | Бесплатно (Open Source)  |
| Envoy (Lyft)     | Да                     | Да             | Да               | Бесплатно (Open Source)  |

Выбор решения может зависеть от дополнительных факторов, таких как стоимость, масштабируемость, и уровень поддержки. Например, если вам нужно бесплатное и открытое решение, то **Kong** или **Traefik** могут быть хорошими вариантами. Если вы ищете коммерческое решение, то **NGINX Plus** может быть лучшим выбором.

В качестве обоснованного выбора, я бы рекомендовал Kong. Он бесплатен, открыт, имеет богатый набор плагинов и широко используется в индустрии. Кроме того, **Kong** основан на **NGINX**, что гарантирует высокую производительность и стабильность.

## Задача 2: Брокер сообщений

Составьте таблицу возможностей различных брокеров сообщений. На основе таблицы сделайте обоснованный выбор решения.

Решение должно соответствовать следующим требованиям:
- поддержка кластеризации для обеспечения надёжности,
- хранение сообщений на диске в процессе доставки,
- высокая скорость работы,
- поддержка различных форматов сообщений,
- разделение прав доступа к различным потокам сообщений,
- простота эксплуатации.

Обоснуйте свой выбор.

## Решение 2: 

#### **Таблица брокеров сообщений:**
| Брокер сообщений | Кластеризация | Хранение на диске | Скорость | Форматы сообщений | Разделение прав доступа | Простота эксплуатации |
|---|---|---|---|---|---|---|
| RabbitMQ | Да | Да | Высокая | AMQP, STOMP, MQTT | Да | Средняя |
| Apache Kafka | Да | Да | Очень высокая | Ключ-значение, Avro, JSON, Протобуф | Да | Высокая |
| ActiveMQ | Да | Да | Высокая | JMS, STOMP, REST, AMQP | Да | Высокая |
| Amazon MQ | Да | Да | Высокая | JMS, STOMP, REST, AMQP | Да | Высокая |
| Google Cloud Pub/Sub | Да | Нет | Очень высокая | Протобуф | Да | Очень высокая |
| Azure Service Bus | Да | Да | Высокая | AMQP, SBMP, REST | Да | Высокая |

На основе таблицы и требований, можно сделать вывод, что подходящими решениями могут быть **RabbitMQ**, **Apache Kafka**, **ActiveMQ** и **Azure Service Bus.**

Я бы выбрал **Apacke Kafka**, эири блокер сообщений является подходящим решением для указанных требований. Он предоставляет возможность хранения сообщений на диске в процессе доставки, обеспечивает высокую скорость работы, поддерживает различные форматы сообщений, позволяет разграничивать права доступа к различным потокам сообщений и имеет простую эксплуатацию. Кроме того, **Apache Kafka** масштабируем и обеспечивает высокую доступность за счет кластеризации.

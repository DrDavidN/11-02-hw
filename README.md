# «Микросервисы: принципы» - Дрибноход Давид

Вы работаете в крупной компании, которая строит систему на основе микросервисной архитектуры.
Вам как DevOps-специалисту необходимо выдвинуть предложение по организации инфраструктуры для разработки и эксплуатации.

## Задача 1: API Gateway 

Предложите решение для обеспечения реализации API Gateway. Составьте сравнительную таблицу возможностей различных программных решений. На основе таблицы сделайте выбор решения.

Решение должно соответствовать следующим требованиям:
- маршрутизация запросов к нужному сервису на основе конфигурации,
- возможность проверки аутентификационной информации в запросах,
- обеспечение терминации HTTPS.

Обоснуйте свой выбор.

**Решение:**

| Критерий               | Kong                  |Apache APISIX    | Tyk      | 
| ---------------------- | --------------------- | --------------- | -------- |
| Сложность установки    | Просто                | Просто          | Просто   |
| База данных            | Cassandra or Postgres | etcd            | Redis    |
| Open Source            | Yes, Apache 2.0       | Yes, Apache 2.0 | Yes, MPL |
| Core Technology        | NGINX/Lua             | NGINX/Lua       | GoLang   |
| On Premise             | Да                    | Да              | Да       |
| Community/Extensions   | Большое               | Среднее         | Среднее  |
| Authorization/API Keys | да                    | да              | да       |
| Rate Limiting          | да                    | да              | да       |
| Data Transformation    | да                    | да              | да       |
| Производительность     | Средняя               | Высокая         | Средняя  |
| Консоль управления     | да                    | да              | да       |


**Реультат**

*TYK*

В этом продукте все возможности доступны из коробки (без дополнительных расходов)
Tyk написан на языке GoLang, который был создан специально для параллельных задач и высокой нагрузки


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

**Решение:**

| Критерий                     | Apache Kafka       | Redis        | RabbitMQ        |
| ---------------------------- | ------------------ | ------------ | --------------- |
| поддержка кластеризации      | да                 | да           | да              |
| хранение сообщений на диске  | да                 | нет          | да              |
| высокая скорость             | да                 | да           | нет             |
| поддержка различных форматов | String, JSON, Avro | String, JSON | JSON,XML,Binary |
| разделение прав доступа      | да                 | да           | да              |
| простота эксплуатации        | да                 | да           | да              |

**Реультат**

Kafka

По совокупности приемуществ. Высокая пропускная способность, гарантия доставки.

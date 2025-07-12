[English](#english)
[Russian](#russian)

# English

**A Roadmap for a Tech Lead: Designing a New Business-Critical Microservice**

```
Before you give me an answer, evaluate its uncertainty. If it's greater than 0.1, ask me clarifying questions until the uncertainty is 0.1 or less.

Hi! I'm about to take on the tech lead role for the creation of a new business-critical microservice. I'm new to the team and don't know much about this domain. Help me create a roadmap so I can gather the necessary information and properly design the microservice's architecture. It needs to be reliable, fault-tolerant, and scalable, and its internal architecture should be easily extensible for new functionalities.

We use in-house frameworks in Golang/C++, have a configured CI/CD pipeline, and can use the distributed database YDB, the relational database Postgres, or ClickHouse. For asynchronous communication, we use Logbroker (similar to Kafka) and STQ (similar to Amazon SQS). For requests from the frontend, we use HTTP via an API gateway, and for inter-service communication, we use gRPC. For monitoring and logging, we have a proprietary metrics collection system and dashboards in Grafana. The microarchitecture is hexagonal, but if others are better, feel free to suggest them, describing the pros and cons. The frameworks support out-of-the-box code generation for queue handlers, OpenAPI for REST HTTP, and proto for gRPC, as well as structured logging, tracing, and metrics.

Clarifying questions to reduce uncertainty:

1.  About the Business Domain and Functionality:
    * Core purpose of the service: What exactly will this microservice do? What is the main business problem it solves? (e.g., "process payments," "manage a product catalog," "calculate personalized discounts").
    * Key consumers (clients) of the service: Who will use it? Other internal services, frontend applications, external partners?
    * Critical business operations: What are the 1-3 most important operations in this service? Their failure or slowdown would cause the most significant business damage.
2.  About Non-Functional Requirements (NFRs) and Load:
    * Expected load: Are there any rough estimates for RPS (requests per second)? How much data will the service process or store?
    * Latency requirements: What is the maximum acceptable response time for the main operations (p95, p99)?
    * Reliability: What level of availability (SLA/SLO) is expected? 99.9%? 99.99%?
3.  About the Stack and Infrastructure:
    * What is the programming language and technology stack?
    * What are the infrastructural capabilities and constraints? AWS cloud, CI/CD, Metrics?

Let's not include common engineering practices in the roadmap, such as creating a runbook or setting up alerts—that's a given. I'm interested in the design, architecture, and the project work itself—my task as the tech lead is to get it launched.
```

# Russian

**Дорожная карта для техлида: Проектирование нового бизнес-критичного микросервиса**

```
Прежде чем дать мне ответ, оцени его неопределённость. Если она больше, чем 0.1 — задавай мне уточняющие вопросы до тех пор, пока неопределённость будет 0.1 или меньше.
Привет! Мне предстоит техлидить создание нового бизнес-критичного микросервиса. Я недавно в команде и мало знаю про этот домен. Помоги мне составить дорожную карту, чтобы я мог собрать необходимую информацию и грамотно продумать архитектуру микросервиса. Он должен быть надежный, отказоустойчивый и масштабируемый, а также внутреняя архитектура должна легко расширяться для новых функциональностей.

Мы используем разработанный в компании фреймворки на Golang/C++, есть настроенный CI/CD пайплайн, а также распределенная БД YDB, или реляционная postgres, можно использовать clickhouse. Для асинхронного взаимодействия: Logbroker (аналог Kafka) и STQ (аналог Amazon SQS), для запросов с фронтендам через api-gateway HTTP, межсервисное взаимодействие через gRPC. Для мониторинга и логов есть собстввенная система сбора метрик и дашборды в grafana. Микроархитектура - гексагональная, но если другие лучше - смело предлагай, описав плюсы и минусы. Фреймворки поддерживают из коробки кодогенерацию хэндлеров для очередей, Openapi для REST HTTP и proto для gRPC, а также структурные логи, трейсинг и метрики. 

Уточняющие вопросы для снижения неопределенности:

1. О Бизнес-домене и Функциональности:
- Основная задача сервиса: Что конкретно будет делать этот микросервис? Какую главную бизнес-проблему он решает? (например, "обрабатывать платежи", "управлять каталогом товаров", "рассчитывать персональные скидки").
- Ключевые потребители (клиенты) сервиса: Кто будет его использовать? Другие внутренние сервисы, фронтенд-приложения, внешние партнеры?
- Критические бизнес-операции: Какие 1-3 операции в этом сервисе являются самыми важными? Их отказ или замедление нанесет наибольший ущерб бизнесу.
2. О Нефункциональных Требованиях (NFRs) и Нагрузке:
- Ожидаемая нагрузка: Есть ли примерные оценки по RPS (requests per second)? Сколько данных сервис будет обрабатывать или хранить?
- Требования по времени ответа (Latency): Какое максимальное время ответа приемлемо для основных операций (p95, p99)?
- Надежность (Reliability): Какой уровень доступности (SLA/SLO) ожидается? 99.9%? 99.99%?
3. О стеке и инфраструктуре:
- Какой язык программирования и технологийский стек?
- Какие есть инфраструктурные возможности и ограничения? Aws cloud, CI/CD, Metrics?

Давай не учитывать в роадмапе общеинжереные практики, такие как создать runbook или настроить алерты - это очевидно. Меня интересует проектирование, архитектура и работа над проектом - ведь моя задача к техлида запустить его.
```

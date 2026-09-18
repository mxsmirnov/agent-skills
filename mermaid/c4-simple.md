# Пример улучшения mermaid диаграммы 

## Исходная диаграмма
``` mermaid
flowchart LR
    WebApp["WebApp<br/>[React]"]
    MobileApp["MobileApp<br/>[React Native]"]
    API["API Gateway<br/>[Kong]"]
    UserService["UserService<br/>[Java]"]
    OrderService["OrderService<br/>[Python]"]
    PaymentService["PaymentService<br/>[Go]"]
    Cache["Cache<br/>[Redis]"]
    UserDB["UserDB<br/>[PostgreSQL]"]
    OrderDB["OrderDB<br/>[MongoDB]"]
    PaymentDB["PaymentDB<br/>[MySQL]"]
    ExternalAuth["External Auth<br/>[OAuth2]"]
    ExternalInventory["External Inventory<br/>[REST]"]
    ExternalPay["External Payment<br/>[Stripe]"]

    WebApp --> API
    MobileApp --> API
    API --> UserService
    API --> OrderService
    API --> PaymentService
    UserService --> UserDB
    OrderService --> OrderDB
    PaymentService --> PaymentDB
    UserService --> ExternalAuth
    OrderService --> ExternalInventory
    PaymentService --> ExternalPay
    WebApp --> OrderService
    MobileApp --> PaymentService
    API --> Cache
    UserService --> Cache
    OrderService --> Cache
    PaymentService --> Cache
    UserService --> OrderService
    OrderService --> PaymentService
    ExternalAuth --> UserDB
    ExternalPay --> PaymentDB
    Cache --> UserDB
    Cache --> OrderDB
```
## Преобразованная диаграмма
``` mermaid
flowchart TB
    subgraph Frontend
        WebApp["WebApp<br/>[React]"]
        MobileApp["MobileApp<br/>[React Native]"]
    end

    subgraph Backend
        API["API Gateway<br/>[Kong]"]

        subgraph UserCluster [" "]
            UserService["UserService<br/>[Java]"]
            UserDB[("UserDB<br/>[PostgreSQL]")]
        end

        subgraph OrderCluster [" "]
            OrderService["OrderService<br/>[Python]"]
            OrderDB[("OrderDB<br/>[MongoDB]")]
        end

        Cache[("Cache<br/>[Redis]")]

        subgraph PaymentCluster [" "]
            PaymentService["PaymentService<br/>[Go]"]
            PaymentDB[("PaymentDB<br/>[MySQL]")]
        end
    end

    ExternalAuth["External Auth<br/>[OAuth2]"]
    ExternalInventory["External Inventory<br/>[REST]"]
    ExternalPay["External Payment<br/>[Stripe]"]

    WebApp --> API
    MobileApp --> API
    API --> UserService
    API --> OrderService
    API --> PaymentService

    UserService --> Cache
    OrderService --> Cache
    PaymentService --> Cache

    UserService --> UserDB
    OrderService --> OrderDB
    PaymentService --> PaymentDB

    UserService --> ExternalAuth
    OrderService --> ExternalInventory
    PaymentService --> ExternalPay

    style Frontend fill:#e8f0fe,stroke:#333
    style Backend fill:#e6f4ea,stroke:#333
    style UserCluster fill:#f2f2f2,stroke:#333
    style OrderCluster fill:#f2f2f2,stroke:#333
    style PaymentCluster fill:#f2f2f2,stroke:#333
    style ExternalAuth fill:#c8d8e8,stroke:#333
    style ExternalInventory fill:#c8d8e8,stroke:#333
    style ExternalPay fill:#c8d8e8,stroke:#333
```

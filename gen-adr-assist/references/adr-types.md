# Типы ADR и что в них важно

## 1. Выбор технологии (Technology Choice)
Сфокусируйся на:
- business need;
- quality attributes;
- зрелости технологии;
- skills / support model;
- соответствии `tech-radar.json`.

Типовые варианты:
- adopt existing standard;
- introduce new technology;
- stay with current platform.

## 2. Интеграция (Integration)
Сфокусируйся на:
- synchronous vs asynchronous;
- API / RPC / messaging / file exchange;
- ownership of contract;
- reliability, retries, idempotency;
- coupling.

## 3. Данные (Data)
Сфокусируйся на:
- source of truth;
- ownership;
- consistency model;
- storage technology;
- retention / residency / compliance.

## 4. Безопасность (Security)
Сфокусируйся на:
- identity and access management (IAM);
- secrets;
- audit;
- data protection;
- regulatory constraints.

## 5. Развертывание (Deployment / Runtime)
Сфокусируйся на:
- target platform;
- operational model;
- resilience;
- rollout / rollback;
- cost.

## 6. Build vs Buy
Сфокусируйся на:
- strategic differentiation;
- time-to-market;
- total cost of ownership (TCO);
- vendor lock-in;
- extensibility.

## 7. Архитектурное правило или принцип (Architecture Principle / Policy)
Сфокусируйся на:
- scope of enforcement;
- exceptions;
- governance;
- measurable compliance.

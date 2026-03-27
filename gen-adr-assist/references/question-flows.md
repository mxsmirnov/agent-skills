# Уточняющие вопросы по типам решений

## Общие вопросы
Задавай не все сразу, а только нужные.

1. Что именно нужно решить одним ADR?
2. Какие системы или команды затрагиваются?
3. Что важнее всего: speed, cost, reliability, security, scalability, compliance?
4. Есть ли ограничения по стандартам, стеку, cloud, данным или срокам?
5. Какие варианты уже обсуждаются?
6. Есть ли явная технология, которую надо проверить по `tech-radar.json`?

## Для Technology Choice
- Это стандарт для всей организации или локальный выбор команды?
- Это замена текущего решения или новая capability?
- Насколько критичны support skills и hiring?
- Допустим ли experimental choice?

## Для Integration
- Нужен sync или async?
- Кто владеет контрактом (contract ownership)?
- Нужна ли guaranteed delivery?
- Есть ли требования к latency или offline-обмену?

## Для Data
- Где source of truth?
- Кто владеет данными?
- Нужна strong consistency или eventual consistency?
- Есть ли требования по residency, retention, audit?

## Для Security
- Что именно защищаем?
- Нужны ли SSO, RBAC/ABAC, MFA?
- Есть ли требования к audit trail?
- Есть ли compliance constraints?

## Для Deployment
- Где будет runtime: on-prem, cloud, hybrid?
- Нужны ли blue/green, canary, rollback?
- Какой ожидается operational burden?
- Есть ли ограничения по platform team или tooling?

## Для Build vs Buy
- Это стратегическая capability или commodity?
- Что критичнее: control или speed?
- Допустим ли vendor lock-in?
- Насколько важны кастомизация и интеграция?

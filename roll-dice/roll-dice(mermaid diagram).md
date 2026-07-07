# Бросок кубика: sequence diagram

Кратко: пользователь просит бросок в чате Cursor. Агент (Composer) опирается на инструкции из `SKILL.md`, запускает команду в терминале, PowerShell возвращает число, ответ показывается в чате.

```mermaid
sequenceDiagram
    autonumber
    participant U as Пользователь
    participant C as Agent
    participant L as LLM
    participant S as Файл навыка<br/>roll-dice/SKILL.md
    participant P as PowerShell

    U->>C: Сообщение в чате<br/>«брось d6»
    C->>L: Запрос + контекст сессии<br/>(в т.ч. доступные skills)

    opt Навык не в контексте
        L->>S: Read / загрузка SKILL.md
        S-->>L: Правила: shell, формула d6
    end

    L->>C: Инструмент: выполнить команду<br/>в терминале
    C->>P: Запуск процесса<br/>powershell -Command …
    P-->>C: stdout: число 1–6<br/>exit code 0
    C-->>L: Результат инструмента<br/>(вывод терминала)
    L-->>C: Финальный ответ в чат
    C-->>U: «Выпало N»
```

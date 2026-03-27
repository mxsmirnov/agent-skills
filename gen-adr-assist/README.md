# gen-adr-assist

Навык для подготовки архитектурных решений (ADR, Architectural Decision Records) в формате MADR (Markdown Architectural Decision Records).

## Назначение

Навык помогает LLM:
- собрать недостающий контекст по решению;
- задать минимально необходимые уточняющие вопросы;
- подготовить короткий черновик ADR для review;
- после подтверждения раскрыть его в полный ADR в формате MADR;
- учитывать ограничения и рекомендации из `assets/tech-radar.json`.

## Использование

- Скопируйте каталог `gen-adr-assist` в подкаталоги проекта: `.claude/skills/` или  `.cursor/skills/`; если навык необходим для всех проектов, то сохраните его в одноименных каталогах глобального уровня
- Дополните или замените `assets/tech-radar.json` набором корпоративных технологических стандартов

## Структура каталогов

```text
gen-adr-assist/
├── SKILL.md
├── README.md
├── assets/
│   ├── madr-short-template.md
│   ├── madr-full-template.md
│   ├── review-checklist.md
│   └── tech-radar.json
└── references/
    ├── madr-guide.md
    ├── adr-types.md
    ├── question-flows.md
    ├── tech-radar-guide.md
    └── examples.md
```

## Содержимое

### Корневой каталог
- `SKILL.md` — основная инструкция навыка: когда применять, как вести диалог, когда делать short draft и когда раскрывать full MADR.
- `README.md` — краткое описание навыка и состава файлов.

### `assets/`
- `madr-short-template.md` — шаблон короткого ADR для review.
- `madr-full-template.md` — шаблон полного ADR в формате MADR.
- `review-checklist.md` — checklist для проверки draft перед отправкой человеку.
- `tech-radar.json` — технологический радар в формате Thoughtworks Build Your Own Radar.

### `references/`
- `madr-guide.md` — краткое руководство по структуре MADR.
- `adr-types.md` — подсказки по типам архитектурных решений.
- `question-flows.md` — сценарии уточняющих вопросов.
- `tech-radar-guide.md` — правила интерпретации `tech-radar.json`.
- `examples.md` — примеры коротких и полных ADR.

## Правило по `tech-radar.json`

Если пользователь указал конкретную технологию:
1. сначала проверить её наличие в `assets/tech-radar.json`;
2. если `ring = hold` — отвергнуть решение;
3. если технология отсутствует — спросить, нужно ли добавить её в `tech-radar.json` навыка;
4. если `ring = trial` или `assess` — разрешать только с явной пометкой риска и дополнительным обоснованием.

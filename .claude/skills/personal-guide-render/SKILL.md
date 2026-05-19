---
name: personal-guide-render
description: Собирает (или пересобирает) персональное руководство в УЖЕ существующем репо `personal-guide` (плоское имя, один на пилота) — читает RCS из Память.Derived, выбирает заготовки stage×domain, пишет 6 файлов через personal_write. Используй когда пилот просит «пересобери руководство», «обнови мой план», «обнови methods» — или когда репо создан, а контента ещё нет.
argument-hint: "[необязательно: override домена — knowledge-worker / generic] [необязательно: first-run — пропустить Шаг 5 архивации, используется при делегировании из /personal-guide-start]"
experimental: true
sunset: "после DONE WP-222 (Портной, ~июнь 2026) и WP-149 Ф6 (книга ЛР v3)"
related: [WP-245, WP-222, WP-149, PD.FORM.089, PD.CAT.003, personal-guide-start]
---

# Render персонального руководства

> ⚡ **Алгоритм, не диалог.** Выполни шаги 1-7 последовательно. Вопросы — только если `dt_read_digital_twin` вернул пустой результат или нет ни одного RCS-слота (W/M1/M2/M4). Наличие знаний о домене в MCP (Pack, сущности, концепции) ≠ Память.Derived. Диагностика «что ты создаёшь», «какова твоя главная система» — запрещена.

> **Experimental MVP-скилл** (IntegrationGate exception по WP-245 Ф28 Open Decision #7). Парный к `/personal-guide-start`: тот создаёт репо (один раз), этот наполняет/обновляет содержание (N раз).

## Контракт скилла

- **Вход:** существующий GitHub-репо `personal-guide` под аккаунтом пилота. Активная подписка «Бесконечное развитие» (DP.SC.112). Доступ к `dt_read_digital_twin`, `personal_write`.
- **Выход:** 6 файлов (`README.md`, `profile.md`, `worldview.md`, `methods.md`, `weekly/<YYYY-Www>.md`, `daily/<YYYY-MM-DD>.md`) перезаписаны актуальной версией под текущий RCS+домен.
- **Время:** ≤5 мин на пересборку (без диалога), ≤15 мин с диалогом.

## Шаги

1. Прочитать Память.Derived → `dt_read_digital_twin(path: "/")`
2. Вычислить ступень: `stage_raw = min(W, M1, M2, M4)` → выбрать заготовку
3. Выбрать домен: knowledge-worker (IT/аналитика) или generic
4. Прочитать заготовки из PACK-personal
5. Архивировать прежние weekly/daily в `history/` (пропустить при first-run)
6. Записать 6 файлов через `personal_write`
7. Подтвердить пилоту

Подробный алгоритм: см. оригинал в `~/IWE/.claude/skills/personal-guide-render/SKILL.md`

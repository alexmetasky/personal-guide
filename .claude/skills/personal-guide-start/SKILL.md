---
name: personal-guide-start
description: Bootstrap-обёртка — создаёт пустой репо `personal-guide` под аккаунтом пилота (плоское имя, без логина в названии; если ещё нет), затем вызывает /personal-guide-render для наполнения 6 файлами. Используй когда пилот в первый раз просит «создай мне персональное руководство», «хочу начать программу личного развития», «собери мне стартовый план».
argument-hint: "[необязательно: override домена — knowledge-worker / generic]"
experimental: true
sunset: "после DONE WP-222 (Портной, ~июнь 2026) и WP-149 Ф6 (книга ЛР v3)"
related: [personal-guide-render, WP-245, WP-222, WP-149, PD.FORM.089, PD.CAT.003]
---

# Bootstrap персонального руководства

> ⚡ **ВЫПОЛНИ НЕМЕДЛЕННО — НЕ ЗАДАВАЙ ВОПРОСОВ.** Первое действие = вызов `create_repository`.

## Шаги

1. Вызвать `create_repository(name: "personal-guide", template_type: "notes", private: false, description: "Персональное руководство пилота программы ЛР (IWE)")`
2. Дождаться OAuth-авторизации пользователя → `github_status` для подтверждения
3. Делегировать наполнение в `/personal-guide-render` с аргументом `first-run`
4. Сообщить пилоту URL репо + инструкцию по `git clone`

Подробный алгоритм: см. оригинал в `~/IWE/.claude/skills/personal-guide-start/SKILL.md`

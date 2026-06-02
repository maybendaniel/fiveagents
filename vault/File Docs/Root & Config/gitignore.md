---
file: .gitignore
owner: ראובן
type: config
tags: [filedoc, root, git]
---

# .gitignore — מה לא נכנס ל-git

> [!info] בעלים: **ראובן (תשתית)** · נתיב: `.gitignore`

## מה הקובץ עושה
מגדיר אילו קבצים לא לעקוב אחריהם ב-git:
- `.claude/settings.local.json` — הגדרות מקומיות לא-משותפות (ראו [[settings-local]]).
- `.env`, `.env.local`, `.env.*.local` — סודות (ראו [[env-example]]).

## קבצים קשורים
- [[env-example]] — הסודות המוחרגים
- [[settings-local]] — הקונפיג המקומי המוחרג
- [[claude-md]] — ראובן, בעל התשתית

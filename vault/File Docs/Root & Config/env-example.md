---
file: .env.example
owner: ראובן
type: config-secrets
tags: [filedoc, root, env, secrets]
---

# .env.example — תבנית משתני סביבה

> [!info] בעלים: **ראובן (תשתית)** · נתיב: `.env.example` (+ ה-`.env` האמיתי, לא ב-git)

## מה הקובץ עושה
תבנית לקובץ הסודות. מעתיקים אותו ל-`.env` וממלאים ערכים אמיתיים. ה-`.env` עצמו
מוחרג מ-git דרך [[gitignore]].

## משתנים מוגדרים
- `ANTHROPIC_API_KEY` — כללי / ראובן.
- `SEARCH_API_KEY` — לחן (Tavily/Serper/Brave וכד').
- `IMAGE_API_KEY` / `OPENAI_API_KEY` — ליובל; ה-OPENAI_API_KEY הוא שצורך הסקיל
  [[gpt-image-gen]] (מודל `gpt-image-2`).
- `APP_ENV`, `LOG_LEVEL` — הגדרות כלליות.

> [!warning] אסור להעלות את `.env` ל-git. אם המפתח חסר — הסקיל gpt-image-gen עוצר ומדווח.

## קבצים קשורים
- [[gitignore]] — מחריג את `.env` מ-git
- [[gpt-image-gen]] — צורך את OPENAI_API_KEY
- [[yuval-agent]] — הצרכן העקיף (דרך הסקיל)
- [[chen-agent]] — צרכן עתידי של SEARCH_API_KEY

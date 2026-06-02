---
file: .claude/settings.local.json
owner: מערכת
type: config
tags: [filedoc, config, permissions, claude-code]
---

# settings.local.json — הרשאות מקומיות של Claude Code

> [!info] בעלים: **מערכת / ראובן** · נתיב: `.claude/settings.local.json` (לא ב-git)

## מה הקובץ עושה
קובץ הגדרות מקומי וספציפי-למכונה של Claude Code. כרגע מכיל רשימת `permissions.allow`
— פקודות Bash מאושרות (ls, git add/commit/push), `WebSearch`, ו-WebFetch לדומיין
`www.buildfastwithai.com` (שריד מחיפוש של חן). מוחרג מ-git דרך [[gitignore]].

## קבצים קשורים
- [[gitignore]] — מחריג קובץ זה מ-git
- [[chen-memory]] — ה-WebFetch המאושר תואם למקור שחן השתמשה בו
- [[claude-md]] — ראובן, שפועל תחת ההרשאות האלה

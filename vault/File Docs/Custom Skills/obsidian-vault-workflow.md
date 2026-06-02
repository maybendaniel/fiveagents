---
file: .claude/skills/obsidian-vault-workflow/SKILL.md
owner: מערכת
type: skill
tags: [filedoc, skill, obsidian, memory, protocol]
---

# obsidian-vault-workflow — פרוטוקול הזיכרון של ה-vault

> [!info] בעלים: **מערכת / ראובן** · נתיב: `.claude/skills/obsidian-vault-workflow/SKILL.md`

## מה הקובץ עושה
מגדיר את פרוטוקול הקריאה/כתיבה המחייב של ה-`vault/`. ה-vault הוא הזיכרון ארוך-הטווח
של הפרויקט, מאורגן **קובץ אחד לכל נושא** (Overview + Open Questions + Session Log).
לפי הוראת המשתמש, הסקיל מופעל **בתחילת כל סשן/פקודה**.

## נקודות מפתח
- **Phase 1 (לפני משימה):** זיהוי נושא → איתור קובץ הנושא ב-`_index.md` → קריאה
  מלאה → קריאת 2-3 Meeting Notes אחרונים + Content Briefs/Brand Guidelines רלוונטיים.
- **Phase 2 (אחרי משימה):** עדכון Overview אם השתנה scope → עדכון Open Questions →
  הוספת `### YYYY-MM-DD — title [status]` בתחתית ה-Session Log → wikilinks חובה →
  אימות בקריאה חוזרת.
- תיקיות: `Meeting Notes/`, `Content Briefs/`, `Publishing Log/`, `Brand Guidelines/`.
- מאגר [[File Docs/_index|File Docs]] הזה הוא תוצר של ריצת הסקיל (ראו תיעוד הסשן).

## קבצים קשורים
- [[claude-md]] — ראובן, שמחויב להריץ את הפרוטוקול בכל משימה
- [[obsidian-markdown]] — תחביר ה-wikilinks/callouts שבו נכתב ה-vault
- [[obsidian-bases]] — תצוגות Base אפשריות מעל ה-vault
- [[obsidian-config]] — קונפיג ה-vault עצמו

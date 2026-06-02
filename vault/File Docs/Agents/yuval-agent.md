---
file: .claude/agents/yuval.md
owner: יובל
type: agent-definition
tags: [filedoc, agent, yuval, image]
---

# yuval.md — הגדרת הסוכן יובל

> [!info] בעלים: **יובל (מעצב התמונות)** · נתיב: `.claude/agents/yuval.md`

## מה הקובץ עושה
קובץ ההגדרה של הסוכן **יובל**. ה-frontmatter קובע שם, `description` (trigger
keywords: תמונה של/ציור של/איור...) וכלים: `Read, Write, Bash, Glob`. הגוף הוא
system prompt עם flow ההפקה ודגש על עקביות ויזואלית.

## תפקיד במערכת
מעצב התמונות. מקבל בקשה לתמונה (בד"כ מ-IMAGE_NEEDED placeholders של יעל, דרך
ראובן), סורק השראה מ-[[yuval-reference|yuval/reference/]], מנסח prompt, מייצר דרך
הסקיל [[gpt-image-gen]], ושומר ב-[[yuval-outputs|yuval/outputs/]].

## נקודות מפתח מההגדרה
- **יש לו גישה ל-Bash** (בשונה מיעל/חן) — נדרש להרצת הסקיל ולאימות הקובץ.
- שמירה: `yuval/outputs/<YYYY-MM-DD>-<slug>.png` + sibling `.txt` עם ה-prompt המלא.
- אימות חובה: `test -s <file>.png`.
- מטרת-על: **עקביות ויזואלית** בין כל התמונות — ה-reference וקבצי ה-.txt הם זיכרונו.
- אסור לשנות את שם המודל `gpt-image-2`.

## קבצים קשורים
- [[claude-md]] — ראובן, שמעביר אליו את ה-prompts ומשבץ תמונות בחזרה ל-Output
- [[gpt-image-gen]] — הסקיל שהוא מפעיל ליצירת התמונה בפועל
- [[yuval-reference]] — תמונות השראה לסגנון הבית
- [[yuval-outputs]] — היעד לתמונות + קבצי ה-prompt
- [[yael-agent]] — מקור בקשות התמונה (IMAGE_NEEDED placeholders)
- [[env-example]] — מגדיר את OPENAI_API_KEY שהסקיל צורך

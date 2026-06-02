---
file: .claude/agents/chen.md
owner: חן
type: agent-definition
tags: [filedoc, agent, chen, research]
---

# chen.md — הגדרת הסוכנת חן

> [!info] בעלים: **חן (חוקרת הרשת)** · נתיב: `.claude/agents/chen.md`

## מה הקובץ עושה
קובץ ההגדרה של הסוכנת **חן**. ה-frontmatter קובע את שמה, ה-`description` (שלפיו
ראובן מנתב אליה לפי trigger keywords), ואת הכלים שלה: `WebSearch, WebFetch, Read,
Write, Edit, Glob, Grep`. גוף הקובץ הוא ה-system prompt שמגדיר את תפקידה.

## תפקיד במערכת
חוקרת הרשת של הצוות. מקבלת בקשה מ[[claude-md|ראובן]], מחפשת ומסננת מקורות
איכותיים ועכשוויים, ומניחה את הממצא כקובץ ב-[[content-folder|Content/]] (עם לינק
למקור בראש הקובץ). **לא** קוראת ליעל ישירות — רק מדווחת לראובן.

## נקודות מפתח מההגדרה
- **אין גישה ל-Bash או API חיצוני** — רק WebSearch/WebFetch וקבצים.
- **זיכרון חובה:** לפני כל חיפוש עושה Grep על [[chen-memory|searches.md]]; אחרי
  כל חיפוש מוסיפה entry בפורמט קבוע.
- קריטריוני איכות: מקורות ראשוניים, פרסום ב-12 החודשים האחרונים, ללא אגרגטורים.
- פורמט שמירה: `Content/<YYYY-MM-DD>-<slug>.md`.

## קבצים קשורים
- [[claude-md]] — ראובן, שמנתב אליה ומקבל את הדיווח
- [[chen-memory]] — יומן החיפושים שהיא קוראת/כותבת לפני ואחרי כל חיפוש
- [[content-folder]] — היעד שאליו היא מניחה את הממצאים (קלט ליעל)
- [[yael-agent]] — הצרכנית הבאה בשרשרת (דרך ראובן)

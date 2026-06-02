---
file: .claude/agents/yael.md
owner: יעל
type: agent-definition
tags: [filedoc, agent, yael, content]
---

# yael.md — הגדרת הסוכנת יעל

> [!info] בעלים: **יעל (כותבת התוכן)** · נתיב: `.claude/agents/yael.md`

## מה הקובץ עושה
קובץ ההגדרה של הסוכנת **יעל**. ה-frontmatter קובע שם, `description` (trigger
keywords: שכתב/ערוך/תרגם/סכם/מאמר...) וכלים: `Read, Write, Edit, Glob, Grep`.
הגוף הוא system prompt עם flow העבודה, כללי תוכן ותבנית HTML מלאה.

## תפקיד במערכת
כותבת ועורכת התוכן. לוקחת מאמר גלם מ-[[content-folder|Content/]], משכתבת אותו
בסגנון הבית, ומפיקה ל-[[output-folder|Output/]] שני תוצרים: `<name>.md` ו-`<name>.html`.

## נקודות מפתח מההגדרה
- **אין גישה ל-Bash/WebSearch** — עובדת רק עם קבצים שבמאגר.
- קוראת את [[yael-style-guide|style-guide.md]] ואת [[yael-reference|yael/reference/]]
  בתחילת כל משימה; אם ריקים — כותבת בעברית ברורה כברירת מחדל.
- **סימון תמונות:** משתילה `{{IMAGE_NEEDED: "..."}}` placeholders ומחזירה את
  רשימתם לראובן, שמעביר ל[[yuval-agent|יובל]].
- כללי תוכן: מסירה קישורים/CTAs של המחבר המקורי; מותגים בתוך הסיפור נשארים.
- מכילה תבנית HTML עצמאית (CSS מוטמע, RTL, עברית).

## קבצים קשורים
- [[claude-md]] — ראובן, שמפעיל אותה ומשבץ בחזרה את תמונות יובל
- [[content-folder]] — מקור מאמרי הגלם (שחן מניחה)
- [[output-folder]] — היעד לתוצרים (MD + HTML)
- [[yael-style-guide]] — מדריך הסגנון שהיא קוראת לפני כתיבה
- [[yael-reference]] — דוגמאות סגנון
- [[yuval-agent]] — מקבל את ה-IMAGE_NEEDED placeholders (דרך ראובן)
- [[chen-agent]] — מספקת לה את חומר הגלם (דרך ראובן)

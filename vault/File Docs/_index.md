---
type: index
tags: [filedoc, index]
---

# File Docs — מפת הקבצים של הפרויקט

מאגר תיעוד: קובץ MD אחד לכל קובץ/רכיב משמעותי בפרויקט **fiveagents** (מערכת צוות
הסוכנים ליצירת תוכן). כל דף מסביר **מה הקובץ עושה**, **למי הוא משויך** (ראובן /
יעל / יובל / חן / מערכת), ו**אילו קבצים קשורים** אליו (דרך wikilinks).

> [!tip] איך לקרוא את המאגר
> כל דף נושא frontmatter עם `owner` (הבעלים) ו-`file` (הנתיב האמיתי בריפו).
> השתמשו ב-Graph View של Obsidian כדי לראות את מפת הקשרים בין הסוכנים לקבצים.

## הצוות (בעלים)

- **ראובן** — מנכ"ל / מתזמר. בעל הקונפיג, ה-CLAUDE.md והתשתית.
- **חן** — חוקרת הרשת. בעלת `chen/` וה-Content הנכנס.
- **יעל** — כותבת התוכן. בעלת `yael/` וה-Output.
- **יובל** — מעצב התמונות. בעל `yuval/` והסקיל gpt-image-gen.
- **מערכת** — סקילים מותקנים וקונפיג של Obsidian/Claude Code.

## תיקיות התיעוד

- [[Root & Config/_index|Root & Config]] — שורש הפרויקט, קונפיג וסודות (ראובן/מערכת)
- [[Agents/_index|Agents]] — הגדרות שלושת הסוכנים (חן, יעל, יובל)
- [[Custom Skills/_index|Custom Skills]] — סקילים מותאמים לפרויקט
- [[Installed Skills/_index|Installed Skills]] — סקילים מותקנים מצד-שלישי
- [[Work Folders/_index|Work Folders]] — תיקיות העבודה של הסוכנים (קלט/פלט/זיכרון)

## מפת בעלות מהירה

| בעלים | קבצים מרכזיים |
|---|---|
| ראובן | [[claude-md]], [[env-example]], [[gitignore]], [[settings-local]] |
| חן | [[chen-agent]], [[chen-memory]], [[content-folder]] |
| יעל | [[yael-agent]], [[yael-style-guide]], [[yael-reference]], [[output-folder]] |
| יובל | [[yuval-agent]], [[gpt-image-gen]], [[yuval-outputs]], [[yuval-reference]] |
| מערכת | [[obsidian-vault-workflow]], [[obsidian-markdown]], [[obsidian-bases]], [[superpowers-skills]], [[obsidian-config]] |

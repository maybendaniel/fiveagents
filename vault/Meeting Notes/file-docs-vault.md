# File Docs Vault

## Overview
מאגר תיעוד ב-`vault/File Docs/` שמתעד קובץ-קובץ את כל קבצי הפרויקט: מה כל קובץ
עושה, למי הוא משויך (ראובן / חן / יעל / יובל / מערכת), וקישורי wikilink לקבצים
קשורים. קבצי הפרויקט עצמו מתועדים פרטנית; הסקילים המותקנים מצד-שלישי מתועדים
ברמת-קבוצה אחת. מאורגן בתת-תיקיות: Root & Config, Agents, Custom Skills,
Installed Skills, Work Folders — כל אחת עם `_index.md` משלה, ומעליהן `_index.md` ראשי.

## Open Questions
- מדריך הסגנון [[yael-style-guide]] ותיקיות ה-reference של יעל/יובל עדיין ריקים — לעדכן את התיעוד כשיתמלאו.
- האם להוסיף קובץ Obsidian Base (טבלת "כל הקבצים לפי בעלים") מעל מאגר ה-File Docs?

## Session Log

### 2026-06-02 — בניית מאגר File Docs [shipped]
- **What was done:** נסרקו כל קבצי הפרויקט ונוצרו 26 קבצי MD ב-`vault/File Docs/`
  — דף תיעוד לכל קובץ/רכיב של הצוות + 5 אינדקסי תיקיות + אינדקס ראשי. כל דף כולל
  frontmatter (owner/file/type), הסבר תפקיד, ו-wiklinks לקבצים קשורים.
- **Decisions:** היקף = קבצי הפרויקט פרטנית, סקילי Superpowers/Anthropic ברמת-קבוצה
  אחת ([[superpowers-skills]]) כדי לא להציף ברעש על קוד צד-שלישי (המשתמש בחר "מה
  שאתה חושב לנכון"). בעלות מופתה לפי הצוות מ-[[claude-md]]: ראובן=תשתית, חן/יעל/יובל=
  התיקיות שלהם, מערכת=קונפיג/סקילים.
- **Notes / Caveats:** הופעל סקיל obsidian-vault-workflow בתחילת הסשן לפי הוראת
  המשתמש (להפעיל בכל סשן/פקודה). תוקנו לינקים תלויים `file-docs-index` → `[[File Docs/_index]]`.
- **Related:** [[obsidian-vault-workflow]], [[claude-md]], [[chen-agent]], [[yael-agent]], [[yuval-agent]]

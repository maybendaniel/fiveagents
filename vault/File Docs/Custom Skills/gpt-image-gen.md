---
file: .claude/skills/gpt-image-gen/SKILL.md
owner: יובל
type: skill
tags: [filedoc, skill, image, openai]
---

# gpt-image-gen — יצירת תמונות דרך OpenAI Images API

> [!info] בעלים: **יובל (צרכן עיקרי)** · נתיב: `.claude/skills/gpt-image-gen/SKILL.md`

## מה הקובץ עושה
סקיל מותאם שאחראי על דבר אחד: לקחת prompt טקסטואלי, לשלוח אותו ל-OpenAI Images
API, ולשמור את ה-PNG החוזר. זהו ה"שריר" שמאחורי [[yuval-agent|יובל]].

## נקודות מפתח
- **מודל קבוע: `gpt-image-2` בלבד** — הסקיל מזהיר במפורש לא להחליף מודל (לא
  dall-e-3, לא gpt-image-1), גם אם הוא לא בידע הפנימי של המודל.
- צורך `OPENAI_API_KEY` מ-[[env-example|.env]]; אם חסר — עוצר ומדווח.
- פרמטרים קבועים: `1024x1024`, `quality: medium`, `output_format: png`.
- שתי דרכי פענוח: curl+jq+base64, או fallback ל-Python (מומלץ ב-Git Bash/Windows).
- אימות: `test -s <file>.png`.

## קבצים קשורים
- [[yuval-agent]] — הסוכן שמפעיל את הסקיל הזה
- [[env-example]] — מקור ה-OPENAI_API_KEY
- [[yuval-outputs]] — היעד לקבצי ה-PNG + ה-.txt
- [[yuval-reference]] — מקור הסגנון שמעצב את ה-prompt

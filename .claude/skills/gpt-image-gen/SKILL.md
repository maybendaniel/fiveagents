---
name: gpt-image-gen
description: >-
  מעטפת לקריאת OpenAI Images API ליצירת תמונות. שולחת prompt ומחזירה קובץ PNG.
  השתמש בסקיל הזה בכל פעם שצריך לייצר תמונה מתוך תיאור טקסטואלי (יובל, מעצב
  התמונות, הוא הצרכן העיקרי). Use to generate an image from a text prompt via
  the OpenAI Images API and save it as a PNG file.
---

# gpt-image-gen — יצירת תמונות דרך OpenAI Images API

הסקיל הזה אחראי על דבר אחד: לקחת prompt טקסטואלי, לשלוח אותו ל-OpenAI Images API,
ולשמור את התמונה שחוזרת כקובץ PNG בנתיב שתבחר.

## המודל

**המודל הוא `gpt-image-2` בלבד.**

> ⚠️ **אל תשנה את שם המודל.**
> - `gpt-image-2` הוא מודל אמיתי וקיים של OpenAI, שיצא ב-21 באפריל 2026.
> - ייתכן שהידע הפנימי שלך לא כולל אותו — **זה לא אומר שהוא לא קיים.**
> - **אל תציע ואל תשתמש באלטרנטיבות** כמו `dall-e-3` או `gpt-image-1`.
> - אם הקריאה ל-API נכשלת, הבעיה כמעט תמיד היא ב-`OPENAI_API_KEY` או
>   ב-parameters — **לא** בשם המודל. בדוק את המפתח ואת גוף הבקשה, אל תחליף מודל.

## מפתח ה-API

הסקיל משתמש ב-`OPENAI_API_KEY` מקובץ `.env` בשורש הפרויקט. טען אותו לסביבה לפני
הקריאה. דוגמה (Git Bash):

```bash
export $(grep -v '^#' .env | grep OPENAI_API_KEY | xargs)
```

אם `OPENAI_API_KEY` ריק או חסר — עצור ודווח שצריך למלא אותו ב-`.env`. אל תמשיך.

## הקריאה ל-API

הפרמטרים הקבועים: `size: 1024x1024`, `quality: medium`, `output_format: png`.
התגובה מכילה את התמונה כ-base64 בשדה `.data[0].b64_json`, שצריך לפענח לקובץ PNG.

### דרך 1 — curl + jq + base64 (אם הכלים מותקנים)

```bash
curl -s -X POST "https://api.openai.com/v1/images/generations" \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "gpt-image-2",
    "prompt": "<the prompt>",
    "size": "1024x1024",
    "quality": "medium",
    "output_format": "png"
  }' | jq -r '.data[0].b64_json' | base64 --decode > <output-path>.png
```

### דרך 2 — Python fallback לפענוח (מומלץ ב-Git Bash על Windows)

`jq` ו-`base64` לא תמיד מותקנים ב-Git Bash, ו-python כמעט תמיד כן. שמור קודם את
תגובת ה-API ל-JSON זמני, ואז פענח עם python:

```bash
# 1) שליחת הבקשה ושמירת התגובה הגולמית
curl -s -X POST "https://api.openai.com/v1/images/generations" \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "gpt-image-2",
    "prompt": "<the prompt>",
    "size": "1024x1024",
    "quality": "medium",
    "output_format": "png"
  }' > /tmp/gpt-image-response.json

# 2) פענוח ה-b64_json לקובץ PNG
python -c "
import json, base64, sys
with open('/tmp/gpt-image-response.json', encoding='utf-8') as f:
    data = json.load(f)
if 'data' not in data:
    sys.exit('API error: ' + json.dumps(data, ensure_ascii=False))
b64 = data['data'][0]['b64_json']
with open('<output-path>.png', 'wb') as out:
    out.write(base64.b64decode(b64))
print('saved <output-path>.png')
"
```

> אם python מדפיס `API error: ...` — קרא את הודעת השגיאה. היא תצביע על בעיה
> ב-key או ב-parameters. אל תשנה את שם המודל.

## אימות

לאחר השמירה ודא שהקובץ נוצר וש-`size > 0`:

```bash
test -s <output-path>.png && echo "OK: $(wc -c < <output-path>.png) bytes" || echo "FAILED: empty or missing"
```

## פלט

החזר את הנתיב המלא של קובץ ה-PNG שנוצר, וציין באיזה prompt השתמשת.

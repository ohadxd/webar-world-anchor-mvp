# WebAR World Anchor MVP

זה דמו בסיסי למה שביקשת:

- פותחים WebAR באנדרואיד
- לוחצים "טען תחנת חלל 2 מטר קדימה"
- המודל נטען בחלל החדר, לא על מרקר
- המשתמש הולך אליו פיזית
- כשקרובים מספיק למשך רגע, מופעל "דף מתהפך" וחותמת
- נשמר localStorage בשם `passport_station_iss_docking`

## איך מריצים נכון

WebXR חייב HTTPS. פתיחה כקובץ מקומי (`file://`) בדרך כלל לא תעבוד.

הדרך הכי קלה:
1. העלה את התיקייה ל-Netlify / Vercel / GitHub Pages
2. פתח את הקישור באנדרואיד עם Chrome
3. ודא שמותקן/פעיל Google Play Services for AR / ARCore
4. לחץ Start AR
5. לחץ "טען תחנת חלל 2 מטר קדימה"

## החלפת המודל ל-ISS אמיתי

שים קובץ בשם:

`models/iss.glb`

ואז בקובץ `index.html` החלף:

```js
const MODEL_URL = "https://modelviewer.dev/shared-assets/models/Astronaut.glb";
```

ל:

```js
const MODEL_URL = "./models/iss.glb";
```

## חיבור לדרכון האמיתי

בקוד יש פונקציה:

```js
completeStation()
```

שם מחברים לדרכון:

```js
localStorage.setItem("passport_station_iss_docking", "completed");
window.parent?.postMessage({ type: "AR_STATION_COMPLETED", stationId: "iss-docking" }, "*");
location.href = "/passport/YOUR_SESSION_ID?completed=iss-docking";
```

## הערות חשובות

- זה לא Marker AR. אין צורך Hiro/Kanji.
- זה World Tracking דרך WebXR.
- הכי מתאים לבדיקה באנדרואיד Chrome.
- באייפון Safari זה לא אותו API, ושם תצטרך ARKit אפליקציה או AR Quick Look מוגבל יותר.

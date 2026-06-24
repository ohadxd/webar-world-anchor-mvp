# WebXR AR Model Loader

דמו WebXR לאנדרואיד Chrome:

- פותח מצלמת AR דרך `immersive-ar`.
- מציג X ליציאה מ-AR כאשר `dom-overlay` נתמך.
- מציג כפתור "טען מודל 2 מטר קדימה" על מסך המצלמה כאשר `dom-overlay` נתמך.
- טוען את `models/iss.glb` במרחק 2 מטר קדימה מהמשתמש.
- אם `dom-overlay` לא נתמך אבל AR כן נפתח, הדף פותח AR מינימלי ומציב את המודל אוטומטית.

## דרישות

- Android עם Chrome מלא, לא WebView.
- מכשיר שתומך ARCore.
- Google Play Services for AR מותקן, פעיל ומעודכן.
- פריסה ב-HTTPS, למשל GitHub Pages.

## הרצה

הפרויקט סטטי. אפשר להעלות ל-GitHub Pages ולפתוח באנדרואיד:

`https://funlab.co.il/webar-world-anchor-mvp/`

אם אחרי deploy עדיין רואים גרסה ישנה, פתח עם cache-buster:

`https://funlab.co.il/webar-world-anchor-mvp/?v=ar-model-loader-1`

## הערה לאייפון

Safari באייפון לא תומך באותו `WebXR immersive-ar`. בשביל אייפון צריך fallback נפרד כמו AR Quick Look עם קובץ `.usdz`, או אפליקציה native עם ARKit.

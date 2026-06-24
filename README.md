# WebXR AR Support Check

דף בדיקה מינימלי לתמיכת WebXR AR במכשיר.

הבדיקה עושה ארבעה דברים:

1. מוודאת שהדף רץ ב-secure context (`https://` או `localhost`).
2. בודקת אם `navigator.xr` קיים.
3. מריצה `navigator.xr.isSessionSupported("immersive-ar")`.
4. בלחיצה על הכפתור, מריצה `navigator.xr.requestSession("immersive-ar")` בלי `dom-overlay`, בלי `hit-test`, ובלי `requiredFeatures`.

אם שלב 4 מצליח, המכשיר תומך WebXR AR בפועל.

אם שלב 4 מחזיר `The specified session configuration is not supported`, למרות שאין configuration בכלל, המשמעות היא בדרך כלל ש-Chrome / המכשיר / Google Play Services for AR לא יכולים לפתוח `immersive-ar`.

## דרישות

- Android עם Chrome מלא, לא WebView.
- מכשיר שתומך ARCore.
- Google Play Services for AR מותקן, פעיל ומעודכן.
- פריסה ב-HTTPS, למשל GitHub Pages.

## הרצה

הפרויקט סטטי. אפשר להעלות ל-GitHub Pages ולפתוח באנדרואיד:

`https://funlab.co.il/webar-world-anchor-mvp/`

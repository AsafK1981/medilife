# MediLife — הוראות לעבודה על האתר

## מה זה הפרויקט
אתר עסקי חד-עמודי עבור **מדילייף** — מכון צילומי שיניים ו-CT בנתניה.
- כתובת: הרצל 7, נתניה
- טלפון: 09-8334427
- שעות: א'–ה' 08:30–18:30

## טכנולוגיה
- **קובץ יחיד**: `index.html` — כל ה-HTML, CSS וה-JavaScript בקובץ אחד. אין framework, אין build.
- **גופן**: Heebo (Google Fonts), כיוון RTL
- **Hosting**: GitHub Pages — ענף `main` = פרודקשן
- **ריפו**: AsafK1981/medilife

## מבנה הדף
ניווט JavaScript בין "עמודים" (`display:none/block`):
- `page-home` — hero, שירותים, אודות, FAQ, שעות, ביקורות, צור קשר
- דפים נוספים: אודות, שירותים, שאלות נפוצות, שעות פעילות, ביקורות, צור קשר, דרושים
- דפים משפטיים: `page-accessibility`, `page-terms`, `page-privacy`

## CSS
- כל ה-CSS בתוך `<style>` ב-`<head>`
- Desktop = ברירת מחדל (ללא media query)
- `@media(max-width:768px)` — מובייל
- `@media(max-width:400px)` — מובייל קטן מאוד
- **לעולם לא לשנות סגנונות desktop כשמבקשים תיקון מובייל**

## מה כבר נעשה (mobile fixes)
- Header מובייל: שורה אחת — לוגו + טקסט, כפתור "צור קשר" מוסתר (`display:none!important`)
- Hero מובייל: stack אנכי — טקסט למעלה, תמונה למטה
- Nav מובייל: `display:grid; grid-template-columns:repeat(4,1fr)` — 2 שורות של 4 כפתורים
- Footer links מובייל: אותו סגנון כמו ה-nav — גריד 4 עמודות, כפתורי `.fsep` מוסתרים
- Footer מובייל: עמודה יחידה, מרוכז
- שעות עודכנו מ-17:30 ל-18:30 (אפריל 2026)
- באנר המלחמה הוסר (המלחמה נגמרה, מאי 2025)

## Deploy
אחרי כל שינוי:
```
git add index.html
git commit -m "תיאור השינוי"
git push origin main
```
GitHub Pages מתעדכן תוך דקה-שתיים.

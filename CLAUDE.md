# MediLife — הוראות לעבודה על האתר

## מה זה הפרויקט
אתר עסקי חד-עמודי עבור **מדילייף** — מכון צילומי שיניים ו-CT בנתניה.
- כתובת: הרצל 7, נתניה
- טלפון: 09-8334427
- שעות: א'–ה' 08:30–18:30, שישי 08:30–12:30

## טכנולוגיה
- **קובץ יחיד**: `index.html` — כל ה-HTML, CSS וה-JavaScript בקובץ אחד. אין framework, אין build.
- **גופן**: Heebo (Google Fonts), כיוון RTL
- **Hosting**: GitHub Pages — ענף `main` = פרודקשן
- **ריפו**: AsafK1981/medilife
- **branch גיבוי**: `backup-before-upgrade` — מצב האתר לפני השדרוג הנוכחי

## מבנה הדף
ניווט JavaScript בין "עמודים" (`display:none/block`):
- `page-home` — hero, אודות (s1), שירותים (s2), FAQ (s3), שעות (s4), ביקורות (s5), צור קשר
- דפים נוספים: אודות, שירותים, שאלות נפוצות, שעות פעילות, ביקורות, צור קשר, דרושים
- דפים משפטיים: `page-accessibility`, `page-terms`, `page-privacy`

## CSS
- כל ה-CSS בתוך `<style>` ב-`<head>`
- Desktop = ברירת מחדל (ללא media query)
- `@media(max-width:768px)` — מובייל
- `@media(max-width:400px)` — מובייל קטן מאוד
- **לעולם לא לשנות סגנונות desktop כשמבקשים תיקון מובייל**

## שינויים שנעשו — מובייל
- Header: שורה אחת — לוגו + טקסט, כפתור "צור קשר" מוסתר (`display:none!important`)
- Hero: stack אנכי — טקסט למעלה, תמונה למטה
- Nav: `display:grid; grid-template-columns:repeat(4,1fr)` — 2 שורות של 4 כפתורים
- Footer links: גריד 4 עמודות, `.fsep` מוסתרים
- Footer: עמודה יחידה, מרוכז

## שינויים שנעשו — תוכן
- שעות עודכנו מ-17:30 ל-18:30 (אפריל 2026)
- באנר המלחמה הוסר (המלחמה נגמרה)

## שינויים שנעשו — שדרוג עיצובי (סשן נוכחי)
- **ערכת צבעים**: לבן מינימליסטי + ירוק (`#3aaa35`). רקע `#fff`, sections alt `#f8fdf8`
- **Nav**: שחור → לבן עם border עדין, טקסט כהה, active ירוק
- **Status bar**: שחור → לבן עם border ירוק
- **Sections**: padding הוגדל ל-52px, כותרות גדולות יותר (32px)
- **Contact section**: גרדיאנט → `#f8fdf8` נקי
- **CTA**: `#0a1a0a` → `#0d1f0d`
- **Footer**: `#0a0a0a` → `#111`
- **Back-nav**: שחור → לבן עם טקסט ירוק
- **Scroll animations**: IntersectionObserver על כל האלמנטים הראשיים — fadeUp, reveal-left, reveal-right, reveal-scale עם stagger delays
- **Hero redesign**:
  - `min-height:88vh` — ממלא את המסך
  - כותרת: 62px, letter-spacing -3px
  - תמונה: `width:42%`, `object-fit:contain` (לא חותך), `height:340px`
  - הבאדג'ים (30+ שנה, פתוח עכשיו) בתוך `.hero-img-box` ממש, על פינות התמונה
  - רקע ירוק מאחורי התמונה הוסר — לבן נקי

## מה לא לשנות
- סקשן השירותים (s2) — נוסה שדרוג ל-3 עמודות, המשתמש לא אהב, בוצע revert
- עיצוב desktop בכלל — שינויים רק במובייל אלא אם נאמר אחרת

## Deploy
אחרי כל שינוי:
```
git add index.html
git commit -m "תיאור השינוי"
git push origin main
```
GitHub Pages מתעדכן תוך דקה-שתיים.

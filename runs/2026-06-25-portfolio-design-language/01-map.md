# מפת-מצב — שפת-העיצוב של אתר-התיק של אביב מידן

> סוכן: קולט-הקשר (Context Reader) · תאריך: 2026-06-25 · סבב: deep-spec שלב-1
> נושא ההרצה: **שפת-העיצוב בפועל** של אתר-התיק (לא layout/motion — אלה כבר אופיינו).
> **מקרא-תגים לכל קביעה:** מקור (`קובץ X`) · סוג (`מצוטט`/`מוסק`) · ביטחון (`גבוה`/`בינוני`/`נמוך`).
> **כלל:** בלי מקור — אין קביעה. מצוטט = כתוב מפורשות בחומר. מוסק = הסקה שלי מהחומר.
>
> **קבצי-המקור:**
> - `SPEC` = `dev/aviv-portfolio/SPEC.md`
> - `global.css` = `dev/aviv-portfolio/src/styles/global.css`
> - `index.astro` = `dev/aviv-portfolio/src/pages/index.astro`
> - `Layout.astro` = `dev/aviv-portfolio/src/layouts/Layout.astro`
> - `bezeq.mdx` / `mykey.mdx` = `dev/aviv-portfolio/src/content/work/`
> - `spec-v2` = `design-os/runs/2026-06-24-portfolio-hero/05-spec-v2.md`
> - `memory-career` / `memory-portfolio` = קבצי-הזיכרון

---

## עדשה 0 — מה זה? (המוצר במשפט אחד)

- אתר-תיק עבודות אישי לאביב מידן, מעצב מוצר/UIUX, שמטרתו למצוא עבודה בישראל 2026, בנוי ב-Astro (מחליף אתר Lovable ישן). · `SPEC §1`, `memory-portfolio` · **מצוטט** · גבוה.
- הקונספט המוצהר (v3/v4): אתר **סינמטי-אישי-כיפי** של מעצב, עם "רמזי עולם-העיצוב" פזורים (Figma/swatches/stickers/cursor), והירו = פורטרט-עם-נורת-"רעיון" נופלת. · `SPEC §3, §18, §21` · **מצוטט** · גבוה.
- הבידול המוצהר: "מעצב מוצרי-AI שבונים בו אמון", tagline = "I design AI products people actually trust" (בהירו בפועל מנוסח אחרת — ראה עדשת-מתחים). · `SPEC §3`, `Layout.astro` (description) · **מצוטט** · גבוה.

---

## עדשה 1 — למי?

- קהל-היעד המוצהר: מנהלי-עיצוב / מגייסים / מייסדים, שצופים זמן-קצר וחייבים להגיע לעבודות מהר. · `SPEC §2`, `spec-v2 §1` · **מצוטט** · גבוה.
- הרושם המבוקש: "מעצב מוצר מנוסה, חושב, יודע לעצב מוצרי AI — וגם בנאדם שכיף לעבוד איתו". · `SPEC §2` · **מצוטט** · גבוה.
- שפת-התוכן: אנגלית (כל הטקסטים באתר באנגלית; מסמכי-העבודה בעברית). · `SPEC §4`, `index.astro`, `bezeq.mdx` · **מצוטט** · גבוה.

---

## עדשה 2 — מה אפשר לעשות? (היכולות על המשטח)

- לקרוא הירו אינטראקטיבי (CV): פורטרט של אביב + נורה שנופלת ונדלקת; ב-hover הפורטרט מתחלף ("think" ↔ "idea"). · `index.astro` (portrait-swap, two imgs), `global.css` (.portrait-swap:hover) · **מצוטט** · גבוה.
- לגלול דרך מעבר "זום-לתוך-הרעיון" (pinned-scrub): הגלגלת מזיזה אנימציה, לא את הדף; אור גדל, ה-CV נעלם, העבודות מתממשות. · `index.astro`, `Layout.astro` (initLamp/GSAP), `spec-v2 §4` · **מצוטט** · גבוה.
- לעיין ב-3 כרטיסי-עבודה (Bezeq, Mykey + PriceMatch-teaser) ולפתוח עמוד case-study לכל אחד. · `index.astro` (work.map, PriceMatch teaser) · **מצוטט** · גבוה.
- בעמוד case-study: לפתוח "show reasoning" (גלובלי או per-block) שחושף את ההנמקה מאחורי החלטות. · `Layout.astro` (initReasoning), `global.css` (.reason), `bezeq.mdx`/`mykey.mdx` (`<Reason>`) · **מצוטט** · גבוה.
- ליצור קשר במייל (avivuiux@gmail.com); קישורי LinkedIn/Dribbble הם placeholder (`href="#"`, TODO). · `index.astro` (footer, "TODO(Aviv): real LinkedIn / Dribbble URLs") · **מצוטט** · גבוה.
- "pins" בסגנון Figma שחושפים תוכן אישי (the story / outside work / how I work) — **קיימים בקוד אך מוסתרים** (`display:none !important`). · `index.astro` (.pin), `global.css` (".pin... display:none !important", הערה "TEMP: hide the pins") · **מצוטט** · גבוה.

---

## עדשה 3 — ארכיטקטורת-מידע (מסכים וזרימות)

- מסך-יחיד (דף-בית) + עמודי case-study נפרדים (`/work/<id>`). הדף-בית = הירו-CV → אור/מעבר → עבודות → contact, הכל בתוך pin-stage אחד. · `index.astro` (scroll-track > pin-stage), `SPEC §5` · **מצוטט** · גבוה.
- ה-IA המוצהר ב-SPEC (Hero סינמטי → סקשן-אישי → עבודות → contact) **התכווץ בפועל** לסקשן-CV-אחד שמשלב hero+אישי, ואז עבודות. · `SPEC §5` מול `index.astro` · **מוסק** · בינוני.
- header קבוע עליון: שם, work, about, contact, "available" עם נקודה-פועמת; ב-case-study נוסף כפתור "show reasoning". · `Layout.astro` (header/nav) · **מצוטט** · גבוה.

---

## עדשה 4 — שפת-עיצוב (העדשה המרכזית) ⭐

### 4.1 טוקנים — צבע

- פלטה מוגדרת ב-`@theme`: paper `#f4f0e6` (קרם), ink `#14110f` (כמעט-שחור), orange `#ff6a1a` (accent ראשי), blue `#1b3a8c` (accent משני). aliases סמנטיים: accent/accent-2. · `global.css` (@theme) · **מצוטט** · גבוה.
- כותרת קובץ-ה-CSS עדיין מתויגת "**Aviv OS — design tokens (SPEC v2.1)... Brutalist Pop: cream/ink base + orange primary + blue secondary**" — שמות מהקונספט-הנטוש. · `global.css` (שורות 3-6) · **מצוטט** · גבוה.
- פלטת-אמבר נפרדת ושנייה הוגדרה ב-`:root` עבור מנגנון-האור: amber-core `#fff6e6`, amber-mid `#ffdfb0`, amber-deep `#d98f4c`, amber-veil `#ffe7c6`, cream `#f6efe2`. · `global.css` (:root, §22) · **מצוטט** · גבוה.
- **קיימים שני "קרמים" שונים**: token `--color-paper` = `#f4f0e6`, ואילו `--cream` (גוף-העבודות) = `#f6efe2`. spec-v2 מאשר שזה "קרם-כפול מכוון" (C7). · `global.css` מול `spec-v2 §6 CONT-2` · **מצוטט** · גבוה.
- הירו/סקשן-אישי רצים על רקע **כהה** (`.hero-canvas` `#0e0c0b`, `.personal` `#14110f`) — לא על הקרם של הבסיס. כלומר ה-paper כמעט לא נראה במסך-הראשון בפועל. · `global.css` (.hero-canvas, .personal) · **מוסק** · גבוה.

### 4.2 טוקנים — טיפוגרפיה

- שני גופנים בלבד: **Space Grotesk** (sans + display) ו-**Space Mono** (mono). נטענים מ-Google Fonts. · `global.css` (@theme), `Layout.astro` (link fonts) · **מצוטט** · גבוה.
- חלוקת-תפקידים עקבית: display/sans-bold לכותרות (`tracking-tighter`, `leading` הדוק), **mono** לתוויות/מטא/UI-chrome (uppercase + letter-spacing רחב). · `global.css` (.boot-line, .reason-label, .pin, .sticker, .swatch span), `index.astro`, `Layout.astro` · **מוסק** · גבוה.
- ה-mono משמש כ"חתימה-של-מעצב/קוד" חוזרת — כמעט כל תווית-מטא, sticker, pin, ו-cursor-tag הם mono-uppercase. · אותם מקורות · **מוסק** · בינוני.

### 4.3 פרימיטיבים — Brutalist Pop (ה-DNA הויזואלי שבקוד-בפועל)

- בלוק ה-CSS המרכזי-בפועל מתויג מפורשות "**Brutalist Pop primitives — thick borders + solid block shadows are the DNA**". · `global.css` (שורות 46-49) · **מצוטט** · גבוה.
- `.bp-border` = `2px solid ink`; `.bp-shadow` = `6px 6px 0 0 ink` (צל-בלוק-מלא, לא-מטושטש); `.bp-press` = הכרטיס "נלחץ" אל הצל ב-hover (translate 4px+הקטנת-צל). · `global.css` (.bp-border/.bp-shadow/.bp-press) · **מצוטט** · גבוה.
- פרימיטיבים אלה הם **השפה-הויזואלית של כל כרטיסי-העבודות** בפועל: כל כרטיס = `bp-border bp-shadow bp-press` + תג-מזהה צבעוני (orange/blue) בפינה. · `index.astro` (work.map class, PriceMatch teaser) · **מצוטט** · גבוה.
- אותו DNA חוזר ב-motifs (swatch עם `2px solid ink`+`3px 3px 0 ink`, sticker אותו-דבר) ובכפתורי-contact (`bp-border`). · `global.css` (.swatch/.sticker), `index.astro` (footer) · **מצוטט** · גבוה.

### 4.4 מוטיבי "עולם-העיצוב" (הקראפט-הגלוי המוצהר)

- מוגדרים ב-CSS: `.motif` (מרחף), `.swatch` (color-swatch עם label), `.fig-tag` (תווית-Figma), `.sticker`, וכן custom cursor עם תג ("Aviv"/"click"). · `global.css` (.motif/.swatch/.fig-tag/.sticker/#cursor), `Layout.astro` (#cursor svg) · **מצוטט** · גבוה.
- **בפועל המוטיבים האמביינטיים (swatch/fig-tag/sticker) לא ממומשים ב-`index.astro`** — אין להם שימוש בדף; רק ה-cursor וה-pins (מוסתרים) חיים. ה-`face-hint` משתמש ב-`.sticker` אבל גם הוא מוסתר (`.face-hint{display:none}`). · `index.astro` (אין `.swatch`/`.fig-tag`/`.motif`), `global.css` (.face-hint display:none) · **מוסק** · בינוני.
- ה-custom cursor הוא המוטיב-העיצובי היחיד שפעיל-בפועל בדף-הבית. · `Layout.astro` (initCursor), `index.astro` · **מוסק** · בינוני.

### 4.5 רכיבים חוזרים ותחושת-מותג

- `show-reasoning`: רכיב-החתימה של אביב — מסגרת שמאלית כחולה (`border-left: 3px solid blue`), toggle mono-uppercase כחול, נפתח grid-rows. מבטא "שקיפות/אמון" כשפה-ויזואלית. · `global.css` (.reason/.reason-toggle), `bezeq.mdx`/`mykey.mdx` · **מצוטט** · גבוה.
- ה-pins/pin-cards: כרטיסי-Figma (פינה-אחת-זוויתית `border-radius: 999px...4px`, dot כתום/כחול, צל-בלוק). שפה עקבית עם ה-Brutalist-Pop, אך **מוסתרים**. · `global.css` (.pin/.pin-card) · **מצוטט** · גבוה.
- ה-`::selection` צבוע orange-on-paper — מגע-מותגי קטן. · `global.css` (::selection) · **מצוטט** · גבוה.

### 4.6 טון כתוב (קול-המותג בטקסט)

- קול אישי-חם-ישיר, גוף-ראשון, משפטים קצרים, בלי ז'רגון מנופח: "Hi, I'm Aviv.", "I make AI feel less like a stranger you're told to trust, and more like something that earns it." · `index.astro` (cv-greet/cv-tagline) · **מצוטט** · גבוה.
- ב-case-studies הטון = סיפור-מבנה (Context → Problem → Insight → Decision → Outcome → What I learned), כן ולא-מתרברב, עם מספרים-אמיתיים ("only 25% completed signup", "16% abandoned at OTP"). · `bezeq.mdx`, `mykey.mdx` · **מצוטט** · גבוה.
- מוטיב-תוכן חוזר: **אמון** ("trust the work, not the brief", "onboarding is trust", "Let's build something people trust"). הטקסט עקבי עם הבידול המוצהר. · `bezeq.mdx`, `mykey.mdx`, `index.astro` (footer) · **מוסק** · גבוה.

---

## עדשה 5 — מציאות טכנית (קלות)

- Astro 5 + Tailwind 4 (`@import "tailwindcss"` + `@theme`) + MDX (content collections ל-case studies). · `global.css`, `SPEC §12`, `bezeq.mdx` · **מצוטט** · גבוה.
- Motion-stack: Lenis (smooth scroll) + GSAP 3.15 + ScrollTrigger; ticker-יחיד מניע את שניהם; snap ידני דרך `lenis.scrollTo`. · `Layout.astro` (imports, startLenis), `memory-portfolio` · **מצוטט** · גבוה.
- וידאו-הנורה: `<video>` עם webm+mp4, screen-blend, scrub/play-once; CSS-lamp כ-fallback (class `has-video` מחליף). · `index.astro` (lamp-video), `global.css` (.lamp-video), `SPEC §20` · **מצוטט** · גבוה.
- נגישות בנויה-פנימה: `prefers-reduced-motion` מכובד בכל מקום (בלוק ייעודי ב-CSS + בדיקות ב-JS), pins נגישים-במקלדת, ARIA roles. · `global.css` (@media reduced-motion), `Layout.astro` · **מצוטט** · גבוה.
- View Transitions מותקן (`ClientRouter`), `transition:name` על כרטיסי-עבודה. · `Layout.astro`, `index.astro` · **מצוטט** · גבוה.

---

## עדשה 6 — מה הם מעריכים (מה שבנו לעומק = מה שחשוב) — היסק זהיר

- ההשקעה-העמוקה-ביותר בקוד היא ב-**מנגנון-המעבר (motion/choreography)**: ~450 שורות JS ל-GSAP-timeline + פאנל-tuner חי (`?tune`, ~140 שורות), מול ~30 שורות לכרטיסי-העבודות. המוצר "אכפת לו" מהחוויה-הסינמטית-הרציפה. · `Layout.astro` (initLamp/buildTuner), `index.astro` · **מוסק** · גבוה.
- ה-`show-reasoning` קיבל מנגנון-מלא (hybrid global+per-block) — מעיד שה"שקיפות/אמון" הוא ערך-ליבה שאביב רצה להפוך לאינטראקציה, לא רק טקסט. · `global.css` (.reason), `Layout.astro` (initReasonBlocks) · **מוסק** · בינוני.
- **שפת-העיצוב עצמה (צבע/טיפו/רכיבים) קיבלה את ההשקעה-הכי-נמוכה**: הטוקנים והפרימיטיבים נשארו כפי שהיו ב-v2 (Brutalist Pop) ולא עודכנו לקונספט-החדש. כלומר הסטיילינג = placeholder, התנועה = הלב. · `global.css` (כותרות-v2.1, primitives), `memory-portfolio` ("עיצוב-כרטיסי-העבודות... לא תואם וייב") · **מוסק** · גבוה.

---

## עדשה 7 — מתחים וסדקים (העדשה השנייה-בחשיבות) ⭐

> כאן ה"placeholder/לא-קוהרנטי/סותר-קונספט" שההרצה מחפשת. תיאור בלבד, בלי שיפוט טוב/רע.

1. **שפת-העיצוב בפועל = Brutalist Pop; הקונספט המוצהר = סינמטי-אישי-כיפי.** הקוד עדיין נושא DNA של "thick borders + solid block shadows" וכותרת "Aviv OS — design tokens (SPEC v2.1) Brutalist Pop", בעוד SPEC v3/v4 מצהיר מפורשות שנטשו את "Brutalist Pop" ואת "Aviv OS". · `global.css` (שורות 3-6, 46-49) מול `SPEC §0, §3, §13`, `memory-portfolio` · **מצוטט** · גבוה.
2. **כרטיסי-העבודות הם בלוקים-ברוטליסטיים-קרמיים** (border+block-shadow על paper) — בעוד הדף סביבם כהה-וסינמטי. memory מאשר "עיצוב-כרטיסי-העבודות (לא תואם וייב)" כצעד-הבא הפתוח. · `index.astro` (work cards), `memory-portfolio` · **מצוטט** · גבוה.
3. **קוד-מת מהקונספט-הנטוש עדיין בבסיס-הקוד:** בלוק `#boot` (boot-overlay "AVIV_OS v1.0 — booting…"), `.hero-sky` (שמיים — נטוש ב-§18), והגדרות-motifs שלא-בשימוש. · `global.css` (#boot, .hero-sky), `Layout.astro` (boot div + AVIV_OS strings), `SPEC §18` ("הרעיון נטוש: שקיעה/שמיים") · **מצוטט** · גבוה.
4. **double-amber לא-פתור בקוד:** ה-CSS עדיין מחזיק *שתי* מערכות-אור נפרדות — `.idea-light` (radial-gradient אמבר §22) וגם `.bulb-glow`/`.lamp.lit` (זוהר-CSS משלו) וגם אמבר-מובלע בווידאו. spec-v2 דורש "מקור-אור-יחיד-נעול" (CH-2), אך הקוד טרם אוחד. · `global.css` (.idea-light, .bulb-glow, .lamp.lit) מול `spec-v2 §5 CH-2`, `SPEC §20 (🔴 double-amber)` · **מוסק** · בינוני.
5. **ה"קרם-כפול"** (`--color-paper` `#f4f0e6` מול `--cream` `#f6efe2`) — מסומן "מכוון" ב-spec-v2, אך הוא הפרש-גוון לא-מתועד-בטוקנים שעלול להיקרא כ-drift. · `global.css` מול `spec-v2 §6 CONT-2` · **מצוטט** · גבוה.
6. **tagline לא-עקבי בין מקומות:** ה-meta/og וה-boot אומרים "I design AI products people actually trust"; ההירו-החי אומר נוסח-אחר ("I make AI feel less like a stranger..."). SPEC §15 מסמן את ה-tagline כ"פתוח-לאישור". · `Layout.astro` (description, boot-l3) מול `index.astro` (cv-tagline), `SPEC §15` · **מצוטט** · גבוה.
7. **placeholder-תוכן חי באתר:** קישורי LinkedIn/Dribbble = `href="#"` עם `TODO(Aviv)`. · `index.astro` (footer) · **מצוטט** · גבוה.
8. **פאנל-tuner ושכבת-`?tune`** = פיגום-מפתח (dev-only) שעדיין יושב בקוד-הייצור; memory מציין ש-`?tune` "כבוי/קשור-למנגנון-הישן, לבנות מחדש". · `Layout.astro` (buildTuner), `global.css` (#ztune), `memory-portfolio` · **מצוטט** · גבוה.
9. **מוטיבי-עיצוב מובטחים-ולא-נוכחים:** SPEC §3/§7 מבטיח "swatches/Figma/stickers כשפה-חוזרת לכל-אורך-הגלילה", אך בפועל הם מוגדרים-ב-CSS-ולא-ממומשים-בדף (חוץ מ-cursor). הקראפט-הגלוי המוצהר כמעט-לא-קיים על המשטח. · `SPEC §3, §7` מול `index.astro` · **מוסק** · בינוני.
10. **הפינים (שכבת-"איך-אני-עובד") מוסתרים** — spec-v2 §8.2 מגדיר אותם כ"יחזרו, שמור-מקום-אדריכלי" ותורמי-אמון, אך כרגע שכבת-האמון הזו לא-נראית. · `global.css` (.pin display:none), `index.astro` (pin buttons), `spec-v2 §8.2` · **מצוטט** · גבוה.
11. **אין זהות-עיצוב-כוללת מוכרעת:** SPEC §13 קובע "הגדרות-הבסיס המדויקות יתגבשו תוך-כדי הפרוטוטייפ" ו"כל-סקשן עם רקע/אווירה משלו" — כלומר אין מערכת-עיצוב נעולה; הבסיס-הקרם-הברוטליסטי הוא ברירת-מחדל-שנשארה, לא בחירה. · `SPEC §13`, `memory-portfolio` ("placeholder דיפולטי, לא בחירת-אביב") · **מוסק** · בינוני.

---

## "מה לא ידוע" — שאלות שהחומר לא ענה עליהן

1. **מהי שפת-העיצוב הרצויה?** אין בחומר אף הגדרה חיובית של פלטה/טיפו/רכיבים שאביב *בחר* לקונספט-החדש — רק שלילה ("לא Brutalist Pop", "לא Aviv OS"). הבסיס-הסינמטי הוגדר מפורשות כ"יתגבש תוך-כדי" (`SPEC §13`).
2. **האם הפלטה (orange/blue/cream/ink) שורדת לקונספט-החדש, או רק ה-accents?** SPEC §13 שומר את ה-accents (orange+blue) אך אומר "הבסיס כבר לא קרם-ברוטליסטי קבוע" — בלי לקבוע מה כן.
3. **מה דמות-המוטיבים בקונספט-החדש?** SPEC מבטיח Figma/swatches/stickers, אך לא הוכרע אם הם נשארים בלבוש-הברוטליסטי הקיים, מקבלים שפה-חדשה, או יורדים.
4. **טון-הטיפוגרפיה:** האם Space Grotesk + Space Mono נעולים, או הם שריד-v2 כמו הפלטה? (החומר לא דן בהם מאז v2; הם פשוט נשארו.)
5. **כיוון-עיצוב-כרטיסי-העבודות:** memory מסמן את זה כ"צעד-הבא פתוח / לא-תואם-וייב" — אך אין אפיון איך הם *אמורים* להיראות.
6. **זהות-עיצוב כוללת מול per-section:** SPEC §5 רוצה "כל-סקשן עם צבע/אווירה משלו". לא ידוע אם זו מערכת-עיצוב-אחת-עם-וריאציות או סקשנים-נפרדים-ויזואלית.
7. **double-amber — איך נפתר בפועל בקוד?** spec-v2 קבע *עקרון* (מקור-יחיד-נעול), אך הקוד עדיין מחזיק כמה מערכות-אור; לא ידוע מה הגוון-הנעול הסופי ואיך מאחדים.
8. **רפרנסים-ויזואליים:** spec-v2 (OD-A12) מבקש מאביב 2-3 רפרנסים שמגדירים "וקטור-נכון / וייב". הם לא קיימים בחומר — אין דוגמאות-מטרה לשפה.
9. **מובייל:** איך שפת-העיצוב (לא רק המוטיון) מתנהגת במובייל מעבר ל"מוטיבים-מרוסנים" (`SPEC §11`) — לא מאופיין ויזואלית.
10. **אימות-חי:** האם השפה-הקיימת אומתה מול עיני-מגייס אמיתי? `spec-v2` מציין אימות-חי כ-ground-truth שטרם בוצע במלואו.

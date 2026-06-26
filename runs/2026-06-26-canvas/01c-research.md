# סקירת-רקע — שכבות / ממדים / תצוגות במערכות-חשיבה (חוקר-רקע, 06)

> סוכן: חוקר-רקע (06), Design OS. תאריך-ריצה: 2026-06-26. גישת-web: WebSearch + WebFetch.
> **מוקד (שער-1):** לא "הקנבס" אלא **מהן השכבות/העמודים/הממדים** של מערכת-חשיבה, איך נעים ביניהם, והקנבס=דרך-תצוגה אחת. היעד-המרכזי של אביב: **להישאר מתמצא ככל שהעבודה גדלה.**
> **משמעת-מקורות:** כל קביעה = URL + טריות + `נמצא-במקור`/`מוסק` + ביטחון. מה שלא נמצא במקור-אמין = בסעיף "מה לא נמצא" בסוף. עומק-לפני-רוחב: חקרתי רק מה שסוגר את 5 הפערים שהוגדרו.

---

## פער 1 — איך כלים מובילים מבנים "שכבות/ממדים/תצוגות", וההבדל view-modes מול עמודים-נפרדים

זה הפער המרכזי שאביב חידד. נמצאו **שני דפוסים שונים-במהותם**, וזו אבחנה load-bearing לאפיון:

### דפוס א' — "אותו תוכן, כמה תצוגות" (views על מקור-אמת אחד) — מודל Notion
- **נמצא-במקור / גבוה / טרי (Notion Help, נצפה 2026-06):** הדפוס המקובל הוא **database אחד = מקור-אמת, ועליו כמה views** (table / board / calendar / timeline / gallery / list / map / chart). "Database views let users see the same data in different ways... a single database can serve many different workflows." לכל view filters/sorts/layout משלו, אבל **התוכן אחד**. מקור: https://www.notion.com/help/views-filters-and-sorts
- **נמצא-במקור / גבוה (Notion VIP best-practice):** עיקרון-עיצוב מפורש — *"rather than creating two Linked Databases for the same database, create multiple views"* — כלומר **לא לשכפל תוכן, אלא להוסיף עדשה**. מקור: https://www.notion.com/help/guides/using-database-views
- **המשמעות לאפיון:** במודל הזה "ממד" אינו עמוד-נפרד אלא **עדשה על אותו מאגר**. ה"קנבס" של אביב יכול להיות *view-mode* אחד מבין כמה על אותם ארטיפקטים — בדיוק עיקרון "תוכן-לפני-מיכל". זה תומך ישירות בהכרעת-שער-1.

### דפוס ב' — "שכבות מקוננות / עמודים-נפרדים" (hierarchy של משטחים) — מודל Heptabase / Figma / Miro
- **נמצא-במקור / גבוה / טרי (Heptabase Wiki v1, נצפה 2026-06):** מבנה ב-**רמות מפורשות:** Cards (יחידה-אטומית) → Whiteboards (משטח-החשיבה) → **Nested Whiteboards** (היררכיה: "organize the structure of topics using Nested Whiteboards") → Sections (קיבוץ-קלפים "to see the big picture") → Mindmaps (auto-layout). **ובמקביל** שכבת-מטא עצמאית: Tags/Properties + Table/Kanban views ("alternative organizational lenses"). מקור: https://wiki.heptabase.com/version-one
- **מוסק / גבוה:** Heptabase ממחיש **את שני הדפוסים יחד** — היררכיית-משטחים מרחבית (nested whiteboards) **וגם** עדשות לא-מרחביות (tags/table) על אותם cards. כלומר השכבות אינן רק "עמודים" — חלקן מרחביות וחלקן מטא-data. הקנבס = רק אחת מהן.
- **נמצא-במקור / בינוני (סקירת-כלים):** Figma=Pages, FigJam=board, Miro=frames, Muse="nested boards for delving into components". הדפוס הרווח להתמודד עם גודל = **חלוקת המשטח האינסופי ל-pages/frames נפרדים** במקום מישור-אחד-ענק. מקור: https://omnicanvasnotes.com/blog/reviews/best-infinite-canvas-apps-2026/

### האבחנה המכריעה (מוסק / גבוה)
- **views = אותו תוכן בעדשות שונות; pages/layers = משטחים/תכנים נפרדים שנעים ביניהם.** רוב הכלים המובילים **משלבים את שניהם:** היררכיית-משטחים (לחלק עבודה גדולה) + עדשות-תצוגה (לראות אותו תוכן אחרת). → לאפיון של אביב: צריך להחליט לכל "ממד" אם הוא **עדשה** (אותו תוכן) או **שכבה/עמוד** (תוכן-נפרד). זו ההכרעה שמייצרת את "רשימת-השכבות" החסרה (מטרה-לא-מוגדרת #2 ב-01b).

---

## פער 2 — מתי קרבה-מרחבית נושאת-משמעות (מסנן-העל של אביב)

זה ה"מסנן-על" ב-01-map (§7) — הקנבס מצדיק עצמו *רק* אם קרבה=משמעות. המחקר תומך חזק ומחדד **מתי כן ומתי לא**.

### מתי כן
- **נמצא-במקור / גבוה (Shipman & Marshall, מאמר-יסוד על spatial hypertext):** משתמשים **נטשו מנגנוני-קישור-מפורשים לטובת קרבה-מרחבית** — "users avoided the explicit linking mechanisms in favor of the more implicit expression of relationships through spatial proximity" — גם בדיגיטלי וגם בקלפי-נייר פיזיים. ארבע תועלות: visual cognition / interpretation גמישה / שיתוף יעיל / **information triage מהיר**. מקור: https://people.engr.tamu.edu/shipman/spatialhypertext.html
- **נמצא-במקור / גבוה:** המושג **"constructive ambiguity"** — להניח דברים קרובים-אך-לא-מאוחדים מבטא *יחס-אפשרי תוך הכרה באי-ודאות*. זה ערך שרשימה/עץ לא נותנים. מקור: כנ"ל.
- **מוסק / בינוני:** זה רלוונטי במיוחד ל"מצב-תקיעה" של אביב (01-map §12) — כשאין-עדיין-מבנה, קרבה-מעורפלת היא בדיוק הכלי לחשיבה-מתהווה. → קרבה מצדיקה עצמה כשהעבודה **בשלב-החקירה/אי-הוודאות**, לא בשלב-הסופי-המסודר.

### מתי לא (הצד השני של המסנן)
- **נמצא-במקור / בינוני / טרי (ביקורת-תחום):** *"on an arbitrary canvas, you don't know if two things are close to each other to indicate a relation, or just for aesthetic reasons"* — קרבה **מאבדת משמעות** אם אין משמעת-פריסה; "users cannot easily glean the structure of content from the layout alone". מקור: https://allo.io/blog/whiteboard-apps-are-dead-but-visual-collaboration-thrives-in-the-ai-era/
- **נמצא-במקור / בינוני:** "If the work is a linear deliverable, structured data, or a quick note — a document, spreadsheet, or notes app is the better tool." → **רשימה/טבלה עדיפה** לתוצר-ליניארי או נתונים-מובנים. מקור: כנ"ל.
- **מוסק / גבוה:** המסנן של אביב מאומת-חיצונית **משני הצדדים** — קרבה=ערך בחקירה/triage/אי-ודאות, אבל **חוב** כשהתוכן ליניארי/מובנה או כשאין משמעת. זה לא בינארי per-canvas אלא **per-שלב-עבודה** — חיזוק להחלטה "איזו שכבה על קנבס ואיזו ברשימה".

---

## פער 3 — זום-סמנטי מול זום-חזותי

הוכרע ב-01-map כ"לא-נחתם" (#8). המחקר נותן הגדרה חדה + שם-מנגנון.

- **נמצא-במקור / גבוה (InfoVis-Wiki + Wikipedia ZUI):** **זום-חזותי (geometric)** = משנה רק *גודל*, כל האלמנטים והמבנה נשמרים. **זום-סמנטי (semantic)** = משנה את *כמות-וצורת-הפירוט* — אלמנטים מופיעים/נעלמים/משנים-צורה לפי רמת-הזום (האנלוגיה הקאנונית: מפה ברמת-עיר מול רמת-רחוב). מקור: https://infovis-wiki.net/wiki/Semantic_Zoom + https://en.wikipedia.org/wiki/Zooming_user_interface
- **נמצא-במקור / גבוה:** תועלות זום-סמנטי = *"enhanced usability, reduced cognitive load, more efficient navigation by presenting only the most relevant details at each zoom level."* מקור: https://arxiv.org/html/2510.00003v1 (Semantic Zoom and Mini-Maps for Software Cities, 2025-10)
- **מוסק / גבוה:** רמות-המקוננות שהמנוע הציע ל-אביב (סקירה ⊃ אשכול ⊃ ארטיפקט ⊃ פרט, 01-map §4) = **בדיוק level-of-detail סמנטי**, לא זום-חזותי. → אם רוצים "להישאר מתמצא כשגדל" (י-1), זום-סמנטי הוא המנגנון-התומך-במחקר; זום-חזותי לבדו לא מפחית-עומס. זה ממליץ-בעקיפין על המנגנון אבל **ההכרעה של המאפיין/אביב**.

---

## פער 4 — התמצאות בקנה-מידה (wayfinding/orientation) — היעד-המרכזי של אביב

זה י-1 ("להישאר מתמצא") = make-or-break. המחקר נותן מנגנונים-ספציפיים + עיקרון-יסוד.

### עיקרון-היסוד: זיכרון-מרחבי דורש יציבות
- **נמצא-במקור / גבוה / 2020-10-11 (NN/g, Spatial Memory):** זיכרון-מרחבי = "learn the location of objects by interacting repeatedly", אבל הוא **fuzzy** (זוכרים "שכונה" לא מיקום-מדויק) ו**שביר** — *"users need stable UIs where things don't move around"*; reflow שובר התמצאות. המלצות: **boundaries+landmarks**, **cues משלימים** (icon+label, צבע/badge), **היררכיה רחבה-ושטוחה עדיפה על עמוקה**, **להימנע מ-adaptive-rearranging**. מקור: https://www.nngroup.com/articles/spatial-memory/
- **מוסק / גבוה — מתח לאפיון:** קנבס-חופשי שבו אביב מזיז דברים **מתנגש** עם דרישת-היציבות של זיכרון-מרחבי. → או שהמערכת שומרת מיקומים יציבים (auto-layout שמשמר), או שההתמצאות נשענת על landmarks/minimap ולא על זיכרון-מיקום. דגל-מתח חשוב.
- **חיזוק (NN/g):** המלצת "broad-shallow > deep" מתלכדת עם א-5/ת-2 של אביב (מיעוט-שכבות-שמחזיק) — **גם ההתמצאות וגם הקמצנות מצביעות לאותו כיוון: פחות-רמות, רחב.**

### המנגנונים הקונקרטיים (פתוח ב-01-map #7)
- **נמצא-במקור / בינוני / טרי:** הדפוס המקובל ב-infinite-canvas: **minimap בפינה + zoom-level-indicator** ("never get lost"), בהשראת-משחקים; חיצים-בקצוות לכיוון-תוכן-נוסף. מקור: https://www.goodnotes.com/blog/building-whiteboard-infinite-canvas
- **נמצא-במקור / גבוה (NN/g, Local Navigation):** ניווט-מקומי = "valuable orientation and wayfinding aid"; **breadcrumbs** ל-"you-are-here" בעומק; "always want them to know where they are". מקור: https://www.nngroup.com/articles/local-navigation/
- **מוסק / בינוני:** breadcrumbs מתאים יותר ל**היררכיה (nested whiteboards)**; minimap מתאים ל**מישור-מרחבי-יחיד**. → בחירת-מנגנון-ההתמצאות תלויה בבחירת דפוס-המבנה (פער 1): אם שכבות-מקוננות → breadcrumbs; אם מישור-גדול → minimap; אם שניהם → שניהם.

---

## פער 5 — מגמת AX / AI-workspaces (לשכבה שמארחת פלט-AI)

- **נמצא-במקור / בינוני / טרי (mid-2025):** הדפוס הרווח להצגת פלט-AI = **Canvas/Artifacts = פאנל-צד שמפריד את התוצר-היצירתי מזרם-הצ'אט** ("digital whiteboard/editor", "persistent workspace to return to"). ChatGPT Canvas / Claude Artifacts / Gemini Canvas. מקור: https://www.mindstudio.ai/blog/what-is-claude-generative-ui-vs-canvas-artifacts
- **מוסק / בינוני:** המגמה היא **הפרדת-פלט-מתהליך** (artifact עומד-בפני-עצמו, נשמר, חוזרים אליו) — מתלכדת עם יכולת-A של אביב ("פלט נוחת ומעוגן למקור", 01-map §4) ועם north-star "תצוגת-התובנות". → אבל הכלים האלה **chat-first** (פלט יחיד בצד), לא **canvas-first עם כמה ארטיפקטים מרחביים** — שם יש **פער/הזדמנות** (מוסק): אף אחד מהמובילים לא נותן משטח-מרחבי שמארח-ומנהל *כמה* פלטי-AI עם אינדיקציות-אמון. זה בדיוק המרחב של אביב.
- **מוסק / נמוך-בינוני:** ה-AI-workspaces הנוכחיים **לא מציגים אינדיקציות-אמון מובנות** (מקור/ביטחון/⚠️) על-פני המשטח — דבר שהמערכת של אביב כבר מחויבת לו (א-4). הזדמנות-בידול.

---

## תקציר-החלטה: 4-6 הממצאים שהכי משנים את האפיון

1. **שני דפוסי-מבנה שונים-במהותם, והמובילים משלבים אותם** — "views על מקור-אחד" (Notion) מול "שכבות-מקוננות/עמודים-נפרדים" (Heptabase/Figma/Miro). Heptabase עושה את שניהם: nested-whiteboards מרחביים **+** tags/table כעדשות על אותם cards. → אביב צריך להכריע **לכל ממד אם הוא עדשה או שכבה** — זה מה שמייצר את רשימת-השכבות החסרה. *(נמצא-במקור, גבוה, טרי)*
2. **מסנן-הקרבה של אביב מאומת משני הצדדים, ותלוי-שלב לא תלוי-קנבס** — קרבה=ערך בחקירה/triage/אי-ודאות ("constructive ambiguity", Shipman); קרבה=חוב כשהתוכן ליניארי/מובנה או בלי משמעת-פריסה → אז רשימה עדיפה. רלוונטי ישירות ל"מצב-תקיעה" כמצב-ערך-שיא. *(נמצא-במקור, גבוה)*
3. **זום-סמנטי (לא חזותי) הוא המנגנון שהמחקר קושר ל"מתמצא-כשגדל"** — משנה רמת-פירוט (סקירה⊃אשכול⊃ארטיפקט⊃פרט), מפחית-עומס. זום-חזותי לבדו לא עוזר להתמצאות. *(נמצא-במקור, גבוה, מקור 2025)*
4. **זיכרון-מרחבי דורש יציבות — ויש כאן מתח-ליבה עם קנבס-חופשי** — NN/g: דברים-זזים שוברים התמצאות; פתרון = landmarks+minimap+cues + **היררכיה רחבה-ושטוחה**. החיזוק הכפול: גם התמצאות וגם קמצנות-שכבות → פחות-רמות. *(נמצא-במקור, גבוה, 2020 אך עקרון-יסוד)*
5. **מנגנון-ההתמצאות נגזר מבחירת-המבנה** — היררכיה→breadcrumbs/"you-are-here"; מישור-מרחבי→minimap+zoom-indicator; שניהם→שניהם. לא לבחור מנגנון לפני שבוחרים דפוס-מבנה (פער 1). *(מוסק, בינוני)*
6. **הזדמנות-בידול ב-AI-workspaces** — המובילים chat-first עם artifact-יחיד-בצד, בלי אינדיקציות-אמון על-המשטח. canvas-first שמארח *כמה* פלטים מרחבית **עם** מקור/ביטחון/⚠️ = מרחב לא-תפוס. *(מוסק, בינוני-נמוך)*

---

## מה לא נמצא / לא אומת

- **מספר-benchmark כמותי לאף מדד של אביב** (מד-1…מד-4 ב-01b, כולם ⚠️). לא נמצא baseline-תחום ל"שימור-התמצאות תחת-גידול" או "כמה ארטיפקטים לפני שההתמצאות נשברת". אין מספר-תחום לתת — נשאר להכרעת-אביב. *(לא-נמצא)*
- **מחקר חד-משמעי 2D מול רשימה** — הספרות **מעורבת** (ScienceDirect: "task performance degrades in 3D vs 2D"; מחקרי-זיכרון-מרחבי תלויי-משימה). אין קביעה גורפת "קנבס תמיד עדיף/גרוע" — תלוי-משימה. → תומך במסנן-תלוי-שלב, לא בהכרעה גורפת. מקור-ההסתייגות: https://www.sciencedirect.com/science/article/abs/pii/S1071581904000096
- **אילו מתודות-נוספות (מעבר לפירוק-משימה) הקנבס יארח** — פער-פנימי (01-map #3), לא נושא-web; לא חיפשתי.
- **stack/מציאות-טכנית** — מחוץ-לתפקיד; לא חיפשתי.
- **דפוס מאומת ל-"canvas-first עם אינדיקציות-אמון על כמה פלטי-AI"** — לא נמצא כלי-קיים שעושה זאת (לכן סומן הזדמנות=מוסק, לא נמצא-במקור). היעדר-מקור הוא עצמו האות.

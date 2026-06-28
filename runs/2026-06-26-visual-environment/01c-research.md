# סקירת-רקע — הסביבה-הוויזואלית של DesignOS

> סוכן: חוקר-רקע (06), Design OS. תאריך: 2026-06-28. גישה: web (WebSearch/WebFetch).
> **משמעת-מקור:** כל קביעה = **URL** + **תאריך/טריות** + `נמצא-במקור`/`מוסק` + ביטחון. **לא הומצא URL.** מה שלא אומת → §5.
> **scope:** רק מה שסוגר פער של *הסביבה* (לפי `01b-goals` פ-2/4, `01-map` §10). לא סקר-שוק גנרי. עומק-לפני-רוחב — שאלת-המוקד (פ-4) קיבלה את העומק.

---

## 🔴 1. שאלת-המוקד — הקו בין מבנה-אינטראקציה לעיצוב-ויזואלי-סופי

**הפער (פ-4 / מטרה-לא-מוגדרת #2):** האם יש קונבנציה ל"נאמנות-ביניים" — מבנה שמרמז היררכיה בלי לקבע עיצוב?

### ממצא 1א — כן, יש קונבנציה מפורשת: **lo-fi mockup / mid-fidelity** = השכבה בדיוק בין שלד-מבנה ל"עור" ויזואלי
- **נמצא-במקור / ביטחון: גבוה.** התעשייה מבחינה במפורש בין **wireframe (השלד — boxes, בלי תוכן/צבע)** ל**mockup (העור — צבע/תוכן/טיפוגרפיה)**, ויש **שלב-ביניים מוכר**: *lo-fi mockup* — "turn wireframes into designs that approximate the finished product. Although they still use plain boxes and shapes, lo-fis **solidify the arrangement of information and visuals**." הרצף הקנוני: **Wireframe → Lo-fi Mockup → Hi-fi Mockup → Prototype**, "add levels of detail only as your ideas solidify." מקור: UXPin, https://www.uxpin.com/studio/blog/wireframe-mockup-lofi-hifi-nomenclature/ (מאמר-עזר, ללא-תאריך-מפורש; קונבנציה יציבה לאורך-שנים, ביטחון-גבוה שהיא לא-בת-חלוף). **השלכה ל-DesignOS:** ה"נאמנות-ביניים" שאביב מחפש = **שם מוכר** (lo-fi/mid-fi) — היא מסדרת היררכיה+פריסה במפורש *בלי* לקבע צבע/טיפו/פיקסל. זה בדיוק קו ה-`05c AC-10`.

### ממצא 1ב — 🔑 ה**אזהרה** ששוברת-החלטה: "fake low-fidelity" — מבנה מלוטש-מדי מזמין משוב על העיצוב במקום על המבנה
- **נמצא-במקור / ביטחון: גבוה.** "The problem with **'fake low-fidelity'** wireframes is that they still carry enough polish to trigger aesthetic feedback; **gray boxes won't save you if spacing, typography, and microcopy already imply the solution is settled.**" וגם: "When a screen looks polished, the room responds to polish... When a wireframe looks unfinished, **it signals reviewers the design is still open to change**, encouraging candid big-picture feedback rather than nitpicky comments about button color." מקור: Figr, https://figr.design/blog/low-fidelity-wireframes (2026, עדכני). מחוזק ע"י Balsamiq, https://balsamiq.com/blog/wireframe-vs-mockup-vs-prototype/ (קונבנציית-roughness=permission). **השלכה ישירה להכרעת-פ-4:** הקו אינו רק "מה מותר לצייר" — הוא **אות-תקשורת**. אם הסביבה מציגה פריסה מלוטשת-מדי, אביב (וכל צופה) יתחיל להגיב לאסתטיקה ולא למבנה/לתובנה — וזה **סותר ישירות את a-2** (הטעם נשאר של אביב) ואת AG-2 (לא "יפה" כיעד). כלומר: **נאמנות-ביניים אינה רק מותרת — היא ה-ה-default הנכון** כדי לשמר את גבול ה-scope ולכוון את תשומת-הלב לתובנה (הלב, א-4). זו תמיכה-חיצונית חזקה ב-`DS §11ג` ("פרוטו-wireframe רזה, לא מוקאפ").

### ממצא 1ג — ה**פריסה עצמה כבר נושאת משמעות עיצובית** — מאשר את `DS §11ב`, אבל גם תוחם אותה
- **מוסק / ביטחון: גבוה.** מהאזהרה לעיל נובע ש"spacing/arrangement of information" *כן* מרמז את ההחלטה — זה בדיוק מה ש-`DS §11ב` טען ("הפריסה = אינדיקציה להיררכיית-העיצוב"). הקונבנציה אומרת: זה **בלתי-נמנע** (פריסה תמיד מרמזת), ולכן ההכרעה אינה "האם פריסה מרמזת" אלא **"באיזו נאמנות לעצור כדי שזה יישאר רמז-מבנה ולא יהפוך להצעת-עיצוב".** מקורות: UXPin (lemfi mockup "solidifies arrangement"), Figr (spacing-implies-settled). **לשער-2:** הקו אינו דיכוטומי (מבנה/עיצוב) אלא **רציף** — וההכרעה היא נקודת-עצירה על הרצף, לא קיר. זה ממסגר-מחדש את פ-4 כ"איפה לעצור על הרצף" ולא "האם לחצות".

---

## 2. קנבס-תנועה-חופשית מול רשימה/מובנה — מתי כל אחד מנצח (תומך בטופולוגיה-המעורבת, מ-7)

### ממצא 2 — הקונבנציה תואמת את `05c AC-2` (anti-monolith): קנבס-חופשי≠מבנה, וזו בחירה-לפי-טבע-העבודה
- **נמצא-במקור / ביטחון: בינוני-גבוה.** **קנבס-תנועה-חופשית מנצח** כש"the freedom to drop items anywhere and connect anything to anything is the whole point" — אידאציה, סיעור, חקר. **מבנה/node-based מנצח** כשצריך "structure, context, and a clear path from a sticky note to a shipped feature" — והאזהרה: "the sprawling infinite canvas feels like a messy garage." Whimsical מתואר כ"opinionated visual structure... **less a freeform whiteboard, more a structured diagramming tool** — clean output and speed," לעומת FigJam/Miro freeform-first. הקריטריון המומלץ: לבחור **לפי-fit עם העבודה שאתה עושה רוב-הזמן, לא לפי כמות-פיצ'רים.** מקורות: Storyflow, https://storyflow.so/blog/best-miro-alternatives-2026 (2026); Taskade, https://www.taskade.com/compare/free-miro-alternative (2026). **השלכה:** מאשר חיצונית את `05c AC-2`/מ-7 — **אין מיכל-אחיד נכון.** המיפוי שלכם (ש-2 חקר=קנבס-חופשי; ש-5 תוצר=ליניארי) **תואם בדיוק את הקונבנציה** — חקר=drop-anywhere, תוצר=path-to-shipped. זה לא חידוש מסוכן אלא best-practice. **מבחן-העל שלכם** ("קרבה-בלי-משמעות → רשימה לא קנבס") = ניסוח-מדויק של "messy garage".

---

## 3. התמצאות בקנה-מידה (י-1 = make-or-break) — קונבנציות מוכחות נגד "ללכת לאיבוד"

### ממצא 3א — צמד-הקונבנציות הסטנדרטי: **semantic zoom + minimap קבוע** (מחקר מבוקר, לא דעה)
- **נמצא-במקור / ביטחון: גבוה.** מחקר 2025 על "Software Cities" מצא: **semantic zoom** (פריט מתחלף בייצוג מתאים-לרמה כשמתרחקים — לא רק הגדלה/הקטנה) + **mini-map קבוע** (top-view, ~4% מהמסך, פינה עליונה, סמן-מיקום-משתמש, teleport-בלחיצה). תוצאות-מבחן: **15/16 העדיפו את גרסת ה-semantic-zoom**; minimap "rated more helpful for larger landscapes" (ככל שגדל — יותר חיוני, בדיוק י-1). העיקרון: Shneiderman "**overview first, zoom and filter, details-on-demand**." המלצה מפורשת: **מעברי-זום עם אנימציה חלקה כדי לשמר את ה-mental map.** מקור: arXiv 2510.00003, https://arxiv.org/html/2510.00003v1 (2025). **השלכה:** למק-6/י-1 יש **תשובה-קונבנציונלית מאומתת**: semantic-zoom + minimap + מעברים-מונפשים. זום-סמנטי גם **משרת את ממצא-1** — ברמת-זום-נמוכה רואים מבנה (lo-fi), בזום-פנימה פרטים — כלומר הנאמנות עצמה יכולה להיות *פונקציה-של-זום*.
- **מחוזק / ביטחון: בינוני.** המוסכמה ה"וידאו-גיים": "An infinite canvas means you can easily get lost, **which is where the minimap comes in — inspired by video games**"; ו"dot-grid + minimap בפינה + מחוון-רמת-זום... never get lost." מקורות: Goodnotes, https://www.goodnotes.com/blog/building-whiteboard-infinite-canvas; סיכום-חיפוש Steve Ruiz (zoom-to-fit / zoom-to-content כקונבנציה). **הסתייגות:** מאמר-ה-zoom-UI עצמו של Steve Ruiz עוסק רק במתמטיקה ולא במנגנוני-התמצאות (אומת ב-WebFetch — לא להסתמך עליו לעניין זה).

### ממצא 3ב — **Sensecape (UIST'23)**: האנלוג-הקרוב-ביותר — LLM + קנבס + רמות-הפשטה — ומצא שמבנה-היררכי ניצח
- **נמצא-במקור / ביטחון: גבוה.** Sensecape = מערכת sensemaking על קנבס עם פלט-LLM, שפותרת עומס דרך **"multilevel abstraction"** — ארגון-ידע **היררכי ולא ליניארי**, מעבר חלק "foraging↔sensemaking." מחקר-משתמשים: המבנה הרב-רמתי **העצים חקירת-יותר-נושאים ובניית-ידע-מובנית** — כלומר **ריבוד-רמות-הפשטה ניצח על קנבס-שטוח** למשימות-מורכבות. מקור: arXiv 2305.11483, UIST'23, https://arxiv.org/abs/2305.11483 (2023). **השלכה חזקה:** זה כמעט-בדיוק DesignOS (פלט-AI על מרחב-ויזואלי, ניווט-בין-רמות). הממצא תומך ישירות ב-(א) י-1 — רמות-הפשטה מפורשות = התרופה לקריסת-התמצאות; (ב) המבנה-המעורב — לא קנבס-שטוח אחד. **זו ולידציה-חיצונית שהכיוון "7 חדרים + ניווט-בין-רמות" אינו מומצא — הוא דפוס-מחקר מוכח.**

---

## 4. נחיתת פלט-AI בסביבה — דפוסי trust/provenance על פלט-מחולל

### ממצא 4 — דפוס-2026 מבוסס: **confidence indicator** מדורג-לפי-סוג-פלט + **אזהרת over-indication**
- **נמצא-במקור / ביטחון: בינוני-גבוה.** "אחד מדפוסי-העיצוב המשמעותיים ב-2026 = **visual confidence indicator**": badge-אחוז ("92%") לסיווג; **קישור-מקור** לאחזור-עובדתי; **מסגרת-צבע** (ירוק=ביטחון-גבוה, **אמבר=בינוני**) להמלצות-מחוללות. 🔑 **אזהרה שובת-החלטה:** "**avoiding over-indication — if every response is labelled with uncertainty signals, users lose trust in all outputs equally.** Best implementations use indicators only where the stakes of being wrong are meaningful, and keep them subtle enough that high-confidence responses feel clean." מקור: Groovyweb, https://www.groovyweb.co/blog/ui-ux-design-trends-ai-apps-2026 (2026). **השלכה ל-מ-6/א-3:** דרישת-ה-AX שלכם (מקור+ביטחון+⚠️+עקיבות **על כל פלט**) מתנגשת עם best-practice: **אם הכל מסומן — האות מאבד-ערך.** המלצה: לדרג את עוצמת-הסימון לפי-ביטחון (סימון-בולט רק על סטייה/אי-ודאות; פלט-בטוח נקי). זה **לא מערער** את א-3 (האינדיקציות חייבות להיות *זמינות*), אבל מציע ש**ברירת-המחדל הוויזואלית** תהיה שקטה, עם הבלטה לפי-צורך. ⚠️ זה מתח שכדאי להביא לשער-2.
- **מחוזק / ביטחון: בינוני.** סטנדרט-provenance תעשייתי מתגבש: C2PA v2.3 (דצמבר 2025) הרחיב manifests ל**טקסט-לא-מובנה / פלט-LLM**. מקור: Trantor, https://www.trantorinc.com/blog/digital-provenance-ai (2025). + מחקר-נגישות: יישומי-provenance הנוכחיים "inconsistent, limited accessibility, lack of standardization." מקור: arXiv 2505.16057, https://arxiv.org/pdf/2505.16057 (2025). **השלכה:** אין-עדיין שפה-ויזואלית קנונית יחידה ל-provenance — מרחב פתוח, אך הכיוון (מקור-מקושר + מדרג-ביטחון) מיושר עם התקן-המתגבש.

---

## 5. מה לא נמצא / לא אומת

- **מנגנון מעבר-מצב קנבס-חופשי→מבנה-מקונן** (ש-2→ש-3, פ-8 / `01-map` §8): לא נמצא דפוס-תעשייה ספציפי ל"promote-from-loose-to-structured" תוך-שימור-עקיבות. Sensecape מציע foraging↔sensemaking כמסגרת אך לא מנגנון-מעבר מדויק. **פער פתוח.**
- **ייצוג-ויזואלי של master+instances בניווט** (פ-7): מודל-Figma אומת כעיקרון, אך *איך הוא נראה בניווט-בין-חדרים* (עדשה מול עותק, ויזואלית) — לא נמצא דפוס-מפורש. **פער פתוח.**
- **מספרי-baseline ל-"קריסת-התמצאות"** (פ-4 ב-`01b-goals`, מ-1): המחקר אמר "minimap יותר-חיוני בגדל" אך **לא נתן סף-מספרי** (כמה פריטים = "גדול"). מקור: arXiv 2510.00003. baseline נשאר להכרעת-אביב — לא להמציא.
- **golden-output לתצוגת-תובנות** (מ-5): שאלה פנימית, web לא רלוונטי. לא בוצע.
- **בחירת-stack** (AG-3): חוץ-scope במכוון. לא נחקר.
- **רמת-ה-fidelity המספרית המדויקת לעצור-בה** (פ-4): המקורות נתנו את ה*קונבנציה* (lo-fi mid-fi) ואת ה*אזהרה* (fake-lo-fi), אך הנקודה-המדויקת על-הרצף = **הכרעת-עיצוב, לא עובדת-תחום.** מקופל לשער-2.

---

## תקציר לשער-2 (3-5 ממצאים שמשנים-החלטה)

1. **🔴 [פ-4] נאמנות-ביניים = קונבנציה קיימת ושמה lo-fi/mid-fi mockup** — מסדרת היררכיה+פריסה בלי לקבע צבע/טיפו. URL: uxpin.com/.../wireframe-mockup-lofi-hifi-nomenclature. ביטחון: גבוה.
2. **🔴 [פ-4, שובר-החלטה] "fake low-fidelity" — מבנה מלוטש-מדי מזמין משוב-על-עיצוב במקום על-מבנה/תובנה.** ⇒ נאמנות-ביניים *רזה* אינה רק מותרת, היא ה-default-הנכון לשמירת a-2/AG-2 ולמיקוד-בלב. הקו אינו דיכוטומי אלא **רציף — ההכרעה = איפה לעצור.** URL: figr.design/blog/low-fidelity-wireframes (2026). ביטחון: גבוה.
3. **[קנבס↔רשימה] המיפוי שלכם (חקר=קנבס-חופשי, תוצר=ליניארי) = best-practice מדויק, לא חידוש.** קנבס מנצח כש"drop-anywhere הוא הפואנטה"; מבנה מנצח כשצריך "path-to-shipped"; אין מיכל-אחיד נכון (מאשר `05c AC-2`). URL: storyflow.so/blog/best-miro-alternatives-2026 (2026). ביטחון: בינוני-גבוה.
4. **[י-1 התמצאות] צמד מאומת: semantic-zoom + minimap-קבוע + מעברים-מונפשים** (15/16 העדיפו; minimap יותר-חיוני ככל-שגדל). **בונוס:** זום-סמנטי מאחד את ממצא-2 — הנאמנות יכולה להיות פונקציה-של-זום (מבנה בחוץ, פרט בפנים). URL: arxiv.org/html/2510.00003v1 (2025). ביטחון: גבוה.
5. **[ולידציה-על] Sensecape (UIST'23): LLM-על-קנבס עם רמות-הפשטה היררכיות ניצח קנבס-שטוח** למשימות-מורכבות — האנלוג-הקרוב-ביותר ל-DesignOS, מוכיח ש"7-חדרים + ניווט-בין-רמות" = דפוס-מחקר מוכח, לא מומצא. URL: arxiv.org/abs/2305.11483 (2023). ביטחון: גבוה.
6. **[מ-6/א-3, מתח לשער-2] over-indication: אם כל-פלט מסומן (מקור+ביטחון+⚠️) — האות מאבד-ערך.** ⇒ דרג עוצמת-סימון לפי-ביטחון (בולט על-סטייה, שקט על-בטוח). לא מבטל א-3, ממסגר-מחדש את ברירת-המחדל. URL: groovyweb.co/blog/ui-ux-design-trends-ai-apps-2026 (2026). ביטחון: בינוני-גבוה.

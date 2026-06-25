# סקירת-רקע: שכבת-העיצוב-העמוק (Design OS)

> סוכן: חוקר-רקע (Background Researcher, Design OS). תאריך: 2026-06-25.
> מחקר-web אמיתי, 3 פערים בלבד (עומק-לא-רוחב). כל קביעה: מקור (URL) · סוג · ביטחון+טריות.
>
> **🔎 ולידציית-מתזמר:** שני העוגנים הנושאים-משקל אומתו בנפרד (WebFetch) — **UI-Bench** (uibench.ai/leaderboard: "blinded pairwise matches… n=4,047… Rankings based on TrueSkill model", Orchids מוביל) ו-**ADR** (adr.github.io: "single AD and its rationale… can be extended to design and other decisions"). תואמים-לטענה, לא הומצא. הסוכן סימן בעצמו מקורות-חלשים (Constructor=לא-נמצא; DesignManager=paywall/לא-אומת).

---

## פער 1 — מתחרים/תקדימים: "AI שמגביר עיצוב בלי להחליף טעם"

**ממצא מרכזי:** כמעט כל שוק כלי-העיצוב-AI הציבורי הוא **ייצור פיקסלים/UI** (text-to-app), לא **תמיכה-בהחלטת-עיצוב**. ה-"augment-not-replace" קיים בעיקר כ**רטוריקת-שיווק** סביב כלי-ייצור — פחות כמוצר-עצמאי. **זה תומך בבידול של השכבה** (קטגוריה כמעט-ריקה), אבל המקורות לתת-התחום דלילים.

- **Microsoft Copilot for design** ממסגר עצמו "ideation partner, **not a replacement for craft**" — מאיץ שלב-מוקדם, משאיר שיפוט-סופי לאדם. · https://www.microsoft.com/en-us/microsoft-copilot/for-individuals/do-more-with-ai/ai-art-and-creativity/designing-with-copilot-ai-prompts · נמצא-במקור · בינוני-גבוה, חי.
- **"design copilot" כ-senior teammate** שמאתגר reasoning חלש, מסמן החלטות בלי-rationale, מציג tradeoffs — מסגור קרוב לשכבה (פוסט-דעה, לא מוצר). · https://adplist.substack.com/p/build-your-design-copilot · מוסק · בינוני, 2025.
- **DesignManager** (ACM TOG) — copilot אקדמי עם ויזואליזציה node-based של אבולוציית-העיצוב (track/branch של *תהליך*). הקרוב-ביותר ל"ארגון החלטות". · https://dl.acm.org/doi/10.1145/3730919 · **מוסק מ-snippet; הדף 403/paywall — לא אומת ישירות** · נמוך-בינוני.
- **OpenPencil/Pencil** = design-as-code / text-to-UI (מייצר פיקסלים) — **לא** design-rationale; לא מתחרה-ישיר. · https://github.com/ZSeven-W/openpencil · נמצא-במקור · בינוני.
- **"Constructor" כמתחרה ספציפי — לא נמצא.** אל תתייחס אליו כמאומת.

## פער 2 — מוסכמת-תחום: ארגון "החלטות-עיצוב" ונימוקיהן

שתי מסורות בשלות לעגן בהן את O3 (ארגון-החלטות בר-התנהלות):

**א. ADR (Architecture / Any Decision Record)** — הדפוס המקובל, ניתן-להרחבה במפורש לעיצוב:
- ADR = מסמך-קצר הלוכד **החלטה-בודדת + הקשר + rationale + Alternatives(pros/cons) + Consequences + Confidence + Status (proposed/accepted/superseded)**; markdown ממוספר ב-repo. · https://martinfowler.com/bliki/ArchitectureDecisionRecord.html · נמצא-במקור · גבוה, עודכן 3/2026.
- נטבע ע"י Michael Nygard (2011); ניתן-להרחבה ל**"any decision record"** — אותם חלקים עובדים להחלטות-עיצוב. · https://adr.github.io/ · נמצא-במקור (אומת) · גבוה.

**ב. Design Rationale (DR)** — ההורה האקדמית (HCI, מ-1970), עם אזהרה קריטית:
- 4 frameworks: **IBIS** (Issue/Position/Argument), **QOC** (Questions-Options-Criteria), **DRL**, **Toulmin**. · https://en.wikipedia.org/wiki/Design_rationale · נמצא-במקור · גבוה.
- ⚠️ **חסם-אימוץ מאומת:** לכידת-rationale מפורטת היא **intrusive**, "high cost and biases" — זו הסיבה ההיסטורית ש-DR לא נתפס בתעשייה. · אותו מקור · נמצא-במקור · גבוה.

**🔑 עיגון לשכבה (מוסק):** "להתנהל בנוחות עם החלטות" פתור-חלקית = **ADR-קל** (status+alternatives+confidence). וה**שיעור-ההיסטורי החשוב:** ה-DR העשיר נכשל *דווקא בגלל עלות-הלכידה* — אבל AI יכול ללכוד rationale כ**byproduct זול**, מה שעוקף בדיוק את החסם שהרג את הקטגוריה. זו הזדמנות-הליבה.

## פער 3 — עוגן-מדידה: "איכות-עיצוב מעל baseline" + "השוואה-עיוורת"

הפער עם **העיגון החזק והעדכני ביותר** — השיטה שצריך כבר קיימת ומיושמת חי:

- **UI-Bench** — benchmark לאיכות-עיצוב-AI מבוסס **blind pairwise preference + TrueSkill** (לא רובריקה-קשיחה). איכות = "ההסתברות שמעצב-מקצועי מעדיף A על B". · https://arxiv.org/pdf/2508.20410 · נמצא-במקור · גבוה, 9/2025.
- לידרבורד **חי**: **n=4,047 השוואות-עיוורות-זוגיות**, ציון μ+σ+רווח, win-rate. · https://uibench.ai/leaderboard · נמצא-במקור (אומת) · גבוה, חי.
- **PURE** (Practical Usability Rating by Experts) — מומחים מדרגים UX לפי **רובריקה מוגדרת-מראש**, Likert. · https://measuringu.com/pure/ · נמצא-במקור · גבוה.
- **Heuristic Evaluation** — סטנדרט; ⚠️ הטיה כשהצוות מעריך את עבודתו-שלו. · https://fuselabcreative.com/heuristic-evaluation-in-ux-usability-guide/ · נמצא-במקור · גבוה.

**🔑 עיגון ישיר ל-⚠️ M5 ("פלט-שכבה מול גנרי, עיוור"):** UI-Bench הוא **בדיוק התבנית** — הצג שני פלטים (שכבה vs דיפולט-גנרי) למעצב, עיוור, אסוף העדפה, צבור TrueSkill/Elo. זה ממיר את המדד ⚠️ ל-baseline בר-הגנה. להערכה-מובנית לא-זוגית — PURE נותן רובריקה מוכנה.

---

## מה לא נמצא / לא אומת

- **"Constructor" ככלי-מתחרה** — לא הופיע. אל תניח שקיים.
- **Pencil/OpenPencil כ-design-rationale** — אומת שהם בצד ייצור-UI, לא תמיכת-החלטה.
- **DesignManager (ACM 3730919)** — הדף 403/paywall; DOI אמיתי אך **תוכן לא אומת ישירות**, ללא תאריך-מדויק.
- **Benchmark שמודד "design-rationale quality" (לא UI-quality)** — לא נמצא. UI-Bench מודד פיקסל-תוצר, לא איכות-ההחלטה. לפער "ארגון-החלטות-מעל-גנרי" אין benchmark מוכן — לגזור מ-PURE/blind-preference.
- **תת-התחום "AI design-decision-support כמוצר עצמאי"** — דליל-מקורות אמיתי (פער-שוק אמיתי, אבל גם אין עוגן-מתחרה חזק להעתיק).

**3 נקודות-החיבור החזקות:** (1) ADR-קל כמבנה-ארגון · (2) ה-⚠️שיעור שעלות-לכידה הרגה design-rationale היסטורית — וה-AI עוקף אותו · (3) UI-Bench כתבנית-מדידה blind-pairwise מוכנה-לאימוץ.

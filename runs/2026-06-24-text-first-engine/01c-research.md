# סקירת-רקע — PriceMatch, מנוע "טקסט-תחילה" (T-0042)

> סוכן: חוקר-רקע (Background Researcher, Design OS). תאריך: 2026-06-25.
> קלט: `01-map.md` + `01b-goals.md`. מיקוד: 4 פערים מוגדרים בלבד (עומק, לא רוחב).
> כל קביעה: **מקור** (URL אמיתי) · **סוג** (נמצא-במקור/מוסק) · **ביטחון + טריות**.
>
> **🔎 ולידציית-מתזמר (2026-06-25):** זו הבדיקה-החיה הראשונה של חוקר-רקע. שלושה URLs מרכזיים אומתו בנפרד (WebFetch) ונמצאו אמיתיים + תואמים-לטענה, כולל ציטוטים מדויקים: getquotable.ai ("Universal AI Parser" / "compare quotes... 60%" / "Quotation-First SMB"), vellum.ai (טבלת-עלות $1.67/10k + "OCR for header data, LLMs for line items"), virtido.com ("Extract text first... loses spatial relationships" + "85-95% for well-structured documents"). **לא אותרה המצאת-מקור.** הסוכן גם סימן בעצמו מקורות-חלשים (Lido 99.9% = שיווק-ספק; מספרי businesswaretech = מסיכום-חיפוש, לא נקרא ישירות → ביטחון-בינוני).

---

## עדשה 1 · נוף-מתחרים

המסקנה הראשית: שוק רווי של "חילוץ-AI ממסמך פיננסי", אבל מפוצל. כמעט כל הכלים הבולטים הם **חשבוניות לתשלום (AP)** — לא **השוואת הצעות-מחיר נכנסות** מצד הקונה. זה הבידול של PriceMatch.

### מתחרים ישירים (חילוץ + השוואת הצעות לקונה SMB)

- **Quotable AI** — הקרוב ביותר ל-PriceMatch. "Universal AI Parser" שממיר "any PDF, spreadsheet, email, scan, or photo" להצעות/הזמנות מובנות; פונקציית RFQ עם "compare quotes, cut supplier response time by 60%"; ממקד "Quotation-First Small to Medium Size Businesses" (בנייה, IT, הפצה, ייצור).
  · מקור: https://getquotable.ai/ · סוג: נמצא-במקור · ביטחון גבוה, טרי (אומת 2026-06-25)
  · הערה (מוסק): אין אזכור ישראל/עברית; בסיס Austin/Singapore/Manila — אין נוכחות RTL/עברית, וזה החפיר של PriceMatch.

- **NeenOpal — AI RFQ Automation** — אוטומציה של סיווג-RFQ, חילוץ-דרישות והפקת-הצעות; "cuts quote preparation time from hours to minutes".
  · מקור: https://www.neenopal.com/ai-solutions/ai-powered-rfq-automation · סוג: נמצא-במקור · ביטחון בינוני, טרי
  · הערה (מוסק): ממוקד ייצור/הנדסה (חילוץ משרטוטים), לא קבלן/מעצב-פנים — חופף חלקית בלבד.

- **AutoRFP.ai** — "better serves small-to-medium businesses that want streamlined document workflows"; כלי RFQ ל-SMB.
  · מקור: https://autorfp.ai/blog/best-rfq-software · סוג: נמצא-במקור · ביטחון בינוני, טרי (מדריך 2026)

### מתחרים עקיפים (חילוץ-חשבוניות AP — לא השוואת-הצעות, אבל אותו core של חילוץ-שדות)

- **Lido** — קולט חשבוניות מהמייל, מחלץ נתונים מובנים "with 99.9% accuracy", ללא תבניות; מ-$29/חודש ל-100 עמודים.
  · מקור: https://www.lido.app/blog/best-invoice-automation-software · סוג: נמצא-במקור · ביטחון בינוני (טענת-ספק, לא benchmark ניטרלי), טרי
- **Docsumo / Stampli / BILL / Tipalti** — פלטפורמות חילוץ-חשבוניות מובילות ל-AP; חופפות ב-core של "AI מחלץ שדות ממסמך פיננסי" אבל מכוונות accounts-payable, לא להחלטת-קנייה בין כמה ספקים.
  · מקור: https://www.stampli.com/blog/invoice-processing/invoice-processing-software/ · סוג: נמצא-במקור · ביטחון בינוני, טרי (מדריך 2025)

### זווית ישראל / עברית

- **Build App (build-app.co.il)** — תוכן ישראלי על "השוואת הצעות מחיר לספקים" + ניהול מאגר-ספקים; מתחרה-תוכן/כלי בעברית, אך נראה ניהול-ספקים ולא חילוץ-AI אוטומטי.
  · מקור: https://www.build-app.co.il/ · סוג: נמצא-במקור · ביטחון נמוך (לא אומת שיש חילוץ-AI), טרי
- **REV / automateai.co.il** ו-**"תיקתוק הצעות מחיר"** (App Store IL) — כלים ישראליים סביב **הפקת** הצעות-מחיר (צד-המוכר), לא **חילוץ והשוואת** הצעות נכנסות (צד-הקונה).
  · מקור: https://automateai.co.il/rev-features/quote-management-system/ · https://apps.apple.com/il/app/id1629306493 · סוג: נמצא-במקור · ביטחון נמוך, טרי
- **SAP Ariba / SAP Business AI / Keelvar** — אנטרפרייז S2P, מחוץ לקהל ה-SMB הלא-טכני.
  · מקור: https://www.sap.com/israel/products/spend-management/ai-for-procurement.html · סוג: נמצא-במקור · ביטחון בינוני, טרי

**הזדמנות (מוסק, ביטחון בינוני):** שום מתחרה שנמצא לא משלב את שלושת המאפיינים יחד — (א) השוואת הצעות נכנסות לצד-הקונה, (ב) קהל SMB לא-טכני (קבלן/מעצב-פנים), (ג) עברית/RTL ילידי. ה-RTL+עברית הוא חפיר אמיתי מול Quotable/NeenOpal.

---

## עדשה 2 · מוסכמת-תחום — text-layer מקומי מול שליחה ל-LLM/OCR

זו ההחלטה האדריכלית של T-0042, והיא **מאומתת כמוסכמת-תחום מקובלת**, עם הסתייגות אחת חשובה.

- **הדפוס "native text first, OCR/vision fallback" הוא הסטנדרט בפרודקשן.** מימוש טיפוסי: ניסיון-חילוץ ראשון עם native text extraction (pdfplumber), ואם הטקסט דליל/נכשל — fallback ל-OCR (Tesseract). בדיוק שכבת-העל של T-0042.
  · מקור: https://www.cradl.ai/posts/llm-ocr · סוג: נמצא-במקור · ביטחון גבוה, טרי
- **virtido (Document Intelligence guide, פבר' 2026)** מאשר במפורש: "Extract text first using OCR or PDF text extraction, then use an LLM to structure... Lower cost per document". טקסט-תחילה = זול-יותר, מומלץ ל-text-heavy/simple-layout.
  · מקור: https://virtido.com/blog/document-intelligence-llm-extraction-guide · סוג: נמצא-במקור · ביטחון גבוה, טרי (אומת 2026-06-25)
- **המוסכמה היא "format-aware routing", לא סדר-קשיח אחד.** ההמלצה: "match your pipeline to your specific document types rather than following one universal order" — טקסט-תחילה למסמכים פשוטים, vision למורכבים/מושחתים.
  · מקור: https://virtido.com/blog/document-intelligence-llm-extraction-guide · סוג: נמצא-במקור · ביטחון גבוה, טרי

**הסתייגות מהותית (נמצא-במקור, ביטחון בינוני-גבוה):** text-layer-first חוסך עלות אבל **מאבד יחסים-מרחביים** (קואורדינטות/מיקום-בטבלה). Vellum ממליצה ל-hybrid בחשבוניות: "OCR for headers, LLMs for line items". כלומר: עבור טבלת-השוואה (מחיר/אספקה/מע"מ) שמסתמכת על מבנה-טבלאי, text-layer גולמי לבדו עלול לפספס קישור-שדות. כדאי שלב-החוקים ישמר רמז-מבני (מיקום-שורה), לא טקסט-שטוח.
· מקור: https://www.vellum.ai/blog/document-data-extraction-llms-vs-ocrs · סוג: נמצא-במקור · ביטחון בינוני-גבוה, טרי (אומת 2026-06-25)

**מסקנת-העדשה:** הכיוון של T-0042 (text-layer מקומי → AI-זול-על-טקסט → תמונה fallback) תואם best-practice מקובל, וגם מרוויח יתרון-פרטיות שהתעשייה מכירה כסיבה לגיטימית. הסיכון היחיד למקד עליו: שמירת-מבנה לטבלת-ההשוואה.

---

## עדשה 3 · benchmarks חיצוניים לעיגון מדדים ⚠️

### (א) דיוק-חילוץ (field-extraction accuracy)

- **טווח-תחום מצופה: ~85-95% למסמכים מובנים-היטב** ("typically 85-95% for well-structured documents, lower for handwritten or degraded scans"; ובשדות-מבנה כמו תאריך/סכום — "90-98%").
  · מקור: https://virtido.com/blog/document-intelligence-llm-extraction-guide · סוג: נמצא-במקור · ביטחון גבוה, טרי (אומת 2026-06-25)
- **מודלים מובילים (2025): o4-mini ≈ 95.0%; o3 ≈ 96.33%.** Claude Sonnet 3.5 = "highest overall accuracy and resilience" בבנצ'מרק-חשבוניות.
  · מקור (o4-mini/o3): https://www.businesswaretech.com/blog/research-ai-models-invoice-processing-benchmark · סוג: נמצא-במקור · **ביטחון בינוני** (מספר מסיכום-חיפוש, לא נקרא בגוף-העמוד) · לאמת לפני ציטוט-פומבי.
  · מקור (Claude Sonnet): https://aimultiple.com/invoice-ocr · סוג: נמצא-במקור · ביטחון בינוני-גבוה, טרי (עודכן ינו' 2026)
- **OCR מסורתי מגיע ~99% רק על מסמכים אחידים-לחלוטין** (טפסים קבועים) — לא על הצעות-מחיר חופשיות.
  · מקור: https://www.vellum.ai/blog/document-data-extraction-llms-vs-ocrs · סוג: נמצא-במקור · ביטחון גבוה, טרי
- מתודולוגיית-מדידה לעיגון: **Field Accuracy** (אחוז-שדות-נכונים) + **Document Accuracy** (אחוז-מסמכים שכל-שדה בהם נכון).
  · מקור: https://aimultiple.com/invoice-ocr · סוג: נמצא-במקור · ביטחון גבוה, טרי

**עיגון ל-PriceMatch (מוסק, ביטחון בינוני):** יעד-דיוק סביר מול התחום ≈ **90-95% field-accuracy על PDF טקסטואלי נקי** (החלק שטקסט-תחילה אמור לכסות), עם הכרה שאיכות-נמוכה/תמונה תוריד. לדווח גם Document-Accuracy, כי החלטת-קנייה דורשת שכל השדות הקריטיים (מחיר, מע"מ) נכונים בו-זמנית.

### (ב) טווח-עלות לחילוץ (מול ה-baseline ~$0.0003/חילוץ)

- **Gemini Flash 2.0 ≈ $1.67 ל-10,000 עמודים → ~$0.000167/עמוד** ("6000 pages for just $1"). ה-baseline שלכם (~$0.0003/חילוץ) **תואם את סדר-הגודל** של Gemini Flash — אתם כבר בקצה-הזול.
  · מקור: https://www.vellum.ai/blog/document-data-extraction-llms-vs-ocrs · סוג: נמצא-במקור · ביטחון גבוה, טרי (אומת 2026-06-25)
- **טבלת-עלות (10,000 עמ'):** Gemini Flash 2.0 ≈ $1.67 · Google Document AI $20-50 · GPT-4 Vision ≈ $50-100 · OCR-מסורתי מורשה $5,000-20,000+.
  · מקור: https://www.vellum.ai/blog/document-data-extraction-llms-vs-ocrs · סוג: נמצא-במקור · ביטחון גבוה, טרי
- **vision-LLM טיפוסי: $0.01-0.10+/עמוד** — ה-fallback-לתמונה יקר פי ~30-300 משכבת-הטקסט. מאשש כלכלית את סדר-העדיפויות (תמונה אחרונה).
  · מקור: https://virtido.com/blog/document-intelligence-llm-extraction-guide · סוג: נמצא-במקור · ביטחון גבוה, טרי
- **עוגן-בקרה (מוסק):** עיבוד-חשבונית ידני ≈ $23/חשבונית — כל מסלול-AI זול ממנו בסדרי-גודל.
  · מקור: https://aimultiple.com/invoice-ocr · סוג: נמצא-במקור · ביטחון בינוני, טרי

**מסקנה כלכלית:** ה-baseline כבר אופטימלי בסדר-הגודל; ה-ROI של T-0042 אינו בעיקר חיסכון מול Gemini Flash (כבר זול), אלא ב**הסטת חלק-הארי של החילוצים לשכבת-החוקים החינמית + צמצום חשיפת-תוכן-רגיש** — שני אלה מחוץ-לעלות-ה-API, ולכן ה-baseline לבדו לא מודד אותם.

---

## עדשה 4 · מגמה (2025-2026)

- **המגמה הדומיננטית 2026 = pipelines היברידיים**, לא LLM-טהור ולא OCR-טהור ("Most production pipelines in 2026 don't use pure LLM or pure OCR"). מאשר את text-first+fallback של T-0042 ככיוון נכון-לזמן.
  · מקור: https://parsli.co/blog/llm-ocr-vs-traditional-ocr · https://www.vellum.ai/blog/document-data-extraction-llms-vs-ocrs · סוג: נמצא-במקור · ביטחון גבוה, טרי
- **תת-מגמה נגדית: "OCR-free / image-native"** — דחיפה לשלוח תמונת-עמוד ישירות ל-VLM כדי לעקוף הצטברות-שגיאות-OCR; VLMs מובילים על מסמכים מורכבים.
  · מקור: https://parsli.co/blog/llm-ocr-vs-traditional-ocr · סוג: נמצא-במקור · ביטחון בינוני-גבוה, טרי (2026)
  · **השלכה (מוסק, ביטחון בינוני):** "text-first/local-first" נתמך ככיוון-עלות-ופרטיות, אבל זרם-מתחרה ("שלח-הכל-ל-VLM") מרוויח מ-fallback-לתמונה זול-ומדויק יותר. כלומר שכבת-התמונה שלכם מתייעלת עם הזמן — לא "חוב". אבל המיצוב "מקומי-תחילה לפרטיות" הוא שמבדל מזרם-ה-VLM-לכל.
- **מניע-שוק לטקסט-תחילה: פרטיות** — צמצום-חשיפה ל-LLM-חיצוני, בדיוק היעד השלישי של T-0042.
  · מקור: https://virtido.com/blog/document-intelligence-llm-extraction-guide · סוג: מוסק · ביטחון בינוני, טרי

---

## מה לא נמצא / לא אומת

- **מספר-דיוק ייחודי לעברית/RTL** — לא נמצא benchmark חילוץ בעברית. כל המספרים (85-95%, 95-96%) על קורפוסים אנגליים. ייתכן ש-RTL/עברית מוריד דיוק; לא אומת. **פער-ידע אמיתי שכדאי למדוד פנימית.**
- **דיוק/עלות ספציפי של Quotable AI או NeenOpal** — אין מספרים ציבוריים מאומתים; "99.9%" של Lido = שיווק-ספק, לא benchmark ניטרלי (ביטחון-נמוך).
- **האם קיים מתחרה ישראלי שעושה חילוץ-AI + השוואת-הצעות נכנסות** — לא אומת. Build App/REV/"תיקתוק" נראים ניהול-ספקים או הפקת-הצעות. גוף-העמוד של Build App לא נקרא בעומק → ההפרדה ישיר/עקיף שם בביטחון-נמוך.
- **מספר-דיוק נקודתי לשכבת-text-layer-בלבד (ללא AI)** — התחום מדבר על pipelines משולבים; אין מספר מבודד ל"כמה-אחוז נסגרים בחוקים-בלבד". תלוי-קורפוס — **כדאי למדוד פנימית מהפיילוט.**
- **aimultiple לא חשף אחוזי-דיוק לכלי-בודד** בגוף-העמוד; מספרי o4-mini/o3 הגיעו מסיכום-חיפוש (businesswaretech) שלא נקרא ישירות → ביטחון-בינוני, לאמת לפני ציטוט-פומבי.

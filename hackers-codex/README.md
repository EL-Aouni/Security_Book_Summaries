# The Hacker's Codex — Modern Web Application Attacks Demystified
**By Brandon — 173 pages**

>  Personal study summary/resume written after reading the full book. Shared for learning purposes.

---

## 🇬🇧 English Summary

### What this book is about
Told through the lens of a fictional financially-motivated attacker ("Yuri"), the book argues that real-world criminals don't chase glamorous RCEs — they chase high-volume, low-effort, **client-side** bugs that security teams routinely rate "low/informational" and never fix, because these bugs scale to thousands of victims, evade blue-team detection, and monetize fast.

### Section-by-section

| Section | Topics | What you learn |
|---|---|---|
| **1 — Low-severity bugs that aren't** | HTML injection, host header injection, SSN enumeration | How "informational" findings (reflected HTML in emails, attacker-controlled Host headers, client-side lockouts/encryption) become real identity-theft and account-takeover attacks at scale. |
| **2 — Cross-Origin Attacks** | CORS misconfigurations, origin-reflection, regex bypasses, subdomain takeover, CSRF, CSRF bypasses, clickjacking (drag-and-drop), open/local redirects | Deep dive into how the Same-Origin Policy gets relaxed incorrectly, and how attackers chain CORS + subdomain takeover + CSRF to exfiltrate authenticated data or force state changes. |
| **3 — Client-Side Injection** | XSS (WAF-bypass mindset), XSS polyglots, JSONP callback leakage, language-specific XSS (ASP.NET `ResolveUrl`), SOME attacks, CSV/formula injection | How flexible JavaScript grammar defeats blacklist-based filters, why polyglot payloads matter for fast pentests, and how unsanitized exports become remote-code-execution via Excel formulas. |
| **4 — Advanced/Recent Research** | HTTP Request Smuggling (CL.TE/TE.CL desync), Web Cache Poisoning | James Kettle's research on front-end/back-end parsing mismatches and "unkeyed input" cache poisoning — turning unexploitable self-XSS into mass attacks with zero victim interaction. |

### Key takeaway
Three defensive principles to remember: (1) never put security controls client-side; (2) never trust reflected/attacker-supplied data without strict allowlisting; (3) "low severity" doesn't mean "low impact" — the bugs criminals actually weaponize are exactly the ones your scanner flags as boring.

---

## 🇸🇦 الملخص بالعربية

### عن ماذا يتحدث الكتاب
مرويّ من منظور مهاجم خيالي بدافع مادي ("يوري")، الكتاب كيوضح أن المجرمين الحقيقيين ما كيقلبوش على ثغرات RCE فخمة — كيقلبوا على ثغرات **من جهة العميل** بسيطة وسهلة وقابلة للتوسع، اللي فرق الأمن عادة كيصنفوها "منخفضة الخطورة" وما كيصلحوهاش، حيت كتضرب آلاف الضحايا وكتدر فلوس بسرعة.

### ملخص الأقسام

| القسم | المواضيع | شنو غادي تتعلم |
|---|---|---|
| **1 — ثغرات "بسيطة" فالظاهر** | حقن HTML، حقن Host Header، تخمين SSN | كيفاش نتائج "معلوماتية" (HTML منعكس فالإيميلات، هيدر Host متحكم فيه، أقفال/تشفير من جهة العميل) كتتحول لهجمات سرقة هوية حقيقية. |
| **2 — هجمات Cross-Origin** | أخطاء CORS، Origin Reflection، تخطي regex، Subdomain Takeover، CSRF وتخطياتو، Clickjacking، Open/Local Redirects | فهم عميق لكيفاش سياسة Same-Origin كترتخي بشكل خاطئ، وكيفاش المهاجمين كيدمجو CORS + Subdomain Takeover + CSRF. |
| **3 — حقن من جهة العميل** | XSS (عقلية تخطي WAF)، XSS Polyglots، تسريب JSONP، XSS خاصة بلغة (ASP.NET)، هجمات SOME، حقن CSV | كيفاش مرونة JavaScript كتهزم الفلاتر، وكيفاش التصدير الغير مصفى كيتحول لتنفيذ كود عن بعد عبر صيغ Excel. |
| **4 — أبحاث متقدمة ومؤخرة** | HTTP Request Smuggling، Web Cache Poisoning | بحث James Kettle على تضارب التحليل بين الواجهة الأمامية والخلفية، وتسميم الكاش عبر "unkeyed input". |

### الخلاصة
ثلاث مبادئ دفاعية: (1) عمرك ما تحط ضوابط أمنية من جهة العميل؛ (2) عمرك ما تثق فمعطيات المهاجم بلا whitelist صارمة؛ (3) "خطورة منخفضة" ما كتعنيش "تأثير منخفض".

# The Hacker Playbook 3 — Practical Guide to Penetration Testing (Red Team Edition)
**By Peter Kim (Secure Planet LLC, 2018) — 264 pages**

> 📖 Personal study summary/resume written after reading the full book. Shared for learning purposes — go buy the original if this is useful to you.

---

## 🇬🇧 English Summary

### What this book is about
Written as a running American-football metaphor (each chapter is a "play"), THP3 is the most **end-to-end, operationally-focused** book of the set. It shifts the series' focus from classic penetration testing to full **Red Team engagements** against a fictional target company, "Cyber Space Kittens" (CSK), used as a running lab throughout. Unlike the other books, it leans heavily on orchestrating existing frameworks (Metasploit, Cobalt Strike, PowerShell Empire, Responder, BloodHound, CrackMapExec) rather than writing tools from scratch — because a real red team engagement is about efficient tradecraft, not reinventing wheels.

### Chapter-by-chapter

| # | "Play" | What it covers |
|---|--------|-----------------|
| **Intro** | — | Clarifies the **Red Team vs. Penetration Testing** distinction — scope, objectives, and mindset differences that shape everything that follows. |
| 1 | **Pregame – The Setup** | Planning an assumed-breach campaign, building external C2 infrastructure, and a survey of the red-team tooling landscape: Metasploit, Cobalt Strike, PowerShell Empire, dnscat2, p0wnedShell, Pupy, PoshC2, Merlin, Nishang. |
| 2 | **Before the Snap – Red Team Recon** | Continuous environment monitoring (Nmap diffing, web screenshotting at scale, cloud asset scanning), network/service search engines (Shodan/Censys-style), SSL certificate parsing for subdomain discovery, GitHub recon, and email/OSINT gathering. |
| 3 | **The Throw – Web Application Exploitation** | A full modern web-attack arsenal against the CSK "Chat Support" lab: XSS (reflected/blind/DOM, advanced Node.js XSS), NoSQL injection, insecure deserialization, template injection (SSTI), SSRF, XXE and out-of-band XXE. |
| 4 | **The Drive – Compromising the Network** | The core of the book. Finding leaked credentials externally; Responder/MultiRelay for NTLM relay attacks with no initial creds; CrackMapExec for network-wide scanning; dumping cleartext creds from memory and browsers; Active Directory abuse (SPNs, BloodHound/SharpHound mapping); lateral movement via process migration, DCOM, and Pass-the-Hash; dumping the Domain Controller; and a parallel Linux pivoting/privesc track. |
| 5 | **The Screen – Social Engineering** | Building phishing campaigns: doppelganger domains, cloning auth pages (including capturing 2FA-protected creds), malicious Office macro and DDE (non-macro) payloads, encrypted payload delivery, and a case study phishing internal Jenkins. |
| 6 | **The Onside Kick – Physical Attacks** | Hardware implants for on-site engagements: card-reader cloners, the LAN Turtle, Packet Squirrel, and the Bash Bunny (including its QuickCreds and BunnyTap payloads), plus WiFi attacks. |
| 7 | **The Quarterback Sneak – Evading AV and Network Detection** | Writing custom droppers and keyloggers from source, obfuscation techniques, recompiling Metasploit/Meterpreter to dodge signature detection, SharpShooter, application-whitelisting bypasses, code caves, and PowerShell obfuscation (including "PowerShell without powershell.exe"). |
| 8 | **Special Teams – Cracking, Exploits, and Tricks** | Automating Metasploit/Empire/Cobalt Strike with resource scripts, efficient mass password cracking, disabling PowerShell logging, local-admin-to-SYSTEM escalation, and extracting NTLM hashes without touching LSASS (to dodge EDR). |
| 9 | **Two-Minute Drill – From Zero to Hero** | A condensed, speed-run version of the entire attack chain — useful as a cheat-sheet when time is short on an engagement. |
| 10 | **Post Game Analysis – Reporting** | How to actually write a red-team report that gets taken seriously and drives remediation — the unglamorous but critical final step most books skip. |

### Key takeaway
This book is less about any single novel technique and more about **operational tradecraft**: how a real red team plans, scopes, tools up, and chains together recon → initial access → AD domain compromise → persistence → reporting as one continuous campaign rather than a list of disconnected tricks.

---

## 🇸🇦 الملخص بالعربية

### عن ماذا يتحدث الكتاب
مكتوب بأسلوب استعارة كرة القدم الأمريكية (كل فصل هو "لعبة")، THP3 هو أكثر كتاب **شامل وعملي** فهاد المجموعة. كيحول تركيز السلسلة من اختبار الاختراق الكلاسيكي إلى عمليات **Red Team** كاملة ضد شركة خيالية، "Cyber Space Kittens" (CSK)، مستعملة كمختبر طول الكتاب. بخلاف الكتب الأخرى، كيعتمد بزاف على تنسيق أطر جاهزة (Metasploit، Cobalt Strike، PowerShell Empire، Responder، BloodHound، CrackMapExec) بدل كتابة أدوات من الصفر — حيت عملية red team حقيقية هي قبل كلشي كفاءة فالتنفيذ، ماشي إعادة اختراع العجلة.

### ملخص الفصول

| # | "اللعبة" | شنو كيغطي |
|---|---------|-----------|
| **مقدمة** | — | توضيح الفرق بين **Red Team واختبار الاختراق** — النطاق، الأهداف، والعقلية. |
| 1 | **Pregame – الإعداد** | تخطيط حملة assumed-breach، بناء بنية تحتية خارجية للـ C2، واستعراض أدوات red team: Metasploit، Cobalt Strike، PowerShell Empire، dnscat2، وغيرها. |
| 2 | **Before the Snap – استطلاع Red Team** | مراقبة مستمرة للبيئة (Nmap diffing، لقطات شاشة للمواقع، فحص أصول السحابة)، محركات بحث الشبكة/الخدمات، تحليل شهادات SSL لاكتشاف subdomains، استطلاع GitHub، وجمع OSINT/إيميلات. |
| 3 | **The Throw – استغلال تطبيقات الويب** | ترسانة هجمات ويب حديثة ضد مختبر CSK: XSS (reflected/blind/DOM)، حقن NoSQL، deserialization غير آمن، SSTI، SSRF، XXE. |
| 4 | **The Drive – اختراق الشبكة** | جوهر الكتاب. إيجاد بيانات اعتماد مسربة خارجيًا؛ Responder/MultiRelay لهجمات NTLM relay بلا بيانات اعتماد أولية؛ CrackMapExec للفحص الشامل؛ استخراج بيانات اعتماد من الذاكرة والمتصفحات؛ استغلال Active Directory (SPNs، BloodHound)؛ الحركة الجانبية عبر DCOM وPass-the-Hash؛ تفريغ Domain Controller؛ ومسار موازي لـ Linux. |
| 5 | **The Screen – الهندسة الاجتماعية** | بناء حملات تصيد: دومينات مزيفة شبيهة، استنساخ صفحات تسجيل دخول (حتى مع 2FA)، ماكروهات Office خبيثة وDDE، تسليم حمولات مشفرة. |
| 6 | **The Onside Kick – هجمات فيزيائية** | أدوات هاردوير للعمليات الميدانية: مستنسخات بطاقات، LAN Turtle، Packet Squirrel، Bash Bunny، وهجمات WiFi. |
| 7 | **The Quarterback Sneak – تخطي مضادات الفيروسات والشبكة** | كتابة droppers وkeyloggers مخصصة، تقنيات التشويش، إعادة تجميع Metasploit/Meterpreter لتفادي الكشف، تخطي application whitelisting، وتشويش PowerShell. |
| 8 | **Special Teams – الكراكينج والاستغلالات والحيل** | أتمتة Metasploit/Empire/Cobalt Strike، كسر كلمات السر بكفاءة، تعطيل تسجيل PowerShell، تصعيد من local admin لـ SYSTEM، واستخراج NTLM hashes بدون لمس LSASS. |
| 9 | **Two-Minute Drill – من الصفر للبطولة** | نسخة مختصرة وسريعة من كامل سلسلة الهجوم — مفيدة كورقة غش ملي الوقت قصير. |
| 10 | **Post Game Analysis – التقرير** | كيفاش تكتب تقرير red team ياخدوه بجدية ويدفع للإصلاح — الخطوة الأخيرة المهمة اللي أغلب الكتب كتهملها. |

### الخلاصة
هاد الكتاب ماشي غير على تقنية واحدة جديدة — هو على **الحرفية العملية**: كيفاش فريق red team حقيقي كيخطط، كيحدد النطاق، كيجهز الأدوات، وكيربط الاستطلاع ← الوصول الأولي ← اختراق Active Directory ← الاستمرارية ← التقرير كحملة واحدة متواصلة، ماشي لائحة حيل منفصلة.

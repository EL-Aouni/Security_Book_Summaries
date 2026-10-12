# Black Hat Python — Python Programming for Hackers and Pentesters
**By Justin Seitz (No Starch Press, 2014) — 193 pages**

> 📖 Personal study summary/resume written after reading the full book. Shared for learning purposes — go buy the original if this is useful to you. Note: this is the classic 1st edition (2014); a 2nd edition updated for Python 3 exists and covers slightly different tooling.

---

## 🇬🇧 English Summary

### What this book is about
A hands-on, no-fluff guide to writing your *own* hacking tools in Python instead of only relying on other people's. The author (a senior researcher at Immunity, Inc.) is upfront that the code style here favors **speed of execution over elegance** — this is pentester code, written to get a job done under time pressure, not production software. The book moves from networking fundamentals to full Windows trojan development.

### Chapter-by-chapter

| # | Chapter | What you learn |
|---|---------|-----------------|
| 1 | **Setting Up Your Python Environment** | Getting a working dev setup (Kali + WingIDE recommended for its debugger), including how to actually use breakpoints and the Debug Probe to inspect variables mid-execution — a skill most "hacking" books skip. |
| 2 | **The Network: Basics** | Core `socket` programming: TCP clients/servers, a UDP client, and building your own **netcat clone with a command shell** — the foundation for everything that follows. |
| 3 | **The Network: Raw Sockets and Sniffing** | Writing a cross-platform (Windows/Linux) packet sniffer from raw sockets, then decoding IP and ICMP headers by hand with `ctypes` to build a simple host/OS discovery tool. |
| 4 | **Owning the Network with Scapy** | Using the Scapy library to do in a few lines what took 100+ lines of raw-socket code in Chapter 3 — e.g., sniffing stored credentials (FTP/email) and ARP-cache poisoning. |
| 5 | **Web Hackery** | Building your own custom web-app attack tooling: a simple open-source web app mapper, a bruteforcer for login forms, and a directory/file content-discovery tool. |
| 6 | **Extending Burp Proxy** | Writing Burp Suite extensions in Python (via Jython) — a custom fuzzing payload generator and a bing/search-based content discovery plugin that runs directly inside Burp. |
| 7 | **Github Command and Control** | Building a trojan that uses a **private GitHub repository as its C2 channel** — pulling task config/commands from repo files instead of talking to your own infrastructure directly, which is stealthier and resilient. |
| 8 | **Common Trojaning Tasks on Windows** | Core trojan functionality: keylogging, taking screenshots, running shellcode via `ctypes`, and basic sandbox/VM detection to avoid executing inside an analyst's sandbox. |
| 9 | **Fun with Internet Explorer** | Using Windows COM automation to control Internet Explorer programmatically — hiding malicious browsing activity behind a legitimate, whitelisted process, and exfiltrating data via IE itself. |
| 10 | **Windows Privilege Escalation** | Automating detection of common Windows privesc opportunities (weak file/service permissions) and chaining them into actual privilege escalation from a compromised low-priv foothold. |
| 11 | **Automating Offensive Forensics** | Using the Volatility memory-forensics framework programmatically to automate artifact extraction from memory dumps — useful both offensively (automation) and defensively (incident response). |

### Key takeaway
The book's real lesson isn't any single exploit — it's the **mindset of writing disposable, task-specific tools quickly** rather than depending entirely on existing frameworks. Even though some APIs referenced are dated (2014-era Windows/IE), the patterns — raw sockets, ctypes-based Windows API calls, Burp extensibility, memory forensics automation — remain directly applicable today.

---

## 🇸🇦 الملخص بالعربية

### عن ماذا يتحدث الكتاب
دليل عملي مباشر لكتابة أدوات اختراق خاصة بك بلغة Python بدل الاعتماد الكلي على أدوات الآخرين. المؤلف (باحث أول فشركة Immunity) كيوضح من البداية أن أسلوب الكود هنا كيفضل **السرعة فالتنفيذ على الأناقة** — هادا كود مختبر اختراق، مكتوب باش يخدم تحت ضغط الوقت، ماشي سوفتوير جاهز للإنتاج. الكتاب كيمشي من أساسيات الشبكات حتى تطوير تروجان كامل لـ Windows.

### ملخص الفصول

| # | الفصل | شنو غادي تتعلم |
|---|------|-----------------|
| 1 | **إعداد بيئة Python** | إعداد بيئة تطوير شغالة (Kali + WingIDE مقترح لمصحح الأخطاء ديالو)، بما فيها استعمال نقاط التوقف (breakpoints) وفحص المتغيرات أثناء التنفيذ. |
| 2 | **الشبكة: الأساسيات** | برمجة `socket`: عملاء وسيرفرات TCP، عميل UDP، وبناء **نسخة خاصة من netcat مع شل أوامر**. |
| 3 | **الشبكة: Raw Sockets والتنصت** | كتابة متنصت حزم (sniffer) متعدد الأنظمة من raw sockets، وفك ترميز هيدرات IP وICMP يدويًا بـ `ctypes` لبناء أداة اكتشاف نظام تشغيل. |
| 4 | **السيطرة على الشبكة بـ Scapy** | استعمال مكتبة Scapy باش تدير بسطور قليلة اللي كان خاصو 100+ سطر من raw sockets — مثلا التنصت على بيانات اعتماد مخزنة (FTP/إيميل) وتسميم ARP cache. |
| 5 | **اختراق الويب** | بناء أدوات هجوم ويب خاصة: خريطة بسيطة لتطبيق ويب، أداة bruteforce لنماذج تسجيل الدخول، وأداة اكتشاف مجلدات/ملفات. |
| 6 | **توسيع Burp Proxy** | كتابة إضافات Burp Suite بـ Python (عبر Jython) — مولد payloads مخصص للـ fuzzing، وإضافة اكتشاف محتوى عبر البحث، تخدم مباشرة داخل Burp. |
| 7 | **تحكم وسيطرة عبر Github** | بناء تروجان كيستعمل **مستودع GitHub خاص كقناة C2** — سحب الأوامر من ملفات المستودع بدل التواصل مع بنية تحتية خاصة بيك مباشرة، وهادشي أكثر خفية وصمودًا. |
| 8 | **مهام التروجان الشائعة على Windows** | وظائف تروجان أساسية: تسجيل ضغطات لوحة المفاتيح، أخذ لقطات شاشة، تشغيل shellcode عبر `ctypes`، واكتشاف بيئة sandbox/VM باش ما يتنفذش عند محلل. |
| 9 | **المرح مع Internet Explorer** | استعمال أتمتة COM فـ Windows للتحكم فـ Internet Explorer برمجيًا — إخفاء نشاط تصفح خبيث خلف عملية شرعية موثوقة. |
| 10 | **تصعيد الصلاحيات فـ Windows** | أتمتة اكتشاف فرص تصعيد الصلاحيات الشائعة (صلاحيات ملفات/خدمات ضعيفة) وتسلسلها لتصعيد فعلي. |
| 11 | **أتمتة التحليل الجنائي الهجومي** | استعمال إطار Volatility لتحليل الذاكرة برمجيًا باش تؤتمت استخراج الأدلة من dumps الذاكرة — مفيدة هجوميًا ودفاعيًا. |

### الخلاصة
الدرس الحقيقي ديال الكتاب ماشي ثغرة معينة — هو **عقلية كتابة أدوات سريعة وخاصة بمهمة محددة** بدل الاعتماد الكلي على أطر جاهزة. رغم أن بعض الـ APIs قديمة شوية (Windows/IE ديال 2014)، الأنماط — raw sockets، استدعاءات Windows API بـ ctypes، توسيع Burp، أتمتة التحليل الجنائي — مازالت صالحة اليوم.

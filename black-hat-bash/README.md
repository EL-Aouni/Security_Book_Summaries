# Black Hat Bash — Creative Scripting for Hackers and Pentesters
**By Dolev Farhi & Nick Aleks (No Starch Press, 2025) — 347 pages**

> 📖 This is a personal study summary/resume, written after reading the full book. Shared for learning purposes — go buy the original book if this is useful to you.

---

## 🇬🇧 English Summary

### What this book is about
Most pentesting books focus on using tools like Nmap, Metasploit, or Burp Suite. *Black Hat Bash* instead teaches you to **build your own offensive tooling using nothing but the bash shell** — the one scripting language guaranteed to exist on nearly every Linux target you'll ever touch. The book walks through a full penetration test lifecycle (recon → exploitation → privilege escalation → persistence → lateral movement → exfiltration), re-implementing or orchestrating classic tooling as bash one-liners and scripts, inside a hands-on Kali + Docker lab the authors provide.

### Chapter-by-chapter

| # | Chapter | What you learn |
|---|---------|-----------------|
| 1 | **Bash Basics** | Shell fundamentals: variables, arrays, streams, redirection, exit codes, shebang, debugging (`bash -x`). The groundwork everything else builds on. |
| 2 | **Flow Control and Text Processing** | `if`/`case`, loops (`while`/`until`/`for`), functions, and the real workhorses of offensive bash: `grep`, `awk`, `sed` for parsing tool output. Also job control and `.bashrc` customization for pentesters (aliases, PATH tricks). |
| 3 | **Setting Up a Hacking Lab** | Building a safe, isolated Kali + Docker lab with a "public" and "corporate" network segment, plus installing extra tools (RustScan, Nuclei, dirsearch, LinEnum, pwncat, Gitjacker, etc.) and aliasing them for speed. |
| 4 | **Reconnaissance** | Scripting target-list generation (IP ranges, subdomain wordlists), host discovery (ping sweeps, Nmap, arp-scan), port scanning (Nmap/RustScan/Netcat), banner grabbing, and OS/service fingerprinting — all glued together with bash. |
| 5 | **Vulnerability Scanning and Fuzzing** | Automating Nikto scans, writing custom Nuclei templates, brute-forcing directories (dirsearch/ffuf/Wfuzz), and mining exposed `.git` repositories for secrets via `git log`. |
| 6 | **Gaining a Web Shell** | Exploiting arbitrary file upload flaws (bypassing extension/MIME filters), chaining them with directory traversal to stage a web shell, then building bash wrappers around OS command injection — including WAF/filter bypass tricks (encoding, globbing). |
| 7 | **Reverse Shells** | How reverse shells actually work (ingress vs. egress filtering), crafting and delivering payloads, upgrading to full TTYs (`python -c 'import pty'`, `socat`), encrypting shell traffic, and brute-forcing SSH for initial access. |
| 8 | **Local Information Gathering** | Post-exploitation recon: users/groups, processes, the OS, logs, cron jobs, storage, kernel version — essentially a scripted version of what tools like LinEnum do, so you understand what's happening under the hood. |
| 9 | **Privilege Escalation** | Linux permission models (SUID/SGID, ACLs, sticky bit), finding misconfigured files/binaries, and turning them into root shells. |
| 10 | **Persistence** | Backdooring services (SysV/systemd), hijacking PAM, planting rogue SSH keys, poisoning `.bashrc`/profile files, trojaning `sudo`, and building malicious DEB packages. |
| 11 | **Network Probing and Lateral Movement** | Pivoting from one compromised host deeper into a network: port forwarding, exploiting shared-volume cron jobs, attacking database/Redis/WordPress servers, and dumping exposed DB files. |
| 12 | **Defense Evasion and Exfiltration** | Understanding what you're up against (EDR, logging, honeypots), hiding processes (LD_PRELOAD, masquerading), tampering with shell history/logs, encoding/encrypting data for exfiltration. |

### Key takeaway
Bash isn't just "the shell you type commands into" — it's a legitimate, always-available offensive programming language. Learning to glue `grep`/`awk`/`sed`/`curl`/`nc` together fluently means you can operate effectively on a target even when you can't bring your usual toolkit with you (a very common real-world constraint in restricted/air-gapped environments).

---

## 🇸🇦 الملخص بالعربية

### عن ماذا يتحدث الكتاب
أغلب كتب اختبار الاختراق كترتكز على أدوات جاهزة بحال Nmap، Metasploit، أو Burp Suite. كتاب *Black Hat Bash* بالعكس كيعلمك **كيفاش تبني أدواتك الخاصة الهجومية بغير لغة bash** — اللغة الوحيدة اللي مضمونة موجودة فأي جهاز Linux غادي تلقاه. الكتاب كيمشي معاك على كامل دورة اختبار الاختراق (استطلاع ← استغلال ← تصعيد صلاحيات ← استمرارية ← حركة جانبية ← تسريب بيانات)، وكيعيد بناء الأدوات الكلاسيكية كسكريبتات bash، فمختبر Kali + Docker جاهز وفره المؤلفين.

### ملخص الفصول

| # | الفصل | شنو غادي تتعلم |
|---|------|-----------------|
| 1 | **أساسيات Bash** | أساسيات الشل: المتغيرات، المصفوفات، التدفقات (streams)، إعادة التوجيه، أكواد الخروج، الـ shebang، والتصحيح (`bash -x`). |
| 2 | **التحكم بالتدفق ومعالجة النصوص** | `if`/`case`، الحلقات (`while`/`until`/`for`)، الدوال، وأهم أدوات معالجة النصوص فالهجوم: `grep`، `awk`، `sed`. زائد التحكم فالمهام و تخصيص `.bashrc` لمختبري الاختراق. |
| 3 | **إعداد مختبر الاختراق** | بناء مختبر آمن ومعزول بـ Kali + Docker بشبكتين ("عمومية" و"شركة")، مع تثبيت أدوات إضافية (RustScan، Nuclei، dirsearch، LinEnum، pwncat...) وإعداد اختصارات ليهم. |
| 4 | **الاستطلاع** | سكريبتات لتوليد لوائح الأهداف (نطاقات IP، قوائم subdomains)، اكتشاف الأجهزة (ping، Nmap، arp-scan)، فحص البورتات (Nmap/RustScan/Netcat)، وأخذ بصمة الخدمة/نظام التشغيل — كلشي بالبash. |
| 5 | **فحص الثغرات والـ Fuzzing** | أتمتة فحوصات Nikto، كتابة قوالب Nuclei مخصصة، تخمين المجلدات (dirsearch/ffuf/Wfuzz)، واستخراج الأسرار من مستودعات `.git` المكشوفة عبر `git log`. |
| 6 | **الحصول على Web Shell** | استغلال ثغرات رفع الملفات (تخطي فلاتر الامتداد/MIME)، دمجها مع Directory Traversal لرفع web shell، وبناء غلاف bash حول حقن أوامر النظام — مع حيل لتخطي الـ WAF. |
| 7 | **Reverse Shells** | كيفاش كتخدم الـ reverse shells (الفرق بين ingress وegress)، صناعة وتوصيل payload، الترقية لـ TTY كامل، تشفير حركة الشل، وتخمين SSH للوصول الأولي. |
| 8 | **جمع المعلومات محليًا** | استطلاع بعد الاستغلال: المستخدمين، العمليات، نظام التشغيل، السجلات، مهام cron، التخزين — نسخة مسكربتة من اللي كتديرها أدوات بحال LinEnum. |
| 9 | **تصعيد الصلاحيات** | نماذج صلاحيات Linux (SUID/SGID، ACLs)، إيجاد ملفات/برامج معدة بشكل خاطئ، وتحويلها لصلاحيات root. |
| 10 | **الاستمرارية (Persistence)** | زرع backdoor فالخدمات، اختراق PAM، إضافة مفاتيح SSH مزيفة، تسميم ملفات `.bashrc`، وبناء حزم DEB خبيثة. |
| 11 | **فحص الشبكة والحركة الجانبية** | الانتقال من جهاز مخترق لعمق الشبكة: port forwarding، استغلال cron jobs على volumes مشتركة، مهاجمة سيرفرات قواعد البيانات/Redis/WordPress. |
| 12 | **تخطي الدفاعات وتسريب البيانات** | فهم أدوات الدفاع (EDR، السجلات، honeypots)، إخفاء العمليات، التلاعب بسجل الأوامر، تشفير البيانات قبل التسريب. |

### الخلاصة
Bash ماشي غير "شل كتكتب فيه أوامر" — هي لغة برمجة هجومية حقيقية ومتوفرة دائمًا. إتقان الربط بين `grep`/`awk`/`sed`/`curl`/`nc` كيخليك قادر تخدم بفعالية على الهدف حتى ملي ما تقدرش تجيب معاك الأدوات المعتادة ديالك.

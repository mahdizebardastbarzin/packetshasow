# PACKETSHADOW | پکِت‌شدو

## 🛡️ Security Awareness Tool | ابزار آگاهی امنیتی

PACKETSHADOW is a **completely educational and awareness-focused** network security tool designed to **better understand VPN behavior, internet connection status, DNS leaks, and network routing**. This project is **not a hacking or penetration tool** and performs no malicious operations.  
PACKETSHADOW یک ابزار **کاملاً آموزشی و آگاهی‌بخش** در حوزهٔ امنیت شبکه است که با هدف **درک بهتر رفتار VPN، وضعیت اتصال اینترنت، نشت DNS و مسیر شبکه** طراحی شده است. این پروژه **ابزار هک یا نفوذ نیست** و هیچ‌گونه عملیات مخرب انجام نمی‌دهد.

---

## 📌 Project Overview | معرفی پروژه

**PACKETSHADOW** analyzes your system's real internet connection status and clearly shows:  
**PACKETSHADOW** وضعیت واقعی اتصال اینترنت سیستم شما را تحلیل می‌کند و به زبان ساده نشان می‌دهد:

* Whether VPN is active or not | آیا VPN فعال است یا خیر
* Trust level of the connection | سطح اطمینان اتصال چقدر است
* DNS leak presence | آیا نشت DNS وجود دارد یا نه
* IPv6 status and possible leaks | IPv6 فعال است یا ممکن است باعث نشت شود
* Network traffic interfaces | ترافیک شبکه از چه اینترفیس‌هایی عبور می‌کند

The main goal is to **increase users’ security literacy** and understand the hidden risks of fake VPNs or misconfigured networks.  
هدف اصلی پروژه، **افزایش سواد امنیتی کاربران** و درک خطرات پنهان VPNهای جعلی یا تنظیمات نادرست شبکه است.

---

## ⚙️ Architecture | معماری برنامه

The program consists of **four main components**:  
این برنامه در اصل از **چهار بخش اصلی** تشکیل شده است:

### 1️⃣ Python Agent (Backend) | عامل پایتون (بک‌اند)

* Collect real network information (Local IP, Public IP, DNS, Interfaces)  
  جمع‌آوری اطلاعات واقعی شبکه (Local IP, Public IP, DNS, Interfaces)
* Smart VPN Detection | تشخیص هوشمند VPN
* DNS leak and IPv6 status check | بررسی نشت DNS و وضعیت IPv6
* Provide local API | ارائه API محلی

📄 Main file | فایل اصلی:

* `packetshadow.py`

---

### 2️⃣ HTML (User Interface) | HTML (رابط کاربری)

* Core UI structure | ساختار اصلی رابط کاربری
* Display statuses, texts, and sections | نمایش وضعیت‌ها، متن‌ها و بخش‌ها

📄 File | فایل:

* `index.html`

---

### 3️⃣ CSS (Design & Styling) | CSS (طراحی و استایل)

* Visual design | طراحی ظاهری
* Trust level color coding (Green, Yellow, Red) | رنگ‌بندی سطح اطمینان (سبز، زرد، قرمز)
* Animations and visual effects | انیمیشن‌ها و جلوه‌های بصری

📄 File | فایل:

* `style.css`

---

### 4️⃣ JavaScript (Logic & UI Update) | جاوااسکریپت (منطق و بروزرسانی رابط)

* Communicate with local API | ارتباط با API محلی
* Fetch live data from Agent | دریافت اطلاعات زنده از Agent
* Smart UI updates | بروزرسانی هوشمند رابط کاربری

📄 File | فایل:

* `app.js`

---

## 📦 Executable Version | نسخه اجرایی

For user convenience, the project is packaged as an **executable file**.  
برای راحتی کاربران، پروژه به **فایل اجرایی (Executable)** تبدیل شده است.

✅ In the executable version:  
در نسخه اجرایی:

* No need to install Python | نیازی به نصب Python نیست
* All files are internally managed | تمام فایل‌ها به‌صورت داخلی مدیریت می‌شوند
* User just runs the program | کاربر فقط برنامه را اجرا می‌کند

⚠️ No personal or real IP information is published in README or source.  
⚠️ هیچ اطلاعات شخصی یا آی‌پی واقعی داخل README یا سورس منتشر نمی‌شود.

---

## 🧠 Security Indicators Explained | توضیح مفاهیم امنیتی

### 🔐 VPN Status | وضعیت VPN

**VPN DETECTED / VPN روشن**  

Indicates that the system detects internet connection via VPN.  
یعنی سیستم تشخیص داده اتصال اینترنت از طریق VPN انجام می‌شود.

Safe? | امن است؟  

* Yes, IP masking is safer than direct connection.  
  بله، از نظر مخفی‌سازی آی‌پی نسبت به اتصال مستقیم امن‌تر است.

---

### 📊 Trust Level | سطح اطمینان

**High / Medium / Low**  

Result of combined analysis of:  
نتیجه تحلیل ترکیبی از:

* VPN status | وضعیت VPN
* DNS | DNS
* Network route | مسیر شبکه

Safe? | امن است؟  

* High → Secure connection | اتصال امن  
* Medium → Needs review | نیاز به بررسی  
* Low → Possible leak or invalid VPN | احتمال نشت یا VPN نامعتبر

---

### 🌍 Public IP Address | آی‌پی عمومی

The IP that websites see you with.  
آی‌پی‌ای که وب‌سایت‌ها شما را با آن می‌بینند.

⚠️ In this project | در این پروژه:

* Real user IP is not displayed | آی‌پی واقعی کاربر در README نمایش داده نمی‌شود
* Examples are purely educational | مثال‌ها صرفاً آموزشی هستند

Safe? | امن است؟  

* If VPN is active, this should not be your real IP | اگر VPN فعال باشد، این آی‌پی نباید آی‌پی واقعی شما باشد

---

### 🧪 DNS Leak Test | بررسی نشت DNS

**NO DNS LEAK / بدون نشت DNS**  

Means internet requests do not leave the VPN tunnel.  
یعنی درخواست‌های اینترنتی از تونل VPN خارج نشده‌اند.

Safe? | امن است؟  

* Yes, this is one of the most important indicators of a correct VPN | بله، این یکی از مهم‌ترین نشانه‌های امنیت درست VPN است.

---

### 🌐 DNS Servers | سرورهای DNS

Servers that convert domain names to IP addresses.  
سرورهایی که نام سایت‌ها را به آی‌پی تبدیل می‌کنند.

⚠️ Security note | نکته امنیتی:

* If VPN is on but local DNS (like router) is used, leaks may occur | اگر VPN روشن باشد ولی DNS محلی (مثل مودم) استفاده شود، احتمال نشت وجود دارد.

---

### 🧬 IPv6 Status | وضعیت IPv6

**IPv6 ENABLED / فعال**  

Safe? | امن است؟  

* If VPN does not support IPv6, it may cause IPv6 leaks | اگر VPN از IPv6 پشتیبانی نکند، ممکن است باعث IPv6 Leak شود.

---

### 🔌 VPN Interface | اینترفیس VPN

Shows active network cards (TAP, TUN, WireGuard).  
نمایش کارت‌های شبکه فعال (مثل TAP, TUN, WireGuard).

Safe? | امن است؟  

* Presence of TAP or TUN indicates a valid software VPN | وجود TAP یا TUN نشان‌دهنده VPN نرم‌افزاری معتبر است.

---

### 🧭 Network Route | مسیر شبکه

**Routing Table / جدول مسیر شبکه**  

Shows through which path internet packets travel.  
نشان می‌دهد بسته‌های اینترنتی از چه مسیری عبور می‌کنند.

Safe? | امن است؟  

* If the path goes through VPN interface, the connection is secure | اگر مسیر از اینترفیس VPN عبور کند، اتصال امن محسوب می‌شود.

---

## 🚨 Security Warning | هشدار امنیتی

This project:  
این پروژه:

* Is not a penetration tool | ابزار نفوذ نیست
* Does not send data to any server | اطلاعات را به هیچ سروری ارسال نمی‌کند
* Runs only locally on user system | فقط روی سیستم کاربر و به‌صورت محلی اجرا می‌شود

Any malicious use outside educational purpose is prohibited.  
هرگونه استفاده مخرب خارج از هدف آموزشی، ممنوع است.

---

## 🗺️ Roadmap | نقشه راه

* [ ] Advanced IPv6 Leak Detection | تشخیص پیشرفته IPv6 Leak  
* [ ] macOS & Linux GUI Support | پشتیبانی از macOS و Linux GUI  
* [ ] Export Security Reports | Export گزارش امنیتی  
* [ ] Educational Mode (Simulation) | حالت آموزشی (Simulation Mode)

---

## 📜 License | مجوز

This project is published **solely for educational, security awareness, and defensive analysis purposes**.  
این پروژه صرفاً برای **آموزش، آگاهی امنیتی و تحلیل دفاعی** منتشر شده است.

© Mahdi Zebardast Barzin

---

## ⭐ Final Note | نکته نهایی

PACKETSHADOW is made to **help users understand when it is safe and when it is not** — not to scare, but to raise awareness.  
PACKETSHADOW ساخته شده تا **کاربر بفهمد چه زمانی امن است و چه زمانی نیست** — نه برای ترساندن، بلکه برای آگاهی.

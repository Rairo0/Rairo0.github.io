---
title: "RE4B:Introduction_01"
date: 2025-10-01
categories: [Reverse, Books]
tags: [Reverse, RE4B, Basics]
image: /assets/img/posts/ch1/optimized.jpeg
---

### Source code can be compiled by different compilers with various optimization levels.

### General idea

<div dir="rtl" style="padding:12px 14px; margin:12px 0; border-radius:10px; border:1px solid rgba(148,163,184,.18); background:rgba(148,163,184,.05); line-height:1.9; color:#E5E7EB;">
نفس كود الـ<span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">C</span>
ممكن يطلع <span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">Assembly</span> مختلف حسب:<br>
1) نوع الـ<span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">compiler</span><br>
2) مستوى الـ<span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">optimization</span><br>
3) هل فيه <span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">debug info</span> ولا لا
</div>

### What does the optimization mean ?

<div dir="rtl" style="padding:12px 14px; margin:12px 0; border-radius:10px; border:1px solid rgba(148,163,184,.18); background:rgba(148,163,184,.05); line-height:1.9; color:#E5E7EB;">
الـ<span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">compiler</span>
مش بس بيترجم، ده كمان ممكن:<br>
- يعدل الكود<br>
- يشيل حاجات<br>
- يغير الترتيب<br><br>
علشان:<br>
- يخليه أسرع<br>
- أو أقل حجمًا
</div>

### optimization level

<div dir="rtl" style="padding:12px 14px; margin:12px 0; border-radius:10px; border:1px solid rgba(245,158,11,.22); background:rgba(245,158,11,.08); line-height:1.9; color:#E5E7EB;">
<b style="color:#FBBF24;">Optimization = 0</b><br>
غالبًا فيه 3 مستويات مشهورة، وأولهم ده.<br>
مفيش تعديل على الكود، فبيكون:<br>
- طويل وواضح وسهل الفهم<br>
- كل سطر <span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">C</span>
تقريبًا ليه <span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">Assembly</span> مقابل<br><br>
وده مفيد جدًا في:<br>
<b>التعليم – Debugging – Reverse</b>
</div>

### Other types of Optimization (O1 / O2 / O3)

<div dir="rtl" style="padding:12px 14px; margin:12px 0; border-radius:10px; border:1px solid rgba(148,163,184,.18); background:rgba(148,163,184,.05); line-height:1.9; color:#E5E7EB;">
الـ<span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">Compiler</span>
بيحاول:<br>
- يسرع البرنامج<br>
- يشيل أي كود ملوش لازمة<br><br>
<b>النتيجة:</b><br>
- كود <span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">Assembly</span> أقصر<br>
- بس أصعب في الفهم<br>
- سطور <span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">C</span> ممكن تختفي تمامًا
</div>

### Example C Code

```c
int x = 5;
```
<div dir="rtl" style="padding:12px 14px; margin:12px 0; border-radius:10px; border:1px solid rgba(148,163,184,.18); background:rgba(148,163,184,.05); line-height:1.9; color:#E5E7EB;"> لو <span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">x</span> مش مستخدم، هيتحذف بالكامل من النسخة الـ<span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">optimized</span>. </div>
Compiler speed
<div dir="rtl" style="padding:12px 14px; margin:12px 0; border-radius:10px; border:1px solid rgba(96,165,250,.22); background:rgba(96,165,250,.07); line-height:1.9; color:#E5E7EB;"> 1) بدون <span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">optimization</span>: الترجمة أسرع<br> 2) مع <span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">optimization</span>: الترجمة أبطأ<br> بس البرنامج النهائي أسرع </div>
Optimization for speed or size?
<div dir="rtl" style="padding:12px 14px; margin:12px 0; border-radius:10px; border:1px solid rgba(148,163,184,.18); background:rgba(148,163,184,.05); line-height:1.9; color:#E5E7EB;"> الـ<span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">compiler</span> ممكن يركز على:<br> 🔸 سرعة التنفيذ (<span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">performance</span>)<br> 🔸 صغر حجم الملف </div>
What does the Debug Code mean?
<div dir="rtl" style="padding:12px 14px; margin:12px 0; border-radius:10px; border:1px solid rgba(34,197,94,.18); background:rgba(34,197,94,.07); line-height:1.9; color:#E5E7EB;"> لو فعلت <span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">debug mode</span>، الملف الناتج هيبقى فيه:<br> - معلومات عن المتغيرات<br> - أسماء الدوال<br> - أرقام السطور<br><br> وفيه ربط مباشر:<br> سطر <span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">C</span> ↔ عنوان في الـ<span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">Assembly</span><br><br> وده بيخلي:<br> - الـ<span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">debugging</span> سهل<br> - والـ<span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">reversing</span> أسهل </div>
In the Optimized version
<div dir="rtl" style="padding:12px 14px; margin:12px 0; border-radius:10px; border:1px solid rgba(245,158,11,.22); background:rgba(245,158,11,.08); line-height:1.9; color:#E5E7EB;"> في النسخة الـ<span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">optimized</span>:<br> - مفيش ربط واضح بين كود الـ<span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">C</span> والـ<span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">Assembly</span><br> - سطور الـ<span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">C</span> ممكن تندمج أو تختفي<br> - ترتيب الكود بيتغير<br><br> وده الطبيعي في البرامج الحقيقية </div>
ليه دا مهم في الـReverse Engineering
<div dir="rtl" style="padding:12px 14px; margin:12px 0; border-radius:10px; border:1px solid rgba(148,163,184,.18); background:rgba(148,163,184,.05); line-height:1.9; color:#E5E7EB;"> مش كل البرامج متترجمة بنفس الطريقة.<br> ممكن تقابل:<br> - حاجة سهلة زي <span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">debug build</span><br> - حاجة صعبة زي <span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">release build</span><br><br> علشان كده لازم تتعود على الاتنين. </div>
وصلنا للخلاصة
<div dir="rtl" style="padding:12px 14px; margin:12px 0; border-radius:10px; border:1px solid rgba(96,165,250,.22); background:rgba(96,165,250,.07); line-height:1.9; color:#E5E7EB;"> في الكتاب بنستخدم <span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">compilers</span> قديمة علشان:<br> - تطلع <span style="direction:ltr; unicode-bidi:isolate; font-weight:600;">asm code</span> أبسط<br> - تقلل التشويش<br> - وتسهّل الشرح<br><br> وبكده يبقى فاضل شوية نظري وندخل على العملي. </div>

<div dir="rtl" style="padding:12px 14px; margin:12px 0; border-radius:10px; border:1px solid rgba(148,163,184,.18); background:rgba(148,163,184,.05); line-height:1.9; color:#E5E7EB;"> كل جديد هينزل على Discord </div>

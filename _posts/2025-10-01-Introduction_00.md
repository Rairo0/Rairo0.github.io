---
title: "RE4B:Introduction_00"
date: 2025-10-01
categories: [Reverse, Books]
tags: [Reverse, RE4B, Basics]
image: /assets/img/posts/ch1/kadar.jpeg
---

### Introduction_00

<div dir="rtl" style="padding:12px 14px; margin:12px 0; border-radius:10px; border:1px solid rgba(148,163,184,.18); background:rgba(148,163,184,.05); line-height:1.9; color:#E5E7EB;">
هنتكلم عن شوية حاجات أساسية في المجمل بالمختصر المفيد.
</div>

### الطريقة اللي مؤلف الكتاب ذاكر بيها

<div dir="rtl" style="padding:12px 14px; margin:12px 0; border-radius:10px; border:1px solid rgba(148,163,184,.18); background:rgba(148,163,184,.05); line-height:1.9; color:#E5E7EB;">
مفيش مصدر يعلمك كل حاجة أو طريقة ثابتة تمشي عليها عشان تذاكر.<br>
وده اللي انا شوفته عشان كل معلومة كانت من مصدر مختلف فعلا.<br><br>
ودلوقتي كل اللي عايزين نعرفه:<br>
أساسيات لغة الـ <span style="direction:ltr; unicode-bidi:isolate; display:inline-block; font-weight:600;">C</span>,
<span style="direction:ltr; unicode-bidi:isolate; display:inline-block; font-weight:600;">Assembly</span>
بعدين هنبقي نشوف الـ<span style="direction:ltr; unicode-bidi:isolate; display:inline-block; font-weight:600;">C++</span> (مش محتاجينها حاليا).
</div>

### المهم

<div dir="rtl" style="padding:12px 14px; margin:12px 0; border-radius:10px; border:1px solid rgba(245,158,11,.22); background:rgba(245,158,11,.08); line-height:1.9; color:#E5E7EB;">
<b style="color:#FBBF24;">مهم:</b>
لما توصل لإنك فاهم اساسيات كتابة كود <span style="direction:ltr; unicode-bidi:isolate; display:inline-block; font-weight:600;">C</span> و <span style="direction:ltr; unicode-bidi:isolate; display:inline-block; font-weight:600;">asm</span>،
ساعتها ابدأ اكتب <span style="direction:ltr; unicode-bidi:isolate; display:inline-block; font-weight:600;">C code</span> بسيط واعمله
<span style="direction:ltr; unicode-bidi:isolate; display:inline-block; font-weight:600;">Reverse</span>
وشوف ال<span style="direction:ltr; unicode-bidi:isolate; display:inline-block; font-weight:600;">asm code</span> بتاعه شكله ايه.
</div>

<div dir="rtl" style="padding:12px 14px; margin:12px 0; border-radius:10px; border:1px solid rgba(148,163,184,.18); background:rgba(148,163,184,.05); line-height:1.9; color:#E5E7EB;">
طيب كل دا كلام حلو نبدأ منين وازاي؟<br>
أول حاجة هنذاكر كورسين صغيرين.<br>
هنبدأ بالـ<span style="direction:ltr; unicode-bidi:isolate; display:inline-block; font-weight:600;">C</span>
وبعد ما نخلص جزئية كويسة منه نبدأ جنبه بالـ<span style="direction:ltr; unicode-bidi:isolate; display:inline-block; font-weight:600;">Assembly</span>.
</div>

<div dir="rtl" style="padding:12px 14px; margin:12px 0; border-radius:10px; border:1px solid rgba(96,165,250,.22); background:rgba(96,165,250,.07); line-height:1.9; color:#E5E7EB;">
<b>Courses:</b><br>
C Course:<br>
<a href="https://youtube.com/playlist?list=PLRtfJqT1hc31ZP4tr3ijypE_0T-4PE_kZ&si=511CjR3PBSTyDPqP"
   style="direction:ltr; unicode-bidi:isolate; display:inline-block; color:#60A5FA; text-decoration:none; border-bottom:1px solid rgba(96,165,250,.35);">
  https://youtube.com/playlist?list=PLRtfJqT1hc31ZP4tr3ijypE_0T-4PE_kZ&si=511CjR3PBSTyDPqP
</a><br><br>
ASM Course:<br>
<a href="https://youtube.com/playlist?list=PLMm8EjqH1EFVodghdDWaAuHkHqj-nJ0bN&si=stgUx5onhMKcEtPh"
   style="direction:ltr; unicode-bidi:isolate; display:inline-block; color:#60A5FA; text-decoration:none; border-bottom:1px solid rgba(96,165,250,.35);">
  https://youtube.com/playlist?list=PLMm8EjqH1EFVodghdDWaAuHkHqj-nJ0bN&si=stgUx5onhMKcEtPh
</a>
</div>

<div dir="rtl" style="padding:12px 14px; margin:12px 0; border-radius:10px; border:1px solid rgba(148,163,184,.18); background:rgba(148,163,184,.05); line-height:1.9; color:#E5E7EB;">
دول كراش كورس… فيما بعد انت محتاج تتعمق أكتر وتفهم <span style="direction:ltr; unicode-bidi:isolate; display:inline-block; font-weight:600;">programming</span> أكتر.<br>
بس وقت ما تخلصهم هتعرف تدور فين وتسأل مين.<br><br>
طيب عدي اسبوع أو اتنين وبدأت الدنيا توضح معاك شوية في اللغتين دول…<br>
هتروح لموقع:
<a href="https://godbolt.org/"
   style="direction:ltr; unicode-bidi:isolate; display:inline-block; color:#60A5FA; text-decoration:none; border-bottom:1px solid rgba(96,165,250,.35);">
  https://godbolt.org/
</a><br>
هتكتب فيه كود الـ<span style="direction:ltr; unicode-bidi:isolate; display:inline-block; font-weight:600;">C</span> هيتحول لـ<span style="direction:ltr; unicode-bidi:isolate; display:inline-block; font-weight:600;">Assembly</span>.<br>
مش لازم تفهم حاجة من أول مرة… ممكن التانية التالتة… ال15 عادي جدًا.<br>
هيساعدك تتعود على شكل كود <span style="direction:ltr; unicode-bidi:isolate; display:inline-block; font-weight:600;">asm</span> وتفهم معنى الأوامر لما تيجي ورا بعض.
</div>

### شوية ملاحظات بسيطة

<div dir="rtl" style="padding:12px 14px; margin:12px 0; border-radius:10px; border:1px solid rgba(245,158,11,.22); background:rgba(245,158,11,.08); line-height:1.9; color:#E5E7EB;">
<b style="color:#FBBF24;">نصيحة:</b>
متقرأش مقالتين ورا بعض غير لما تكون فهمت كل اللي في المقالة الأولي كويس.<br>
عشان متتشتتش وتحس إن الموضوع صعب لما تشوف حاجة جديدة انت مش فاهمها.
</div>

<div dir="rtl" style="padding:12px 14px; margin:12px 0; border-radius:10px; border:1px solid rgba(148,163,184,.18); background:rgba(148,163,184,.05); line-height:1.9; color:#E5E7EB;">
لو انت متعرفش حاجة من اللي اتكلمنا عليها فوق عامة… ممكن تسألني في أي حاجة والدنيا تبقى تمام إن شاء الله.<br>
المهم لو استفدت متنساش تدعيلي، وكل حاجة جديدة هتنزل على Discord.
</div>

![Gonoon El3azama](/assets/img/posts/ch1/Tafa.jpeg)

---
title: "CCNA Cables Type"
date: 2025-10-01
categories: [CCNA]
tags: [CCNA]
---

<style>
.ccna{direction:rtl;text-align:right;line-height:1.95;font-size:1.02em}
.ccna \*{box-sizing:border-box}
.ccna .sec{margin:42px 0 14px;padding:10px 18px;border-radius:12px;border-right:6px solid rgb(96,165,250);background:linear-gradient(270deg,rgba(96,165,250,.22),rgba(96,165,250,0));font-weight:800}
.ccna h3.s3{margin:30px 0 10px;padding:4px 14px 4px 0;font-size:1.25em;font-weight:800;border-right:4px solid rgb(168,85,247);padding-right:14px}
.ccna .box{--c:148,163,184;padding:14px 20px;margin:16px 0;border-radius:12px;border:1px solid rgba(var(--c),.3);border-right:5px solid rgb(var(--c));background:rgba(var(--c),.08)}
.ccna .blue{--c:96,165,250}
.ccna .green{--c:34,197,94}
.ccna .red{--c:239,68,68}
.ccna .amber{--c:245,158,11}
.ccna .purple{--c:168,85,247}
.ccna .gray{--c:148,163,184}
.ccna .box .ttl{font-weight:800;font-size:1.12em;margin-bottom:6px}
.ccna .box p{margin:6px 0}
.ccna ul{margin:6px 0;padding-right:22px;padding-left:0}
.ccna li{margin:4px 0}
.ccna .grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:14px;margin:16px 0}
.ccna .grid .box{margin:0}
.ccna .t{direction:ltr;unicode-bidi:isolate;display:inline-block;padding:0 8px;margin:0 2px;border-radius:6px;font-family:ui-monospace,Consolas,monospace;font-size:.9em;background:rgba(148,163,184,.18);border:1px solid rgba(148,163,184,.28)}
.ccna .step{display:flex;gap:12px;align-items:flex-start;margin:12px 0}
.ccna .step>div:last-child{flex:1}
.ccna .num{flex:0 0 34px;height:34px;line-height:34px;text-align:center;border-radius:50%;font-weight:800;color:#fff;background:rgb(var(--c))}
.ccna .sub{margin:8px 0;padding:8px 14px;border-radius:10px;border:1px dashed rgba(var(--c),.55);background:rgba(var(--c),.07)}

<div class="ccna" dir="rtl">
<h2 class="sec"><span class="t">Coaxial Cable</span>:</h2>
<div class="box blue">
<p>كابل بيتكون من <span class="t">Copper Conductor</span> في المنتصف، وحواليه طبقة عزل ثم <span class="t">Shielding</span> ثم الغلاف الخارجي.</p>
</div>
<div class="box green">
<div class="ttl">الإستخدام:</div>
<ul>
<li><span class="t">Cable TV</span></li>
<li><span class="t">Internet</span> عبر بعض شبكات <span class="t">Cable</span></li>
<li><span class="t">CCTV</span> في بعض الأنظمة</li>
<li>بعض أنظمة الاتصالات القديمة</li>
</ul>
</div>
<h2 class="sec"><span class="t">UTP — Unshielded Twisted Pair</span></h2>
<div class="box blue">
<p>بيتكون من 4 أزواج من الأسلاك النحاسية، وكل زوج عبارة عن سلكين ملفوفين حول بعضهم</p>
<p>يعني مفيش <span class="t">Shielding</span> إضافي حوالين الأزواج.</p>
</div>
<div class="box purple">
<div class="ttl">الاستخدامات</div>
<p>ده أشهر نوع في شبكات <span class="t">Ethernet</span> الحديثة، وبيستخدم في:</p>
<ul>
<li>توصيل الكمبيوتر بالـ<span class="t">Switch</span>.</li>
<li>توصيل الـ<span class="t">Access Point</span> بالـ<span class="t">Switch</span>.</li>
<li>توصيل أجهزة الشبكة داخل الـ<span class="t">LAN</span>.</li>
<li>شبكات المنازل والشركات.</li>
</ul>
</div>
<div class="grid">
<div class="box green">
<div class="ttl">المميزات:</div>
<ul>
<li>رخيص نسبيًا.</li>
<li>خفيف ومرن.</li>
<li>سهل التركيب</li>
</ul>
</div>
<div class="box red">
<div class="ttl">العيوب:</div>
<ul>
<li>أكثر تأثرًا بالـ<span class="t">Electromagnetic Interference</span> من <span class="t">STP</span></li>
<li>ممكن يتأثر بالتداخل في البيئات اللي فيها أجهزة كهربائية قوية.</li>
</ul>
</div>
</div>
<h2 class="sec"><span class="t">STP — Shielded Twisted Pair</span></h2>
<div class="box blue">
<p>شبيه جدًا بالـ<span class="t">UTP</span>، لكن فيه <span class="t">Shielding</span> إضافي لحماية الأسلاك من التداخل الكهرومغناطيسي.</p>
</div>
<div class="box purple">
<div class="ttl">الاستخدامات</div>
<p>بيستخدم غالبًا في البيئات اللي فيها <span class="t">Electromagnetic Interference (EMI)</span> عالي، مثل:</p>
<ul>
<li>المصانع.</li>
<li>الأماكن اللي فيها <span class="t">Motors</span> ومعدات كهربائية.</li>
<li>بعض مراكز البيانات.</li>
<li>البيئات الصناعية.</li>
</ul>
</div>
<div class="grid">
<div class="box green">
<div class="ttl">المميزات</div>
<ul>
<li>مقاومة أفضل للـ<span class="t">EMI</span> مقارنة بالـ<span class="t">UTP</span>.</li>
<li>يوفر حماية إضافية للإشارة.</li>
<li>مناسب للبيئات اللي فيها <span class="t">Electrical Noise</span> عالي.</li>
</ul>
</div>
<div class="box red">
<div class="ttl">العيوب</div>
<ul>
<li>أغلى من <span class="t">UTP</span>.</li>
<li>أكثر سمكًا وأقل مرونة.</li>
<li>تركيبه أصعب نسبيًا.</li>
</ul>
</div>
</div>
<h2 class="sec"><span class="t">Fiber Optic Cable</span></h2>
<div class="box blue">
<div class="ttl">يعني إيه <span class="t">Fiber Optic</span>؟</div>
<p>هو كابل بيستخدم الضوء (<span class="t">Light</span>) لنقل البيانات بدل الإشارات الكهربائية المستخدمة في الـ<span class="t">Copper Cables</span>.</p>
</div>
<div class="box purple">
<div class="ttl">مكونات الـ<span class="t">Fiber Optic Cable</span></div>
<p>الـ<span class="t">Fiber</span> بشكل أساسي بيتكون من:</p>
<div class="step"><div class="num">1</div><div><b><span class="t">Core</span></b>
<div class="sub">الجزء الداخلي اللي بيمر فيه الـ<span class="t">Light</span>.<br>هو الجزء المسؤول عن نقل البيانات.</div></div></div>
<div class="step"><div class="num">2</div><div><b><span class="t">Cladding</span></b>
<div class="sub">بيحيط بالـ<span class="t">Core</span>.<br>بيساعد على إبقاء الضوء داخل الـ<span class="t">Core</span> باستخدام مبدأ <span class="t">Total Internal Reflection</span>.</div></div></div>
<div class="step"><div class="num">3</div><div><b><span class="t">Buffer / Coating</span></b>
<div class="sub">طبقة حماية حوالين الـ<span class="t">Cladding</span>.<br>بتحمي الـ<span class="t">Fiber</span> من الرطوبة والأضرار الميكانيكية.</div></div></div>
<div class="step"><div class="num">4</div><div><b><span class="t">Outer Jacket</span></b>
<div class="sub">الغلاف الخارجي للكابل.<br>بيحمي المكونات الداخلية للكابل.</div></div></div>
</div>
<h2 class="sec">أنواع الـ <span class="t">Fiber optic</span></h2>
<p>عندنا نوعين اساسيين</p>
<h3 class="s3">1- <span class="t">Single-Mode</span></h3>
<div class="grid">
<div class="box blue">
<div class="ttl">استخداماته</div>
<ul>
<li>بيستخدم <span class="t">Core</span> صغير جدًا.</li>
<li>بيسمح بمرور مسار ضوئي واحد بشكل أساسي.</li>
<li>مناسب للمسافات الطويلة جدًا.</li>
<li>بيستخدم غالبًا في <span class="t">WANs, ISP Networks, Telecom</span>.</li>
</ul>
</div>
<div class="box green">
<div class="ttl">مميزاته</div>
<ul>
<li>مسافات نقل طويلة جدًا.</li>
<li><span class="t">Bandwidth</span> عالي.</li>
<li>أقل تأثيرًا من التشتت مقارنة بالـ<span class="t">Multimode</span>.</li>
</ul>
</div>
<div class="box red">
<div class="ttl">عيوبه</div>
<ul>
<li>المعدات الخاصة به عادةً أغلى.</li>
<li>يحتاج دقة أكبر في التركيب والـ<span class="t">Splicing</span>. (وصلة) وليه ناس متتخصصين في أعمال تركيبه</li>
</ul>
</div>
</div>
<h3 class="s3">2. <span class="t">Multi-Mode Fiber (MMF)</span></h3>
<div class="grid">
<div class="box blue">
<div class="ttl">الإستخدام</div>
<ul>
<li>بيستخدم <span class="t">Core</span> أكبر من <span class="t">Single-Mode</span>.</li>
<li>بيسمح بمرور عدة مسارات للضوء.</li>
<li>مناسب للمسافات الأقصر.</li>
</ul>
</div>
<div class="box green">
<div class="ttl">مميزاته</div>
<ul>
<li>المعدات عادةً أقل تكلفة من <span class="t">Single-Mode</span> .</li>
<li>مناسب للـ<span class="t">LANs</span> و<span class="t">Data Centers</span> والمسافات الداخلية.</li>
</ul>
</div>
<div class="box red">
<ul>
<li>المسافة أقصر من <span class="t">Single-Mode</span>.</li>
<li>أكثر تأثرًا بالـ<span class="t">Modal Dispersion</span>.</li>
</ul>
</div>
</div>
<h2 class="sec">مميزات <span class="t">Fiber Optic</span></h2>
<div class="box green">
<div class="ttl"><span class="t">Advantages</span></div>
<ul>
<li>سرعات عالية جدًا.</li>
<li><span class="t">Bandwidth</span> عالي.</li>
<li>مناسب للمسافات الطويلة.</li>
<li>لا يتأثر بالـ<span class="t">Electromagnetic Interference (EMI)</span> مثل النحاس.</li>
<li>أخف وزنًا من كابلات النحاس لمسافات طويلة وبسعات كبيرة.</li>
<li>مناسب جدًا للـ<span class="t">Backbone</span> والـ<span class="t">WAN</span> والـ<span class="t">Data Centers</span>.</li>
</ul>
</div>
<h2 class="sec">عيوب <span class="t">Fiber Optic</span></h2>
<div class="box red">
<ul>
<li>أغلى من بعض حلول الـ<span class="t">Copper</span>.</li>
<li>تركيبه يحتاج مهارة وأدوات متخصصة.</li>
<li>الـ<span class="t">Fiber</span> أكثر حساسية للانحناء والضرر الميكانيكي من الكابلات النحاسية في بعض أنواع التركيبات.</li>
<li>إصلاحه و<span class="t">Splicing</span> يحتاج معدات وخبرة.</li>
</ul>
</div>
</div>


---
title: "CCNA: OSI Model"
date: 2025-10-01
categories: [CCNA]
tags: [CCNA]
---

<style>
.ccna{direction:rtl;text-align:right;line-height:1.95;font-size:1.02em}
.ccna *{box-sizing:border-box}
.ccna .sec{margin:42px 0 14px;padding:10px 18px;border-radius:12px;border-right:6px solid rgb(96,165,250);background:linear-gradient(270deg,rgba(96,165,250,.22),rgba(96,165,250,0));font-weight:800}
.ccna h3.s3{margin:28px 0 10px;padding-right:14px;font-size:1.2em;font-weight:800;border-right:4px solid rgb(168,85,247)}
.ccna .box{--c:148,163,184;padding:14px 20px;margin:16px 0;border-radius:12px;border:1px solid rgba(var(--c),.3);border-right:5px solid rgb(var(--c));background:rgba(var(--c),.08)}
.ccna .dg{--c:96,165,250;direction:ltr;display:flex;align-items:center;justify-content:center;margin:18px 0;padding:18px 14px;border-radius:12px;border:1px dashed rgba(148,163,184,.5);background:rgba(148,163,184,.05);overflow-x:auto}
.ccna .blue{--c:96,165,250}
.ccna .green{--c:34,197,94}
.ccna .red{--c:239,68,68}
.ccna .amber{--c:245,158,11}
.ccna .purple{--c:168,85,247}
.ccna .gray{--c:148,163,184}
.ccna .l7{--c:168,85,247}
.ccna .l6{--c:96,165,250}
.ccna .l5{--c:34,197,94}
.ccna .l4{--c:245,158,11}
.ccna .l3{--c:239,68,68}
.ccna .l2{--c:236,72,153}
.ccna .l1{--c:148,163,184}
.ccna .box .ttl{font-weight:800;font-size:1.12em;margin-bottom:6px}
.ccna .box p{margin:6px 0}
.ccna p{margin:8px 0}
.ccna ul{margin:6px 0;padding-right:22px;padding-left:0}
.ccna li{margin:4px 0}
.ccna .grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:14px;margin:16px 0}
.ccna .grid .box{margin:0}
.ccna .cols{direction:ltr;display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:14px;margin:16px 0}
.ccna .cl{padding:12px;border-radius:12px;border:1px dashed rgba(148,163,184,.5);background:rgba(148,163,184,.05)}
.ccna .cl .ct{text-align:center;font-weight:800;margin-bottom:8px}
.ccna .t{direction:ltr;unicode-bidi:isolate;display:inline-block;padding:0 8px;margin:0 2px;border-radius:6px;font-family:ui-monospace,Consolas,monospace;font-size:.9em;background:rgba(148,163,184,.18);border:1px solid rgba(148,163,184,.28)}
.ccna .line{direction:ltr;text-align:left;unicode-bidi:isolate;padding:10px 16px;margin:8px 0;border-radius:10px;border:1px solid rgba(var(--c),.4);border-left:5px solid rgb(var(--c));background:rgba(var(--c),.08);font-family:ui-monospace,Consolas,monospace;font-weight:700}
.ccna .nd{flex:0 0 auto;min-width:84px;padding:8px 14px;text-align:center;border-radius:10px;font-weight:700;border:1px solid rgba(var(--c),.65);background:rgba(var(--c),.15)}
.ccna .nd small{display:block;font-weight:400;font-size:.8em;opacity:.9}
.ccna .nd.wide{min-width:150px}
.ccna .wl{display:flex;flex-direction:column;align-items:center;flex:1 1 90px;min-width:90px;margin:0 8px;font-size:.8em;text-align:center}
.ccna .wire{position:relative;flex:1 1 60px;min-width:60px;height:2px;margin:0 8px;background:rgb(var(--c))}
.ccna .wl .wire{flex:0 0 2px;width:100%;min-width:0;margin:8px 0 0}
.ccna .wire.r::after{content:"";position:absolute;right:-2px;top:-5px;border-left:9px solid rgb(var(--c));border-top:6px solid transparent;border-bottom:6px solid transparent}
.ccna .wire.l::before{content:"";position:absolute;left:-2px;top:-5px;border-right:9px solid rgb(var(--c));border-top:6px solid transparent;border-bottom:6px solid transparent}
.ccna .colon{font-size:1.6em;font-weight:800;margin:0 8px}
.ccna .fl{direction:ltr;display:flex;flex-direction:column;align-items:center;margin:14px 0}
.ccna .fb{min-width:220px;padding:8px 18px;text-align:center;border-radius:10px;font-weight:700;border:1px solid rgba(var(--c),.65);background:rgba(var(--c),.15)}
.ccna .fa{opacity:.7;line-height:1.3;font-size:1.15em}
.ccna .tbl{overflow-x:auto;margin:16px 0}
.ccna table.osi{direction:ltr;width:100%;min-width:480px;border-collapse:collapse}
.ccna table.osi th,.ccna table.osi td{padding:10px 14px;border:1px solid rgba(148,163,184,.3);text-align:left}
.ccna table.osi th{background:rgba(96,165,250,.2)}
.ccna table.osi tr{background:rgba(var(--c,148,163,184),.1)}
.ccna table.osi td:first-child{background:rgba(var(--c,148,163,184),.35);font-weight:800;text-align:center;width:70px}
.ccna table.osi td.du{text-align:center;font-weight:800}
.ccna .strip{direction:ltr;display:flex;flex-wrap:wrap;margin:18px 0;border-radius:10px;overflow:hidden;border:1px solid rgba(148,163,184,.5)}
.ccna .strip>div{flex:1 1 90px;padding:12px 10px;text-align:center;font-weight:700;border-left:1px solid rgba(148,163,184,.5);background:rgba(var(--c),.18)}
.ccna .strip>div small{display:block;font-weight:400;font-size:.8em}
.ccna .nest{direction:ltr;max-width:620px;margin:18px auto}
.ccna .lv{padding:8px 10px 10px;border-radius:12px;border:2px solid rgba(var(--c),.85);background:rgba(var(--c),.1)}
.ccna .lv .lb{font-weight:800;font-size:.85em;margin-bottom:6px;text-align:left;opacity:.9}
.ccna .lv .row{display:flex;flex-wrap:wrap;gap:8px;align-items:stretch}
.ccna .lv .row>.lv{flex:1 1 200px}
.ccna .hd{flex:0 0 auto;display:flex;align-items:center;padding:8px 12px;border-radius:8px;font-weight:700;background:rgba(var(--c),.4)}
</style>
<div class="ccna" dir="rtl">
<h2 class="sec"><span class="t">OSI Model</span></h2>
<div class="box blue">
<p><span class="t">OSI</span> اختصار لـ:</p>
<p><span class="t">Open Systems Interconnection</span></p>
<p>وهو <span class="t">Reference Model</span> تم تصميمه علشان يشرح لنا إزاي الـ <span class="t">data</span> بتنتقل من جهاز لجهاز تاني عبر الـ <span class="t">Network</span>.</p>
<p>الـ <span class="t">OSI Model</span> بيقسم عملية الـ <span class="t">Network Communication</span> إلى 7 <span class="t">Layers</span>، وكل <span class="t">Layer</span> لها وظيفة محددة.</p>
</div>
<div class="box purple">
<p>قبل ما نتعرف علي الـ<span class="t">layers</span> تعالي ناخد مثال واقعي</p>
<p>شخص صيني بيكلم شخص ألماني ومش بيتكلمو أي لغة تانية غير لغتهم الأصلية</p>
<p>بالتالي محتاجين حاجة تترجم كلامهم وبتعتمد علي قواعد ترجمة ثابتة عشان يكلمو بعض</p>
<p>القواعد دي هي الـ<span class="t">protocols</span></p>
</div>
<div class="dg purple"><div class="nd">شخص صيني</div><div class="wl"><div class="wire r"></div><div class="wire l" style="margin-top:8px"></div></div><div class="nd">Protocols</div><div class="wl"><div class="wire r"></div><div class="wire l" style="margin-top:8px"></div></div><div class="nd">شخص ألماني</div></div>
<div class="box blue">
<div class="ttl">الـ 7 <span class="t">Layers</span> من تحت لفوق:</div>
</div>
<div class="tbl"><table class="osi">
<thead><tr><th>Layer</th><th>Name</th><th>Main Function</th></tr></thead>
<tbody>
<tr class="l7"><td>7</td><td>Application</td><td>Network services used by applications</td></tr>
<tr class="l6"><td>6</td><td>Presentation</td><td>Data format, encryption, compression</td></tr>
<tr class="l5"><td>5</td><td>Session</td><td>Establish/manage/end sessions</td></tr>
<tr class="l4"><td>4</td><td>Transport</td><td>End-to-end delivery</td></tr>
<tr class="l3"><td>3</td><td>Network</td><td>IP addressing &amp; routing</td></tr>
<tr class="l2"><td>2</td><td>Data Link</td><td>MAC addressing &amp; Frames</td></tr>
<tr class="l1"><td>1</td><td>Physical</td><td>Bits &amp; physical transmission</td></tr>
</tbody>
</table></div>
<p>هنبدأ من <span class="t">Layer 1</span> ونطلع واحدة واحدة.</p>
<h2 class="sec"><span class="t">Layer 1 — Physical Layer</span></h2>
<div class="box l1">
<p>الـ <span class="t">Physical Layer</span> هي أول وأقل <span class="t">Layer</span> في الـ <span class="t">OSI Model</span>.</p>
<p>وظيفتها الأساسية هي التعامل مع <span class="t">physical transmission of data</span>، يعني إزاي الـ <span class="t">data</span> تتحول إلى <span class="t">Bits</span> وتتنقل فعليًا من جهاز لجهاز.</p>
<p>والـ <span class="t">Physical Layer</span> مش مهتمة بالـ <span class="t">IP Address</span> أو <span class="t">MAC Address</span> أو مين الجهاز اللي هيستقبل الـ <span class="t">data</span>.</p>
</div>
<div class="box blue">
<div class="ttl">هي بتتعامل مع:</div>
<ul>
<li><span class="t">Electrical Signals</span></li>
<li><span class="t">Light Signals</span></li>
<li><span class="t">Radio Signals</span></li>
</ul>
</div>
<h3 class="s3">يعني إيه <span class="t">Bits</span>؟</h3>
<div class="box purple">
<p>في النهاية الـ <span class="t">data</span> اللي بنبعتها على الـ <span class="t">Network</span> بتتحول إلى:</p>
<p><span class="t">0s and 1s</span></p>
<p>والـ <span class="t">Physical Layer</span> مسؤولة عن إرسال الـ <span class="t">bits</span> دي كـ <span class="t">signals</span>.</p>
</div>
<p>مثلاً:</p>
<div class="grid">
<div class="box amber">
<div class="ttl">لو بنستخدم <span class="t">Copper Cable</span>:</div>
<div class="line">0 → Electrical Signal</div>
<div class="line">1 → Electrical Signal</div>
</div>
<div class="box green">
<div class="ttl">ولو بنستخدم <span class="t">Fiber Optic</span>:</div>
<div class="line">0 → Light Signal</div>
<div class="line">1 → Light Signal</div>
</div>
<div class="box blue">
<div class="ttl">ولو <span class="t">Wireless</span>:</div>
<div class="line">0/1 → Radio Signal</div>
</div>
</div>
<h3 class="s3">أمثلة على <span class="t">Physical Layer</span></h3>
<div class="box l1">
<p>من أشهر الـ <span class="t">devices</span> والـ <span class="t">components</span> المرتبطة بالـ <span class="t">Physical Layer</span>:</p>
<ul>
<li><span class="t">Ethernet Cable</span></li>
<li><span class="t">Fiber Optic Cable</span></li>
<li><span class="t">Network Interface</span></li>
<li><span class="t">Hub</span></li>
<li><span class="t">Repeaters</span></li>
<li><span class="t">Radio/Wireless transmission</span></li>
</ul>
<p>مثلاً الـ <span class="t">Hub</span> يعتبر <span class="t">Layer 1 device</span> لأنه مش بيقرأ <span class="t">MAC Address</span>، هو ببساطة يستقبل <span class="t">signal</span> ويعمل لها <span class="t">repeat/forward</span> على باقي الـ <span class="t">ports</span>.</p>
</div>
<h3 class="s3">مثال عملي</h3>
<p>لو عندنا:</p>
<div class="dg l1"><div class="nd">PC</div><div class="wl"><span>Ethernet Cable</span><div class="wire"></div></div><div class="nd">Switch</div></div>
<div class="grid">
<div class="box green">
<div class="ttl">الـ <span class="t">Physical Layer</span> هنا مسؤولة عن:</div>
<ul>
<li>الكابل</li>
<li>الـ <span class="t">connector</span></li>
<li>الإشارة الكهربائية</li>
<li>سرعة الـ <span class="t">transmission</span></li>
<li>تحويل الـ <span class="t">bits</span> إلى <span class="t">signals</span></li>
<li>نقل الـ <span class="t">signals</span> عبر الـ <span class="t">cable</span></li>
</ul>
</div>
<div class="box red">
<div class="ttl">لكنها مش مسؤولة عن معرفة إن الـ <span class="t">destination</span> هو:</div>
<div class="line">MAC Address = AA:BB:CC:DD:EE:FF</div>
</div>
</div>
<p>ده دور <span class="t">Layer 2</span>.</p>
<h2 class="sec"><span class="t">Layer 2 — Data Link Layer</span></h2>
<p>نطلع <span class="t">Layer</span> واحدة.</p>
<div class="box l2">
<p>وهنا بنبدأ ندخل في موضوع مهم جدًا في الـ <span class="t">Networking</span>:</p>
<p><span class="t">MAC Address</span></p>
<p>الـ <span class="t">Data Link Layer</span> مسؤولة عن التواصل داخل الـ <span class="t">Local Network</span>، وبتتعامل مع الـ <span class="t">Frames</span>.</p>
</div>
<div class="box blue">
<div class="ttl">أهم حاجات <span class="t">Layer 2</span>:</div>
<ul>
<li><span class="t">MAC Address</span></li>
<li><span class="t">Frames</span> دا شكل البيانات في الطبقة دي زي ما قولنا ان شكل البيانات في الطبقي اللي قبلها هو الـ <span class="t">Bits</span></li>
<li><span class="t">Switches</span></li>
<li><span class="t">Ethernet</span></li>
<li><span class="t">Error Detection</span></li>
</ul>
</div>
<div class="box purple">
<p>كل <span class="t">Network Interface</span> تقريبًا عندها <span class="t">MAC Address</span>.</p>
<p>مثال:</p>
<div class="line">00:1A:2B:3C:4D:5E</div>
<p>الـ <span class="t">MAC Address</span> بيستخدم لتحديد الـ <span class="t">device</span> على مستوى <span class="t">Layer 2</span>.</p>
</div>
<p>مثلاً:</p>
<div class="dg l2"><div class="nd wide">PC1<small>MAC: AA:AA:AA:AA:AA:AA</small></div><div class="wire r"></div><div class="nd">Switch</div><div class="wire r"></div><div class="nd wide">PC2<small>MAC: BB:BB:BB:BB:BB:BB</small></div></div>
<p>الـ <span class="t">Switch</span> بيتعلم الـ <span class="t">MAC Addresses</span> الموجودة على الـ <span class="t">ports</span> بتاعته، وبعد كده يقدر يحدد الـ <span class="t">Frame</span> يروح على أنهي <span class="t">port</span>.</p>
<p>والـ <span class="t">Frame</span> يحتوي على معلومات منها:</p>
<div class="strip l2"><div>Source MAC</div><div>Destination MAC</div><div>Data</div><div>FCS<small>4 bytes = 32 bits</small></div></div>
<div class="box amber">
<p>الـ <span class="t">FCS</span> هو اختصار <span class="t">Frame Check Sequence</span> وفايدته هنا انه بيكشف عن أي تلف أو خطأ أو تداخل حصل للبيانات اثناء الإرسال عبر الشبكة</p>
<p>موقعه وحجمه: موجود في نهياة الـ <span class="t">frame</span> وبيحتوي علي <span class="t">4bytes</span> يعني <span class="t">32bits</span></p>
<p>بيشتغل ازاي: نتكلم عنها بشكل عام الجهاز اللي بيرسل بيحسب قيمة الـ <span class="t">CRC-32</span> بناءا علي محتوي الفريم وتضيفها كقيمة</p>
<p>والجهاز اللي بيستقبل بيرجع يعمل نفس العملية تاني ويحسبها ويقارن القيمة اللي حسبها بالقيمة اللي جتله لو زي بعض يبقي الفريم سليم لو مختلفين بيرفض الفريم</p>
</div>
<div class="dg amber"><div class="nd">Sender<small>CRC-32</small></div><div class="wl"><span>Frame + FCS</span><div class="wire r"></div></div><div class="nd">Receiver<small>CRC-32</small></div></div>
<h2 class="sec"><span class="t">Layer 3 — Network Layer</span></h2>
<div class="box l3">
<p>هنا بندخل على واحدة من أهم <span class="t">Layers</span> في الـ <span class="t">Networking</span>.</p>
<p>الـ <span class="t">Network Layer</span> مسؤولة بشكل أساسي عن:</p>
<p><span class="t">IP Addressing and Routing</span></p>
</div>
<div class="box blue">
<p>يعني تحديد:</p>
<p>مين الـ <span class="t">source</span>؟</p>
<p>و:</p>
<p>مين الـ <span class="t">destination</span>؟</p>
<p>وكمان إزاي الـ <span class="t">packet</span> توصل من <span class="t">Network</span> إلى <span class="t">Network</span> أخرى.</p>
</div>
<div class="box purple">
<p>مثلاً:</p>
<p><span class="t">PC1</span></p>
<p><span class="t">192.168.1.10</span></p>
<p>والـ <span class="t">destination</span>:</p>
<p><span class="t">Server</span></p>
<p><span class="t">192.168.2.20</span></p>
<p>الجهاز هنا محتاج يعرف:</p>
<p>هل الـ <span class="t">destination</span> موجود في نفس الـ <span class="t">Network</span> ولا <span class="t">Network</span> مختلفة؟</p>
<p>لو <span class="t">Network</span> مختلفة، بنحتاج <span class="t">Router</span>.</p>
</div>
<p>الـ <span class="t">Router</span> يعتبر من أشهر أجهزة <span class="t">Layer 3</span>.</p>
<p>مثلاً:</p>
<div class="dg l3"><div class="nd wide">PC1<small>192.168.1.10</small></div><div class="wire r"></div><div class="nd wide">Network A<small>192.168.1.0/24</small></div><div class="wire r"></div><div class="nd">Router</div><div class="wire r"></div><div class="nd wide">Network B<small>192.168.2.0/24</small></div><div class="wire r"></div><div class="nd wide">Server<small>192.168.2.20</small></div></div>
<p>الـ <span class="t">Router</span> يستخدم الـ <span class="t">IP Address</span> والـ <span class="t">Routing Table</span> علشان يحدد أفضل <span class="t">path</span> للـ <span class="t">destination</span>.</p>
<h3 class="s3"><span class="t">Data Unit</span></h3>
<div class="box amber">
<p>في <span class="t">Layer 3</span> الـ <span class="t">data</span> اسمها:</p>
<p><span class="t">Packet</span></p>
<p>إذن:</p>
<div class="line l2">Layer 2 → Frame</div>
<div class="line l3">Layer 3 → Packet</div>
<p><span class="t">Layer 4 — Transport Layer</span></p>
<p>نطلع <span class="t">Layer</span> أعلى.</p>
</div>
<h2 class="sec"><span class="t">Layer 4 = Transport Layer</span></h2>
<div class="box l4">
<p>ودي مسؤولة عن <span class="t">End-to-End Communication</span> بين التطبيقات الموجودة على الأجهزة.</p>
</div>
<div class="box blue">
<div class="ttl">أهم <span class="t">Protocols</span> هنا:</div>
<ul>
<li><span class="t">TCP</span></li>
<li><span class="t">UDP</span></li>
</ul>
</div>
<div class="grid">
<div class="box green">
<div class="ttl"><span class="t">TCP</span> بيقدم <span class="t">reliable communication</span>.</div>
<p>يعني يهتم إن الـ <span class="t">data</span>:</p>
<ul>
<li>توصل</li>
<li>توصل بالترتيب الصحيح</li>
<li>يتم اكتشاف الـ <span class="t">lost data</span></li>
<li>يتم إعادة إرسال البيانات عند الحاجة</li>
</ul>
<p>مثلاً عند تحميل <span class="t">File</span> مهم، <span class="t">reliability</span> تكون مهمة.</p>
</div>
<div class="box amber">
<div class="ttl"><span class="t">UDP</span></div>
<p><span class="t">UDP</span> أبسط وأسرع من <span class="t">TCP</span> لأنه لا يوفر نفس مستوى الـ <span class="t">reliability</span>.</p>
<p>ممكن نستخدمه في <span class="t">applications</span> محتاجة:</p>
<p><span class="t">Speed over reliability</span></p>
<p>زي بعض أنواع:</p>
<ul>
<li><span class="t">Voice</span></li>
<li><span class="t">Video</span></li>
<li><span class="t">Streaming</span></li>
<li><span class="t">DNS</span></li>
</ul>
</div>
</div>
<div class="line green">TCP → Segment</div>
<div class="line amber">UDP → Datagram</div>
<div class="box purple">
<p><span class="t">Layer 4</span> كمان مسؤولة عن <span class="t">Port Numbers</span>.</p>
<p>مثلاً:</p>
<div class="line">HTTP  → 80</div>
<div class="line">HTTPS → 443</div>
<div class="line">DNS   → 53</div>
<div class="line">SSH   → 22</div>
<p>فالـ <span class="t">IP Address</span> بيحدد الجهاز، والـ <span class="t">Port</span> بيساعدنا نحدد الـ <span class="t">application/service</span> على الجهاز.</p>
<p>مثلاً:</p>
<p><span class="t">192.168.1.10:443</span></p>
<p>يعني:</p>
<div class="line">IP Address → 192.168.1.10</div>
<div class="line">Port       → 443</div>
</div>
<div class="dg l4"><div class="nd">192.168.1.10<small>IP Address</small></div><div class="colon">:</div><div class="nd">443<small>Port</small></div></div>
<h3 class="s3"><span class="t">Data Unit</span></h3>
<p>في <span class="t">Layer 4</span>:</p>
<h2 class="sec"><span class="t">Layer 5 — Session Layer</span></h2>
<div class="box l5">
<p>الـ <span class="t">Session Layer</span> مسؤولة عن:</p>
<p><span class="t">Establishing, managing, and terminating communication sessions.</span></p>
<p>يعني بتساعد في إدارة الـ <span class="t">Session</span> بين جهازين أو تطبيقين.</p>
</div>
<p>مثلاً:</p>
<div class="fl l5"><div class="fb">Client</div><div class="fa">↕</div><div class="fb">Session</div><div class="fa">↕</div><div class="fb">Server</div></div>
<div class="box blue">
<p>هي بتتعامل مع بداية الـ <span class="t">session</span> واستمرارها وإنهائها.</p>
<p>ومن المفاهيم المرتبطة بيها:</p>
<ul>
<li><span class="t">Session establishment</span></li>
<li><span class="t">Session management</span></li>
<li><span class="t">Session termination</span></li>
<li><span class="t">Synchronization</span></li>
</ul>
</div>
<h3 class="s3">مثال بسيط</h3>
<p>لما <span class="t">application</span> تعمل <span class="t">communication</span> مع <span class="t">Server</span>:</p>
<div class="fl l5"><div class="fb">Start Session</div><div class="fa">↓</div><div class="fb">Communication</div><div class="fa">↓</div><div class="fb">Maintain Session</div><div class="fa">↓</div><div class="fb">End Session</div></div>
<div class="box gray">
<p>الـ <span class="t">Session Layer</span> <span class="t">conceptually</span> مسؤولة عن إدارة الجزء ده.</p>
<p>في الـ <span class="t">real-world networking</span>، وظائف الـ <span class="t">Session Layer</span> مش دائمًا بتكون منفصلة كـ <span class="t">protocol</span> مستقل؛ أحيانًا بتكون مدمجة داخل <span class="t">protocols</span> أو <span class="t">applications</span> في <span class="t">Layers</span> أخرى.</p>
</div>
<h2 class="sec"><span class="t">Layer 6 — Presentation Layer</span></h2>
<div class="box l6">
<p>وظيفتها الأساسية هي التعامل مع:</p>
<p><span class="t">How data is represented</span></p>
<p>يعني الـ <span class="t">data</span> تكون بصيغة يفهمها الطرف الآخر.</p>
</div>
<div class="box blue">
<div class="ttl">ومن أشهر الوظائف المرتبطة بالـ <span class="t">Presentation Layer</span>:</div>
<ul>
<li><span class="t">Data Formatting</span></li>
<li><span class="t">Encryption</span></li>
<li><span class="t">Decryption</span></li>
<li><span class="t">Compression</span></li>
<li><span class="t">Decompression</span></li>
</ul>
</div>
<h3 class="s3"><span class="t">Data Formatting</span></h3>
<div class="box purple">
<p>مثلاً جهاز ممكن يمثل البيانات بطريقة معينة، والجهاز الآخر يحتاج <span class="t">format</span> مختلف.</p>
<p>فالـ <span class="t">Presentation Layer</span> تهتم بتحويل الـ <span class="t">data</span> إلى <span class="t">format</span> مناسب للتواصل.</p>
</div>
<h3 class="s3"><span class="t">Encryption</span></h3>
<p>من المفاهيم المرتبطة بالـ <span class="t">Presentation Layer</span>:</p>
<div class="fl l6"><div class="fb">Plain Data</div><div class="fa">↓</div><div class="fb">Encryption</div><div class="fa">↓</div><div class="fb">Encrypted Data</div></div>
<p>وعند الطرف الآخر:</p>
<div class="fl l6"><div class="fb">Encrypted Data</div><div class="fa">↓</div><div class="fb">Decryption</div><div class="fa">↓</div><div class="fb">Original Data</div></div>
<h3 class="s3"><span class="t">Compression</span></h3>
<p>ممكن كمان يتم ضغط البيانات لتقليل حجمها:</p>
<div class="fl l6"><div class="fb">Large Data</div><div class="fa">↓</div><div class="fb">Compression</div><div class="fa">↓</div><div class="fb">Smaller Data</div></div>
<h2 class="sec"><span class="t">Layer 7 — Application Layer</span></h2>
<div class="box l7">
<p>وصلنا لأعلى <span class="t">Layer</span>.</p>
<p><span class="t">Layer 7 = Application Layer</span></p>
<p>ودي الـ <span class="t">Layer</span> الأقرب للـ <span class="t">User Applications</span>.</p>
</div>
<div class="box amber">
<p>لكن مهم جدًا نفهم:</p>
<p><span class="t">Application Layer</span> مش معناها إن الـ <span class="t">application</span> نفسها هي الـ <span class="t">Layer</span>.</p>
<p>هي بتوفر <span class="t">Network Services</span> للـ <span class="t">applications</span>.</p>
</div>
<h3 class="s3">أمثلة على <span class="t">Application Layer Protocols</span></h3>
<div class="box blue">
<p>من أشهر الـ <span class="t">protocols</span>:</p>
<ul>
<li><span class="t">HTTP</span></li>
<li><span class="t">HTTPS</span></li>
<li><span class="t">DNS</span></li>
<li><span class="t">DHCP</span></li>
<li><span class="t">FTP</span></li>
<li><span class="t">SMTP</span></li>
<li><span class="t">SSH</span></li>
</ul>
</div>
<p>مثلاً لما تفتح <span class="t">Website</span>:</p>
<div class="fl l7"><div class="fb">Browser</div><div class="fa">↓</div><div class="fb">HTTP / HTTPS</div><div class="fa">↓</div><div class="fb">Network</div></div>
<p>الـ <span class="t">Browser</span> بيستخدم <span class="t">Application Layer protocols</span> علشان يتواصل مع الـ <span class="t">Web Server</span>.</p>
<h3 class="s3">مثال كامل من <span class="t">Layer 7</span> إلى <span class="t">Layer 1</span></h3>
<p>خلينا نفترض إنك فتحت:</p>
<div class="line">https://example.com</div>
<p>الـ <span class="t">data</span> وهي نازلة من <span class="t">Application</span> إلى <span class="t">Physical</span> بتعدي على الـ <span class="t">Layers</span>:</p>
<div class="fl"><div class="fb l7">Application</div><div class="fa">↓</div><div class="fb l6">Presentation</div><div class="fa">↓</div><div class="fb l5">Session</div><div class="fa">↓</div><div class="fb l4">Transport</div><div class="fa">↓</div><div class="fb l3">Network</div><div class="fa">↓</div><div class="fb l2">Data Link</div><div class="fa">↓</div><div class="fb l1">Physical</div></div>
<div class="box purple">
<p>وفي كل <span class="t">Layer</span> بيتم إضافة معلومات مرتبطة بالـ <span class="t">Layer</span> دي.</p>
<p>وده اسمه:</p>
<p><span class="t">Encapsulation</span></p>
</div>
<p>بشكل مبسط:</p>
<div class="fl"><div class="fb l7">Application Data</div><div class="fa">↓</div><div class="fb l4">Transport Header + Data</div><div class="fa">↓</div><div class="fb l3">IP Header + Transport Data</div><div class="fa">↓</div><div class="fb l2">Ethernet Header + IP Packet</div><div class="fa">↓</div><div class="fb l1">Bits</div></div>
<div class="nest"><div class="lv l2"><div class="lb">Frame</div><div class="row"><div class="hd">Ethernet Header</div><div class="lv l3"><div class="lb">Packet</div><div class="row"><div class="hd">IP Header</div><div class="lv l4"><div class="lb">Segment</div><div class="row"><div class="hd">Transport Header</div><div class="hd l7">Application Data</div></div></div></div></div></div></div></div>
<p>وبتخرج فعليًا على الـ <span class="t">Network</span> كـ <span class="t">signals</span>.</p>
<h3 class="s3">وعند الـ <span class="t">Receiver</span>؟</h3>
<p>العملية بتحصل بالعكس.</p>
<p>الـ <span class="t">receiver</span> يستقبل الـ <span class="t">Bits</span>:</p>
<div class="fl"><div class="fb l1">Physical</div><div class="fa">↓</div><div class="fb l2">Data Link</div><div class="fa">↓</div><div class="fb l3">Network</div><div class="fa">↓</div><div class="fb l4">Transport</div><div class="fa">↓</div><div class="fb l5">Session</div><div class="fa">↓</div><div class="fb l6">Presentation</div><div class="fa">↓</div><div class="fb l7">Application</div></div>
<div class="box purple">
<p>وده اسمه:</p>
<p><span class="t">Decapsulation</span></p>
</div>
<h3 class="s3">أهم حاجة تحفظها</h3>
<p>احفظ الـ 7 <span class="t">Layers</span> بالترتيب:</p>
<div class="line l7">7 - Application</div>
<div class="line l6">6 - Presentation</div>
<div class="line l5">5 - Session</div>
<div class="line l4">4 - Transport</div>
<div class="line l3">3 - Network</div>
<div class="line l2">2 - Data Link</div>
<div class="line l1">1 - Physical</div>
<p>ومن تحت لفوق:</p>
<div class="box amber">
<p><span class="t">Please Do Not Throw Sausage Pizza Away</span></p>
</div>
<div class="line l1">P → Physical</div>
<div class="line l2">D → Data Link</div>
<div class="line l3">N → Network</div>
<div class="line l4">T → Transport</div>
<div class="line l5">S → Session</div>
<div class="line l6">P → Presentation</div>
<div class="line l7">A → Application</div>
<p>وده ترتيب ممتاز جدًا للحفظ.</p>
<h3 class="s3">وربطهم بالـ <span class="t">Data Units</span>:</h3>
<div class="tbl"><table class="osi">
<thead><tr><th>Layer</th><th>Name</th><th>Data Unit</th></tr></thead>
<tbody>
<tr class="l7"><td>7</td><td>Application</td><td class="du" rowspan="3">Data</td></tr>
<tr class="l6"><td>6</td><td>Presentation</td></tr>
<tr class="l5"><td>5</td><td>Session</td></tr>
<tr class="l4"><td>4</td><td>Transport</td><td class="du">Segment / Datagram</td></tr>
<tr class="l3"><td>3</td><td>Network</td><td class="du">Packet</td></tr>
<tr class="l2"><td>2</td><td>Data Link</td><td class="du">Frame</td></tr>
<tr class="l1"><td>1</td><td>Physical</td><td class="du">Bits</td></tr>
</tbody>
</table></div>
<div class="box blue">
<div class="ttl">وأهم 4 حاجات في الـ <span class="t">CCNA</span> في البداية:</div>
</div>
<div class="line l1">Layer 1 → Signals / Bits / Cables</div>
<div class="line l2">Layer 2 → MAC / Frames / Switch</div>
<div class="line l3">Layer 3 → IP / Packets / Router</div>
<div class="line l4">Layer 4 → TCP/UDP / Ports / End-to-End Communication</div>
</div>

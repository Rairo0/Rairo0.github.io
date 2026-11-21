---
title: "CCNA: Session 1 — Network Basics & Components"
date: 2025-10-01
categories: [CCNA]
tags: [CCNA]

---

<style>
.ccna{direction:rtl;text-align:right;line-height:1.95;font-size:1.02em}
.ccna *{box-sizing:border-box}
.ccna .blue{--c:96,165,250}
.ccna .green{--c:34,197,94}
.ccna .red{--c:239,68,68}
.ccna .amber{--c:245,158,11}
.ccna .purple{--c:168,85,247}
.ccna .gray{--c:148,163,184}
.ccna .sec{margin:42px 0 14px;padding:10px 18px;border-radius:12px;border-right:6px solid rgb(96,165,250);background:linear-gradient(270deg,rgba(96,165,250,.22),rgba(96,165,250,0));font-weight:800}
.ccna .box{--c:148,163,184;padding:14px 20px;margin:16px 0;border-radius:12px;border:1px solid rgba(var(--c),.3);border-right:5px solid rgb(var(--c));background:rgba(var(--c),.08)}
.ccna .box .ttl{font-weight:800;font-size:1.12em;margin-bottom:6px}
.ccna .box p{margin:6px 0}
.ccna ul{margin:6px 0;padding-right:22px;padding-left:0}
.ccna li{margin:4px 0}
.ccna .grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:14px;margin:16px 0}
.ccna .grid .box{margin:0}
.ccna .t{direction:ltr;unicode-bidi:isolate;display:inline-block;padding:0 8px;margin:0 2px;border-radius:6px;font-family:ui-monospace,Consolas,monospace;font-size:.9em;background:rgba(148,163,184,.18);border:1px solid rgba(148,163,184,.28)}
.ccna .badge{display:inline-block;direction:ltr;padding:2px 12px;margin-inline-start:8px;border-radius:999px;font-size:.78em;font-weight:700;color:#fff;background:rgb(var(--c))}
.ccna .step{display:flex;gap:12px;align-items:flex-start;margin:10px 0}
.ccna .num{flex:0 0 34px;height:34px;line-height:34px;text-align:center;border-radius:50%;font-weight:800;color:#fff;background:rgb(var(--c))}
.ccna .road{display:flex;flex-wrap:wrap;gap:10px;align-items:center;justify-content:center;margin:18px 0}
.ccna .chip{padding:8px 18px;border-radius:999px;font-weight:700;border:1px solid rgba(var(--c),.5);background:rgba(var(--c),.12)}
.ccna .arrow{font-size:1.4em;opacity:.6}
.ccna .net{direction:ltr;display:flex;flex-wrap:wrap;gap:8px;align-items:center;justify-content:center;margin:18px 0;text-align:center}
.ccna .node{min-width:92px;padding:10px 12px;border-radius:12px;font-weight:700;border:1px solid rgba(var(--c),.5);background:rgba(var(--c),.12)}
.ccna .node small{display:block;font-weight:400;opacity:.8}
.ccna .link{font-size:.8em;opacity:.85;min-width:70px}
.ccna .tbl{overflow-x:auto;margin:16px 0}
.ccna table{width:100%;border-collapse:collapse;min-width:520px}
.ccna th,.ccna td{padding:10px 12px;border:1px solid rgba(148,163,184,.3);text-align:center}
.ccna th{background:rgba(96,165,250,.18)}
.ccna td:first-child{font-weight:700;background:rgba(148,163,184,.08)}
.ccna details{margin:10px 0;padding:10px 16px;border-radius:10px;border:1px solid rgba(148,163,184,.3);background:rgba(148,163,184,.06)}
.ccna summary{cursor:pointer;font-weight:700}
.ccna details p{margin:8px 0 2px}
</style>
<div class="ccna" dir="rtl">
<h2 class="sec">1. إيه هي الـ Network؟</h2>
<div class="box blue">
<div class="ttl">📌 التعريف</div>
<p>الـ <span class="t">Network</span> عبارة عن جهازين أو أكتر متوصلين ببعض، مباشرةً أو عن طريق جهاز توصيل، عشان <b>نشارك من خلالها بيانات أو موارد</b>.</p>
</div>
<p>طيب إيه وجه الاستفادة؟ الشبكة بتحل لنا 3 مشاكل أساسية، هنشوفهم بمثال واقعي: <b>مكتب فيه 10 موظفين</b>.</p>
<div class="grid">
<div class="box blue">
<div class="ttl">1️⃣ مشاركة البيانات <span class="t">Data Sharing</span></div>
<p><b>المشكلة:</b> الموظفين شغالين على مشروع واحد بالتوالي، كل واحد يخلص التاسك ويسلّم للي بعده.</p>
<ul>
<li>من غير شبكة هنضطر نستخدم فلاشة أو هارد متنقل</li>
<li>كل ما العدد يزيد، الوقت الضايع بيزيد ومش عملي خالص</li>
</ul>
<p><b>الحل:</b> نرفع الداتا على جهاز معيّن ونعمل لها <span class="t">Share</span>، فنوصل لها كلنا ونشتغل عليها عن بُعد.</p>
</div>
<div class="box green">
<div class="ttl">2️⃣ مشاركة الأجهزة <span class="t">Hardware / Resources</span></div>
<p><b>المشكلة:</b> الطابعة متوصلة عند موظف اسمه (س)، وكل ما حد يحتاج يطبع يروحله بالداتا على فلاشة.</p>
<ul>
<li>الموظف (س) بيتعطل عن شغله</li>
<li>الموظفين كلهم بيخسروا وقت، خصوصًا لو الطباعة كتير</li>
</ul>
<p><b>الحل:</b> نوصّل الطابعة بالشبكة ونعمل لها مشاركة، وكل الموظفين يوصلوا لها عن طريق <span class="t">IP</span> و <span class="t">Port</span> (المفهومين دول هنتكلم عنهم بعدين).</p>
</div>
<div class="box amber">
<div class="ttl">3️⃣ حماية البيانات <span class="t">Data Protection</span></div>
<p><b>المشكلة:</b> المشروع مهم جدًا ومينفعش يتحذف أو يتلف، ولو حصل هنخسر وقت ومجهود كبير.</p>
<p><b>الحل:</b> الـ <span class="t">Backup</span>، يعني ناخد نسخة من الملفات والبرامج كل فترة:</p>
<ul>
<li>كل أسبوع</li>
<li>أو كل يوم</li>
<li>أو كل ساعة لو الداتا مهمة جدًا</li>
</ul>
</div>
</div>
<h2 class="sec">2. الـ Network Components</h2>
<p>عندنا مجموعة أجهزة بتساعدنا نوصّل الـ <span class="t">End Devices</span> ببعضها وننشئ شبكة بطريقة سلسة. هنمشي عليهم بالترتيب، من الأبسط للأعقد:</p>
<div class="road">
<span class="chip blue">🔌 Hub</span><span class="arrow">←</span>
<span class="chip green">🔀 Switch</span><span class="arrow">←</span>
<span class="chip purple">🌐 Router</span>
</div>
<h2 class="sec">3. الـ Hub <span class="badge blue">Layer 1</span></h2>
<div class="box blue">
<div class="ttl">📌 إيه هو؟</div>
<p>جهاز بيربط مجموعة أجهزة مع بعض.</p>
</div>
<div class="grid">
<div class="box green">
<div class="ttl">✅ المميزات</div>
<ul>
<li>بسيط جدًا في الاستخدام</li>
<li>مش محتاج <span class="t">Configuration</span></li>
<li>سهل في الفهم والتشغيل</li>
</ul>
</div>
<div class="box red">
<div class="ttl">❌ العيوب</div>
<ul>
<li>بيبعت البيانات لجميع الـ <span class="t">Ports</span></li>
<li>مبيستخدمش الـ <span class="t">MAC Address</span> لتحديد الجهاز المستهدف</li>
<li>كل الأجهزة بتشارك نفس الـ <span class="t">Collision Domain</span></li>
</ul>
</div>
</div>
<h2 class="sec">4. الـ Switch <span class="badge green">Layer 2</span></h2>
<div class="box green">
<div class="ttl">📌 إيه هو؟</div>
<p>جهاز بيربط مجموعة أجهزة مع بعض <b>داخل نفس الشبكة</b>، بس مش بيبعت البيانات لكل الأجهزة زي الـ Hub، بل بيوجّهها <b>للجهاز المحدد</b> عن طريق الـ <span class="t">MAC</span>.</p>
<p>عشان كده بنقول عليه جهاز <span class="t">Layer 2</span>، لأنه بيقدر يستخدم الـ MAC.</p>
</div>
<div class="box amber">
<div class="ttl">💡 الفرق في سطر واحد</div>
<p><b>Hub</b> = بيصرخ في الأوضة كلها 📢 &nbsp;|&nbsp; <b>Switch</b> = بيكلم الشخص المطلوب بس 🗣️</p>
</div>
<div class="box green">
<div class="ttl">✅ إيه مميزاته؟</div>
<ul>
<li>بيربط الأجهزة داخل نفس الـ <span class="t">LAN</span></li>
<li>بيستخدم الـ <span class="t">MAC Address</span> لتحديد الجهاز المطلوب</li>
<li>بيبعت الـ <span class="t">Frame</span> للـ Port المناسب بدل ما يبعتها لكل الأجهزة</li>
<li>بيقلل الـ <span class="t">Network Traffic</span> مقارنةً بالـ Hub</li>
<li>كل Port بيمثل <span class="t">Collision Domain</span> منفصل في الشبكات الحديثة</li>
<li>الـ <span class="t">Managed Switches</span> بتدعم <span class="t">VLANs</span></li>
<li>أداء أفضل وكفاءة أعلى من الـ Hub</li>
<li>مناسب لتوصيل عدد كبير من الأجهزة</li>
</ul>
</div>
<div class="box gray">
<div class="ttl">⚠️ إيه اللي مبيقدرش يعمله؟</div>
<p>دي مش عيوب بالمعنى الحرفي، لكن حاجات لازم نعرفها أو بتبقى صعبة على المهندس وهو بيظبط الشبكة:</p>
<ul>
<li>الـ Switch العادي <b>مبيعملش <span class="t">Routing</span></b> بين الشبكات المختلفة</li>
<li>الـ <span class="t">Managed Switch</span> محتاج <span class="t">Configuration</span> وإدارة</li>
</ul>
</div>
<h2 class="sec">5. الـ Router <span class="badge purple">Layer 3</span></h2>
<div class="box purple">
<div class="ttl">📌 إيه هو؟</div>
<p>جهاز بيربط بين <b>شبكات مختلفة</b> وبيساعد في توجيه البيانات بينها.</p>
</div>
<h3>✅ إيه مميزاته؟</h3>
<div class="box purple">
<div class="step"><div class="num">1</div><div><b>بيربط بين شبكات مختلفة</b>
<p>لو جهاز في الشبكة A متصل بسويتش وعايز يكلم جهاز في <b>نفس الشبكة</b>، هيتكلم معاه عن طريق الـ <span class="t">MAC Address</span>.</p>
<p>لكن لو عايز يكلم جهاز في <b>الشبكة B</b>، هيتكلم من خلال الـ Router، وهنا محتاج <span class="t">IP</span> لأن الراوتر بيشتغل <span class="t">Layer 3</span> وبيوجّه على أساس الـ IP.</p></div></div>
<div class="net">
<div class="node blue">💻 PC<small>Network A</small></div><div class="link">MAC<br>⇄</div>
<div class="node green">🔀 Switch A</div><div class="link">⇄</div>
<div class="node purple">🌐 Router<small>بيفهم IP</small></div><div class="link">⇄</div>
<div class="node green">🔀 Switch B</div><div class="link">MAC<br>⇄</div>
<div class="node blue">💻 PC<small>Network B</small></div>
</div>
<div class="step"><div class="num">2</div><div><b>بيحدد أفضل مسار</b> للـ <span class="t">Packets</span>.</div></div>
<div class="step"><div class="num">3</div><div><b>بيستخدم الـ <span class="t">IP Address</span></b> في عملية الـ Routing.</div></div>
<div class="step"><div class="num">4</div><div><b>ممكن يوفر خدمات</b> زي <span class="t">NAT</span> و <span class="t">DHCP</span> و <span class="t">ACLs</span> (حسب نوع الجهاز).</div></div>
<div class="step"><div class="num">5</div><div><b>بيربط الـ <span class="t">LAN</span> بالـ <span class="t">WAN</span> والـ <span class="t">Internet</span>.</b></div></div>
<div class="step"><div class="num">6</div><div><b>بيساعد في التحكم</b> في حركة البيانات بين الشبكات.</div></div>
</div>
<div class="grid">
<div class="box amber">
<div class="ttl">🔁 إيه هو الـ NAT؟</div>
<p>عملية تحويل الـ <span class="t">IP</span> الداخلي (<span class="t">Private</span>) لـ <span class="t">IP</span> خارجي (<span class="t">Public</span>).</p>
</div>
<div class="box amber">
<div class="ttl">📮 إيه هو الـ DHCP؟</div>
<p>سيرفر بيقدم خدمة في الشبكة: بيدّي كل جهاز جديد بيدخل الشبكة <span class="t">IP</span> أوتوماتيك عشان يتعامل بيه مع باقي الأجهزة. (ده لما نكون شغالين <span class="t">Layer 3</span>)</p>
</div>
</div>
<div class="box red">
<div class="ttl">❌ العيوب</div>
<ul>
<li>أكتر تعقيدًا في الإعداد من الـ Switch والـ Hub</li>
<li>محتاج معرفة كويسة بالـ <span class="t">Networking</span> لإدارته</li>
<li>إعدادات الـ <span class="t">Routing</span> الغلط ممكن تسبب مشاكل في الاتصال</li>
</ul>
</div>
<h2 class="sec">6. مقارنة سريعة</h2>
<div class="tbl">
<table>
<thead><tr><th></th><th>🔌 Hub</th><th>🔀 Switch</th><th>🌐 Router</th></tr></thead>
<tbody>
<tr><td>الـ Layer</td><td>Layer 1</td><td>Layer 2</td><td>Layer 3</td></tr>
<tr><td>بيعتمد على</td><td>مفيش</td><td>MAC Address</td><td>IP Address</td></tr>
<tr><td>بيبعت البيانات لـ</td><td>كل الـ Ports</td><td>الـ Port المحدد</td><td>أفضل مسار للشبكة التانية</td></tr>
<tr><td>بيربط</td><td>أجهزة</td><td>أجهزة داخل نفس الـ LAN</td><td>شبكات مختلفة (LAN / WAN / Internet)</td></tr>
<tr><td>الـ Collision Domain</td><td>واحد مشترك</td><td>منفصل لكل Port</td><td>-</td></tr>
<tr><td>الـ Configuration</td><td>مش محتاج</td><td>Managed فقط</td><td>محتاج</td></tr>
<tr><td>خدمات إضافية</td><td>-</td><td>VLANs (Managed)</td><td>NAT / DHCP / ACLs</td></tr>
</tbody>
</table>
</div>
<h2 class="sec">7. الملخص</h2>
<div class="box green">
<div class="ttl">🎯 خلّي في بالك</div>
<ul>
<li>الشبكة بتحل 3 مشاكل: <b>مشاركة البيانات</b>، <b>مشاركة الأجهزة</b>، <b>حماية البيانات</b></li>
<li><b>Hub</b> بيبعت للكل ومش بيفهم MAC</li>
<li><b>Switch</b> بيوجّه بالـ MAC داخل نفس الشبكة</li>
<li><b>Router</b> بيوجّه بالـ IP بين الشبكات المختلفة</li>
</ul>
</div>
<h2 class="sec">8. اختبر نفسك</h2>
<details><summary>1) ليه الـ Switch أفضل من الـ Hub؟</summary><p>لأنه بيبعت الـ Frame للـ Port المحدد عن طريق الـ MAC بدل ما يبعتها لكل الأجهزة، وده بيقلل الـ Traffic وبيخلي كل Port Collision Domain منفصل.</p></details>
<details><summary>2) جهاز في الشبكة A عايز يكلم جهاز في الشبكة B، بيحتاج إيه؟</summary><p>بيحتاج Router والـ IP Address، لأن الراوتر Layer 3 وبيوجّه على أساس الـ IP.</p></details>
<details><summary>3) إيه الفرق بين الـ NAT والـ DHCP؟</summary><p>الـ NAT بيحوّل الـ IP الداخلي لـ IP خارجي، أما الـ DHCP فبيدّي كل جهاز جديد IP أوتوماتيك أول ما يدخل الشبكة.</p></details>
<details><summary>4) إمتى نستخدم الـ Backup؟</summary><p>لما تكون الداتا مهمة ومينفعش تتحذف أو تتلف، بنأخد نسخة كل أسبوع أو كل يوم أو كل ساعة حسب أهمية الداتا.</p></details>
</div>

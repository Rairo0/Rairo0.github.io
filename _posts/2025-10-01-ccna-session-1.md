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
.ccna .grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:14px;margin:16px 0}
.ccna .grid .box{margin:0}
.ccna .t{direction:ltr;unicode-bidi:isolate;display:inline-block;padding:0 8px;margin:0 2px;border-radius:6px;font-family:ui-monospace,Consolas,monospace;font-size:.9em;background:rgba(148,163,184,.18);border:1px solid rgba(148,163,184,.28)}
.ccna .step{display:flex;gap:12px;align-items:flex-start;margin:10px 0}
.ccna .step>div:last-child{flex:1}
.ccna .num{flex:0 0 34px;height:34px;line-height:34px;text-align:center;border-radius:50%;font-weight:800;color:#fff;background:rgb(var(--c))}
.ccna .sub{margin:8px 0;padding:8px 14px;border-radius:10px;border:1px dashed rgba(var(--c),.55);background:rgba(var(--c),.07)}
</style>
<div class="ccna" dir="rtl">
<h2 class="sec">إيه هي النيتوورك</h2>
<div class="box blue">
<div class="ttl">📌 التعريف</div>
<p>عبارة عن جهازين أو أكثر متصليين ببعض مباشرة أو عن طريق جهاز توصيل (ايه وجه الإستفادة ؟) بنشارك من خلالها بيانات أو موارد</p>
</div>
<div class="box purple">
<div class="ttl">مثال:</div>
<p>مكتب شغال فيه أكثر من موظف وشغالين علي مشروع بالتوالي... كل واحد يخلص التاسك ويسلم للشخص اللي بعده</p>
<p>لو معندناش <span class="t">Network</span> هنضطر نشارك البيانات دي عن طريق فلاشة أو هارد متنقل ولو عدد الموظفين اللي شغالين علي المشروع كبير</p>
<p>دا هيستهلك مننا وقت كتير ومش عملي خالص</p>
</div>
<div class="box green">
<p>....... تيجي هنا الشبكة وتحللنا المشكلة دي وهي ان انا نقدر نشارك البيانات مع بعض وننقلها عن طريق النيتوورك أو نرفع الداتا علي جهاز معين</p>
<p>ونعملها <span class="t">Share</span> ونوصلها كلنا ونشتغل عليها عن بعد</p>
</div>
<div class="box blue">
<div class="ttl">🖨️ الـ Hardware والـ resource</div>
<p>نروح لجزئية الـ<span class="t">Hardware</span> والـ<span class="t">resource</span> ناخد مثال علي الـ<span class="t">printer</span> في نفس المكتب اللي احنا فيه حاليا ونعتبر اننا 10 موظفين</p>
<p>بنحتاج نطبع ورق كتير والطابعة متوصلة عند شخص وليكن اسمه (س) وكل ما حد بيحتاج يطبع بيروحله بالداتا علي فلاشة ويطبع من عنده... هكذا</p>
<p>ودا بيسبب تعطيل للموظف اللي عنده الـ<span class="t">printer</span> وبيخسر الموظفين كلهم وقت كبير خصوصا لو بيطبعو ورق كتير</p>
<p>ونحل المشكلة دي عن طريق توصيل الـ<span class="t">printer</span> بأي جهاز ونعملها مشاركة علي الشبكة وكل الموظفين يقدرو يوصلو ليها عن طريق عنوان الـ<span class="t">ip</span></p>
<p>والـ<span class="t">port</span></p>
<p>والمفهومين دول هنتكل عليهم بعدين</p>
</div>
<div class="box amber">
<div class="ttl">🛡️ الـ Data Protection</div>
<p>تالت حاجة وهي الـ<span class="t">Data Protection</span> المشروع اللي احنا شغالين عليه حاليا مهم جدا ومينفعش يتحذف او يحصله تلف ولو دا حصل هيخسرنا وقت ومجهود كبير</p>
<p>وعشان نبعد عن الخطر دا ييجي حل بسيط اسمه الـ<span class="t">Backup</span> وهو عبارة عن اننا بناخد نسخة منن الملفات والبرامج كل فترة معينة مثلا كل اسبوع او كل يوم</p>
<p>او كل ساعة لو الداتا مهمة</p>
</div>
<h2 class="sec">ندخل علي الـ<span class="t">Network Component</span></h2>
<p>عندنا عدد من الأجهزة اللي بيساعدنا نوصل الـ<span class="t">End Devices</span> ببعضها وننشيء <span class="t">Network</span> بطريقة سلسة</p>
<h2 class="sec">أول جهاز عندنا هو الـ<span class="t">Hub</span> :</h2>
<div class="box blue">
<p>جهاز بيربط مجموعة أجهزة مع بعض</p>
</div>
<div class="grid">
<div class="box green">
<div class="ttl">المميزات:</div>
<ul>
<li>هو بسيط جدا في الإستخدام مش محتاج <span class="t">Configuration</span></li>
<li>سهل في الفهم والتشغيل</li>
</ul>
</div>
<div class="box red">
<div class="ttl">العيوب:</div>
<ul>
<li>بيبعت البيانات لجميع الـ<span class="t">Ports</span></li>
<li>لا يستخدم الـ<span class="t">MAC Address</span> لتحديد الجهاز المستهدف</li>
<li>كل الأجهزة بتشارك نفس الـ<span class="t">Collision Domain</span></li>
</ul>
</div>
</div>
<h2 class="sec">تاني جهاز معانا وهو الـ<span class="t">Switch</span> :</h2>
<div class="box green">
<p>جهاز بيربط مجموعة أجهزة مع بعض داخل نفس الشبكة بس مش بيبعت البيانات لكل الأجهزة زي الـ<span class="t">Hub</span></p>
<p>لا هو بيوجهها للجهاز المحدد عن طريق الـ<span class="t">MAC</span></p>
<p>وهنا نقدر نقول عليه انه جهاز <span class="t">layer 2</span> لإنه بيقدر يستخدم الـ<span class="t">MAC</span></p>
</div>
<div class="box green">
<div class="ttl">طيب ايه هي مميزاته ؟</div>
<ul>
<li>بيربط الأجهزة داخل نفس الـ<span class="t">LAN</span>.</li>
<li>بيستخدم الـ<span class="t">MAC Address</span> لتحديد الجهاز المطلوب.</li>
<li>بيبعت الـ<span class="t">Frame</span> للـ<span class="t">Port</span> المناسب بدل ما يبعتها لكل الأجهزة.</li>
<li>بيقلل الـ<span class="t">Network Traffic</span> مقارنة بالـ<span class="t">Hub</span>.</li>
<li>كل <span class="t">Port</span> يمثل <span class="t">Collision Domain</span> منفصل في الشبكات الحديثة.</li>
<li>الـ<span class="t">Managed Switches</span> بتدعم <span class="t">VLANs</span>.</li>
<li>بيوفر أداء أفضل وكفاءة أعلى من الـ<span class="t">Hub</span>.</li>
<li>مناسب لتوصيل عدد كبير من الأجهزة.</li>
</ul>
</div>
<div class="box gray">
<p>نروح للعيوب واللي برضو متعتبرش عيوب</p>
<p>ولكن نعرف ايه الحاجات اللي مبيقدرش يعملها او بتبقي صعبة علي المهندس وهو بيظبط الـ<span class="t">Network</span>;</p>
<ul>
<li>الـ<span class="t">Switch</span> العادي لا يقوم بعملية <span class="t">Routing</span> بين الشبكات المختلفة.</li>
<li>الـ<span class="t">Managed Switch</span> يحتاج إلى <span class="t">Configuration</span> وإدارة.</li>
</ul>
</div>
<h2 class="sec">تالت جهاز معانا هو الـ<span class="t">Router</span> :</h2>
<div class="box purple">
<p>جهاز بيربط بين شبكات مختلفة وبيساعد في توجيه البيانات بينها.</p>
</div>
<div class="box purple">
<div class="ttl">ايه هي مميزاته؟:</div>
<div class="step"><div class="num">1</div><div><b>بيربط بين شبكات مختلفة.</b>
<div class="sub">لو عندنا جهاز في الشبكة A متصل بسويتش وعايز يكلم أي جهاز في نفس الشبكة هيتكم معاه من خلال الـ<span class="t">MAC Address</span> طيب لو عايز يكلم جهاز في الشبكة B وقتها هيتكلم من خلال الـ<span class="t">Router</span> وهنا هيحتاج <span class="t">IP</span> عشان الراوتر مش بيفهم الـ<span class="t">MAC</span> هو بس بيفهم الـ<span class="t">IP</span> لإنه <span class="t">layer3</span></div></div></div>
<div class="step"><div class="num">2</div><div><b>بيحدد أفضل مسار للـ<span class="t">Packets</span>.</b></div></div>
<div class="step"><div class="num">3</div><div><b>بيستخدم الـ<span class="t">IP Address</span> في عملية الـ<span class="t">Routing</span>.</b></div></div>
<div class="step"><div class="num">4</div><div><b>ممكن يوفر خدمات زي <span class="t">NAT</span> و<span class="t">DHCP</span> و<span class="t">ACLs</span> حسب نوع الجهاز.</b>
<div class="sub">ايه هو الـ<span class="t">NAT</span>: هو عملية تحويل الـ<span class="t">ip</span> الداخلي لـ<span class="t">ip</span> خارجي</div>
<div class="sub">ايه هو الـ<span class="t">DHCP</span>: سيرفر بيقدم خدمة في الـ<span class="t">Network</span> عبارة عن انه بيدي كل جهاز جديد بيدخل الشبكة <span class="t">IP</span> عشان يتعامل بيه مع بقيت الأجهزة دا لو احنا شغالين <span class="t">layer3</span></div></div></div>
<ul>
<li>يقدر يربط الـ<span class="t">LAN</span> بالـ<span class="t">WAN</span> والـ<span class="t">Internet</span>.</li>
<li>بيساعد في التحكم في حركة البيانات بين الشبكات.</li>
</ul>
</div>
<div class="box red">
<div class="ttl">العيوب ؟:</div>
<ul>
<li>أكثر تعقيدًا في الإعداد من الـ<span class="t">Switch</span> والـ<span class="t">Hub</span>.</li>
<li>يحتاج إلى معرفة جيدة بالـ<span class="t">Networking</span> لإدارته.</li>
<li>إعدادات الـ<span class="t">Routing</span> الخاطئة ممكن تسبب مشاكل في الاتصال.</li>
</ul>
</div>
<h2 class="sec">رابع جهاز معانا هو <span class="t">NIC</span> — <span class="t">Network Interface Card</span></h2>
<div class="box blue">
<p><b>تعريفه:</b> قطعة أو واجهة بتسمح للجهاز إنه يتصل بالشبكة</p>
</div>
<div class="box green">
<div class="ttl">المميزات:</div>
<div class="step"><div class="num">1</div><div>بتسمح للجهاز بالاتصال بالشبكة</div></div>
<div class="step"><div class="num">2</div><div>بتوفر <span class="t">MAC Address</span> لواجهة الشبكة.
<div class="sub amber">قبل ما نكمل ناخد فكرة سريعة عن الـ<span class="t">MAC Address</span> هو عبارة عن عنوان 12 رقم وحرف العنوان دا مش بيتكرر علي أي كارت شبكة تاني<br>أول 6 أرقام بيعرفونا مين الشركة المصنعة لكارت الشبكة وال 6 التانيين دول عنوان الكارت ومش بيتشابهو مع أي كارت تاني لنفس الشركة</div></div></div>
<div class="step"><div class="num">3</div><div>متوفرة كـ<span class="t">Wired Ethernet</span> أو <span class="t">Wireless Wi-Fi</span>.</div></div>
<div class="step"><div class="num">4</div><div>بتدعم سرعات مختلفة حسب نوع الـ<span class="t">NIC</span>.</div></div>
<div class="step"><div class="num">5</div><div>ممكن تكون مدمجة داخل الجهاز أو <span class="t">External</span>.</div></div>
<ul>
<li>بتسمح بإرسال واستقبال البيانات عبر الشبكة.</li>
</ul>
</div>
<div class="box red">
<div class="ttl">العيوب:</div>
<ul>
<li>إمكانياتها بتختلف حسب النوع والموديل.</li>
<li>الـ<span class="t">NIC</span> القديمة ممكن تحد من سرعة الشبكة.</li>
<li>الـ<span class="t">Wireless NICs</span> بتتأثر بالتداخل والمسافة والعوائق.</li>
<li>تلف الـ<span class="t">NIC</span> ممكن يمنع الجهاز من الاتصال بالشبكة.</li>
<li>بعض الـ<span class="t">NICs</span> المتقدمة ممكن تكون مكلفة.</li>
</ul>
</div>
<h2 class="sec"><span class="t">Access Point (AP)</span>:</h2>
<div class="box blue">
<p>جهاز بيسمح للأجهزة اللاسلكية إنها تتصل بالشبكة.</p>
</div>
<div class="grid">
<div class="box green">
<div class="ttl">المميزات:</div>
<ul>
<li>بيوفر اتصال <span class="t">Wireless</span> بالشبكة.</li>
<li>بيسمح للأجهزة اللاسلكية بالاتصال بالـ<span class="t">LAN</span>.</li>
<li>بيقلل الحاجة للكابلات في توصيل الأجهزة.</li>
<li>يوسع نطاق تغطية الشبكة اللاسلكية.</li>
<li>بيسمح لعدد كبير من الأجهزة بالاتصال في نفس الوقت.</li>
</ul>
</div>
<div class="box red">
<div class="ttl">العيوب:</div>
<ul>
<li>الأداء بيتأثر بالمسافة بين الجهاز والـ<span class="t">AP</span>.</li>
<li>الإشارة ممكن تتأثر بالحوائط والعوائق.</li>
<li>السرعة الفعلية ممكن تكون أقل من السرعة النظرية.</li>
<li>محتاج <span class="t">Configuration</span> وتأمين مناسب.</li>
<li>عدد الأجهزة اللي يقدر يخدمها بكفاءة محدود حسب إمكانيات الـ<span class="t">AP</span>.</li>
<li>الاتصال <span class="t">Wireless</span> ممكن يكون أقل استقرارًا من الاتصال السلكي في بعض الحالات.</li>
</ul>
</div>
</div>
</div>

---
title: "003-CCNA: Network Categories & Message Types"
date: 2025-10-01
categories: [CCNA]
tags: [CCNA]
---

<style>
.ccna{direction:rtl;text-align:right;line-height:1.95;font-size:1.02em}
.ccna *{box-sizing:border-box}
.ccna .sec{margin:42px 0 14px;padding:10px 18px;border-radius:12px;border-right:6px solid rgb(96,165,250);background:linear-gradient(270deg,rgba(96,165,250,.22),rgba(96,165,250,0));font-weight:800}
.ccna .box{--c:148,163,184;padding:14px 20px;margin:16px 0;border-radius:12px;border:1px solid rgba(var(--c),.3);border-right:5px solid rgb(var(--c));background:rgba(var(--c),.08)}
.ccna .dg{--c:96,165,250;direction:ltr;display:flex;align-items:center;justify-content:center;margin:18px 0;padding:18px 14px;border-radius:12px;border:1px dashed rgba(148,163,184,.5);background:rgba(148,163,184,.05);overflow-x:auto}
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
.ccna .cols{direction:ltr;display:grid;grid-template-columns:repeat(auto-fit,minmax(300px,1fr));gap:14px;margin:16px 0}
.ccna .cols .dg{margin:0}
.ccna .t{direction:ltr;unicode-bidi:isolate;display:inline-block;padding:0 8px;margin:0 2px;border-radius:6px;font-family:ui-monospace,Consolas,monospace;font-size:.9em;background:rgba(148,163,184,.18);border:1px solid rgba(148,163,184,.28)}
.ccna .line{direction:ltr;text-align:left;unicode-bidi:isolate;padding:10px 16px;margin:8px 0;border-radius:10px;border:1px solid rgba(var(--c),.4);border-left:5px solid rgb(var(--c));background:rgba(var(--c),.08);font-family:ui-monospace,Consolas,monospace;font-weight:700}
.ccna .nd{flex:0 0 auto;min-width:84px;padding:8px 14px;text-align:center;border-radius:10px;font-weight:700;border:1px solid rgba(var(--c),.65);background:rgba(var(--c),.15)}
.ccna .nd.off{opacity:.3}
.ccna .wl{display:flex;flex-direction:column;align-items:center;flex:1 1 90px;min-width:90px;margin:0 8px;font-size:.8em}
.ccna .wire{position:relative;flex:1 1 60px;min-width:60px;height:2px;margin:0 8px;background:rgb(var(--c))}
.ccna .wl .wire{flex:0 0 2px;width:100%;min-width:0;margin:8px 0 0}
.ccna .wire.r::after{content:"";position:absolute;right:-2px;top:-5px;border-left:9px solid rgb(var(--c));border-top:6px solid transparent;border-bottom:6px solid transparent}
.ccna .wire.l::before{content:"";position:absolute;left:-2px;top:-5px;border-right:9px solid rgb(var(--c));border-top:6px solid transparent;border-bottom:6px solid transparent}
.ccna .wire.off{opacity:.25}
.ccna .rc{display:flex;flex-direction:column;gap:10px;margin-left:6px}
.ccna .rr{display:flex;align-items:center}
.ccna .rr .wire{flex:0 0 80px;min-width:80px}
.ccna .rr .nd{min-width:70px}
</style>
<div class="ccna" dir="rtl">
<h2 class="sec"><span class="t">Network Categories</span></h2>
<h2 class="sec"><span class="t">Simplex</span></h2>
<div class="box blue">
<p>في الـ <span class="t">Simplex</span>، البيانات بتتحرك في اتجاه واحد فقط.</p>
<p>يعني جهاز بيبعت، والجهاز التاني بيستقبل، ومفيش إمكانية للـ <span class="t">Receiver</span> إنه يبعت بيانات في الاتجاه العكسي.</p>
</div>
<div class="box purple">
<p>الـ <span class="t">TV Station</span> بتبعت الإشارة، والـ <span class="t">TV</span> بيستقبل فقط</p>
</div>
<div class="dg blue"><div class="nd">TV Station</div><div class="wire r"></div><div class="nd">TV</div></div>
<div class="grid">
<div class="box green">
<div class="ttl">المميزات:</div>
<ul>
<li><span class="t">Simple communication</span>.</li>
<li>سهل في التصميم والتنفيذ.</li>
<li>مناسب لما يكون الاتصال في اتجاه واحد فقط.</li>
</ul>
</div>
<div class="box amber">
<div class="ttl">أمثلة:</div>
<ul>
<li><span class="t">TV Broadcasting</span></li>
<li>بعض أجهزة الـ <span class="t">Sensors</span></li>
</ul>
</div>
</div>
<h2 class="sec"><span class="t">Half Duplex</span></h2>
<div class="box blue">
<p>في الـ <span class="t">Half Duplex</span>، البيانات ممكن تتحرك في الاتجاهين، لكن مش في نفس الوقت.</p>
<p>يعني الجهازين يقدروا يبعتوا ويستقبلوا، لكن لازم واحد يتكلم والتاني يستنى.</p>
</div>
<div class="box purple">
<p>لما شخص بيتكلم، الشخص التاني بيسمع.</p>
<p>بعد ما الأول يخلص، التاني يقدر يتكلم.</p>
</div>
<div class="cols">
<div class="dg purple"><div class="nd">A</div><div class="wl"><span>1</span><div class="wire r"></div></div><div class="nd">B</div></div>
<div class="dg purple"><div class="nd">A</div><div class="wl"><span>2</span><div class="wire l"></div></div><div class="nd">B</div></div>
</div>
<div class="box green">
<div class="ttl">المميزات:</div>
<ul>
<li>بيوفر <span class="t">Two-Way Communication</span>.</li>
<li>ممكن يكون مناسب للبيئات اللي مش محتاجة إرسال واستقبال في نفس الوقت.</li>
</ul>
</div>
<h2 class="sec"><span class="t">Full Duplex</span></h2>
<div class="box blue">
<p>في الـ <span class="t">Full Duplex</span>، البيانات بتتحرك في الاتجاهين في نفس الوقت.</p>
<p>يعني الجهازين يقدروا يبعتوا ويستقبلوا <span class="t">Simultaneously</span>.</p>
</div>
<div class="box purple">
<p>الاتجاهين شغالين في نفس الوقت.</p>
<p>مثال: <span class="t">Phone Call</span></p>
<p>أنت تقدر تتكلم، وفي نفس الوقت الشخص التاني يقدر يتكلم ويسمعك.</p>
</div>
<div class="dg green"><div class="nd">A</div><div class="wl"><div class="wire r"></div><div class="wire l"></div></div><div class="nd">B</div></div>
<div class="grid">
<div class="box green">
<div class="ttl">المميزات:</div>
<ul>
<li><span class="t">Two-Way Communication</span> في نفس الوقت.</li>
<li><span class="t">Higher efficiency</span>.</li>
<li>مفيش <span class="t">Waiting</span> بين الإرسال والاستقبال.</li>
<li>أفضل للـ <span class="t">Real-Time Communication</span>.</li>
</ul>
</div>
<div class="box red">
<div class="ttl">العيوب:</div>
<ul>
<li>أكثر تعقيدًا من <span class="t">Simplex</span> و<span class="t">Half Duplex</span>.</li>
</ul>
</div>
</div>
<h2 class="sec"><span class="t">Message Types on a Network</span></h2>
<div class="box blue">
<p>الـ <span class="t">Message Type</span> بيحدد مين هيستقبل الـ <span class="t">Data</span> اللي جهاز معين بيبعتها على الـ <span class="t">Network</span>.</p>
</div>
<div class="box purple">
<div class="ttl">عندنا 3 أنواع أساسية:</div>
<ul>
<li><span class="t">Unicast</span></li>
<li><span class="t">Multicast</span></li>
<li><span class="t">Broadcast</span></li>
</ul>
</div>
<h2 class="sec"><span class="t">Unicast</span></h2>
<div class="box blue">
<p>الـ <span class="t">Unicast</span> يعني إن جهاز واحد بيبعت <span class="t">Data</span> لجهاز واحد محدد</p>
</div>
<div class="box purple">
<div class="ttl">مثال:</div>
<p>لما جهازك يفتح موقع <span class="t">Web Server</span>، بيكون فيه اتصال بين جهازك والـ <span class="t">Server</span>.</p>
</div>
<div class="dg blue"><div class="nd">Sender</div><div class="rc"><div class="rr"><div class="wire r off"></div><div class="nd off">D1</div></div><div class="rr"><div class="wire r"></div><div class="nd">D2</div></div><div class="rr"><div class="wire r off"></div><div class="nd off">D3</div></div><div class="rr"><div class="wire r off"></div><div class="nd off">D4</div></div></div></div>
<div class="grid">
<div class="box green">
<div class="ttl">المميزات:</div>
<ul>
<li>الـ <span class="t">Data</span> بتوصل للـ <span class="t">Specific Device</span> المطلوب فقط.</li>
<li>بتقلل الـ <span class="t">Network Traffic</span> مقارنة بإرسال نفس البيانات لكل الأجهزة.</li>
</ul>
</div>
<div class="box red">
<div class="ttl">العيب:</div>
<ul>
<li>لو عايز تبعت نفس الـ <span class="t">Data</span> لعدد كبير من الأجهزة، ممكن تحتاج إرسالها بشكل منفصل لكل جهاز.</li>
</ul>
</div>
</div>
<div class="line blue">Unicast = One-to-One</div>
<div class="box gray">
<p>ونحل المشكلة دي ازاي ؟</p>
<p>نروح للـ <span class="t">Multicast</span></p>
</div>
<h2 class="sec"><span class="t">Multicast</span></h2>
<div class="box blue">
<p>الـ<span class="t">Multicast</span> يعني إن جهاز واحد بيبعت <span class="t">Data</span> لمجموعة محددة من الأجهزة.</p>
<p>يعني:</p>
</div>
<div class="line purple">One Sender → Multiple Specific Receivers</div>
<div class="box purple">
<p>الأجهزة اللي عايزة تستقبل الـ <span class="t">Multicast</span> بتكون مشتركة في <span class="t">Multicast Group</span>.</p>
</div>
<div class="dg purple"><div class="nd">Sender</div><div class="rc"><div class="rr"><div class="wire r"></div><div class="nd">D1</div></div><div class="rr"><div class="wire r off"></div><div class="nd off">D2</div></div><div class="rr"><div class="wire r"></div><div class="nd">D3</div></div><div class="rr"><div class="wire r"></div><div class="nd">D4</div></div><div class="rr"><div class="wire r off"></div><div class="nd off">D5</div></div></div></div>
<div class="box amber">
<div class="ttl">مثال:</div>
<p>تخيل إن عندك <span class="t">Live Video Stream</span> ومجموعة معينة من الأجهزة عايزة تستقبل الـ <span class="t">Stream</span>.</p>
<p>بدل ما الـ <span class="t">Sender</span> يبعت نسخة منفصلة لكل جهاز، ممكن يستخدم <span class="t">Multicast</span>.</p>
</div>
<div class="grid">
<div class="box green">
<div class="ttl">المميزات:</div>
<ul>
<li>أكثر كفاءة من إرسال نفس الـ <span class="t">Data</span> باستخدام عدة <span class="t">Unicast connections</span>.</li>
<li>مناسب لإرسال نفس الـ <span class="t">Data</span> إلى مجموعة محددة من الأجهزة.</li>
<li>ممكن يقلل <span class="t">Network Traffic</span>.</li>
</ul>
</div>
<div class="box red">
<div class="ttl">العيب:</div>
<ul>
<li>الأجهزة والـ <span class="t">Network</span> لازم تدعم <span class="t">Multicast</span>.</li>
<li>الـ <span class="t">Configuration</span> ممكن تكون أكثر تعقيدًا من <span class="t">Unicast</span>.</li>
</ul>
</div>
</div>
<div class="line purple">Multicast = One-to-Many (Specific Group)</div>
<div class="box gray">
<p>طب لو عايزين نبعت لكل الأجهزة اللي معانا مش بعض الأجهزة؟</p>
</div>
<h2 class="sec"><span class="t">Broadcast</span></h2>
<div class="box gray">
<p>يبقي هنستخدم الـ <span class="t">Broadcast</span></p>
</div>
<div class="box blue">
<p>الـ <span class="t">Broadcast</span> يعني إن جهاز واحد بيبعت <span class="t">Data</span> لكل الأجهزة الموجودة داخل نفس الـ <span class="t">Broadcast Domain</span>.</p>
<p>يعني:</p>
</div>
<div class="line amber">One Sender → All Devices</div>
<div class="dg amber"><div class="nd">Sender</div><div class="rc"><div class="rr"><div class="wire r"></div><div class="nd">D1</div></div><div class="rr"><div class="wire r"></div><div class="nd">D2</div></div><div class="rr"><div class="wire r"></div><div class="nd">D3</div></div><div class="rr"><div class="wire r"></div><div class="nd">D4</div></div></div></div>
<div class="box purple">
<div class="ttl">مثال:</div>
<p>من أشهر الأمثلة:</p>
<p><span class="t">DHCP Discover</span></p>
<p>لما جهاز لسه داخل الشبكة ومش عنده <span class="t">IP Address</span>، بيبعت <span class="t">DHCP Discover</span> كـ <span class="t">Broadcast</span> عشان يلاقي <span class="t">DHCP Server</span>.</p>
</div>
<div class="dg purple"><div class="nd">New Device</div><div class="wl"><span>DHCP Discover</span><div class="wire r"></div></div><div class="rc"><div class="rr"><div class="nd off">D1</div></div><div class="rr"><div class="nd">DHCP Server</div></div><div class="rr"><div class="nd off">D3</div></div></div></div>
<div class="grid">
<div class="box green">
<div class="ttl">المميزات:</div>
<ul>
<li>مفيد لما الجهاز محتاج يوصل إلى <span class="t">All Devices</span> داخل الـ <span class="t">Broadcast Domain</span>.</li>
<li>مناسب لبعض <span class="t">Network Discovery processes</span>.</li>
</ul>
</div>
<div class="box red">
<div class="ttl">العيوب:</div>
<ul>
<li>بيعمل <span class="t">Network Traffic</span> على جميع الأجهزة داخل الـ <span class="t">Broadcast Domain</span>.</li>
<li>لو الـ <span class="t">Broadcast Traffic</span> زاد جدًا، ممكن يأثر على أداء الشبكة.</li>
<li>الـ <span class="t">Router</span> عادةً بيمنع الـ <span class="t">Broadcast</span> من الانتقال بين الشبكات المختلفة.</li>
</ul>
</div>
</div>
</div>

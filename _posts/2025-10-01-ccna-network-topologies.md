\---

title: "CCNA: Network Topologies"
date: 2026-11-22
categories: \[CCNA]
tags: \[CCNA]
---

<style>
.ccna{direction:rtl;text-align:right;line-height:1.95;font-size:1.02em}
.ccna \*{box-sizing:border-box}
.ccna .sec{margin:42px 0 14px;padding:10px 18px;border-radius:12px;border-right:6px solid rgb(96,165,250);background:linear-gradient(270deg,rgba(96,165,250,.22),rgba(96,165,250,0));font-weight:800}
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
.ccna .line{direction:ltr;text-align:left;unicode-bidi:isolate;padding:10px 16px;margin:8px 0;border-radius:10px;border:1px solid rgba(var(--c),.4);border-left:5px solid rgb(var(--c));background:rgba(var(--c),.08);font-family:ui-monospace,Consolas,monospace;font-weight:700}

<div class="ccna" dir="rtl">
<h2 class="sec"><span class="t">Network Topologies</span></h2>
<div class="box blue">
<p>الـ <span class="t">Network Topology</span> هي الطريقة أو الشكل اللي بتتوصّل بيه أجهزة الشبكة مع بعضها.</p>
<p>يعني ببساطة:</p>
<p>الأجهزة متوصلة ببعض إزاي؟ ومين متصل بمين؟</p>
</div>
<div class="box purple">
<div class="ttl">عندنا 6 أنواع أساسية:</div>
<ul>
<li><span class="t">Bus Topology</span></li>
<li><span class="t">Star Topology</span></li>
<li><span class="t">Ring Topology</span></li>
<li><span class="t">Mesh Topology</span></li>
<li><span class="t">Tree Topology</span></li>
<li><span class="t">Hybrid Topology</span></li>
</ul>
</div>
<h2 class="sec"><span class="t">Bus Topology</span></h2>
<div class="box blue">
<p>في الـ <span class="t">Bus Topology</span> كل الأجهزة بتكون متوصلة على <span class="t">Cable</span> رئيسي واحد اسمه <span class="t">Backbone</span>.</p>
</div>
<div class="grid">
<div class="box green">
<div class="ttl">المميزات:</div>
<ul>
<li>بسيطة في التصميم.</li>
<li>سهلة في التركيب.</li>
<li>بتحتاج <span class="t">Cable</span> أقل، وبالتالي كانت قليلة التكلفة.</li>
</ul>
</div>
<div class="box red">
<div class="ttl">العيوب:</div>
<ul>
<li>لو الـ <span class="t">Backbone Cable</span> حصل فيه <span class="t">Failure</span>، ممكن الشبكة كلها تتأثر.</li>
<li>الـ <span class="t">Performance</span> بتقل كل ما عدد الأجهزة يزيد.</li>
<li>صعب تحديد مكان الـ <span class="t">Failure</span>.</li>
</ul>
</div>
</div>
<div class="box amber">
<div class="ttl">الاستخدام:</div>
<p>كانت شائعة في الشبكات القديمة، خصوصًا مع <span class="t">Coaxial Cable</span>، لكنها حاليًا نادرة جدًا في الشبكات الحديثة.</p>
</div>
<h2 class="sec"><span class="t">Star Topology</span></h2>
<div class="box blue">
<p>في الـ <span class="t">Star Topology</span> كل الأجهزة بتتصل بجهاز مركزي <span class="t">Central Device</span>، وغالبًا بيكون <span class="t">Switch</span>.</p>
</div>
<div class="grid">
<div class="box green">
<div class="ttl">المميزات:</div>
<ul>
<li>سهلة في الـ <span class="t">Installation</span> والـ <span class="t">Management</span>.</li>
<li>سهلة في الـ <span class="t">Troubleshooting</span>.</li>
<li>لو <span class="t">Cable</span> واحد حصل فيه مشكلة، جهاز واحد بس هو اللي هيتأثر.</li>
<li>سهل إضافة أو إزالة <span class="t">Devices</span>.</li>
<li>من أكثر الـ <span class="t">Topologies</span> استخدامًا في الـ <span class="t">LANs</span> الحديثة.</li>
</ul>
</div>
<div class="box red">
<div class="ttl">العيوب:</div>
<ul>
<li>لو الـ <span class="t">Central Switch</span> حصل فيه <span class="t">Failure</span>، الأجهزة المتصلة بيه ممكن تفقد الاتصال.</li>
<li>بتحتاج <span class="t">Cable</span> أكتر من الـ <span class="t">Bus</span>.</li>
<li>محتاجة <span class="t">Central Device</span>، وبالتالي التكلفة أعلى من الـ <span class="t">Bus</span>.</li>
</ul>
</div>
</div>
<div class="box amber">
<div class="ttl">الاستخدام:</div>
<p>دي من أشهر الـ <span class="t">Topologies</span> المستخدمة حاليًا في <span class="t">LAN Networks</span>.</p>
</div>
<h2 class="sec"><span class="t">Ring Topology</span></h2>
<div class="box blue">
<p>في الـ <span class="t">Ring Topology</span> كل جهاز بيكون متصل بالجهاز اللي قبله واللي بعده، وبالتالي الأجهزة بتكوّن حلقة مغلقة <span class="t">Closed Loop</span>.</p>
</div>
<div class="grid">
<div class="box green">
<div class="ttl">المميزات:</div>
<ul>
<li>الـ <span class="t">Data Transmission</span> ممكن تكون منظمة ويمكن التنبؤ بها في بعض <span class="t">implementations</span>.</li>
<li>في بعض أنواع الـ <span class="t">Ring</span>، بيتم تقليل احتمالية حدوث <span class="t">Collisions</span>.</li>
<li>كل <span class="t">Device</span> عنده اتصال محدد بالـ <span class="t">Devices</span> المجاورة.</li>
</ul>
</div>
<div class="box red">
<div class="ttl">العيوب:</div>
<ul>
<li><span class="t">Failure</span> في <span class="t">Device</span> أو <span class="t">Link</span> ممكن يؤثر على الـ <span class="t">Ring</span>، حسب التصميم.</li>
<li>إضافة أو إزالة <span class="t">Devices</span> ممكن تكون صعبة.</li>
<li>الـ <span class="t">Troubleshooting</span> ممكن يكون أصعب.</li>
<li>استخدامها قليل جدًا في الـ <span class="t">Modern LANs</span>.</li>
</ul>
</div>
</div>
<div class="box amber">
<div class="ttl">الاستخدام:</div>
<p>كانت مستخدمة في بعض الشبكات القديمة، مثل <span class="t">Token Ring</span>.</p>
</div>
<h2 class="sec"><span class="t">Mesh Topology</span></h2>
<div class="box blue">
<p>في الـ <span class="t">Mesh</span> الأجهزة بتكون متصلة ببعض من خلال عدة <span class="t">Links</span>.</p>
<p>عندنا نوعين مهمين:</p>
</div>
<div class="grid">
<div class="box purple">
<div class="ttl"><span class="t">Full Mesh</span></div>
<p>كل جهاز متصل بكل الأجهزة الأخرى.</p>
</div>
<div class="box purple">
<div class="ttl"><span class="t">Partial Mesh</span></div>
<p>مش كل الأجهزة متصلة ببعض، لكن بعض الأجهزة بيكون عندها <span class="t">Multiple Connections</span>.</p>
</div>
</div>
<div class="grid">
<div class="box green">
<div class="ttl">المميزات:</div>
<ul>
<li><span class="t">High Redundancy</span>.</li>
<li>وجود أكتر من <span class="t">Path</span> للـ <span class="t">Data</span>.</li>
<li>لو <span class="t">Link</span> واحد حصل فيه <span class="t">Failure</span>، ممكن الـ <span class="t">Traffic</span> يستخدم <span class="t">Path</span> تاني.</li>
</ul>
</div>
<div class="box red">
<div class="ttl">العيوب:</div>
<ul>
<li>مكلفة.</li>
<li>محتاجة عدد كبير من الـ <span class="t">Links</span> و<span class="t">Cables</span> في حالة الـ <span class="t">Full Mesh</span>.</li>
<li>الـ <span class="t">Design</span> والـ <span class="t">Management</span> أكثر تعقيدًا.</li>
<li>صعب تتوسع فيها مع عدد كبير جدًا من الأجهزة.</li>
</ul>
</div>
</div>
<div class="box amber">
<div class="ttl">الاستخدام:</div>
<p>بتستخدم في الأماكن اللي محتاجة <span class="t">Redundancy</span> و <span class="t">High Availability</span>، خصوصًا في بعض أجزاء الـ <span class="t">WAN</span>.</p>
</div>
<h2 class="sec"><span class="t">Tree Topology</span></h2>
<div class="box blue">
<p>الـ <span class="t">Tree Topology</span> عبارة عن <span class="t">Network</span> معمولة بشكل <span class="t">Hierarchical Structure</span>.</p>
<p>وغالبًا بتكون عبارة عن مجموعة من <span class="t">Star Topologies</span> مرتبطة ببعض في شكل هرمي.</p>
</div>
<div class="grid">
<div class="box green">
<div class="ttl">المميزات:</div>
<ul>
<li>سهلة في الـ التوسع.</li>
<li>مناسبة للشبكات الكبيرة.</li>
<li>بتوفر نظام او نمط هرمي واضح.</li>
<li>الـ <span class="t">Troubleshooting</span> ممكن يكون أسهل لأن الشبكة متقسمة إلى <span class="t">Branches</span>.</li>
</ul>
</div>
<div class="box red">
<div class="ttl">العيوب:</div>
<ul>
<li>لو حصل <span class="t">Failure</span> في جهاز أو <span class="t">Link</span> في مستوى أعلى، ممكن <span class="t">Branch</span> كاملة تتأثر.</li>
<li>أكثر تعقيدًا من الـ <span class="t">Star</span>.</li>
<li>بتحتاج <span class="t">Network Devices</span> و<span class="t">Cabling</span> أكتر.</li>
</ul>
</div>
</div>
<div class="box amber">
<div class="ttl">الاستخدام:</div>
<p>مناسبة للشبكات الكبيرة اللي محتاجة نظام هرمي .</p>
</div>
<h2 class="sec"><span class="t">Hybrid Topology</span></h2>
<div class="box blue">
<p>الـ <span class="t">Hybrid Topology</span> معناها إننا بنستخدم أكثر من <span class="t">Topology</span> مع بعض في نفس الشبكة.</p>
</div>
<div class="box purple">
<div class="ttl">مثلاً:</div>
<ul>
<li><span class="t">Star + Bus</span></li>
<li><span class="t">Star + Ring</span></li>
</ul>
</div>
<div class="grid">
<div class="box green">
<div class="ttl">المميزات:</div>
<ul>
<li><span class="t">Flexible</span>.</li>
<li>ممكن تصميمها حسب احتياجات الشبكة.</li>
<li>سهلة الـ <span class="t">Scalability</span> مقارنة ببعض التصاميم الأخرى.</li>
<li>ممكن نستفيد من مميزات أكثر من <span class="t">Topology</span>.</li>
</ul>
</div>
<div class="box red">
<div class="ttl">العيوب:</div>
<ul>
<li>أكثر تكلفة.</li>
<li>الـ <span class="t">Design</span> والـ <span class="t">Management</span> أكثر تعقيدًا.</li>
<li>الـ <span class="t">Troubleshooting</span> ممكن يكون أصعب.</li>
</ul>
</div>
</div>
<div class="box amber">
<div class="ttl">الاستخدام:</div>
<p>ممكن تشوفها كتير <span class="t">Large Enterprise Networks</span> لأن الشبكات الكبيرة غالبًا بتستخدم أكتر من نوع <span class="t">Topology</span> حسب كل جزء من الشبكة.</p>
</div>
<h2 class="sec">ملخص الـ <span class="t">Network Topologies</span></h2>
<div class="grid">
<div class="line blue" dir="ltr">Bus → Backbone</div>
<div class="line green" dir="ltr">Star → Central Device</div>
<div class="line purple" dir="ltr">Ring → Closed Loop</div>
<div class="line amber" dir="ltr">Mesh → Multiple Paths</div>
<div class="line red" dir="ltr">Tree → Hierarchical Structure</div>
<div class="line gray" dir="ltr">Hybrid → Combination of Multiple Topologies</div>
</div>
</div>


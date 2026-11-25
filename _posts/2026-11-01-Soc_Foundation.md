---
title: "Soc_Foundation"
date: 2026-11-01
categories: [Club]
tags: [Soc]
---

<style>
.lx{--surface:#ffffff;--surface-2:#f1f5f9;--text:#1e293b;--muted:#64748b;--border:#dde4ec;--accent:#0e7490;--accent-2:#0f766e;--accent-soft:#e3f2f6;--warn:#b45309;--crit:#b91c1c;--high:#c2410c;--ok:#0f766e;--code-bg:#0a1017;--code-bar:#101922;--code-border:#1a2733;--code-fg:#d3dde8;--inline-bg:#e4eef2;--inline-fg:#0b5c70;--shadow:0 1px 2px rgba(15,23,42,.06),0 8px 24px rgba(15,23,42,.06);--mono:ui-monospace,SFMono-Regular,Menlo,Consolas,"Liberation Mono",monospace;--sans:-apple-system,BlinkMacSystemFont,"Segoe UI",Inter,Roboto,"Helvetica Neue",Arial,sans-serif;position:relative;box-sizing:border-box;max-width:920px;margin:0 auto;padding:clamp(16px,4vw,40px);background:var(--surface);color:var(--text);font-family:var(--sans);font-size:1.02rem;line-height:1.75;border:1px solid var(--border);border-radius:16px;box-shadow:var(--shadow)}
.lx[data-theme="dark"]{--surface:#0b1218;--surface-2:#111b24;--text:#d7e0ea;--muted:#8a9bb0;--border:#1b2938;--accent:#38bdf8;--accent-2:#2dd4bf;--accent-soft:#0f2430;--warn:#f0a63a;--crit:#f07178;--high:#f08c4a;--ok:#2dd4bf;--code-bg:#070c11;--code-bar:#0c141b;--code-border:#18262f;--inline-bg:#142331;--inline-fg:#7dd3fc;--shadow:0 1px 2px rgba(0,0,0,.35),0 8px 24px rgba(0,0,0,.3)}
.lx *,.lx *::before,.lx *::after{box-sizing:border-box}
.lx-hero{position:relative;overflow:hidden;margin:0 0 1.75rem;padding:1.1rem 1.4rem 1.6rem;border-radius:14px;background:linear-gradient(135deg,#0a1017,#0d2430);color:#e6edf6}
.lx-hero .lx-term{display:flex;align-items:center;gap:7px;margin-bottom:1.3rem}
.lx-hero .dot{display:inline-block;width:10px;height:10px;border-radius:50%;background:#2b3b4d}
.lx-hero .lx-term-title{margin-left:8px;font-family:var(--mono);font-size:.78rem;color:#8fa3bd}
.lx-hero .lx-prompt{position:relative;margin:0 0 .5rem;font-family:var(--mono);font-size:.9rem;color:#9fb3c8}
.lx-hero .lx-prompt .u{color:#2dd4bf}
.lx-hero .lx-prompt .p{color:#7dd3fc}
.lx-hero .lx-prompt::after{content:"";display:inline-block;width:.55em;height:1.05em;margin-left:5px;background:#38bdf8;vertical-align:-.17em;animation:lx-blink 1.2s steps(1) infinite}
.lx-hero .lx-title{position:relative;margin:0;font-size:clamp(1.8rem,5vw,2.6rem);line-height:1.15;font-weight:700;letter-spacing:-.02em;color:#f8fafc}
.lx-hero .lx-sub{position:relative;margin:.7rem 0 0;max-width:54ch;font-size:1rem;line-height:1.6;color:#b7c4d6}
.lx-hero .lx-chips{position:relative;display:flex;flex-wrap:wrap;gap:8px;margin-top:1.2rem}
.lx-hero .lx-chips span{padding:.2rem .7rem;border:1px solid rgba(148,163,184,.35);border-radius:999px;font-size:.82rem;color:#cbd5e1}
.lx-hero .lx-radar{position:absolute;right:1.4rem;bottom:1rem;width:150px;height:150px;opacity:.9}
.lx-hero .lx-radar .pulse{transform-box:fill-box;transform-origin:center;animation:lx-pulse 2s ease-out infinite}
.lx-toggle{position:absolute;top:.9rem;right:1rem;z-index:2;padding:.25rem .75rem;border:1px solid rgba(148,163,184,.4);border-radius:999px;background:transparent;color:#cbd5e1;font:inherit;font-size:.8rem;line-height:1.5;cursor:pointer}
.lx-toggle:hover{background:rgba(148,163,184,.15)}
.lx-toc{margin:0 0 2rem;padding:1rem 1.25rem;border:1px solid var(--border);border-radius:12px;background:var(--surface-2)}
.lx-toc .toc-title{margin:0 0 .5rem;font-weight:650;color:var(--text)}
.lx-toc ul{display:grid;grid-template-columns:1fr 1fr;gap:.1rem 1.5rem;margin:0;padding:0;list-style:none}
.lx-toc li{margin:0;padding:0}
.lx-toc a{display:block;padding:.18rem 0;color:var(--muted);font-size:.93rem;line-height:1.5;text-decoration:none}
.lx-toc a:hover{color:var(--accent)}
.lx h2{margin:2.8rem 0 1rem;padding-bottom:.55rem;border-bottom:1px solid var(--border);font-size:1.55rem;line-height:1.3;font-weight:700;letter-spacing:-.01em;color:var(--text);scroll-margin-top:16px}
.lx h2::before{content:"";display:inline-block;width:5px;height:1.05em;margin-right:.65rem;border-radius:3px;background:var(--accent);vertical-align:-.15em}
.lx h3{margin:2rem 0 .6rem;font-size:1.18rem;line-height:1.4;font-weight:650;color:var(--text);scroll-margin-top:16px}
.lx h4{margin:1.2rem 0 .4rem;font-size:1rem;font-weight:650;color:var(--text)}
.lx p{margin:.8rem 0}
.lx a{color:var(--accent)}
.lx strong{font-weight:650}
.lx ul,.lx ol{margin:.8rem 0;padding-left:1.5rem}
.lx li{margin:.3rem 0}
.lx li::marker{color:var(--accent)}
.lx .src{margin:.6rem 0 0;font-size:.82rem;line-height:1.5;color:var(--muted)}
.lx blockquote{margin:1.2rem 0;padding:.6rem 1.1rem;border-left:4px solid var(--accent);border-radius:0 8px 8px 0;background:var(--accent-soft);color:var(--text)}
.lx blockquote p{margin:.3rem 0}
.lx :not(pre)>code{padding:.12em .42em;border-radius:5px;background:var(--inline-bg);color:var(--inline-fg);font-family:var(--mono);font-size:.88em;word-break:break-word}
.lx .code-card{margin:1.1rem 0;border:1px solid var(--code-border);border-radius:10px;overflow:hidden;background:var(--code-bg)}
.lx .code-bar{display:flex;align-items:center;justify-content:space-between;padding:.35rem .5rem .35rem .9rem;background:var(--code-bar);border-bottom:1px solid var(--code-border)}
.lx .code-lang{font-family:var(--mono);font-size:.76rem;color:#8fa3bd}
.lx .code-copy{padding:.15rem .65rem;border:1px solid #28394a;border-radius:6px;background:transparent;color:#b7c4d6;font:inherit;font-size:.78rem;line-height:1.6;cursor:pointer}
.lx .code-copy:hover{background:#17242f}
.lx .code-card .highlighter-rouge,.lx .code-card .highlight,.lx .code-card pre{margin:0;border:0;border-radius:0;background:transparent;box-shadow:none}
.lx pre{margin:1.1rem 0;padding:.95rem 1.1rem;overflow-x:auto;background:var(--code-bg);color:var(--code-fg);font-family:var(--mono);font-size:.88rem;line-height:1.65;tab-size:4}
.lx pre code{padding:0;border:0;background:transparent;color:inherit;font-family:inherit;font-size:inherit;word-break:normal;white-space:pre}
.lx .table-wrap{margin:1.2rem 0;overflow-x:auto;border:1px solid var(--border);border-radius:10px}
.lx table{width:100%;margin:0;border-collapse:collapse;font-size:.92rem;line-height:1.55}
.lx .table-wrap table{border:0}
.lx th,.lx td{padding:.6rem .85rem;border-bottom:1px solid var(--border);text-align:left;vertical-align:top}
.lx th{background:var(--surface-2);font-weight:650;white-space:nowrap}
.lx tr:last-child td{border-bottom:0}
.lx tbody tr:hover{background:var(--surface-2)}
.lx .callout{margin:1.3rem 0;padding:.8rem 1.1rem;border:1px solid var(--border);border-left:4px solid var(--accent);border-radius:8px;background:var(--surface-2)}
.lx .callout.warn{border-left-color:var(--warn)}
.lx .callout.ok{border-left-color:var(--ok)}
.lx .callout>:first-child{margin-top:0}
.lx .callout>:last-child{margin-bottom:0}
.lx .callout p{margin:.4rem 0}
.lx .cards{display:grid;grid-template-columns:repeat(auto-fit,minmax(230px,1fr));gap:12px;margin:1.2rem 0}
.lx .card{padding:.8rem 1rem .9rem;border:1px solid var(--border);border-top:3px solid var(--accent);border-radius:10px;background:var(--surface-2)}
.lx .card.alt{border-top-color:var(--accent-2)}
.lx .card.warn{border-top-color:var(--warn)}
.lx .card h4{margin:0 0 .35rem;font-size:1rem}
.lx .card p{margin:.3rem 0 0;font-size:.92rem;line-height:1.6}
.lx .card ul{margin:.4rem 0 0;padding-left:1.2rem;font-size:.92rem;line-height:1.55}
.lx .card li{margin:.2rem 0}
.lx .tier{display:inline-block;margin-right:.45rem;padding:.02rem .5rem;border:1px solid var(--accent);border-radius:6px;color:var(--accent);font-family:var(--mono);font-size:.78rem;font-weight:700;vertical-align:.08em}
.lx .sev{display:inline-block;margin:0 .35rem .3rem 0;padding:.05rem .65rem;border:1px solid var(--border);border-radius:999px;font-size:.82rem;font-weight:650}
.lx .sev.low{color:var(--ok);border-color:var(--ok)}
.lx .sev.med{color:var(--warn);border-color:var(--warn)}
.lx .sev.high{color:var(--high);border-color:var(--high)}
.lx .sev.crit{color:var(--crit);border-color:var(--crit)}
.lx .flow{display:flex;flex-wrap:wrap;gap:12px 28px;margin:1.3rem 0}
.lx .flow .step{position:relative;flex:1 1 105px;min-width:100px;padding:.6rem .7rem;border:1px solid var(--border);border-radius:10px;background:var(--surface-2);text-align:center}
.lx .flow .step b{display:block;font-size:.93rem;line-height:1.35;color:var(--text)}
.lx .flow .step span{display:block;margin-top:.15rem;font-size:.78rem;line-height:1.4;color:var(--muted)}
.lx .flow .step:not(:last-child)::after{content:"";position:absolute;top:50%;right:-21px;width:10px;height:10px;border-top:2px solid var(--accent-2);border-right:2px solid var(--accent-2);transform:translateY(-50%) rotate(45deg)}
.lx .hub{display:grid;grid-template-columns:1fr 1.1fr 1fr;gap:36px;margin:1.3rem 0}
.lx .hub-col{position:relative;padding:.8rem 1rem;border:1px solid var(--border);border-radius:12px;background:var(--surface-2)}
.lx .hub-col.core{border-color:var(--accent);background:var(--accent-soft)}
.lx .hub-col b{display:block;margin-bottom:.35rem;color:var(--text)}
.lx .hub-col span{display:block;padding:.12rem 0;font-size:.92rem;color:var(--muted)}
.lx .hub-col:not(:last-child)::after{content:"";position:absolute;top:50%;right:-24px;width:10px;height:10px;border-top:2px solid var(--accent-2);border-right:2px solid var(--accent-2);transform:translateY(-50%) rotate(45deg)}
.lx .chain{margin:1.2rem 0;padding:0;list-style:none}
.lx .chain li{position:relative;margin:0 0 .7rem;padding:.65rem 1rem .7rem 4.4rem;min-height:3rem;border:1px solid var(--border);border-radius:10px;background:var(--surface-2)}
.lx .chain li::before{content:attr(data-tag);position:absolute;left:.8rem;top:50%;transform:translateY(-50%);min-width:2.6rem;padding:.15rem .4rem;border:1px solid var(--accent);border-radius:6px;color:var(--accent);font-family:var(--mono);font-size:.78rem;font-weight:700;text-align:center}
.lx .chain li b{display:block}
.lx .diagram{margin:1.3rem 0;padding:.8rem;overflow-x:auto;border:1px solid var(--border);border-radius:10px;background:var(--surface-2)}
.lx .diagram svg{display:block;width:100%;min-width:560px;height:auto}
.lx .diagram .cap{margin:.5rem 0 0;font-size:.82rem;line-height:1.5;color:var(--muted);text-align:center}
.lx svg .bx{fill:var(--surface);stroke:var(--border);stroke-width:1.3}
.lx svg .bx.hl{stroke:var(--accent);stroke-width:1.6}
.lx svg .bx.wn{stroke:var(--warn);stroke-width:1.6}
.lx svg .tx{fill:var(--text);font-family:var(--sans);font-size:13px;font-weight:650}
.lx svg .sm{fill:var(--muted);font-family:var(--sans);font-size:11px;font-weight:500}
.lx svg .ln{stroke:var(--muted);stroke-width:1.4;fill:none}
.lx svg .ar{stroke:var(--accent-2);stroke-width:1.7;fill:none}
.lx svg .mk{fill:var(--accent-2)}
.lx svg .ct{fill:var(--accent);font-family:var(--sans);font-size:15px;font-weight:700}
.lx details{margin:1.2rem 0;border:1px solid var(--border);border-radius:10px;background:var(--surface-2)}
.lx summary{padding:.7rem 1rem;font-weight:650;cursor:pointer;color:var(--accent)}
.lx details[open] summary{border-bottom:1px solid var(--border)}
.lx details>:not(summary){margin-left:1rem;margin-right:1rem}
.lx details>ol{padding-left:1.5rem;margin-left:1rem}
.lx-progress{position:fixed;top:0;left:0;z-index:50;width:0;height:3px;background:var(--accent);transition:width .1s linear}
.lx-top{position:fixed;right:1.2rem;bottom:1.2rem;z-index:50;padding:.45rem .9rem;border:1px solid var(--border);border-radius:999px;background:var(--surface);color:var(--accent);font:inherit;font-size:.85rem;cursor:pointer;box-shadow:var(--shadow);opacity:0;pointer-events:none;transition:opacity .2s}
.lx-top.show{opacity:1;pointer-events:auto}
.lx a:focus-visible,.lx button:focus-visible,.lx summary:focus-visible{outline:2px solid var(--accent);outline-offset:2px}
@keyframes lx-blink{50%{opacity:0}}
@keyframes lx-pulse{0%{opacity:.9;transform:scale(1)}100%{opacity:0;transform:scale(3)}}
@media (max-width:760px){.lx .flow,.lx .hub{display:flex;flex-direction:column;gap:28px}.lx .flow .step{flex:none}.lx .flow .step:not(:last-child)::after,.lx .hub-col:not(:last-child)::after{top:auto;bottom:-20px;right:50%;transform:translateX(50%) rotate(135deg)}.lx-hero .lx-radar{display:none}}
@media (max-width:640px){.lx{border-radius:0;font-size:1rem}.lx-toc ul{grid-template-columns:1fr}.lx-hero{padding:1rem 1rem 1.3rem}.lx-toggle{position:static;margin-top:1rem}.lx h2{font-size:1.35rem}}
@media (prefers-reduced-motion:reduce){.lx-hero .lx-prompt::after,.lx-hero .lx-radar .pulse{animation:none}.lx-progress{transition:none}}
@media print{.lx-progress,.lx-top,.lx-toggle,.code-copy{display:none}.lx{border:0;box-shadow:none}}
</style>

<script>
(function () {
  'use strict';
  function ready(fn) {
    if (document.readyState !== 'loading') { fn(); }
    else { document.addEventListener('DOMContentLoaded', fn); }
  }
  function each(list, fn) { Array.prototype.forEach.call(list, fn); }
  ready(function () {
    var root = document.querySelector('.lx');
    if (!root) { return; }
    var KEY = 'lx-theme';
    var saved = null;
    try { saved = window.localStorage.getItem(KEY); } catch (e) { saved = null; }
    var dark = saved ? saved === 'dark' : true;
    var toggle = document.createElement('button');
    toggle.type = 'button';
    toggle.className = 'lx-toggle';
    function applyTheme() {
      root.setAttribute('data-theme', dark ? 'dark' : 'light');
      toggle.textContent = dark ? 'Light mode' : 'Dark mode';
    }
    toggle.addEventListener('click', function () {
      dark = !dark;
      applyTheme();
      try { window.localStorage.setItem(KEY, dark ? 'dark' : 'light'); } catch (e) { /* storage unavailable */ }
    });
    var hero = root.querySelector('.lx-hero');
    (hero || root).appendChild(toggle);
    applyTheme();
    var used = {};
    function slug(text) {
      var s = text.toLowerCase().replace(/[^a-z0-9\s-]/g, '').trim().replace(/\s+/g, '-');
      return s || 'section';
    }
    each(root.querySelectorAll('h2, h3'), function (h) {
      if (!h.id) {
        var base = slug(h.textContent);
        var id = base;
        var i = 2;
        while (used[id] || document.getElementById(id)) { id = base + '-' + i; i += 1; }
        h.id = id;
      }
      used[h.id] = true;
    });
    var tocHost = document.getElementById('lx-toc');
    var h2s = root.querySelectorAll('h2');
    if (tocHost && h2s.length) {
      tocHost.className = 'lx-toc';
      var title = document.createElement('div');
      title.className = 'toc-title';
      title.textContent = 'Contents';
      var ul = document.createElement('ul');
      each(h2s, function (h) {
        var li = document.createElement('li');
        var a = document.createElement('a');
        a.href = '#' + h.id;
        a.textContent = h.textContent;
        li.appendChild(a);
        ul.appendChild(li);
      });
      tocHost.appendChild(title);
      tocHost.appendChild(ul);
    }
    each(root.querySelectorAll('table'), function (t) {
      if (t.parentNode.classList.contains('table-wrap')) { return; }
      var wrap = document.createElement('div');
      wrap.className = 'table-wrap';
      t.parentNode.insertBefore(wrap, t);
      wrap.appendChild(t);
    });
    function copyText(text, done) {
      if (navigator.clipboard && window.isSecureContext) {
        navigator.clipboard.writeText(text).then(done, function () { fallbackCopy(text, done); });
      } else {
        fallbackCopy(text, done);
      }
    }
    function fallbackCopy(text, done) {
      var ta = document.createElement('textarea');
      ta.value = text;
      ta.setAttribute('readonly', '');
      ta.style.position = 'fixed';
      ta.style.opacity = '0';
      document.body.appendChild(ta);
      ta.select();
      try { document.execCommand('copy'); done(); } catch (e) { /* copy not supported */ }
      document.body.removeChild(ta);
    }
    each(root.querySelectorAll('pre'), function (pre) {
      var host = pre.closest('.highlighter-rouge') || pre;
      if (host.getAttribute('data-lx') || !host.parentNode) { return; }
      host.setAttribute('data-lx', '1');
      var match = (host.className || '').match(/language-([\w-]+)/);
      var lang = match ? match[1] : 'text';
      var card = document.createElement('div');
      card.className = 'code-card';
      var bar = document.createElement('div');
      bar.className = 'code-bar';
      var label = document.createElement('span');
      label.className = 'code-lang';
      label.textContent = lang;
      var btn = document.createElement('button');
      btn.type = 'button';
      btn.className = 'code-copy';
      btn.textContent = 'Copy';
      btn.addEventListener('click', function () {
        copyText(pre.textContent, function () {
          btn.textContent = 'Copied';
          window.setTimeout(function () { btn.textContent = 'Copy'; }, 1500);
        });
      });
      bar.appendChild(label);
      bar.appendChild(btn);
      host.parentNode.insertBefore(card, host);
      card.appendChild(bar);
      card.appendChild(host);
    });
    var progress = document.createElement('div');
    progress.className = 'lx-progress';
    var topBtn = document.createElement('button');
    topBtn.type = 'button';
    topBtn.className = 'lx-top';
    topBtn.setAttribute('aria-label', 'Back to top');
    topBtn.textContent = 'Back to top';
    topBtn.addEventListener('click', function () { window.scrollTo({ top: 0, behavior: 'smooth' }); });
    root.appendChild(progress);
    root.appendChild(topBtn);
    function onScroll() {
      var de = document.documentElement;
      var y = window.pageYOffset || de.scrollTop || 0;
      var max = de.scrollHeight - de.clientHeight;
      var p = max > 0 ? y / max : 0;
      progress.style.width = (Math.min(1, Math.max(0, p)) * 100) + '%';
      if (y > 600) { topBtn.classList.add('show'); } else { topBtn.classList.remove('show'); }
    }
    window.addEventListener('scroll', onScroll, { passive: true });
    window.addEventListener('resize', onScroll);
    onScroll();
  });
})();
</script>

<div class="lx" markdown="1">

<div class="lx-hero">
<div class="lx-term"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="lx-term-title">soc-console</span></div>
<p class="lx-prompt"><span class="u">analyst@soc</span>:<span class="p">~</span>$ tail -f alerts.log</p>
<p class="lx-title">SOC Foundation</p>
<p class="lx-sub">Basic SOC (Security Operations Center): what it is, how it works, who does what, and how incidents are handled.</p>
<div class="lx-chips"><span>Club</span><span>SOC</span><span>Security Operations</span></div>
<svg class="lx-radar" viewBox="0 0 200 200" aria-hidden="true" focusable="false"><g fill="none" stroke="#38bdf8" stroke-opacity=".35" stroke-width="1.2"><circle cx="100" cy="100" r="88"/><circle cx="100" cy="100" r="66"/><circle cx="100" cy="100" r="44"/><circle cx="100" cy="100" r="22"/><path d="M12 100 H188 M100 12 V188"/></g><path d="M100 100 L100 12 A88 88 0 0 1 162 38 Z" fill="#38bdf8" fill-opacity=".14"/><circle cx="100" cy="100" r="3" fill="#38bdf8"/><circle cx="140" cy="58" r="3.5" fill="#f0a63a"/><circle class="pulse" cx="140" cy="58" r="3.5" fill="#f0a63a"/><circle cx="68" cy="132" r="3" fill="#2dd4bf"/><circle cx="124" cy="150" r="3" fill="#2dd4bf"/></svg>
</div>

<div id="lx-toc"></div>

## 1. What Is a SOC?

SOC stands for **Security Operations Center**.

A SOC is a centralized team responsible for monitoring, detecting, analyzing, and responding to cybersecurity threats and incidents within an organization.

Its main goal is to protect the organization's systems, networks, and data from cyber threats.

<div class="hub">
<div class="hub-col"><b>Data sources</b><span>Servers</span><span>Endpoints</span><span>Firewalls</span><span>Network devices</span></div>
<div class="hub-col core"><b>SOC</b><span>Monitor</span><span>Detect</span><span>Analyze</span><span>Respond</span></div>
<div class="hub-col"><b>Protected</b><span>Systems</span><span>Networks</span><span>Data</span></div>
</div>

A SOC is usually described as a combination of three things:

<div class="cards">
<div class="card"><h4>People</h4><p>Analysts, responders, and a manager, organized into tiers (sections 4 and 5).</p></div>
<div class="card alt"><h4>Process</h4><p>A defined workflow from monitoring to reporting, and an incident response lifecycle (sections 3 and 7).</p></div>
<div class="card warn"><h4>Technology</h4><p>Security tools that collect logs and raise alerts, such as a SIEM (section 3).</p></div>
</div>

## 2. What Does a SOC Do in a Company?

<div class="cards">
<div class="card"><h4>Monitor</h4><p>Monitor the company's network and systems.</p></div>
<div class="card"><h4>Detect</h4><p>Detect suspicious activities and cyber threats.</p></div>
<div class="card"><h4>Analyze</h4><p>Analyze security alerts.</p></div>
<div class="card alt"><h4>Investigate</h4><p>Investigate potential security incidents.</p></div>
<div class="card alt"><h4>Respond</h4><p>Respond to cyberattacks.</p></div>
<div class="card alt"><h4>Protect</h4><p>Protect sensitive company data.</p></div>
<div class="card warn"><h4>Reduce risk</h4><p>Reduce security risks.</p></div>
</div>

## 3. How Does a SOC Work?

<div class="flow">
<div class="step"><b>1. Monitoring</b><span>watch traffic and systems</span></div>
<div class="step"><b>2. Log Collection</b><span>gather logs</span></div>
<div class="step"><b>3. Detection</b><span>spot suspicious activity</span></div>
<div class="step"><b>4. Alert Generation</b><span>raise an alert</span></div>
<div class="step"><b>5. Investigation</b><span>real threat or not?</span></div>
<div class="step"><b>6. Response</b><span>contain and resolve</span></div>
<div class="step"><b>7. Reporting</b><span>document and report</span></div>
</div>

| Step | What happens | Illustrative example |
|------|--------------|----------------------|
| 1. Monitoring | Continuously monitor network traffic and systems. | Analysts watch dashboards for login and network activity. |
| 2. Log Collection | Collect logs from servers, endpoints, firewalls, and other devices. | Authentication logs from a server arrive in a central system. |
| 3. Detection | Identify suspicious activities using security tools. | A rule matches many failed logins followed by a success. |
| 4. Alert Generation | Generate alerts when potential threats are detected. | The tool raises an alert with a severity. |
| 5. Investigation | Analyze alerts to determine whether they represent real threats. | An analyst checks the account, the source IP, and the time. |
| 6. Response | Take appropriate actions to contain and resolve incidents. | Reset the password, disable the account, block the IP. |
| 7. Reporting | Document incidents and prepare security reports. | The ticket records what happened and what was done. |

### 3.1 Example: One Alert, Step by Step

The log lines below are an illustrative example, not real data (`203.0.113.45` is a documentation-only IP address).

```text
09:14:02  auth  FAILED   user=sara  src=203.0.113.45
09:14:05  auth  FAILED   user=sara  src=203.0.113.45
09:14:09  auth  FAILED   user=sara  src=203.0.113.45
09:14:14  auth  SUCCESS  user=sara  src=203.0.113.45

ALERT  severity=High  rule="Multiple failed logins followed by a success"
```

The logs were collected (step 2), a detection rule matched (step 3), and an alert was generated (step 4). Now an analyst investigates (step 5): is this the real user who forgot a password, or an attacker who guessed it?

### 3.2 Supporting Tools

These tools are not part of the slides, but you will hear them in almost every SOC discussion.

| Tool | Purpose |
|------|---------|
| SIEM (Security Information and Event Management) | Collects and correlates logs from many sources and raises alerts. |
| EDR (Endpoint Detection and Response) | Monitors endpoints for suspicious behavior and supports response actions such as isolating a host. |
| IDS / IPS | An IDS detects suspicious network activity; an IPS can also block it. |
| Firewall | Filters traffic by rules. Its logs are an important data source. |
| SOAR (Security Orchestration, Automation and Response) | Automates repetitive tasks and response workflows. |
| Threat intelligence | Information about known threats and indicators (IP addresses, domains, file hashes) used to enrich alerts. |

## 4. SOC Team Structure

A typical SOC team consists of:

* SOC Analyst L1 (Tier 1).
* SOC Analyst L2 (Tier 2).
* SOC Analyst L3 (Tier 3).
* SOC Manager.
* Incident Responder.

<div class="diagram">
<svg viewBox="0 0 700 215" role="img" aria-label="SOC team structure: the SOC Manager oversees L1, L2, L3 analysts and the Incident Responder"><path class="ln" d="M350 64 V100 M85 100 H605 M85 100 V140 M255 100 V140 M425 100 V140 M605 100 V140"/><rect class="bx hl" x="250" y="10" width="200" height="54" rx="10"/><text class="tx" x="350" y="34" text-anchor="middle">SOC Manager</text><text class="sm" x="350" y="51" text-anchor="middle">Oversees operations</text><rect class="bx" x="10" y="140" width="150" height="60" rx="10"/><text class="tx" x="85" y="166" text-anchor="middle">SOC Analyst L1</text><text class="sm" x="85" y="184" text-anchor="middle">Tier 1</text><rect class="bx" x="180" y="140" width="150" height="60" rx="10"/><text class="tx" x="255" y="166" text-anchor="middle">SOC Analyst L2</text><text class="sm" x="255" y="184" text-anchor="middle">Tier 2</text><rect class="bx" x="350" y="140" width="150" height="60" rx="10"/><text class="tx" x="425" y="166" text-anchor="middle">SOC Analyst L3</text><text class="sm" x="425" y="184" text-anchor="middle">Tier 3</text><rect class="bx" x="520" y="140" width="170" height="60" rx="10"/><text class="tx" x="605" y="166" text-anchor="middle">Incident Responder</text><text class="sm" x="605" y="184" text-anchor="middle">Coordinates response</text></svg>
<p class="cap">Figure: a typical SOC team. Structure varies by organization; in small SOCs one person may cover several roles.</p>
</div>

Alerts move up the tiers as they get more serious or more complex:

<div class="flow">
<div class="step"><b>L1</b><span>monitor, triage, escalate</span></div>
<div class="step"><b>L2</b><span>deeper investigation</span></div>
<div class="step"><b>L3</b><span>advanced analysis and hunting</span></div>
</div>

## 5. SOC Roles and Responsibilities

### 5.1 SOC Analyst L1 (Tier 1)

<div class="card" markdown="1">

<span class="tier">L1</span> **Responsibilities**

* Monitor security alerts.
* Perform initial alert investigation.
* Identify false positives.
* Classify alerts based on severity.
* Collect basic investigation information.
* Escalate suspicious incidents to L2.

</div>

How an L1 analyst handles an alert:

<div class="diagram">
<svg viewBox="0 0 700 215" role="img" aria-label="L1 alert triage: an alert is received, checked, then either closed as a false positive or classified and escalated to L2"><defs><marker id="arw1" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path class="mk" d="M0 0 L10 5 L0 10 z"/></marker></defs><rect class="bx" x="10" y="75" width="120" height="50" rx="10"/><text class="tx" x="70" y="104" text-anchor="middle">Alert received</text><path class="bx hl" d="M215 58 L282 100 L215 142 L148 100 Z"/><text class="tx" x="215" y="105" text-anchor="middle">Real threat?</text><rect class="bx" x="330" y="70" width="170" height="60" rx="10"/><text class="tx" x="415" y="97" text-anchor="middle">Classify severity</text><text class="sm" x="415" y="115" text-anchor="middle">collect basic information</text><rect class="bx wn" x="530" y="75" width="160" height="50" rx="10"/><text class="tx" x="610" y="104" text-anchor="middle">Escalate to L2</text><rect class="bx" x="120" y="168" width="190" height="42" rx="10"/><text class="tx" x="215" y="194" text-anchor="middle">False positive: close and record</text><path class="ar" d="M130 100 H146" marker-end="url(#arw1)"/><path class="ar" d="M282 100 H328" marker-end="url(#arw1)"/><path class="ar" d="M500 100 H528" marker-end="url(#arw1)"/><path class="ar" d="M215 142 V166" marker-end="url(#arw1)"/><text class="sm" x="305" y="92" text-anchor="middle">Yes</text><text class="sm" x="228" y="158">No</text></svg>
<p class="cap">Figure: simplified L1 triage flow.</p>
</div>

Alerts are classified by severity. The level names vary between organizations; a common scale is:

<span class="sev low">Low</span><span class="sev med">Medium</span><span class="sev high">High</span><span class="sev crit">Critical</span>

### 5.2 SOC Analyst L2 (Tier 2)

<div class="card alt" markdown="1">

<span class="tier">L2</span> **Responsibilities**

* Perform deeper security investigations.
* Analyze suspicious activities.
* Investigate malware and network attacks.
* Identify the scope of security incidents.
* Recommend containment actions.
* Handle escalated alerts from L1.

</div>

### 5.3 SOC Analyst L3 (Tier 3)

<div class="card warn" markdown="1">

<span class="tier">L3</span> **Responsibilities**

* Perform advanced threat hunting.
* Analyze complex security incidents.
* Conduct advanced malware analysis.
* Investigate Advanced Persistent Threats (APTs).
* Develop and improve detection rules.
* Support L1 and L2 analysts.

</div>

### 5.4 SOC Manager

<div class="card" markdown="1">

<span class="tier">MGR</span> **Responsibilities**

* Manage SOC operations.
* Supervise the SOC team.
* Assign responsibilities and tasks.
* Monitor team performance.
* Ensure security policies are followed.
* Coordinate with other departments.
* Report security performance to management.

</div>

### 5.5 Tiers at a Glance

| Tier | Main focus | Typical hand-off |
|------|------------|------------------|
| L1 | Monitoring, triage, initial investigation | Escalates suspicious incidents to L2 |
| L2 | Deeper investigation, incident scope, containment recommendations | Handles L1 escalations; complex cases go to L3 |
| L3 | Threat hunting, malware analysis, APTs, detection rules | Supports L1 and L2 |
| SOC Manager | Operations, team, performance, reporting | Coordinates with other departments and management |

## 6. Who Is Responsible When an Incident Happens?

Incident responsibility is shared between different SOC roles.

<ol class="chain">
<li data-tag="L1"><b>L1 Analyst</b>Detects and performs initial investigation.</li>
<li data-tag="L2"><b>L2 Analyst</b>Conducts deeper investigation and determines incident scope.</li>
<li data-tag="L3"><b>L3 Analyst</b>Handles advanced technical analysis.</li>
<li data-tag="IR"><b>Incident Responder</b>Coordinates and performs incident response activities.</li>
<li data-tag="MGR"><b>SOC Manager</b>Oversees SOC operations and coordinates resources.</li>
</ol>

<div class="callout" markdown="1">

The exact assignment of duties is defined by each organization's incident response plan. The roles above describe the typical split.

</div>

## 7. Incident Response Process

The Incident Response Lifecycle consists of six main phases:

<div class="diagram">
<svg viewBox="0 0 640 360" role="img" aria-label="Incident response lifecycle: Preparation, Detection and Analysis, Containment, Eradication, Recovery, Lessons Learned, then back to Preparation"><defs><marker id="arw2" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path class="mk" d="M0 0 L10 5 L0 10 z"/></marker></defs><rect class="bx hl" x="235" y="14" width="170" height="44" rx="10"/><text class="tx" x="320" y="41" text-anchor="middle">1. Preparation</text><rect class="bx" x="445" y="88" width="170" height="44" rx="10"/><text class="tx" x="530" y="115" text-anchor="middle">2. Detection &amp; Analysis</text><rect class="bx" x="445" y="228" width="170" height="44" rx="10"/><text class="tx" x="530" y="255" text-anchor="middle">3. Containment</text><rect class="bx" x="235" y="302" width="170" height="44" rx="10"/><text class="tx" x="320" y="329" text-anchor="middle">4. Eradication</text><rect class="bx" x="25" y="228" width="170" height="44" rx="10"/><text class="tx" x="110" y="255" text-anchor="middle">5. Recovery</text><rect class="bx wn" x="25" y="88" width="170" height="44" rx="10"/><text class="tx" x="110" y="115" text-anchor="middle">6. Lessons Learned</text><path class="ar" d="M405 40 L505 86" marker-end="url(#arw2)"/><path class="ar" d="M530 132 V226" marker-end="url(#arw2)"/><path class="ar" d="M505 274 L405 320" marker-end="url(#arw2)"/><path class="ar" d="M235 324 L135 274" marker-end="url(#arw2)"/><path class="ar" d="M110 228 V134" marker-end="url(#arw2)"/><path class="ar" d="M135 88 L235 40" marker-end="url(#arw2)"/><text class="ct" x="320" y="176" text-anchor="middle">Incident Response</text><text class="ct" x="320" y="198" text-anchor="middle">Lifecycle</text></svg>
<p class="cap">Figure: the six-phase incident response lifecycle. Lessons learned feed back into preparation.</p>
</div>

<div class="cards">
<div class="card"><h4>1. Preparation</h4><p>Establish policies, tools, and response plans.</p><ul><li>Examples: an incident response plan, contact lists, logging in place, team training.</li></ul></div>
<div class="card"><h4>2. Detection &amp; Analysis</h4><p>Identify and investigate security incidents.</p><ul><li>Examples: confirm the alert is real, find what is affected, set the priority.</li></ul></div>
<div class="card alt"><h4>3. Containment</h4><p>Limit the impact and prevent further damage.</p><ul><li>Examples: isolate an infected host, disable a compromised account, block a malicious IP.</li></ul></div>
<div class="card alt"><h4>4. Eradication</h4><p>Remove the threat from affected systems.</p><ul><li>Examples: remove malware, close the exploited weakness, remove attacker access.</li></ul></div>
<div class="card alt"><h4>5. Recovery</h4><p>Restore affected systems to normal operation.</p><ul><li>Examples: restore from clean backups, rebuild systems, monitor closely afterwards.</li></ul></div>
<div class="card warn"><h4>6. Lessons Learned</h4><p>Review the incident and improve security measures.</p><ul><li>Examples: a post-incident review, updated detection rules and procedures.</li></ul></div>
</div>

<div class="callout" markdown="1">

**About the models.** This six-phase lifecycle matches the SANS PICERL model: Preparation, Identification, Containment, Eradication, Recovery, Lessons Learned. NIST SP 800-61 Rev. 2 (2012) described four phases: Preparation; Detection and Analysis; Containment, Eradication, and Recovery; Post-Incident Activity. NIST SP 800-61 Rev. 3 (April 2025) supersedes Rev. 2 and aligns incident response with the NIST Cybersecurity Framework (CSF) 2.0 functions.

</div>

## 8. Key Terms

| Term | Meaning |
|------|---------|
| Alert | A notification raised when activity matches a detection rule or looks suspicious. |
| False positive | An alert for activity that is actually harmless. |
| True positive | An alert for activity that really is malicious or violates policy. |
| Triage | Sorting alerts by severity and priority to decide what to handle first. |
| Escalation | Passing an alert or incident to a higher tier. |
| Incident | A security event that actually or imminently harms the confidentiality, integrity, or availability of systems or data. |
| Scope | Which systems, accounts, and data an incident affects. |
| Containment | Actions that limit the impact of an incident and stop it from spreading. |
| Threat hunting | Proactively searching for threats that automated detection missed. |
| APT (Advanced Persistent Threat) | A skilled, well-resourced attacker running a long-term, targeted intrusion. |
| Detection rule | The logic that defines which activity triggers an alert. |

## 9. Review

### 9.1 Key Takeaways

* A SOC is a centralized team that monitors, detects, analyzes, and responds to cyber threats.
* The workflow runs in seven steps: monitoring, log collection, detection, alert generation, investigation, response, reporting.
* L1 triages alerts and escalates; L2 investigates deeper; L3 hunts threats and improves detection rules.
* The SOC Manager runs operations; the Incident Responder coordinates and performs response.
* The incident response lifecycle has six phases and ends with lessons learned that improve preparation.

### 9.2 Review Questions

1. What does SOC stand for, and what is its main goal?
2. Name the seven steps of how a SOC works.
3. What is the difference between a false positive and a true positive?
4. Who escalates to whom between L1, L2, and L3?
5. Who coordinates and performs incident response activities?
6. Name the six phases of the incident response lifecycle.

<details markdown="1">
<summary>Answers</summary>

1. Security Operations Center. Its goal is to protect the organization's systems, networks, and data from cyber threats.
2. Monitoring, log collection, detection, alert generation, investigation, response, reporting.
3. A false positive is an alert for harmless activity; a true positive is an alert for real malicious activity.
4. L1 escalates suspicious incidents to L2. L2 handles escalated alerts, and complex incidents go to L3, who also supports L1 and L2.
5. The Incident Responder.
6. Preparation, Detection and Analysis, Containment, Eradication, Recovery, Lessons Learned.

</details>

## 10. References

* [NIST SP 800-61 Rev. 3: Incident Response Recommendations and Considerations for Cybersecurity Risk Management](https://csrc.nist.gov/pubs/sp/800/61/r3/final)
* [NIST Incident Response project page](https://csrc.nist.gov/projects/incident-response)

</div>

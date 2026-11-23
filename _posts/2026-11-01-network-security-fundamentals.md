---
title: "Network Security Fundamentals"
date: 2026-11-01
categories: [Club]
tags: [Network Security]
---

<style>
.lx{--surface:#ffffff;--surface-2:#f1f5f9;--text:#1e293b;--muted:#64748b;--border:#e2e8f0;--accent:#1d4ed8;--accent-2:#0e7490;--accent-soft:#e8effd;--ok:#0f766e;--warn:#b45309;--code-bg:#0b1324;--code-bar:#111c33;--code-border:#1b2a47;--code-fg:#d6e2f0;--inline-bg:#e7edf8;--inline-fg:#1e40af;--shadow:0 1px 2px rgba(15,23,42,.06),0 8px 24px rgba(15,23,42,.06);--mono:ui-monospace,SFMono-Regular,Menlo,Consolas,"Liberation Mono",monospace;--sans:-apple-system,BlinkMacSystemFont,"Segoe UI",Inter,Roboto,"Helvetica Neue",Arial,sans-serif;position:relative;box-sizing:border-box;max-width:920px;margin:0 auto;padding:clamp(16px,4vw,40px);background:var(--surface);color:var(--text);font-family:var(--sans);font-size:1.02rem;line-height:1.75;border:1px solid var(--border);border-radius:16px;box-shadow:var(--shadow)}
.lx[data-theme="dark"]{--surface:#0e1626;--surface-2:#15213a;--text:#dbe4f0;--muted:#8fa0b8;--border:#1f2d47;--accent:#60a5fa;--accent-2:#22b8cf;--accent-soft:#12233f;--ok:#2dd4bf;--warn:#e0a458;--code-bg:#070d1a;--code-bar:#0c1527;--code-border:#1b2a47;--inline-bg:#192846;--inline-fg:#93c5fd;--shadow:0 1px 2px rgba(0,0,0,.3),0 8px 24px rgba(0,0,0,.25)}
.lx *,.lx *::before,.lx *::after{box-sizing:border-box}
.lx-hero{position:relative;overflow:hidden;margin:0 0 1.75rem;padding:1.1rem 1.4rem 1.6rem;border-radius:14px;background:linear-gradient(135deg,#0b1324,#0e2a4a);color:#e6edf6}
.lx-hero .lx-term{display:flex;align-items:center;gap:7px;margin-bottom:1.3rem}
.lx-hero .dot{display:inline-block;width:10px;height:10px;border-radius:50%;background:#334766}
.lx-hero .lx-term-title{margin-left:8px;font-family:var(--mono);font-size:.78rem;color:#8fa3bd}
.lx-hero .lx-prompt{margin:0 0 .5rem;font-family:var(--mono);font-size:.9rem;color:#9fb3c8}
.lx-hero .lx-prompt .u{color:#22b8cf}
.lx-hero .lx-prompt .p{color:#8fb4f7}
.lx-hero .lx-prompt::after{content:"";display:inline-block;width:.55em;height:1.05em;margin-left:5px;background:#60a5fa;vertical-align:-.17em;animation:lx-blink 1.2s steps(1) infinite}
.lx-hero .lx-title{position:relative;margin:0;font-size:clamp(1.8rem,5vw,2.6rem);line-height:1.15;font-weight:700;letter-spacing:-.02em;color:#f8fafc}
.lx-hero .lx-sub{position:relative;margin:.7rem 0 0;max-width:56ch;font-size:1rem;line-height:1.6;color:#b7c4d6}
.lx-hero .lx-chips{position:relative;display:flex;flex-wrap:wrap;gap:8px;margin-top:1.2rem}
.lx-hero .lx-chips span{padding:.2rem .7rem;border:1px solid rgba(148,163,184,.35);border-radius:999px;font-size:.82rem;color:#cbd5e1}
.lx-hero .lx-net{position:absolute;right:1.2rem;bottom:.9rem;width:230px;height:auto;opacity:.85}
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
.lx .code-copy{padding:.15rem .65rem;border:1px solid #2a3d5e;border-radius:6px;background:transparent;color:#b7c4d6;font:inherit;font-size:.78rem;line-height:1.6;cursor:pointer}
.lx .code-copy:hover{background:#1a2a47}
.lx .code-card .highlighter-rouge,.lx .code-card .highlight,.lx .code-card pre{margin:0;border:0;border-radius:0;background:transparent;box-shadow:none}
.lx pre{margin:1.1rem 0;padding:.95rem 1.1rem;overflow-x:auto;background:var(--code-bg);color:var(--code-fg);font-family:var(--mono);font-size:.88rem;line-height:1.65;tab-size:4}
.lx pre code{padding:0;border:0;background:transparent;color:inherit;font-family:inherit;font-size:inherit;word-break:normal;white-space:pre}
.lx .highlight .c,.lx .highlight .c1,.lx .highlight .cm,.lx .highlight .cs{color:#7b8aa0;font-style:italic}
.lx .highlight .k,.lx .highlight .kd,.lx .highlight .kn,.lx .highlight .kr{color:#67d4e4}
.lx .highlight .nb,.lx .highlight .nf,.lx .highlight .nc{color:#8fb4f7}
.lx .highlight .nv,.lx .highlight .vi,.lx .highlight .vg{color:#c4b5fd}
.lx .highlight .s,.lx .highlight .s1,.lx .highlight .s2,.lx .highlight .sb,.lx .highlight .sd{color:#d9b77e}
.lx .highlight .o,.lx .highlight .p{color:#94a3b8}
.lx .highlight .m,.lx .highlight .mi{color:#e0a96d}
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
.lx .callout ul,.lx .callout ol{margin:.4rem 0}
.lx .cards{display:grid;grid-template-columns:repeat(auto-fit,minmax(230px,1fr));gap:12px;margin:1.2rem 0}
.lx .card{padding:.8rem 1rem .9rem;border:1px solid var(--border);border-top:3px solid var(--accent);border-radius:10px;background:var(--surface-2)}
.lx .card.alt{border-top-color:var(--accent-2)}
.lx .card.open{border-top-color:var(--ok)}
.lx .card.closed{border-top-color:var(--muted)}
.lx .card.filtered{border-top-color:var(--warn)}
.lx .card h4{margin:0 0 .35rem;font-size:1rem}
.lx .card p{margin:0;font-size:.92rem;line-height:1.6}
.lx .flow{display:flex;flex-wrap:wrap;gap:12px 28px;margin:1.3rem 0}
.lx .flow .step{position:relative;flex:1 1 105px;min-width:100px;padding:.6rem .7rem;border:1px solid var(--border);border-radius:10px;background:var(--surface-2);text-align:center}
.lx .flow .step b{display:block;font-size:.93rem;line-height:1.35;color:var(--text)}
.lx .flow .step span{display:block;margin-top:.15rem;font-size:.78rem;line-height:1.4;color:var(--muted)}
.lx .flow .step:not(:last-child)::after{content:"";position:absolute;top:50%;right:-21px;width:10px;height:10px;border-top:2px solid var(--accent-2);border-right:2px solid var(--accent-2);transform:translateY(-50%) rotate(45deg)}
.lx .osi{display:grid;grid-template-columns:1.5fr 1.5fr .8fr 1.2fr;gap:6px;margin:1.2rem 0;font-size:.9rem;line-height:1.4}
.lx .osi>div{padding:.5rem .7rem;border-radius:8px;background:var(--surface-2);border:1px solid var(--border)}
.lx .osi .hd{background:transparent;border-color:transparent;color:var(--muted);font-size:.8rem;padding-top:.1rem;padding-bottom:.1rem}
.lx .osi .num{display:inline-block;min-width:1.2em;margin-right:.35rem;font-weight:700;color:var(--accent)}
.lx .osi .map{display:none;margin-top:.15rem;font-size:.75rem;color:var(--muted)}
.lx .osi .tcpip{display:flex;align-items:center;justify-content:center;grid-column:4;text-align:center;font-weight:650;border-color:var(--accent-2);background:var(--accent-soft)}
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
@media (max-width:760px){.lx .flow{flex-direction:column;gap:28px}.lx .flow .step{flex:none}.lx .flow .step:not(:last-child)::after{top:auto;bottom:-20px;right:50%;transform:translateX(50%) rotate(135deg)}.lx-hero .lx-net{display:none}}
@media (max-width:640px){.lx{border-radius:0;font-size:1rem}.lx-toc ul{grid-template-columns:1fr}.lx-hero{padding:1rem 1rem 1.3rem}.lx-toggle{position:static;margin-top:1rem}.lx h2{font-size:1.35rem}.lx .osi{grid-template-columns:1.6fr 1.3fr .9fr}.lx .osi .tcpip,.lx .osi .hd4{display:none}.lx .osi .map{display:block}}
@media (prefers-reduced-motion:reduce){.lx-hero .lx-prompt::after{animation:none}.lx-progress{transition:none}}
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
    var dark = saved ? saved === 'dark' : !!(window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches);
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
<div class="lx-term"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="lx-term-title">lab</span></div>
<p class="lx-prompt"><span class="u">student@lab</span>:<span class="p">~</span>$ nmap -sn 192.168.56.0/24</p>
<p class="lx-title">Network Security Fundamentals</p>
<p class="lx-sub">From packets to ports: how networks work and how a penetration tester sees them.</p>
<div class="lx-chips"><span>Club</span><span>Network Security</span><span>Introduction to Cybersecurity</span><span>First-Year Lecture</span></div>
<svg class="lx-net" viewBox="0 0 260 160" aria-hidden="true" focusable="false"><g fill="none" stroke="#60a5fa" stroke-opacity=".4" stroke-width="1.3"><path d="M30 120 L100 55 L180 95 L235 35"/><path d="M100 55 L120 140 L180 95"/><path d="M30 120 L120 140"/><path d="M180 95 L235 125"/></g><g fill="#0b1324" stroke="#60a5fa" stroke-width="1.7"><circle cx="30" cy="120" r="7"/><circle cx="100" cy="55" r="8"/><circle cx="180" cy="95" r="8"/><circle cx="235" cy="35" r="6"/><circle cx="120" cy="140" r="6"/><circle cx="235" cy="125" r="6"/></g><circle cx="180" cy="95" r="3" fill="#22b8cf"/></svg>
</div>

<div id="lx-toc"></div>

<div class="callout warn" markdown="1">

**Authorized use only.** All practical work must stay inside a local lab or an explicitly authorized environment. Only scan machines in your own lab, or machines you have written permission to test.

</div>

This lecture is not about memorizing definitions. We will learn how computers talk to each other, and then look at the same network through an attacker's eyes, the way a penetration tester does.

Start with a question: when you open a website, what do you think happens in the 200 milliseconds before the page appears? By the end of the lecture you will be able to answer it in detail.

## Lecture Roadmap

| Part | Topic |
|------|-------|
| 1 | Computer Networks |
| 2 | Network Models |
| 3 | TCP vs UDP |
| 4 | DNS |
| 5 | Enumeration and Recon |
| 6 | Nmap |
| 7 | Hands-on Lab |

**Goal:** understand the network well enough to explain what an attacker sees from one IP address.

Every networking concept we learn is also a security concept. A switch is also a place to sniff traffic, DNS is also a place to leak information, and an open port is also a possible entry point. No prior knowledge is assumed: if you have ever used the terms IP address or Wi-Fi password, you already have a starting point.

Sources: Course outline
{: .src}

## 1. Computer Networks

### 1.1 What Is a Network? Types by Scale

A computer network is two or more devices connected so they can share data and resources. Think of a network as a postal system for computers. Devices communicate because data and services live in different places: a file server, a printer, a website, a game server.

| Type | Typical range | Real-world example | Security angle |
|------|---------------|--------------------|----------------|
| PAN | Around one person (~10 m) | Phone + earbuds (Bluetooth) | Pairing attacks, eavesdropping |
| LAN | Room / building | Home, office, lab (Ethernet) | Trusted zone; insider risk |
| WLAN | Building / campus | Wi-Fi network | Weak passphrase, rogue AP |
| MAN | City / large campus | City-wide ISP or university network | Shared provider infrastructure |
| WAN | Countries / global | The Internet, company links | Untrusted path; needs encryption |

Read the table from the smallest network to the largest. A PAN is your phone and earbuds. A LAN is your home or the lab room. A WLAN is the same idea over Wi-Fi. A MAN covers a city or a large campus. A WAN connects distant LANs, and the Internet is the biggest WAN.

**Security point:** the larger the network, the more places traffic passes through that you do not control.

<div class="cards">
<div class="card"><h4>LAN (you control it)</h4><p>Fast, private, one owner. Devices talk through a switch using MAC addresses.</p></div>
<div class="card alt"><h4>WAN (you rent it)</h4><p>Slower, spans distance, many owners. Devices talk through routers using IP addresses.</p></div>
</div>

Sources: Cisco Networking Academy; Cloudflare Learning Center
{: .src}

### 1.2 Topologies and Architectures

Topology is the shape of the network. Architecture describes who plays which role in it.

<div class="cards">
<div class="card"><h4>Star</h4><p>All devices connect to one switch. Easy to manage; the center is a single point of failure. It is the most common layout today, and the center is a great place to monitor traffic.</p></div>
<div class="card"><h4>Bus</h4><p>One shared cable. Legacy. Every device sees all traffic (every frame).</p></div>
<div class="card"><h4>Ring</h4><p>Each node links to two neighbors. Mostly legacy.</p></div>
<div class="card"><h4>Mesh</h4><p>Many redundant links. Very resilient; used in the Internet core, the Internet backbone, and Wi-Fi mesh systems.</p></div>
<div class="card alt"><h4>Client-Server</h4><p>Clients request, servers respond. Centralized control; servers are the main scan targets because they expose services. Almost everything you scan in a pentest is a server.</p></div>
<div class="card alt"><h4>Peer-to-Peer</h4><p>Every node is client and server (file sharing is a common example). No central control, so trust and patching are harder to enforce.</p></div>
</div>

<div class="callout" markdown="1">

**Think about it:** why is a server a more attractive target than a client?

</div>

Sources: Cisco Networking Academy; Cloudflare Learning Center
{: .src}

### 1.3 Network Components and How They Talk

Follow one message from left to right.

<div class="flow">
<div class="step"><b>Device</b><span>PC / phone</span></div>
<div class="step"><b>Switch</b><span>MAC-based</span></div>
<div class="step"><b>Firewall</b><span>allow / block</span></div>
<div class="step"><b>Router</b><span>IP-based</span></div>
<div class="step"><b>Modem</b><span>ISP link</span></div>
<div class="step"><b>Internet</b><span>WAN</span></div>
</div>

* **Switch:** forwards frames inside the LAN by MAC address.
* **Router:** forwards packets between networks by IP address.
* **Firewall:** filters traffic by rules (ports, IPs, protocols).
* **Access Point:** connects Wi-Fi clients to the wired LAN. It works like a switch for Wi-Fi.
* **Modem:** translates between your network and the ISP medium.

A laptop sends a frame to the switch. The switch looks at the destination MAC address and forwards it only to the right port. If the destination is outside the LAN, the frame goes to the router, which reads the IP address and picks the next hop. The firewall sits at the boundary and allows or blocks traffic using rules. The modem converts the signal for the ISP link.

**Security point:** the firewall rules decide which ports an outsider can even reach, which is exactly what Nmap tests later.

Sources: Cisco Networking Academy; Cloudflare Learning Center
{: .src}

## 2. Network Models

### 2.1 OSI Model vs TCP/IP Model

The OSI model splits communication into seven layers so each problem can be solved separately. Memory trick from top to bottom: **All People Seem To Need Data Processing**.

<div class="osi">
<div class="hd">Layer</div><div class="hd">Examples</div><div class="hd">PDU</div><div class="hd hd4">TCP/IP model (4 layers)</div>
<div><span class="num">7</span>Application<span class="map">TCP/IP: Application</span></div><div>HTTP, DNS, SSH</div><div>Data</div>
<div><span class="num">6</span>Presentation<span class="map">TCP/IP: Application</span></div><div>TLS, encoding</div><div>Data</div>
<div><span class="num">5</span>Session<span class="map">TCP/IP: Application</span></div><div>Sessions</div><div>Data</div>
<div><span class="num">4</span>Transport<span class="map">TCP/IP: Transport</span></div><div>TCP, UDP, ports</div><div>Segment</div>
<div><span class="num">3</span>Network<span class="map">TCP/IP: Internet</span></div><div>IP, routing</div><div>Packet</div>
<div><span class="num">2</span>Data Link<span class="map">TCP/IP: Network Access</span></div><div>MAC, Ethernet</div><div>Frame</div>
<div><span class="num">1</span>Physical<span class="map">TCP/IP: Network Access</span></div><div>Cable, Wi-Fi</div><div>Bits</div>
<div class="tcpip" style="grid-row:2 / 5">Application</div>
<div class="tcpip" style="grid-row:5 / 6">Transport</div>
<div class="tcpip" style="grid-row:6 / 7">Internet</div>
<div class="tcpip" style="grid-row:7 / 9">Network Access</div>
</div>

* **Layer 7 Application:** where HTTP, DNS and SSH live.
* **Layer 6 Presentation:** handles encoding and encryption.
* **Layer 5 Session:** manages sessions.
* **Layer 4 Transport:** gives us TCP and UDP and ports.
* **Layer 3 Network:** gives IP addresses and routing.
* **Layer 2 Data Link:** gives MAC addresses and frames.
* **Layer 1 Physical:** cables, radio and bits.

The TCP/IP model on the right is the practical version used on the Internet: four layers, with the top three OSI layers merged into Application and the bottom two merged into Network Access.

**Security link:** attacks target specific layers.

| Layer | Example attacks |
|-------|-----------------|
| 7 Application | Phishing, SQL injection |
| 4 Transport | Port scanning |
| 3 Network | IP spoofing |
| 2 Data Link | ARP spoofing |

Sources: Cloudflare Learning Center (OSI model); Cisco Networking Academy
{: .src}

### 2.2 Encapsulation and Decapsulation

Analogy: sending a letter. You write the message, put it in an envelope with the receiver's address, then put that envelope in a courier bag with the next depot's label.

<div class="flow">
<div class="step"><b>Data</b><span>HTTP request</span></div>
<div class="step"><b>Segment</b><span>+ TCP header (ports)</span></div>
<div class="step"><b>Packet</b><span>+ IP header (IPs)</span></div>
<div class="step"><b>Frame</b><span>+ Ethernet (MACs)</span></div>
<div class="step"><b>Bits</b><span>signal on the wire</span></div>
</div>

**Sender:** encapsulation (top to bottom). **Receiver:** decapsulation (bottom to top).

* The application creates data.
* Transport adds a TCP or UDP header with source and destination ports, and it becomes a **segment**.
* The network layer adds an IP header with source and destination IP, and it becomes a **packet**.
* The data link layer adds an Ethernet header and trailer with MAC addresses, and it becomes a **frame**.
* The physical layer sends **bits**.

The receiver does the opposite, which is decapsulation: one header is removed at each layer. Each layer adds its own header, and the layer below treats everything above as payload.

**Key idea for security:** each header is information.

* The switch reads the MAC header.
* The router reads the IP header.
* The firewall reads IP and ports.
* Security tools (Wireshark, IDS) inspect these headers to spot suspicious traffic.

Sources: Cloudflare Learning Center; RFC 791, RFC 9293
{: .src}

### 2.3 MAC, IP, Subnet Mask, and Gateway

| | MAC address | IP address |
|---|-------------|------------|
| Layer | 2 (Data Link) | 3 (Network) |
| Scope | Inside one LAN (changes at each hop) | End to end across networks |
| Example | `AA:BB:CC:11:22:33` | `192.168.1.10` |

A MAC address is the hardware address of a network card (48 bits). It is used inside one LAN. An IP address is the logical address used to route between networks. Analogy: the MAC is your national ID that identifies you; the IP is your home address that tells the post where to deliver, and it changes when you move.

#### Private vs. Public

These ranges are private (RFC 1918) and are not routable on the Internet. Everything else is public and reachable globally.

```text
10.0.0.0/8
172.16.0.0/12
192.168.0.0/16
```

#### Subnet Mask

The subnet mask tells a device which part of the address is the network and which is the host.

`255.255.255.0` is the same as `/24`: the first 3 octets are the network and the last one is the host. Same network means direct delivery. For example, `192.168.1.10` and `192.168.1.20` are on the same network, so they talk directly.

#### Default Gateway

The router address (for example `192.168.1.1`) used for any destination outside your subnet.

**Security link:** when you scan, you first need to know which subnet you are in and what the gateway is.

Sources: RFC 1918; RFC 791; Cloudflare Learning Center
{: .src}

### 2.4 What Happens When You Open a Website?

Now we can answer the opening question.

<div class="flow">
<div class="step"><b>1. DNS</b><span>name to IP</span></div>
<div class="step"><b>2. Gateway</b><span>MAC of router</span></div>
<div class="step"><b>3. Routing</b><span>hop by hop</span></div>
<div class="step"><b>4. TCP</b><span>handshake on :443</span></div>
<div class="step"><b>5. TLS</b><span>encryption</span></div>
<div class="step"><b>6. HTTP</b><span>request / page</span></div>
</div>

Client: `192.168.1.10` (private). Server: public IP of `example.com`. NAT on the router translates the private source address to the public one.

1. **DNS:** the browser needs an IP for `example.com`, so it asks DNS.
2. **Gateway:** the OS sees the server is not in my subnet, so the frame goes to the default gateway's MAC.
3. **Routing:** the router forwards the packet hop by hop across the Internet.
4. **TCP:** the client and server complete the TCP three-way handshake on port 443.
5. **TLS:** the two sides negotiate encryption.
6. **HTTP:** the browser sends an HTTP request and the server sends back the page.

At every step something can be observed or attacked: DNS can leak information, the open port 443 is visible to a scanner, and the web app may have flaws. This is why a pentester starts with the network layers before touching the application.

<div class="callout" markdown="1">

**Question:** at which step could an attacker learn that port 443 is open?

</div>

Sources: Cloudflare Learning Center; RFC 1035; RFC 9293
{: .src}

## 3. TCP vs UDP

### 3.1 Comparison

Both live at the transport layer and both use ports.

| Feature | TCP | UDP |
|---------|-----|-----|
| Connection | Connection-oriented (handshake first) | Connectionless |
| Reliability | ACKs, retransmission, ordering | No built-in delivery guarantee |
| Speed / overhead | Slower, more overhead | Faster, lightweight |
| Used by | HTTP/HTTPS, SSH, SMTP, FTP | VoIP, gaming, streaming, DHCP, NTP |
| DNS | Large responses, zone transfers | Normal queries (port 53) |

**Rule of thumb:** need every byte correct, use TCP. Need it now and loss is OK, use UDP.

* **TCP** is like a phone call: you establish the call first, both sides confirm, and if a word is lost you repeat it. Reliability comes from acknowledgments, retransmission and sequence numbers for ordering.
* **UDP** is like shouting a message across the street or sending postcards: fast, no setup, no guarantee. Applications that need speed and can tolerate loss use it: VoIP, video calls, online games.
* Web browsing, SSH and email need every byte correct, so they use TCP.
* **DNS** is the important special case: it normally uses UDP port 53 for small queries, and falls back to TCP when the response is too large or for zone transfers.

**Security link:** TCP scans are fast and reliable, UDP scans are slow and ambiguous, which we will see in Nmap.

Sources: RFC 9293 (TCP); RFC 768 (UDP); Cloudflare Learning Center
{: .src}

### 3.2 TCP Three-Way Handshake

Analogy: a phone call.

```text
  Client                                      Server
    |                                            |
    |-- 1. SYN (seq = x) ----------------------->|
    |<-- 2. SYN-ACK (seq = y, ack = x+1) --------|
    |-- 3. ACK (ack = y+1) --------------------->|
    |                                            |
    |<==========================================>|
```

* Client: "hello, can you hear me?" That is **SYN**.
* Server: "yes I hear you, can you hear me?" That is **SYN-ACK**.
* Client: "yes, let's talk." That is **ACK**.

Only then does data flow. The SYN carries the client's initial sequence number, the SYN-ACK carries the server's own number and acknowledges the client's, and the final ACK acknowledges the server's.

After the handshake: every segment is acknowledged, lost segments are retransmitted, and sequence numbers keep data ordered, so the receiver can put it back in order.

<div class="callout" markdown="1">

**Security link:** this is exactly what Nmap exploits. A SYN scan sends the first packet and reads the reply: SYN-ACK means the port is open, RST means closed, and no reply suggests a firewall is dropping packets.

</div>

Sources: RFC 9293; Cloudflare Learning Center
{: .src}

## 4. DNS

### 4.1 DNS: Domain Name System

DNS exists because humans remember names and computers route with numbers. It is the phone book of the Internet.

<div class="flow">
<div class="step"><b>Browser</b><span>example.com?</span></div>
<div class="step"><b>Resolver</b><span>recursive, cached</span></div>
<div class="step"><b>Root</b><span>points to .com</span></div>
<div class="step"><b>TLD (.com)</b><span>points to NS</span></div>
<div class="step"><b>Authoritative</b><span>returns the IP</span></div>
</div>

Resolving `example.com`:

1. The browser checks its own cache, then the OS cache.
2. If nothing, it asks the recursive resolver, usually your ISP or a public one such as `1.1.1.1` or `8.8.8.8`.
3. The resolver asks a root server, which does not know the answer but points to the `.com` TLD servers.
4. The TLD server points to the authoritative name servers for `example.com`.
5. The authoritative server holds the real record and returns the IP.
6. The resolver caches it for the TTL period and gives the answer to the browser.

Normally the resolver does the whole walk for you.

* The answer returns to the browser: `example.com` maps to an IP address, cached for the record's TTL.
* Caching makes DNS fast; TTL controls how long an old answer can be reused.
* Queries normally use UDP/53; TCP/53 is used for large answers and zone transfers.

Sources: Cloudflare Learning Center (What is DNS); RFC 1035
{: .src}

### 4.2 DNS Records and Security Risks

| Record | Purpose | Example |
|--------|---------|---------|
| A / AAAA | Name to IPv4 / IPv6 | `example.com` maps to `93.184.216.34` |
| CNAME | Alias to another name | `www` is an alias of `example.com` |
| MX | Mail servers for the domain | `mail.example.com` (priority 10) |
| NS | Authoritative name servers | `ns1.example.com` |
| TXT | Free text: SPF, DKIM, verification | `"v=spf1 include:..."` |
| PTR | Reverse lookup: IP to name | `34.216.184.93.in-addr.arpa` |

DNS is a rich source of information about a target and a common attack surface. Common DNS risks:

* **Zone transfer (AXFR) allowed to anyone.** If the authoritative server allows AXFR to anyone, it hands over every record in the zone, which is a complete map of the target.
* **Revealing hostnames** such as `vpn`, `dev`, `admin` and `staging`.
* **Dangling CNAMEs** that point to services nobody owns anymore, which can lead to subdomain takeover.
* **Cache poisoning** and DNS spoofing, mitigated by DNSSEC and modern resolvers.
* **Open resolvers** abused for DDoS amplification.

Sources: Cloudflare Learning Center; RFC 1035
{: .src}

## 5. Reconnaissance and Enumeration

### 5.1 Ports, States, and Workflow

Network reconnaissance is collecting information about a target to understand its attack surface. From an IP address a tester can learn whether it is up, which ports respond, which services and versions run, a guess of the operating system, and sometimes hostnames and certificate details.

<div class="cards">
<div class="card open"><h4>Open</h4><p>A service accepts connections. Needs investigation.</p></div>
<div class="card closed"><h4>Closed</h4><p>Host replied, but nothing listens on that port.</p></div>
<div class="card filtered"><h4>Filtered</h4><p>A firewall drops or blocks probes. State unknown.</p></div>
</div>

Typical workflow:

<div class="flow">
<div class="step"><b>Host discovery</b><span>which IPs are alive?</span></div>
<div class="step"><b>Port scan</b><span>which doors are open?</span></div>
<div class="step"><b>Service / version</b><span>what runs there?</span></div>
<div class="step"><b>OS guess</b><span>what system is it?</span></div>
</div>

* **Banner grabbing:** read the greeting a service sends, for example `SSH-2.0-OpenSSH_x`.
* Port scanning finds doors; enumeration asks what is behind them: which software, which version, which configuration, and what information it gives away.
* Versions matter because vulnerabilities are tied to versions.

Sources: Nmap Reference Guide; HTB Academy (Network Enumeration with Nmap); Cloudflare Learning Center
{: .src}

### 5.2 Common Services and Ports

Read these tables as a pattern, not a list to memorize.

<div class="callout warn" markdown="1">

**These are default ports, not guaranteed.** An admin can run SSH on 2222 or a web server on 8080, and a service on port 80 may not be HTTP at all. That is why we use service detection and not only port numbers. An open port is exposure, not automatically a vulnerability. It becomes a problem when the service is unnecessary, outdated, misconfigured or protected by weak credentials.

</div>

For each row ask: what does it do, what leaks, what is commonly misconfigured, and what would a tester check next? Verify ports against the IANA registry.

#### Group 1: Remote access, mail, name, web

| Service | Port / Proto | What it does | Risks / misconfigurations | Investigate next |
|---------|--------------|--------------|---------------------------|------------------|
| FTP | 21 / TCP | File transfer; cleartext credentials | Anonymous login, cleartext, writable dirs | Try anonymous login; list files; version |
| SSH | 22 / TCP | Encrypted remote shell | Weak passwords, old versions | Banner/version; auth methods |
| Telnet | 23 / TCP | Remote shell, no encryption | Cleartext creds; default device logins | Banner; default credentials |
| SMTP | 25 / TCP | Mail transfer between servers | Open relay; user enumeration (VRFY) | Banner; supported commands |
| DNS | 53 / TCP+UDP | Name resolution | Zone transfer (AXFR); info leak | Test AXFR; record listing |
| DHCP | 67-68 / UDP | Hands out IP, mask, gateway | Rogue DHCP server; spoofing | Observe lease info; snooping? |
| HTTP | 80 / TCP | Web (cleartext) | Cleartext; default pages; old software | Headers; tech stack; directories |
| POP3 | 110 / TCP | Download mail | Cleartext login | Banner; STARTTLS; passwords |
| NTP | 123 / UDP | Time synchronization | Old servers abused for DDoS amplification | Version info; patched? |

#### Group 2: Windows, mail, monitoring, directory

| Service | Port / Proto | What it does | Risks / misconfigurations | Investigate next |
|---------|--------------|--------------|---------------------------|------------------|
| RPC | 135 / TCP | Windows RPC endpoint mapper | Reveals internal services; legacy flaws | Enumerate endpoints; Windows version |
| NetBIOS | 137-138 UDP, 139 TCP | Legacy name/session service | Leaks hostnames, workgroup; null sessions | Query names; check sessions |
| SMB | 445 / TCP | Windows file/printer sharing | Open shares; guest access; SMBv1 | List shares; signing; version |
| SMTP Submission | 587 / TCP | Mail client sending | Weak auth; TLS not enforced | STARTTLS; auth methods |
| IMAP | 143 / TCP | Read mail on the server | Cleartext without STARTTLS | Banner; TLS support |
| SNMP | 161 / UDP | Device monitoring | Default community `public` leaks config | Community strings; device info |
| LDAP | 389 / TCP+UDP | Directory (e.g. Active Directory) | Anonymous bind leaks users/groups | Naming contexts; bind policy |
| HTTPS | 443 / TCP | Encrypted web | Weak TLS; expired certs; web app flaws | Certificate; TLS config; web tests |
| SMB over QUIC | 443 / UDP | SMB tunneled over QUIC | Unintended exposure; cert/auth issues | Confirm it is intended |

SMB (445) and SNMP (161) are classic high-value findings in internal pentests. NetBIOS uses 137 and 138 over UDP and 139 over TCP. SMB over QUIC is a newer Windows Server feature that carries SMB over UDP 443 and is only a risk if exposed unintentionally.

#### Group 3: Remote desktop and databases

| Service | Port / Proto | What it does | Risks / misconfigurations | Investigate next |
|---------|--------------|--------------|---------------------------|------------------|
| LDAPS | 636 / TCP | LDAP over TLS | Certificate issues; weak bind policy | Certificate; bind policy |
| MySQL | 3306 / TCP | Relational database | Exposed to Internet; weak/empty root | Version; remote login policy |
| RDP | 3389 / TCP | Windows remote desktop | Brute force; Internet exposure; old flaws | NLA enforced? Patch level |
| PostgreSQL | 5432 / TCP | Relational database | Weak creds; overly open access rules | Version; auth required? |
| WinRM | 5985 HTTP / 5986 HTTPS (TCP) | Windows remote management | Valid creds give remote shell | Auth methods; who can reach it |
| VNC | 5900 / TCP | Graphical remote desktop | No/weak password; weak encryption | Is auth required? Version |
| Redis | 6379 / TCP | In-memory data store | No auth + exposed = data access | Auth required? Version |
| MongoDB | 27017 / TCP | NoSQL database | Auth disabled + exposed = data leak | Auth enabled? Version |

Databases and caches like Redis and MongoDB should almost never face the Internet. Historically many were deployed without authentication, and exposed instances have led to large data leaks. RDP and VNC give a full desktop, so weak credentials mean full control. WinRM gives remote command execution to anyone with valid credentials.

Sources: IANA Service Name and Port Registry; Nmap Reference Guide; HTB Academy
{: .src}

### 5.3 Exposed Service vs. Exploitable Vulnerability

<div class="cards">
<div class="card"><h4>Exposed service</h4><p>Reachable on the network. Increases attack surface. Not automatically a flaw.</p></div>
<div class="card filtered"><h4>Vulnerability</h4><p>A weakness (bug, outdated version, bad config) that can be abused.</p></div>
</div>

An open port alone proves neither. But every extra exposed service increases the attack surface: more software to patch, more credentials to protect, more chances of misconfiguration. The principle for defenders is **least exposure**: if nobody needs it from that network, close it.

<div class="callout warn" markdown="1">

**Scenario A: Redis on 6379.** Internet-facing, no password. Anyone can read and write data, so session tokens or secrets are exposed, and the attacker can pivot into the app. Nothing was hacked yet, but the exposure is already enough.

**Fix:** bind to localhost/VPN, enable auth, firewall.

</div>

<div class="callout warn" markdown="1">

**Scenario B: anonymous FTP.** Anonymous login plus a writable folder that is also the web root. An attacker uploads a malicious page, and the file server becomes a foothold on the web server.

**Fix:** disable anonymous, separate directories, use SFTP.

</div>

In both cases the root cause is configuration, not a clever exploit. Think about how you would fix each one.

Sources: HTB Academy; PortSwigger Web Security Academy; Nmap Reference Guide
{: .src}

## 6. Nmap

### 6.1 How Port Scanning Works

Nmap (Network Mapper) is a free tool for network discovery and security auditing. It sends crafted packets and interprets the replies.

<div class="cards">
<div class="card"><h4>TCP Connect <code>-sT</code></h4><p>Full 3-way handshake via the OS. No root needed. More visible in target logs.</p></div>
<div class="card"><h4>SYN Scan <code>-sS</code></h4><p>Sends SYN only. SYN-ACK = open, RST = closed, silence = filtered. Needs root. Default when privileged. It never completes the handshake, so it is stealthier and faster.</p></div>
<div class="card"><h4>UDP Scan <code>-sU</code></h4><p>No handshake. No reply = <code>open|filtered</code>; ICMP unreachable = closed. Slow, which is why we use <code>--top-ports</code>.</p></div>
</div>

Also available: host discovery, version detection and OS detection.

* `-sn` finds live hosts without port scanning.
* `-sV` probes services for name and version.
* `-O` fingerprints the OS from TCP/IP behavior.

<div class="callout warn" markdown="1">

**Authorized targets only.** Scanning without permission can be illegal.

</div>

Sources: Nmap Reference Guide; HTB Academy (Network Enumeration with Nmap)
{: .src}

### 6.2 Essential Nmap Commands

Replace `192.168.1.10` with your own lab target.

```bash
# 1. Scan the top 1000 TCP ports
nmap 192.168.1.10

# 2. -p: scan only the listed ports
nmap -p 22,80,443 192.168.1.10

# 3. -p-: all 65535 TCP ports
nmap -p- 192.168.1.10

# 4. -sV: identify service and version
nmap -sV 192.168.1.10

# 5. -O: OS detection (needs root)
sudo nmap -O 192.168.1.10

# 6. -sS: SYN (half-open) scan (needs root)
sudo nmap -sS 192.168.1.10

# 7. -sU: UDP scan; --top-ports 20: the most common 20 UDP ports
sudo nmap -sU --top-ports 20 192.168.1.10

# 8. -sC: default NSE scripts + version detection
nmap -sC -sV 192.168.1.10
```

* `-p` limits the scan to chosen ports: fast and focused.
* `-p-` is slower but finds services on unusual ports.
* `-sU` with `--top-ports` matters because otherwise UDP takes very long.
* `-sC` runs Nmap's default NSE scripts and combines well with `-sV`. Default scripts do more probing than a basic scan, so use them only on authorized targets.

Sources: Nmap Reference Guide (nmap.org/book/man.html)
{: .src}

### 6.3 Reading Nmap Output

This is illustrative output, not from a real system, shaped like what you will see in the lab.

```text
$ nmap -sV 192.168.56.101
PORT     STATE     SERVICE       VERSION
21/tcp   open      ftp           vsftpd 2.3.4
22/tcp   open      ssh           OpenSSH 4.7p1
80/tcp   open      http          Apache httpd 2.2.8
445/tcp  filtered  microsoft-ds
```

Read it column by column:

* **PORT** shows the number and protocol.
* **STATE** is open, closed or filtered.
* **SERVICE** is Nmap's guess from the port number.
* **VERSION** appears only with `-sV` and comes from actually probing the service.

Interpret the rows:

* Port 21 runs `vsftpd 2.3.4`, which is very old. A tester would look up known issues for exactly that version and test for anonymous login.
* Port 22 is SSH: check the version and authentication methods.
* Port 80 is a web server, so we look at the site and the technology.
* Port 445 is filtered, which suggests a firewall is in front of SMB.

<div class="callout" markdown="1">

**A scan result is a lead, not a conclusion.** Everything we find must be verified manually.

</div>

Sources: Nmap Reference Guide; HTB Academy
{: .src}

## 7. Hands-on Lab: Discover, Scan, Identify

### 7.1 Lab Setup

Use Kali Linux and one intentionally vulnerable target VM, such as Metasploitable 2, both on an isolated host-only or internal virtual network, for example `192.168.56.0/24`.

<div class="callout warn" markdown="1">

**Authorized lab targets only.** Never point these commands at public addresses or any system you do not own or have written permission to test. `192.168.56.101` is a placeholder for your own VM; use your own target IP.

</div>

### 7.2 Steps

| Step | Command (lab only) | Goal / what to note |
|------|--------------------|---------------------|
| 1 | `ip a` | Find your IP and subnet (e.g. `192.168.56.0/24`) |
| 2 | `nmap -sn 192.168.56.0/24` | Host discovery: which IPs are alive? |
| 3 | `ping -c 4 192.168.56.101` | Confirm the target is reachable |
| 4 | `nmap 192.168.56.101` | Basic scan: list open ports |
| 5 | `nmap -p- 192.168.56.101` | Any service on an unusual port? |
| 6 | `nmap -sV -sC 192.168.56.101` | Service versions and default scripts |
| 7-9 | Research + discuss | What does each service do? What is misconfigured? Impact? Fix? |

For steps 1 to 6 the same commands as a copyable block:

```bash
ip a
nmap -sn 192.168.56.0/24
ping -c 4 192.168.56.101
nmap 192.168.56.101
nmap -p- 192.168.56.101
nmap -sV -sC 192.168.56.101
```

Steps 7 to 9 are research and discussion: for each service, what does it do, what could be misconfigured, what is the impact, and how do we defend it. The expected output of the basic scan is a list like the one in section 6.3. Write one line per service in a table.

Sources: Nmap Reference Guide; HTB Academy; Cisco Networking Academy
{: .src}

### 7.3 Questions, Instructor Notes, and Challenge

#### Questions

1. How many ports are open? Which are unexpected?
2. What is the difference between open and filtered?
3. Which service shows an old version? Why does it matter?
4. Is an open port the same as a vulnerability?

<div class="callout" markdown="1">

**Instructor notes**

* Isolate VMs (host-only network). Keep the Internet out of the lab, and make sure the VMs cannot reach the university network.
* Common issues: wrong adapter mode (the target is not found), forgetting `sudo` for `-O` or `-sS`, and long `-p-` or UDP scans that seem to hang. Tell students to be patient or use `--top-ports`.
* Discussion answers: an open FTP port is exposure; it becomes a vulnerability if anonymous login is enabled or the version is vulnerable. A filtered port means a firewall, not that the service is absent.

</div>

<div class="callout ok" markdown="1">

**Challenge:** produce a one-page report with each discovered service, its risk, and one defensive fix (for example disable, restrict by firewall, upgrade, or enforce authentication). Then re-scan after disabling one service and compare the results.

</div>

Sources: HTB Academy; Nmap Reference Guide
{: .src}

## 8. Defensive Recommendations

Everything the attacker does in reconnaissance can be reduced. Connect each recommendation to a finding from the services tables.

<div class="cards">
<div class="card open"><h4>Reduce exposure</h4><p>Close unused services; least exposure. Close or remove services nobody needs.</p></div>
<div class="card open"><h4>Filter</h4><p>Firewall rules; admin/DB only via VPN or internal. Only the required networks should reach each service.</p></div>
<div class="card open"><h4>Patch</h4><p>Update versions to remove known flaws, so version-based vulnerabilities disappear.</p></div>
<div class="card open"><h4>Encrypt</h4><p>SFTP/SSH/HTTPS instead of FTP/Telnet/HTTP.</p></div>
<div class="card open"><h4>Authenticate</h4><p>No defaults, no anonymous, MFA. No default or empty passwords.</p></div>
<div class="card open"><h4>Monitor</h4><p>Log and alert on scans; self-scan regularly. Scans create noisy patterns that an IDS or firewall log can detect.</p></div>
</div>

Scan yourself regularly with permission, because you want to find your own exposure before someone else does.

Sources: HTB Academy; PortSwigger Web Security Academy; Cloudflare Learning Center
{: .src}

## 9. Final Quiz

Take five minutes, then discuss your answers in pairs.

1. Which OSI layer deals with IP addresses?
2. What is the PDU at Layer 2?
3. Name the three steps of the TCP handshake.
4. Why does DNS normally use UDP?
5. Which DNS record maps a name to IPv6?
6. What does "filtered" mean in Nmap?
7. Port scanning vs service enumeration?
8. Does an open port always mean a vulnerability?
9. Which Nmap flag detects service versions?
10. Which is private: `8.8.8.8`, `192.168.1.10` or `1.1.1.1`?

<details markdown="1">
<summary>Quiz Answers</summary>

1. Layer 3 (Network)
2. Frame
3. SYN, SYN-ACK, ACK
4. Small, fast queries; TCP fallback for large answers (and zone transfers)
5. AAAA
6. A firewall blocks probes; the state cannot be determined
7. Scanning finds open ports; enumeration identifies service, version, config
8. No. Exposure is not a vulnerability by itself
9. `-sV`
10. `192.168.1.10` (RFC 1918)

</details>

Question 8 is the core idea of the lecture.

Sources: RFC 9293; RFC 1035; RFC 1918; Nmap Reference Guide
{: .src}

## 10. References and Learning Resources

* [Cloudflare Learning Center](https://www.cloudflare.com/learning/)
* [Cloudflare: What is DNS?](https://www.cloudflare.com/learning/dns/what-is-dns/)
* [Cisco Networking Academy](https://www.netacad.com/)
* [Hack The Box Academy](https://academy.hackthebox.com/)
* [PortSwigger Web Security Academy](https://portswigger.net/web-security)
* [Nmap Reference Guide](https://nmap.org/book/man.html)
* [IANA Port Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)
* [RFC 791 / 768 / 9293 / 1035 / 1918](https://www.rfc-editor.org/rfc/rfc9293)

Keep learning on your own. HTB Academy has a Network Enumeration with Nmap module, and PortSwigger has the Web Security Academy for application-layer security. Cloudflare and Cisco explain the fundamentals clearly. The RFCs are the authoritative source for protocol behavior, so use them when two blogs disagree. Check port numbers in the IANA registry.

</div>

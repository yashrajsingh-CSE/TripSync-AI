<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>TripSync AI – README</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Sans:wght@300;400;500&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet"/>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css"/>
<style>
:root {
  --bg: #07070f;
  --surface: #0f0f1a;
  --surface2: #161625;
  --surface3: #1e1e30;
  --border: #2a2a42;
  --text: #f0f0fa;
  --text2: #a0a0c0;
  --text3: #5a5a7a;
  --v: #7c6aff;
  --v2: #a855f7;
  --g: #06d6a0;
  --gold: #f4a261;
  --rose: #ff6b6b;
  --sky: #38bdf8;
}

* { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; }
body {
  font-family: 'DM Sans', sans-serif;
  background: var(--bg);
  color: var(--text);
  line-height: 1.6;
  overflow-x: hidden;
}

/* ── NOISE TEXTURE ── */
body::before {
  content: '';
  position: fixed;
  inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
  pointer-events: none;
  z-index: 0;
}

/* ── KEYFRAMES ── */
@keyframes fadeUp { from { opacity:0; transform:translateY(30px); } to { opacity:1; transform:translateY(0); } }
@keyframes float { 0%,100% { transform:translateY(0); } 50% { transform:translateY(-10px); } }
@keyframes gradShift { 0%,100% { background-position:0% 50%; } 50% { background-position:100% 50%; } }
@keyframes pulse { 0%,100% { opacity:1; } 50% { opacity:.5; } }
@keyframes spin { to { transform:rotate(360deg); } }
@keyframes shimmer { from { background-position:-200% 0; } to { background-position:200% 0; } }
@keyframes ping { 0% { transform:scale(1);opacity:1; } 75%,100% { transform:scale(2);opacity:0; } }
@keyframes borderGlow { 0%,100% { border-color:rgba(124,106,255,.4); } 50% { border-color:rgba(6,214,160,.4); } }
@keyframes slideIn { from { transform:translateX(-20px);opacity:0; } to { transform:translateX(0);opacity:1; } }

/* ── HERO HEADER ── */
.hero {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 80px 24px;
  position: relative;
  overflow: hidden;
}
.hero::before {
  content: '';
  position: absolute;
  inset: 0;
  background:
    radial-gradient(ellipse 80% 60% at 20% 30%, rgba(124,106,255,.18) 0%, transparent 60%),
    radial-gradient(ellipse 60% 50% at 80% 70%, rgba(6,214,160,.12) 0%, transparent 60%),
    radial-gradient(ellipse 50% 40% at 50% 10%, rgba(168,85,247,.1) 0%, transparent 50%);
  z-index: 0;
}
.hero-grid {
  position: absolute;
  inset: 0;
  background-image: linear-gradient(rgba(124,106,255,.04) 1px,transparent 1px), linear-gradient(90deg,rgba(124,106,255,.04) 1px,transparent 1px);
  background-size: 60px 60px;
  z-index: 0;
}
.hero > * { position: relative; z-index: 1; }

.logo-badge {
  display: inline-flex;
  align-items: center;
  gap: 14px;
  background: rgba(124,106,255,.12);
  border: 1px solid rgba(124,106,255,.3);
  border-radius: 100px;
  padding: 10px 24px 10px 10px;
  margin-bottom: 40px;
  animation: fadeUp .6s ease both;
}
.logo-icon {
  width: 48px; height: 48px;
  border-radius: 14px;
  background: linear-gradient(135deg, #7c6aff, #a855f7);
  display: flex; align-items: center; justify-content: center;
  font-size: 22px;
}
.logo-text { font-family: 'Syne', sans-serif; font-weight: 800; font-size: 18px; }

.hero-title {
  font-family: 'Syne', sans-serif;
  font-size: clamp(48px, 8vw, 96px);
  font-weight: 800;
  line-height: 1.0;
  letter-spacing: -2px;
  margin-bottom: 24px;
  animation: fadeUp .6s .1s ease both;
}
.grad-text {
  background: linear-gradient(135deg, #7c6aff 0%, #a855f7 40%, #06d6a0 100%);
  background-size: 200% 200%;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  animation: gradShift 4s ease infinite;
}
.hero-sub {
  font-size: 20px;
  color: var(--text2);
  max-width: 600px;
  margin: 0 auto 48px;
  font-weight: 300;
  animation: fadeUp .6s .2s ease both;
}

/* ── BADGES ROW ── */
.badges {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  justify-content: center;
  margin-bottom: 60px;
  animation: fadeUp .6s .3s ease both;
}
.badge {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 6px 14px;
  border-radius: 100px;
  font-size: 12px;
  font-weight: 600;
  letter-spacing: .5px;
  text-transform: uppercase;
}
.badge-v { background: rgba(124,106,255,.15); color: #a99fff; border: 1px solid rgba(124,106,255,.25); }
.badge-g { background: rgba(6,214,160,.12); color: #06d6a0; border: 1px solid rgba(6,214,160,.2); }
.badge-gold { background: rgba(244,162,97,.12); color: #f4a261; border: 1px solid rgba(244,162,97,.2); }
.badge-rose { background: rgba(255,107,107,.12); color: #ff6b6b; border: 1px solid rgba(255,107,107,.2); }
.badge-sky { background: rgba(56,189,248,.12); color: #38bdf8; border: 1px solid rgba(56,189,248,.2); }

/* ── STATS ROW ── */
.stats {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
  gap: 16px;
  max-width: 700px;
  width: 100%;
  animation: fadeUp .6s .4s ease both;
}
.stat-card {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: 16px;
  padding: 20px;
  text-align: center;
  animation: borderGlow 3s ease-in-out infinite;
}
.stat-num {
  font-family: 'Syne', sans-serif;
  font-size: 32px;
  font-weight: 800;
}
.stat-label { font-size: 12px; color: var(--text3); margin-top: 4px; text-transform: uppercase; letter-spacing: .5px; }

/* ── DIVIDER ── */
.section-divider {
  width: 100%;
  height: 1px;
  background: linear-gradient(90deg, transparent, var(--border), transparent);
  margin: 0;
}

/* ── SECTION COMMON ── */
.section {
  max-width: 1200px;
  margin: 0 auto;
  padding: 80px 24px;
}
.section-label {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  font-size: 12px;
  font-weight: 600;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: var(--v);
  margin-bottom: 16px;
}
.section-title {
  font-family: 'Syne', sans-serif;
  font-size: clamp(28px, 4vw, 48px);
  font-weight: 800;
  line-height: 1.1;
  margin-bottom: 16px;
}
.section-desc {
  font-size: 17px;
  color: var(--text2);
  max-width: 600px;
  font-weight: 300;
  margin-bottom: 48px;
}

/* ── SCREENSHOT CARDS ── */
.screenshots-hero {
  position: relative;
  margin-bottom: 80px;
}
.screenshot-main {
  width: 100%;
  border-radius: 20px;
  border: 1px solid var(--border);
  box-shadow: 0 40px 120px rgba(0,0,0,.6), 0 0 0 1px rgba(124,106,255,.1);
  overflow: hidden;
  display: block;
}
.screenshot-main img {
  width: 100%;
  height: auto;
  display: block;
}
.screenshot-glow {
  position: absolute;
  inset: -20px;
  background: radial-gradient(ellipse at 50% 80%, rgba(124,106,255,.2), transparent 60%);
  z-index: -1;
  filter: blur(40px);
}

/* ── FEATURE GRID ── */
.feature-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
  margin-bottom: 60px;
}
.feature-card {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: 20px;
  padding: 28px;
  position: relative;
  overflow: hidden;
  transition: transform .2s, border-color .2s, box-shadow .2s;
}
.feature-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 1px;
  background: linear-gradient(90deg, transparent, rgba(124,106,255,.5), transparent);
}
.feature-card:hover {
  transform: translateY(-4px);
  border-color: rgba(124,106,255,.3);
  box-shadow: 0 20px 60px rgba(0,0,0,.3), 0 0 0 1px rgba(124,106,255,.1);
}
.feature-icon {
  width: 52px; height: 52px;
  border-radius: 14px;
  display: flex; align-items: center; justify-content: center;
  font-size: 24px;
  margin-bottom: 18px;
}
.feature-title {
  font-family: 'Syne', sans-serif;
  font-size: 18px;
  font-weight: 700;
  margin-bottom: 10px;
}
.feature-desc { font-size: 14px; color: var(--text2); line-height: 1.6; }
.feature-tag {
  display: inline-block;
  margin-top: 14px;
  font-size: 11px;
  padding: 3px 10px;
  border-radius: 20px;
  font-weight: 600;
  letter-spacing: .5px;
}

/* ── SCREENSHOTS GRID ── */
.screenshots-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 16px;
  margin-bottom: 16px;
}
.screenshots-grid.three { grid-template-columns: repeat(3, 1fr); }
.ss-card {
  border-radius: 16px;
  overflow: hidden;
  border: 1px solid var(--border);
  transition: transform .2s, box-shadow .2s, border-color .2s;
  background: var(--surface);
}
.ss-card:hover {
  transform: translateY(-4px) scale(1.01);
  box-shadow: 0 20px 50px rgba(0,0,0,.4);
  border-color: rgba(124,106,255,.3);
}
.ss-card img { width: 100%; height: auto; display: block; }
.ss-caption {
  padding: 12px 16px;
  font-size: 13px;
  font-weight: 500;
  color: var(--text2);
  display: flex;
  align-items: center;
  gap: 8px;
  border-top: 1px solid var(--border);
}
.ss-dot { width: 8px; height: 8px; border-radius: 50%; }

/* ── TECH STACK ── */
.tech-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
  gap: 14px;
}
.tech-card {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: 14px;
  padding: 20px;
  display: flex;
  align-items: center;
  gap: 14px;
  transition: border-color .2s, transform .2s;
}
.tech-card:hover { border-color: rgba(124,106,255,.3); transform: translateY(-2px); }
.tech-icon { font-size: 28px; }
.tech-name { font-family: 'Syne', sans-serif; font-weight: 700; font-size: 14px; }
.tech-desc { font-size: 12px; color: var(--text3); margin-top: 2px; }

/* ── TIMELINE ── */
.timeline { position: relative; padding-left: 32px; }
.timeline::before {
  content: '';
  position: absolute;
  left: 8px; top: 0; bottom: 0;
  width: 2px;
  background: linear-gradient(to bottom, var(--v), var(--v2), var(--g), transparent);
}
.tl-item {
  position: relative;
  margin-bottom: 32px;
  animation: slideIn .4s ease both;
}
.tl-dot {
  position: absolute;
  left: -28px;
  top: 6px;
  width: 12px; height: 12px;
  border-radius: 50%;
  border: 2px solid var(--v);
  background: var(--bg);
}
.tl-title { font-family: 'Syne', sans-serif; font-weight: 700; font-size: 16px; margin-bottom: 6px; }
.tl-desc { font-size: 14px; color: var(--text2); }

/* ── CODE BLOCK ── */
.code-block {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: 14px;
  overflow: hidden;
  margin-bottom: 24px;
}
.code-header {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 14px 18px;
  border-bottom: 1px solid var(--border);
  background: var(--surface2);
}
.code-dot { width: 12px; height: 12px; border-radius: 50%; }
.code-title { font-size: 13px; color: var(--text3); margin-left: 4px; font-family: 'JetBrains Mono', monospace; }
.code-body {
  padding: 20px 24px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 14px;
  line-height: 1.7;
  color: #c9d1d9;
  overflow-x: auto;
}
.code-body .cmd { color: #06d6a0; }
.code-body .comment { color: #5a5a7a; }
.code-body .str { color: #f4a261; }
.code-body .kw { color: #a855f7; }

/* ── GRADIENT DIVIDER ── */
.grad-hr {
  width: 120px; height: 3px;
  background: linear-gradient(90deg, var(--v), var(--v2), var(--g));
  border-radius: 3px;
  margin: 0 0 48px;
}

/* ── FOOTER ── */
.footer {
  text-align: center;
  padding: 60px 24px 40px;
  position: relative;
  overflow: hidden;
}
.footer::before {
  content: '';
  position: absolute;
  inset: 0;
  background: radial-gradient(ellipse at 50% 0%, rgba(124,106,255,.08), transparent 60%);
}
.footer > * { position: relative; z-index: 1; }
.footer-logo {
  font-family: 'Syne', sans-serif;
  font-size: 32px;
  font-weight: 800;
  margin-bottom: 16px;
}
.footer-tagline { font-size: 16px; color: var(--text3); margin-bottom: 32px; }
.footer-links { display: flex; gap: 20px; justify-content: center; flex-wrap: wrap; margin-bottom: 40px; }
.footer-link {
  display: inline-flex; align-items: center; gap: 8px;
  padding: 10px 20px;
  border: 1px solid var(--border);
  border-radius: 100px;
  font-size: 13px;
  color: var(--text2);
  text-decoration: none;
  transition: all .2s;
}
.footer-link:hover { border-color: var(--v); color: var(--text); background: rgba(124,106,255,.08); }
.footer-copy { font-size: 13px; color: var(--text3); }

/* ── HIGHLIGHT BAND ── */
.highlight-band {
  background: linear-gradient(135deg, rgba(124,106,255,.08), rgba(168,85,247,.05), rgba(6,214,160,.05));
  border-top: 1px solid var(--border);
  border-bottom: 1px solid var(--border);
  padding: 60px 24px;
  text-align: center;
}
.highlight-quote {
  font-family: 'Syne', sans-serif;
  font-size: clamp(22px, 3vw, 38px);
  font-weight: 700;
  max-width: 800px;
  margin: 0 auto 20px;
  line-height: 1.3;
}
.highlight-source { font-size: 14px; color: var(--text3); }

/* ── ONLINE DOT ── */
.online-dot {
  width: 8px; height: 8px;
  border-radius: 50%;
  background: var(--g);
  display: inline-block;
  position: relative;
}
.online-dot::after {
  content: '';
  position: absolute;
  inset: -3px;
  border-radius: 50%;
  background: var(--g);
  opacity: .3;
  animation: ping 1.5s ease-out infinite;
}

/* ── SCROLLED SECTIONS ANIMATION ── */
.reveal { opacity: 0; transform: translateY(24px); transition: opacity .6s, transform .6s; }
.reveal.visible { opacity: 1; transform: translateY(0); }

/* ── RESPONSIVE ── */
@media (max-width: 768px) {
  .screenshots-grid { grid-template-columns: 1fr; }
  .screenshots-grid.three { grid-template-columns: 1fr; }
  .stats { grid-template-columns: repeat(2, 1fr); }
}
</style>
</head>
<body>

<!-- ══ HERO ══ -->
<header class="hero">
  <div class="hero-grid"></div>

  <div class="logo-badge">
    <div class="logo-icon">🌍</div>
    <span class="logo-text">TripSync AI</span>
    <span class="badge badge-g" style="margin-left:8px;"><span class="online-dot"></span> &nbsp;v1.0.0</span>
  </div>

  <h1 class="hero-title">
    Your World,<br/>
    <span class="grad-text">Beautifully</span><br/>
    Tracked.
  </h1>

  <p class="hero-sub">
    A production-ready, AI-powered travel companion — built in a single <code style="background:rgba(124,106,255,.15);padding:2px 8px;border-radius:6px;font-family:'JetBrains Mono',monospace;font-size:16px;color:#a99fff;">index.html</code> — that captures every moment, mile, and memory.
  </p>

  <div class="badges">
    <span class="badge badge-v"><i class="fa-solid fa-code"></i> Vanilla JS</span>
    <span class="badge badge-g"><i class="fa-solid fa-palette"></i> TailwindCSS</span>
    <span class="badge badge-gold"><i class="fa-solid fa-chart-pie"></i> Chart.js</span>
    <span class="badge badge-sky"><i class="fa-solid fa-bolt"></i> Zero Build</span>
    <span class="badge badge-rose"><i class="fa-solid fa-moon"></i> Dark / Light</span>
    <span class="badge badge-v"><i class="fa-solid fa-mobile"></i> Mobile First</span>
    <span class="badge badge-g"><i class="fa-solid fa-robot"></i> AI Powered</span>
    <span class="badge badge-gold"><i class="fa-solid fa-database"></i> LocalStorage</span>
  </div>

  <div class="stats">
    <div class="stat-card">
      <div class="stat-num grad-text">12</div>
      <div class="stat-label">Modules</div>
    </div>
    <div class="stat-card">
      <div class="stat-num" style="color:var(--g)">1</div>
      <div class="stat-label">HTML File</div>
    </div>
    <div class="stat-card">
      <div class="stat-num" style="color:var(--gold)">0</div>
      <div class="stat-label">Dependencies</div>
    </div>
    <div class="stat-card">
      <div class="stat-num" style="color:var(--v2)">∞</div>
      <div class="stat-label">Possibilities</div>
    </div>
  </div>
</header>

<div class="section-divider"></div>

<!-- ══ HERO SCREENSHOT ══ -->
<div class="section reveal">
  <div class="section-label"><i class="fa-solid fa-eye"></i> Preview</div>
  <h2 class="section-title">Dribbble-Quality UI,<br/><span class="grad-text">Ready to Launch</span></h2>
  <p class="section-desc">Premium dark-mode design inspired by Apple, Airbnb, Linear, and Notion — fully interactive right out of the box.</p>

  <div class="screenshots-hero">
    <div class="screenshot-glow"></div>
    <div class="screenshot-main">
      <img src="tripsync-readme-assets/02-dashboard.png" alt="TripSync AI Dashboard"/>
    </div>
  </div>

  <!-- 2-col row -->
  <div class="screenshots-grid">
    <div class="ss-card">
      <img src="tripsync-readme-assets/01-login.png" alt="Login Screen"/>
      <div class="ss-caption"><span class="ss-dot" style="background:var(--v);"></span>🔐 Authentication — Login & Sign Up</div>
    </div>
    <div class="ss-card">
      <img src="tripsync-readme-assets/03-tracking.png" alt="Live Tracking"/>
      <div class="ss-caption"><span class="ss-dot" style="background:var(--g);"></span>📍 Live GPS Tracking with SVG Route Map</div>
    </div>
  </div>
</div>

<div class="section-divider"></div>

<!-- ══ FEATURES ══ -->
<div class="section reveal">
  <div class="section-label"><i class="fa-solid fa-sparkles"></i> Features</div>
  <h2 class="section-title">Everything a Traveler<br/><span class="grad-text">Could Ever Need</span></h2>
  <div class="grad-hr"></div>

  <div class="feature-grid">
    <div class="feature-card">
      <div class="feature-icon" style="background:rgba(124,106,255,.15);">🏠</div>
      <div class="feature-title">Smart Dashboard</div>
      <div class="feature-desc">Rich home screen with animated counters, live trip status, interactive mini-map, weather widget, AI recommendations, and expense donut chart — all in one glance.</div>
      <span class="feature-tag" style="background:rgba(124,106,255,.15);color:#a99fff;">Core</span>
    </div>
    <div class="feature-card">
      <div class="feature-icon" style="background:rgba(6,214,160,.12);">📍</div>
      <div class="feature-title">Live GPS Tracking</div>
      <div class="feature-desc">Simulated real-time route visualization with animated SVG paths, travel mode switcher (Flight / Road / Walk), checkpoint markers, and full journey timeline.</div>
      <span class="feature-tag" style="background:rgba(6,214,160,.12);color:#06d6a0;">Tracking</span>
    </div>
    <div class="feature-card">
      <div class="feature-icon" style="background:rgba(244,162,97,.12);">📅</div>
      <div class="feature-title">AI Itinerary Planner</div>
      <div class="feature-desc">7-day drag-and-drop activity planner with AI-generated suggestions, one-click add, day summary stats, and AI itinerary regeneration button.</div>
      <span class="feature-tag" style="background:rgba(244,162,97,.12);color:#f4a261;">AI</span>
    </div>
    <div class="feature-card">
      <div class="feature-icon" style="background:rgba(255,107,107,.12);">💰</div>
      <div class="feature-title">Expense Tracker</div>
      <div class="feature-desc">Full budget management — add/delete expenses, category breakdown with progress bars, Chart.js donut visualization, and LocalStorage persistence across sessions.</div>
      <span class="feature-tag" style="background:rgba(255,107,107,.12);color:#ff6b6b;">Finance</span>
    </div>
    <div class="feature-card">
      <div class="feature-icon" style="background:rgba(56,189,248,.12);">📸</div>
      <div class="feature-title">Memory Journal</div>
      <div class="feature-desc">Masonry photo gallery with location-tagged memory cards, category filters (Photos / Videos / Highlights / Notes), and beautiful gradient placeholder visuals.</div>
      <span class="feature-tag" style="background:rgba(56,189,248,.12);color:#38bdf8;">Memories</span>
    </div>
    <div class="feature-card">
      <div class="feature-icon" style="background:rgba(168,85,247,.12);">🤖</div>
      <div class="feature-title">AI Travel Assistant</div>
      <div class="feature-desc">Full conversational chat interface with typing animations, contextual AI responses, smart prompt suggestions, voice UI button, and trip-aware answers.</div>
      <span class="feature-tag" style="background:rgba(168,85,247,.12);color:#a855f7;">AI Chat</span>
    </div>
    <div class="feature-card">
      <div class="feature-icon" style="background:rgba(6,214,160,.12);">📊</div>
      <div class="feature-title">Travel Analytics</div>
      <div class="feature-desc">Beautiful data dashboards with Chart.js bar, line, and polar area charts — monthly travel frequency, annual expenses, continent breakdown, and top destinations.</div>
      <span class="feature-tag" style="background:rgba(6,214,160,.12);color:#06d6a0;">Analytics</span>
    </div>
    <div class="feature-card">
      <div class="feature-icon" style="background:rgba(124,106,255,.15);">👥</div>
      <div class="feature-title">Group Travel</div>
      <div class="feature-desc">Squad member management with live location indicators, real-time group chat simulation, auto expense splitting calculator, and live location map.</div>
      <span class="feature-tag" style="background:rgba(124,106,255,.15);color:#a99fff;">Social</span>
    </div>
    <div class="feature-card">
      <div class="feature-icon" style="background:rgba(255,107,107,.12);">🛡</div>
      <div class="feature-title">Safety Center</div>
      <div class="feature-desc">Emergency SOS with multi-alert simulation, emergency contacts directory, local emergency numbers by country, medical info card, and safety status checklist.</div>
      <span class="feature-tag" style="background:rgba(255,107,107,.12);color:#ff6b6b;">Safety</span>
    </div>
  </div>
</div>

<div class="section-divider"></div>

<!-- ══ SCREENSHOTS SHOWCASE ══ -->
<div class="section reveal">
  <div class="section-label"><i class="fa-solid fa-images"></i> Screenshots</div>
  <h2 class="section-title">Every Screen,<br/><span class="grad-text">Pixel Perfect</span></h2>
  <p class="section-desc">11 fully designed and interactive screens — all working from a single HTML file.</p>

  <!-- Row 1 -->
  <div class="screenshots-grid" style="margin-bottom:16px;">
    <div class="ss-card">
      <img src="tripsync-readme-assets/04-itinerary.png" alt="Itinerary Planner"/>
      <div class="ss-caption"><span class="ss-dot" style="background:var(--gold);"></span>📅 AI Itinerary Planner — 7-Day View</div>
    </div>
    <div class="ss-card">
      <img src="tripsync-readme-assets/05-expenses.png" alt="Expense Tracker"/>
      <div class="ss-caption"><span class="ss-dot" style="background:var(--rose);"></span>💰 Expense Tracker — Budget & Charts</div>
    </div>
  </div>

  <!-- Row 2 -->
  <div class="screenshots-grid" style="margin-bottom:16px;">
    <div class="ss-card">
      <img src="tripsync-readme-assets/06-memories.png" alt="Memory Journal"/>
      <div class="ss-caption"><span class="ss-dot" style="background:var(--sky);"></span>📸 Memory Journal — Masonry Gallery</div>
    </div>
    <div class="ss-card">
      <img src="tripsync-readme-assets/07-analytics.png" alt="Analytics"/>
      <div class="ss-caption"><span class="ss-dot" style="background:var(--g);"></span>📊 Travel Analytics — Charts & Stats</div>
    </div>
  </div>

  <!-- Row 3 -->
  <div class="screenshots-grid" style="margin-bottom:16px;">
    <div class="ss-card">
      <img src="tripsync-readme-assets/08-assistant.png" alt="AI Assistant"/>
      <div class="ss-caption"><span class="ss-dot" style="background:var(--v2);"></span>🤖 AI Travel Assistant — Chat Interface</div>
    </div>
    <div class="ss-card">
      <img src="tripsync-readme-assets/09-group.png" alt="Group Travel"/>
      <div class="ss-caption"><span class="ss-dot" style="background:var(--v);"></span>👥 Group Travel — Squad & Chat</div>
    </div>
  </div>

  <!-- Row 4 -->
  <div class="screenshots-grid">
    <div class="ss-card">
      <img src="tripsync-readme-assets/10-safety.png" alt="Safety Center"/>
      <div class="ss-caption"><span class="ss-dot" style="background:var(--rose);"></span>🛡 Safety Center — SOS & Emergency</div>
    </div>
    <div class="ss-card">
      <img src="tripsync-readme-assets/11-settings.png" alt="Settings"/>
      <div class="ss-caption"><span class="ss-dot" style="background:var(--text3);"></span>⚙ Settings — Profile & Preferences</div>
    </div>
  </div>
</div>

<div class="section-divider"></div>

<!-- ══ HIGHLIGHT BAND ══ -->
<div class="highlight-band reveal">
  <div class="highlight-quote">
    "Built with zero frameworks, zero build tools, zero backend — just one <span class="grad-text">index.html</span> file that works instantly."
  </div>
  <div class="highlight-source">Open the file → see a full startup-grade app 🚀</div>
</div>

<!-- ══ TECH STACK ══ -->
<div class="section reveal">
  <div class="section-label"><i class="fa-solid fa-layer-group"></i> Tech Stack</div>
  <h2 class="section-title">Built With<br/><span class="grad-text">The Essentials</span></h2>
  <p class="section-desc">No React. No Vue. No Node. Just pure web fundamentals executed at a premium level.</p>

  <div class="tech-grid">
    <div class="tech-card">
      <div class="tech-icon">🌐</div>
      <div><div class="tech-name">HTML5</div><div class="tech-desc">Semantic structure</div></div>
    </div>
    <div class="tech-card">
      <div class="tech-icon" style="font-size:22px;">💨</div>
      <div><div class="tech-name">TailwindCSS CDN</div><div class="tech-desc">Utility-first styling</div></div>
    </div>
    <div class="tech-card">
      <div class="tech-icon">⚡</div>
      <div><div class="tech-name">Vanilla JS</div><div class="tech-desc">Pure ES6+ logic</div></div>
    </div>
    <div class="tech-card">
      <div class="tech-icon">📊</div>
      <div><div class="tech-name">Chart.js</div><div class="tech-desc">Interactive charts</div></div>
    </div>
    <div class="tech-card">
      <div class="tech-icon">🎨</div>
      <div><div class="tech-name">Font Awesome</div><div class="tech-desc">6,000+ icons</div></div>
    </div>
    <div class="tech-card">
      <div class="tech-icon">🔡</div>
      <div><div class="tech-name">Google Fonts</div><div class="tech-desc">Syne + DM Sans</div></div>
    </div>
    <div class="tech-card">
      <div class="tech-icon">💾</div>
      <div><div class="tech-name">LocalStorage</div><div class="tech-desc">Offline persistence</div></div>
    </div>
    <div class="tech-card">
      <div class="tech-icon">🎭</div>
      <div><div class="tech-name">CSS Animations</div><div class="tech-desc">60fps micro-UX</div></div>
    </div>
  </div>
</div>

<div class="section-divider"></div>

<!-- ══ QUICK START ══ -->
<div class="section reveal">
  <div class="section-label"><i class="fa-solid fa-rocket"></i> Quick Start</div>
  <h2 class="section-title">Up & Running in<br/><span class="grad-text">3 Seconds Flat</span></h2>
  <p class="section-desc">No npm install. No build step. No server. Just open and go.</p>

  <div class="code-block">
    <div class="code-header">
      <div class="code-dot" style="background:#ff6b6b;"></div>
      <div class="code-dot" style="background:#f4a261;"></div>
      <div class="code-dot" style="background:#06d6a0;"></div>
      <span class="code-title">terminal</span>
    </div>
    <div class="code-body">
<span class="comment"># Option 1 — Just open the file</span>
<span class="cmd">open</span> index.html

<span class="comment"># Option 2 — Serve locally</span>
<span class="cmd">npx</span> serve .

<span class="comment"># Option 3 — Python server</span>
<span class="cmd">python3</span> -m http.server <span class="str">8080</span>

<span class="comment"># Option 4 — VS Code Live Server</span>
<span class="kw">Right-click</span> index.html → <span class="str">"Open with Live Server"</span>
    </div>
  </div>

  <div class="code-block">
    <div class="code-header">
      <div class="code-dot" style="background:#ff6b6b;"></div>
      <div class="code-dot" style="background:#f4a261;"></div>
      <div class="code-dot" style="background:#06d6a0;"></div>
      <span class="code-title">demo credentials</span>
    </div>
    <div class="code-body">
<span class="comment"># Use any email + password — no validation required!</span>
Email:    <span class="str">alex@tripsync.ai</span>
Password: <span class="str">anything</span>  <span class="comment">← literally any text works</span>
    </div>
  </div>

  <div class="timeline" style="margin-top:48px;">
    <div class="tl-item">
      <div class="tl-dot"></div>
      <div class="tl-title">Step 1 — Download</div>
      <div class="tl-desc">Clone the repo or download the single <code style="color:var(--v);font-family:'JetBrains Mono',monospace;">index.html</code> file.</div>
    </div>
    <div class="tl-item">
      <div class="tl-dot" style="border-color:var(--v2);"></div>
      <div class="tl-title">Step 2 — Open</div>
      <div class="tl-desc">Double-click to open in any modern browser — Chrome, Firefox, Safari, Edge.</div>
    </div>
    <div class="tl-item">
      <div class="tl-dot" style="border-color:var(--g);"></div>
      <div class="tl-title">Step 3 — Login</div>
      <div class="tl-desc">Enter any email + password on the auth screen to enter the app.</div>
    </div>
    <div class="tl-item">
      <div class="tl-dot" style="border-color:var(--gold);"></div>
      <div class="tl-title">Step 4 — Explore</div>
      <div class="tl-desc">Navigate all 10 modules. Add expenses, chat with AI, explore the analytics — all works offline!</div>
    </div>
  </div>
</div>

<div class="section-divider"></div>

<!-- ══ UI FEATURES ══ -->
<div class="section reveal">
  <div class="section-label"><i class="fa-solid fa-wand-magic-sparkles"></i> UI Details</div>
  <h2 class="section-title">Every Micro-Interaction<br/><span class="grad-text">Considered</span></h2>

  <div class="feature-grid">
    <div class="feature-card" style="padding:20px;">
      <div style="display:flex;flex-wrap:wrap;gap:8px;">
        <span class="badge badge-v">✨ Glassmorphism</span>
        <span class="badge badge-g">🌗 Dark/Light Mode</span>
        <span class="badge badge-gold">🎯 Animated Counters</span>
        <span class="badge badge-sky">🔔 Toast Notifications</span>
        <span class="badge badge-v">💬 Modal System</span>
        <span class="badge badge-rose">⌨ Keyboard Shortcuts</span>
        <span class="badge badge-g">📱 Bottom Navigation</span>
        <span class="badge badge-gold">🗂 Sidebar Collapse</span>
        <span class="badge badge-v">⬆ Scroll Animations</span>
        <span class="badge badge-sky">🖱 Hover Interactions</span>
        <span class="badge badge-rose">📶 Offline Toggle</span>
        <span class="badge badge-g">🔄 Live Sync Status</span>
        <span class="badge badge-v">💾 LocalStorage</span>
        <span class="badge badge-gold">🔍 Global Search</span>
        <span class="badge badge-sky">🚀 FAB Button</span>
        <span class="badge badge-rose">🎬 CSS Animations</span>
      </div>
    </div>
  </div>

  <div style="display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:16px;margin-top:16px;">
    <div style="background:var(--surface);border:1px solid var(--border);border-radius:16px;padding:24px;">
      <div style="font-family:'Syne',sans-serif;font-weight:700;margin-bottom:12px;">⌨ Keyboard Shortcuts</div>
      <div style="font-size:13px;color:var(--text2);line-height:2;">
        <div><code style="background:var(--surface2);padding:2px 8px;border-radius:4px;font-family:'JetBrains Mono',monospace;color:var(--v);">Ctrl + K</code> → Focus global search</div>
        <div><code style="background:var(--surface2);padding:2px 8px;border-radius:4px;font-family:'JetBrains Mono',monospace;color:var(--v);">Escape</code> → Close all modals</div>
        <div><code style="background:var(--surface2);padding:2px 8px;border-radius:4px;font-family:'JetBrains Mono',monospace;color:var(--v);">Enter</code> → Send AI chat message</div>
      </div>
    </div>
    <div style="background:var(--surface);border:1px solid var(--border);border-radius:16px;padding:24px;">
      <div style="font-family:'Syne',sans-serif;font-weight:700;margin-bottom:12px;">📦 LocalStorage Keys</div>
      <div style="font-size:13px;color:var(--text2);line-height:2;">
        <div><code style="background:var(--surface2);padding:2px 8px;border-radius:4px;font-family:'JetBrains Mono',monospace;color:var(--g);">theme</code> → dark / light preference</div>
        <div><code style="background:var(--surface2);padding:2px 8px;border-radius:4px;font-family:'JetBrains Mono',monospace;color:var(--g);">expenses</code> → JSON expense array</div>
      </div>
    </div>
    <div style="background:var(--surface);border:1px solid var(--border);border-radius:16px;padding:24px;">
      <div style="font-family:'Syne',sans-serif;font-weight:700;margin-bottom:12px;">🎨 Design System</div>
      <div style="display:flex;gap:8px;flex-wrap:wrap;margin-top:8px;">
        <div style="width:32px;height:32px;border-radius:8px;background:#7c6aff;" title="#7c6aff"></div>
        <div style="width:32px;height:32px;border-radius:8px;background:#a855f7;" title="#a855f7"></div>
        <div style="width:32px;height:32px;border-radius:8px;background:#06d6a0;" title="#06d6a0"></div>
        <div style="width:32px;height:32px;border-radius:8px;background:#f4a261;" title="#f4a261"></div>
        <div style="width:32px;height:32px;border-radius:8px;background:#ff6b6b;" title="#ff6b6b"></div>
        <div style="width:32px;height:32px;border-radius:8px;background:#38bdf8;" title="#38bdf8"></div>
      </div>
      <div style="font-size:12px;color:var(--text3);margin-top:8px;">CSS variables via :root — full theme engine</div>
    </div>
  </div>
</div>

<div class="section-divider"></div>

<!-- ══ MODULES TABLE ══ -->
<div class="section reveal">
  <div class="section-label"><i class="fa-solid fa-table-list"></i> Module Map</div>
  <h2 class="section-title">What's Inside<br/><span class="grad-text">The Single File</span></h2>

  <div style="overflow-x:auto;">
    <table style="width:100%;border-collapse:collapse;font-size:14px;">
      <thead>
        <tr style="border-bottom:2px solid var(--border);">
          <th style="text-align:left;padding:12px 16px;color:var(--text3);font-weight:600;font-size:12px;text-transform:uppercase;letter-spacing:.5px;">#</th>
          <th style="text-align:left;padding:12px 16px;color:var(--text3);font-weight:600;font-size:12px;text-transform:uppercase;letter-spacing:.5px;">Module</th>
          <th style="text-align:left;padding:12px 16px;color:var(--text3);font-weight:600;font-size:12px;text-transform:uppercase;letter-spacing:.5px;">Key Features</th>
          <th style="text-align:left;padding:12px 16px;color:var(--text3);font-weight:600;font-size:12px;text-transform:uppercase;letter-spacing:.5px;">Status</th>
        </tr>
      </thead>
      <tbody>
        <tr style="border-bottom:1px solid var(--border);">
          <td style="padding:14px 16px;color:var(--text3);">01</td>
          <td style="padding:14px 16px;font-weight:600;">🔐 Authentication</td>
          <td style="padding:14px 16px;color:var(--text2);">Login, Signup, Forgot Password, Social Auth</td>
          <td style="padding:14px 16px;"><span class="badge badge-g">Live</span></td>
        </tr>
        <tr style="border-bottom:1px solid var(--border);background:rgba(255,255,255,.01);">
          <td style="padding:14px 16px;color:var(--text3);">02</td>
          <td style="padding:14px 16px;font-weight:600;">🏠 Dashboard</td>
          <td style="padding:14px 16px;color:var(--text2);">Stats, Map Preview, Weather, AI Recs, Charts</td>
          <td style="padding:14px 16px;"><span class="badge badge-g">Live</span></td>
        </tr>
        <tr style="border-bottom:1px solid var(--border);">
          <td style="padding:14px 16px;color:var(--text3);">03</td>
          <td style="padding:14px 16px;font-weight:600;">📍 Live Tracking</td>
          <td style="padding:14px 16px;color:var(--text2);">SVG Map, GPS Simulation, Journey Timeline</td>
          <td style="padding:14px 16px;"><span class="badge badge-g">Live</span></td>
        </tr>
        <tr style="border-bottom:1px solid var(--border);background:rgba(255,255,255,.01);">
          <td style="padding:14px 16px;color:var(--text3);">04</td>
          <td style="padding:14px 16px;font-weight:600;">📅 Itinerary</td>
          <td style="padding:14px 16px;color:var(--text2);">7-Day Planner, AI Generate, Day Tabs, Add/Remove</td>
          <td style="padding:14px 16px;"><span class="badge badge-g">Live</span></td>
        </tr>
        <tr style="border-bottom:1px solid var(--border);">
          <td style="padding:14px 16px;color:var(--text3);">05</td>
          <td style="padding:14px 16px;font-weight:600;">💰 Expenses</td>
          <td style="padding:14px 16px;color:var(--text2);">Budget Tracker, Categories, Charts, LocalStorage</td>
          <td style="padding:14px 16px;"><span class="badge badge-g">Live</span></td>
        </tr>
        <tr style="border-bottom:1px solid var(--border);background:rgba(255,255,255,.01);">
          <td style="padding:14px 16px;color:var(--text3);">06</td>
          <td style="padding:14px 16px;font-weight:600;">📸 Memories</td>
          <td style="padding:14px 16px;color:var(--text2);">Masonry Gallery, Location Tags, Filters</td>
          <td style="padding:14px 16px;"><span class="badge badge-g">Live</span></td>
        </tr>
        <tr style="border-bottom:1px solid var(--border);">
          <td style="padding:14px 16px;color:var(--text3);">07</td>
          <td style="padding:14px 16px;font-weight:600;">📊 Analytics</td>
          <td style="padding:14px 16px;color:var(--text2);">Bar, Line, Polar Charts · Top Destinations</td>
          <td style="padding:14px 16px;"><span class="badge badge-g">Live</span></td>
        </tr>
        <tr style="border-bottom:1px solid var(--border);background:rgba(255,255,255,.01);">
          <td style="padding:14px 16px;color:var(--text3);">08</td>
          <td style="padding:14px 16px;font-weight:600;">🤖 AI Assistant</td>
          <td style="padding:14px 16px;color:var(--text2);">Chat UI, Typing Anim, Context-Aware Responses</td>
          <td style="padding:14px 16px;"><span class="badge badge-g">Live</span></td>
        </tr>
        <tr style="border-bottom:1px solid var(--border);">
          <td style="padding:14px 16px;color:var(--text3);">09</td>
          <td style="padding:14px 16px;font-weight:600;">👥 Group Travel</td>
          <td style="padding:14px 16px;color:var(--text2);">Squad, Group Chat, Expense Splitting, Live Map</td>
          <td style="padding:14px 16px;"><span class="badge badge-g">Live</span></td>
        </tr>
        <tr style="border-bottom:1px solid var(--border);background:rgba(255,255,255,.01);">
          <td style="padding:14px 16px;color:var(--text3);">10</td>
          <td style="padding:14px 16px;font-weight:600;">🛡 Safety</td>
          <td style="padding:14px 16px;color:var(--text2);">SOS Button, Emergency Contacts, Medical Card</td>
          <td style="padding:14px 16px;"><span class="badge badge-g">Live</span></td>
        </tr>
        <tr>
          <td style="padding:14px 16px;color:var(--text3);">11</td>
          <td style="padding:14px 16px;font-weight:600;">⚙ Settings</td>
          <td style="padding:14px 16px;color:var(--text2);">Profile, Themes, Notifications, Export, Pro Plan</td>
          <td style="padding:14px 16px;"><span class="badge badge-g">Live</span></td>
        </tr>
      </tbody>
    </table>
  </div>
</div>

<div class="section-divider"></div>

<!-- ══ FOOTER ══ -->
<footer class="footer">
  <div class="footer-logo grad-text">TripSync AI</div>
  <div class="footer-tagline">Smart Travel Companion · Single HTML File · Zero Dependencies</div>
  <div class="footer-links">
    <a href="#" class="footer-link"><i class="fa-brands fa-github"></i> GitHub</a>
    <a href="#" class="footer-link"><i class="fa-solid fa-globe"></i> Live Demo</a>
    <a href="#" class="footer-link"><i class="fa-brands fa-dribbble"></i> Dribbble</a>
    <a href="#" class="footer-link"><i class="fa-solid fa-envelope"></i> Contact</a>
  </div>

  <div style="display:flex;justify-content:center;gap:24px;margin-bottom:32px;flex-wrap:wrap;">
    <div style="text-align:center;">
      <div style="font-family:'Syne',sans-serif;font-size:24px;font-weight:800;color:var(--v);">1</div>
      <div style="font-size:12px;color:var(--text3);">HTML File</div>
    </div>
    <div style="text-align:center;">
      <div style="font-family:'Syne',sans-serif;font-size:24px;font-weight:800;color:var(--g);">12</div>
      <div style="font-size:12px;color:var(--text3);">Modules</div>
    </div>
    <div style="text-align:center;">
      <div style="font-family:'Syne',sans-serif;font-size:24px;font-weight:800;color:var(--gold);">0</div>
      <div style="font-size:12px;color:var(--text3);">Dependencies</div>
    </div>
    <div style="text-align:center;">
      <div style="font-family:'Syne',sans-serif;font-size:24px;font-weight:800;color:var(--v2);">∞</div>
      <div style="font-size:12px;color:var(--text3);">Adventures</div>
    </div>
  </div>

  <div class="footer-copy">
    Built with ❤️ using HTML5 · TailwindCSS · Chart.js · Font Awesome<br/>
    <span style="color:var(--text3);">© 2025 TripSync AI · MIT License</span>
  </div>
</footer>

<script>
// Scroll reveal
const observer = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      e.target.classList.add('visible');
      observer.unobserve(e.target);
    }
  });
}, { threshold: 0.08 });

document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

// Stagger feature cards
document.querySelectorAll('.feature-card, .ss-card, .tech-card').forEach((el, i) => {
  el.style.transitionDelay = `${i * 0.05}s`;
});
</script>
</body>
</html>

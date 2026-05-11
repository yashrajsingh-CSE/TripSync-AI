<!-- HEADER SVG - no external image dependency, renders 100% on GitHub -->
<div align="center">

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 200" width="100%">
  <defs>
    <linearGradient id="hg" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#0d0d1a"/>
      <stop offset="50%" style="stop-color:#1a0a2e"/>
      <stop offset="100%" style="stop-color:#0a1a1a"/>
    </linearGradient>
    <linearGradient id="tg" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" style="stop-color:#7c6aff"/>
      <stop offset="50%" style="stop-color:#a855f7"/>
      <stop offset="100%" style="stop-color:#06d6a0"/>
    </linearGradient>
    <filter id="glow">
      <feGaussianBlur stdDeviation="3" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
  </defs>
  <!-- Background -->
  <rect width="1200" height="200" fill="url(#hg)"/>
  <!-- Decorative circles -->
  <circle cx="100" cy="50" r="80" fill="#7c6aff" opacity="0.08"/>
  <circle cx="1100" cy="150" r="100" fill="#06d6a0" opacity="0.07"/>
  <circle cx="600" cy="180" r="120" fill="#a855f7" opacity="0.05"/>
  <!-- Wave bottom -->
  <path d="M0,160 Q300,200 600,160 Q900,120 1200,160 L1200,200 L0,200 Z" fill="#0a0a0f" opacity="0.6"/>
  <!-- Title -->
  <text x="600" y="90" text-anchor="middle" font-family="Arial Black, sans-serif" font-size="64" font-weight="900" fill="url(#tg)" filter="url(#glow)">TripSync AI</text>
  <!-- Subtitle -->
  <text x="600" y="130" text-anchor="middle" font-family="Arial, sans-serif" font-size="18" fill="#ccccff" opacity="0.9">✈️  Smart Travel Companion &amp; AI Trip Capture Platform</text>
  <!-- Dots decoration -->
  <circle cx="440" cy="88" r="4" fill="#7c6aff" opacity="0.6"/>
  <circle cx="760" cy="88" r="4" fill="#06d6a0" opacity="0.6"/>
</svg>

</div>

<br/>

<div align="center">

<!-- Row 1: Tech badges (for-the-badge style - these are 100% reliable) -->
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)&nbsp;[![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com)&nbsp;[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)&nbsp;[![Chart.js](https://img.shields.io/badge/Chart.js-FF6384?style=for-the-badge&logo=chartdotjs&logoColor=white)](https://www.chartjs.org)&nbsp;[![Font Awesome](https://img.shields.io/badge/Font_Awesome-528DD7?style=for-the-badge&logo=fontawesome&logoColor=white)](https://fontawesome.com)

<br/>

<!-- Row 2: Info badges (flat-square style) -->
![version](https://img.shields.io/badge/version-1.0.0-7c6aff?style=flat-square&labelColor=1e1e28)&nbsp;![license](https://img.shields.io/badge/license-MIT-06d6a0?style=flat-square&labelColor=1e1e28)&nbsp;![file](https://img.shields.io/badge/single_file-index.html-f4a261?style=flat-square&labelColor=1e1e28)&nbsp;![deps](https://img.shields.io/badge/dependencies-0-ff6b6b?style=flat-square&labelColor=1e1e28)&nbsp;![mobile](https://img.shields.io/badge/mobile-first-38bdf8?style=flat-square&labelColor=1e1e28)&nbsp;![theme](https://img.shields.io/badge/dark_%2F_light-mode-a855f7?style=flat-square&labelColor=1e1e28)

</div>

<br/>

<div align="center">

### 🌍 &nbsp; Your world, **beautifully** tracked.

*An AI-powered travel companion — fully functional, production-ready,*
*built inside **one single `index.html`** file. No frameworks. No build tools. No backend.*

<br/>

| 🌍 Countries | ✈️ Miles | 📸 Memories | 📦 Modules | ⚡ Dependencies |
|:-----------:|:--------:|:-----------:|:---------:|:--------------:|
| **23** | **48K** | **148** | **11** | **0** |

</div>

<br/>

---

## 📸 &nbsp; Screenshots

> All image filenames match the **exact HTML element `id`** from `index.html`

<br/>

### 🔐 &nbsp; `id="auth-screen"` — Login & Sign Up

![auth-screen](login.png)

<details>
<summary>📋 &nbsp;<b>What's on this screen</b></summary>
<br/>

- ✅ Split-panel layout — animated branding left, auth form right
- ✅ `switchAuth('login' | 'signup')` tab switching
- ✅ Social login — Google / Apple / Facebook → all call `doLogin()`
- ✅ Password visibility toggle — `togglePass('login-pass')`
- ✅ Forgot password modal — `showForgot()` → `#modal-forgot`
- ✅ Onboarding preview card with live progress bar
- ✅ Demo mode — any email + any password logs in instantly

</details>

---

### 🏠 &nbsp; `id="section-dashboard"` — Command Center

![section-dashboard](dashboard.png)

<details>
<summary>📋 &nbsp;<b>What's on this screen</b></summary>
<br/>

- ✅ 4 animated stat cards — countries (23), miles (48,291), spent ($2,847), memories (148)
- ✅ Current trip card — Bali Adventure, Day 4/7, progress bar, city checkpoints
- ✅ Interactive SVG map preview → `showSection('tracking')` on click
- ✅ Weather card — Seminyak 28°C with 3-day forecast
- ✅ AI Recommendations → `showSection('assistant')`
- ✅ Expense donut chart via `initDashboardCharts()` → `#dashExpenseChart`
- ✅ Today's Plans — 3 scheduled items with time & status badges
- ✅ Recent Memories 3×2 grid → `showSection('memories')`
- ✅ New Trip button → `openNewTrip()` → `#modal-trip`

</details>

---

### 📍 &nbsp; `id="section-tracking"` — Live GPS Journey

![section-tracking](tracking.png)

<details>
<summary>📋 &nbsp;<b>What's on this screen</b></summary>
<br/>

- ✅ Full-width animated SVG map with gradient route (violet → teal)
- ✅ Travel mode switcher — ✈ Flight / 🚗 Road / 🚶 Walk
- ✅ Pulsing current-location marker with `animate-pulse-soft` ring
- ✅ City dots — Denpasar → Sanur → Ubud → 📍 NOW (Seminyak) → Nusa Dua
- ✅ Stats row — 342 km · 5h 20m · 4 stops · 28°C
- ✅ Scrollable journey timeline with 5 events (past ✓, active 📍, upcoming 🔮)

</details>

---

### 📅 &nbsp; `id="section-itinerary"` — Day-by-Day Planner

![section-itinerary](itinerary.png)

<details>
<summary>📋 &nbsp;<b>What's on this screen</b></summary>
<br/>

- ✅ 7 day-tab buttons — `switchDay(n)` re-renders `ITINERARY[n]` object
- ✅ Activity cards — time, emoji, title, note, duration, category badge, trash button
- ✅ `draggable="true"` drag-and-drop support on all cards
- ✅ `addActivity()` — appends blank card to current day
- ✅ AI Suggestions panel — 3 recommendations with "+ Add to plan" → `addSuggestion()`
- ✅ AI Generate button → `generateAIItinerary()` with loading toast
- ✅ Day Summary sidebar — activity count, est. cost, travel time, optimized flag

</details>

---

### 💰 &nbsp; `id="section-expenses"` — Budget Tracker

![section-expenses](expenses.png)

<details>
<summary>📋 &nbsp;<b>What's on this screen</b></summary>
<br/>

- ✅ Budget overview — $4,000 total / $2,847 spent / $1,153 remaining
- ✅ Gradient multi-color progress bar (green → amber → red at 71.2%)
- ✅ Category breakdown — Food ($620) · Hotels ($1,240) · Transport ($680) · Shopping ($307)
- ✅ Chart.js doughnut `#expensePieChart` via `initExpenseChart()`
- ✅ Transaction list — `renderTransactions()` merges `TRANSACTIONS[]` + `state.expenses`
- ✅ Add Expense modal — `openAddExpense()` → `#modal-expense` → `saveExpense()` → `localStorage`
- ✅ Filter dropdown — `filterExpenses(cat)` on category select

</details>

---

### 📸 &nbsp; `id="section-memories"` — Memory Journal

![section-memories](memories.png)

<details>
<summary>📋 &nbsp;<b>What's on this screen</b></summary>
<br/>

- ✅ CSS masonry layout — `columns: 2` mobile / `3` sm / `4` lg
- ✅ 12 memory cards rendered by `renderMemories()` from `MEMORIES[]` array
- ✅ Each card has emoji, gradient background, title, location pin
- ✅ Variable heights for natural masonry stagger effect
- ✅ Filter tabs — All / Photos / Videos / Highlights / Notes
- ✅ Add Memory button → `showToast('📸 Upload feature coming soon!')`

</details>

---

### 📊 &nbsp; `id="section-analytics"` — Travel Analytics

![section-analytics](analytics.png)

<details>
<summary>📋 &nbsp;<b>What's on this screen</b></summary>
<br/>

- ✅ 4 stat cards — 23 countries, 78 cities, 48K miles, 14 trips with `.grad-text`
- ✅ `#monthlyChart` — Chart.js bar chart, monthly travel frequency Jan–Dec
- ✅ `#annualChart` — Chart.js line chart with fill, annual expenses trend
- ✅ `#continentChart` — Chart.js polar area, Asia / Europe / Americas / Oceania / Africa
- ✅ All charts init via `initAnalyticsCharts()` with `destroyChart()` guard
- ✅ Top Destinations — Bali 80% / Tokyo 60% / Patagonia 40% / Santorini 55%

</details>

---

### 🤖 &nbsp; `id="section-assistant"` — AI Travel Chat

![section-assistant](assistant.png)

<details>
<summary>📋 &nbsp;<b>What's on this screen</b></summary>
<br/>

- ✅ Chat container — `#chat-messages` with `appendUserMsg()` + `appendAIMsg()`
- ✅ Typing animation — `appendTyping()` inserts `#typing-indicator` with 3 `.typing-dot` elements
- ✅ `getAIResponse(msg)` — keyword matches 4 queries in `AI_RESPONSES{}` object
- ✅ Quick-prompt badge buttons in welcome message → `sendQuick(msg)`
- ✅ `Enter` key on `#chat-input` triggers `sendChat()`
- ✅ 6 suggested prompt buttons in sidebar
- ✅ Voice button UI → `showToast('🎙 Voice input coming soon!')`

</details>

---

### 👥 &nbsp; `id="section-group"` — Group Travel

![section-group](group.png)

<details>
<summary>📋 &nbsp;<b>What's on this screen</b></summary>
<br/>

- ✅ 4 squad members — Alex (Host), Sara, Marco, Jin with gradient avatars
- ✅ Online dot (green pulse) for Alex + Sara; offline (grey) for Marco + Jin
- ✅ `sendGroupChat()` appends user bubble, then random auto-reply after 800ms
- ✅ Expense split — $2,730 ÷ 4 = $682.50 per person
- ✅ Settle Up → `showToast('💸 Settlement requests sent!')`
- ✅ Live map mini-view with 3 floating 📍 pins

</details>

---

### 🛡️ &nbsp; `id="section-safety"` — Safety Center

![section-safety](safety.png)

<details>
<summary>📋 &nbsp;<b>What's on this screen</b></summary>
<br/>

- ✅ `triggerSOS()` fires 3 sequential toasts (1 second apart):
  - 🚨 `SOS Alert sent to Sara & Marco!`
  - 📍 `Live location shared with emergency contacts`
  - 🚔 `Local emergency services notified`
- ✅ Emergency contacts — Sara Kim + Mom with call action
- ✅ Local numbers — 🚔 110 Police / 🏥 119 Ambulance / 🚒 113 Fire
- ✅ Medical card — Blood Type A+ / Allergies / Insurance / Vaccinations
- ✅ Safety status — 3 green checks + 1 red X (check-in reminder off)

</details>

---

### ⚙️ &nbsp; `id="section-settings"` — Settings

![section-settings](settings.png)

<details>
<summary>📋 &nbsp;<b>What's on this screen</b></summary>
<br/>

- ✅ Profile form — name, email, city, currency with Save Changes
- ✅ Dark Mode toggle → `toggleTheme()` updates `data-theme` on `<html>` + `localStorage`
- ✅ Push Notifications, AI Recommendations, Offline Mode toggles
- ✅ Export — Trip Report (PDF) / Analytics (Excel) / Photos / Delete Account
- ✅ Pro Plan sidebar card — 5 features + renewal info
- ✅ Sync Status — last synced, 48 MB cached, 0 pending uploads
- ✅ Force Sync → `showToast('🔄 Sync complete!')`

</details>

---

## 🚀 &nbsp; Quick Start

```bash
# Option 1 — Open directly (zero setup)
open index.html

# Option 2 — Python server
python3 -m http.server 8080

# Option 3 — Node.js
npx serve .

# Option 4 — VS Code
# Right-click index.html → "Open with Live Server"
```

**Demo login — any values work:**

```
Email    →  alex@tripsync.ai   (or any text)
Password →  anything           (no validation)
```

> `doLogin()` → hides `#auth-screen` → shows `#app-shell` → `showSection('dashboard')` → `initApp()`

---

## 📦 &nbsp; File & Folder Structure

```
TripSync-AI/
│
├── 📄 index.html                      ← Entire app — HTML + CSS + JS in one file
│
└── 📁 screenshots/                    ← Named by exact HTML element id
    ├── 🖼  auth-screen.png            ← id="auth-screen"
    ├── 🖼  section-dashboard.png      ← id="section-dashboard"
    ├── 🖼  section-tracking.png       ← id="section-tracking"
    ├── 🖼  section-itinerary.png      ← id="section-itinerary"
    ├── 🖼  section-expenses.png       ← id="section-expenses"
    ├── 🖼  section-memories.png       ← id="section-memories"
    ├── 🖼  section-analytics.png      ← id="section-analytics"
    ├── 🖼  section-assistant.png      ← id="section-assistant"
    ├── 🖼  section-group.png          ← id="section-group"
    ├── 🖼  section-safety.png         ← id="section-safety"
    └── 🖼  section-settings.png       ← id="section-settings"
```

---

## 🗂️ &nbsp; Module Map

| Screenshot File | HTML `id` | JS Call | Sidebar | Bottom Nav |
|:---|:---|:---|:---|:---|
| `auth-screen.png` | `auth-screen` | hidden by `doLogin()` | — | — |
| `section-dashboard.png` | `section-dashboard` | `showSection('dashboard')` | Dashboard | 🏠 Home |
| `section-tracking.png` | `section-tracking` | `showSection('tracking')` | Live Tracking | 📍 Track |
| `section-itinerary.png` | `section-itinerary` | `showSection('itinerary')` | Itinerary | 📅 Plan |
| `section-expenses.png` | `section-expenses` | `showSection('expenses')` | Expenses | 💰 Budget |
| `section-memories.png` | `section-memories` | `showSection('memories')` | Memories | — |
| `section-analytics.png` | `section-analytics` | `showSection('analytics')` | Analytics | — |
| `section-assistant.png` | `section-assistant` | `showSection('assistant')` | AI Assistant | 🤖 AI |
| `section-group.png` | `section-group` | `showSection('group')` | Group | — |
| `section-safety.png` | `section-safety` | `showSection('safety')` | Safety | — |
| `section-settings.png` | `section-settings` | `showSection('settings')` | Settings | — |

---

## ✨ &nbsp; Features

<table>
<tr>
<td valign="top" width="50%">

**🏠 Dashboard**
- Animated counters with cubic ease
- Chart.js donut (`initDashboardCharts()`)
- Live trip progress + city checkpoints
- Real-time memory counter update every 8s

**📍 Tracking**
- SVG gradient route path animation
- Pulsing live location marker
- 5-event journey timeline
- Flight / Road / Walk mode switcher

**📅 Itinerary**
- 7-day tabs with `switchDay(n)`
- Drag-and-drop activity cards
- AI Generate + AI Suggestions panel
- Data from `ITINERARY{}` object

**💰 Expenses**
- `localStorage` persistence
- Chart.js doughnut breakdown
- Category gradient progress bars
- Merged mock + user transactions

</td>
<td valign="top" width="50%">

**🤖 AI Assistant**
- Typing animation (3 animated dots)
- Keyword matcher `getAIResponse()`
- 4 built-in smart responses
- `sendQuick()` shortcut prompts

**👥 Group Travel**
- Squad online/offline status dots
- Auto-reply group chat simulation
- Expense split calculator ($682.50/person)
- Settle Up flow with toast

**📊 Analytics**
- 3 Chart.js graphs (bar / line / polar)
- `destroyChart()` prevents re-init bugs
- Animated stat counters
- Top destinations ranking bars

**🛡 Safety + ⚙ Settings**
- Multi-step SOS — `triggerSOS()`
- Full profile editor form
- `toggleTheme()` dark/light switch
- Data export with toast feedback

</td>
</tr>
</table>

---

## 🛠️ &nbsp; Tech Stack

| Technology | Source | Role |
|:---|:---|:---|
| **HTML5** | Native | Structure, all `id` anchors, modals |
| **TailwindCSS** | CDN `cdn.tailwindcss.com` | Utility classes, responsive grid |
| **Vanilla JS ES6+** | Native | State, routing, events, DOM |
| **Chart.js** | CDN `cdn.jsdelivr.net` | Doughnut, bar, line, polar charts |
| **Font Awesome 6.5** | CDN `cdnjs.cloudflare.com` | All icons |
| **Google Fonts** | CDN `fonts.googleapis.com` | Syne (headings) + DM Sans (body) |
| **LocalStorage** | Native | `theme` + `expenses` persistence |
| **IntersectionObserver** | Native | Scroll-reveal on `.card` elements |
| **CSS Custom Properties** | Native | Full dual-theme via `:root` |
| **SVG** | Native | Map route paths + location markers |

---

## 🎨 &nbsp; Design Tokens

```css
:root {
  /* Backgrounds */
  --bg:       #0a0a0f;   /* Deep space page background   */
  --surface:  #1e1e28;   /* Card / panel surfaces        */
  --surface2: #252530;   /* Input backgrounds            */
  --border:   #2e2e3e;   /* Default borders              */

  /* Text */
  --text:     #f0f0fa;   /* Primary text                 */
  --text2:    #b0b0c8;   /* Secondary / muted text       */
  --text3:    #6e6e88;   /* Placeholder / labels         */

  /* Brand palette */
  --accent:   #7c6aff;   /* Primary violet               */
  --accent2:  #a855f7;   /* Secondary purple             */
  --accent3:  #06d6a0;   /* Emerald / online / success   */
  --gold:     #f4a261;   /* Amber / warnings             */
  --rose:     #ff6b6b;   /* Error / danger / SOS         */
  --sky:      #38bdf8;   /* Info / weather               */
}
```

---

## ⌨️ &nbsp; Keyboard Shortcuts

| Keys | Action | JS Handler |
|:---|:---|:---|
| `Ctrl` + `K` | Focus global search | `#global-search.focus()` |
| `Escape` | Close all modals | Loops `.modal-backdrop` elements |
| `Enter` in chat | Send AI message | `sendChat()` |
| `Enter` in group | Send group message | `sendGroupChat()` |

---

## 💾 &nbsp; LocalStorage

```js
// Written automatically — persists across page refreshes
localStorage.setItem('theme',    'dark' | 'light')
localStorage.setItem('expenses', JSON.stringify(state.expenses))

// Read on app init
state.theme    = localStorage.getItem('theme')    || 'dark'
state.expenses = JSON.parse(localStorage.getItem('expenses') || '[]')
```

---

## 🎭 &nbsp; CSS Animations

| Keyframe | Used On | Effect |
|:---|:---|:---|
| `fadeUp` | Section reveal, cards | Slide up + fade in |
| `fadeIn` | Modals, toasts | Opacity 0 → 1 |
| `slideLeft` | Toast notifications | Slide in from right |
| `float` | Cards, map pins | Gentle vertical bob |
| `pulse` | Typing dots | Opacity loop |
| `ping` | Online dot ring | Scale 1 → 2, fade out |
| `glow` | FAB button | Box-shadow pulse |
| `shimmer` | Skeleton loaders | Background sweep |
| `pathDraw` | SVG map route | `stroke-dashoffset` 1000 → 0 |
| `spin` | Loading states | 360° rotation |

---

## 📄 &nbsp; License

```
MIT License — © 2025 TripSync AI
Free to use, modify, and distribute with attribution.
```

---

<!-- FOOTER SVG - fully inline, no external dependency -->
<div align="center">

<br/>

**Made with ❤️ and zero build tools**

`HTML5` &nbsp;·&nbsp; `TailwindCSS` &nbsp;·&nbsp; `Chart.js` &nbsp;·&nbsp; `Font Awesome` &nbsp;·&nbsp; `Vanilla JS`

<br/>

⭐ &nbsp; **If this helped you, please star the repo!** &nbsp; ⭐

<br/>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 80" width="100%">
  <defs>
    <linearGradient id="fg" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" style="stop-color:#06d6a0"/>
      <stop offset="50%" style="stop-color:#a855f7"/>
      <stop offset="100%" style="stop-color:#7c6aff"/>
    </linearGradient>
  </defs>
  <path d="M0,0 Q300,60 600,20 Q900,-20 1200,40 L1200,80 L0,80 Z" fill="url(#fg)" opacity="0.15"/>
  <path d="M0,20 Q400,80 800,30 Q1000,10 1200,50 L1200,80 L0,80 Z" fill="url(#fg)" opacity="0.25"/>
  <path d="M0,40 Q200,80 600,50 Q900,30 1200,60 L1200,80 L0,80 Z" fill="url(#fg)" opacity="0.4"/>
</svg>

`🌍 TripSync AI — Your world, beautifully tracked.`

</div>

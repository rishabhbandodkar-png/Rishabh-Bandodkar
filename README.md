# Rishabh-Bandodkar
<!DOCTYPE html>

<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Quest Log — Task & Reminder App</title>
<link href="https://fonts.googleapis.com/css2?family=MedievalSharp&family=Cinzel:wght@400;600;900&family=Crimson+Text:ital,wght@0,400;0,600;1,400&display=swap" rel="stylesheet">
<style>
  :root {
    --bg-deep: #0d0a1a;
    --bg-mid: #12102a;
    --bg-panel: #1a1630;
    --bg-card: #1f1b3a;
    --border: #3a2d6e;
    --border-glow: #7c5cbf;
    --gold: #f0c040;
    --gold-dim: #a87c20;
    --amber: #e8932a;
    --green: #4ade80;
    --green-dim: #166534;
    --red: #f87171;
    --red-dim: #7f1d1d;
    --purple: #a78bfa;
    --purple-bright: #c4b5fd;
    --blue: #60a5fa;
    --text-main: #e8dfc8;
    --text-dim: #8b7aa0;
    --text-faint: #4a3f60;
    --xp-bar: #7c3aed;
    --xp-fill: #a855f7;
    --shadow-glow: 0 0 20px rgba(124,92,191,0.3);
    --shadow-gold: 0 0 15px rgba(240,192,64,0.4);
  }

- { margin: 0; padding: 0; box-sizing: border-box; }

body {
background: var(–bg-deep);
color: var(–text-main);
font-family: ‘Crimson Text’, Georgia, serif;
font-size: 17px;
min-height: 100vh;
overflow-x: hidden;
background-image:
radial-gradient(ellipse at 20% 20%, rgba(124,92,191,0.07) 0%, transparent 60%),
radial-gradient(ellipse at 80% 80%, rgba(168,133,250,0.05) 0%, transparent 60%),
url(“data:image/svg+xml,%3Csvg width=‘60’ height=‘60’ viewBox=‘0 0 60 60’ xmlns=‘http://www.w3.org/2000/svg’%3E%3Cg fill=‘none’ fill-rule=‘evenodd’%3E%3Cg fill=’%234a3f60’ fill-opacity=‘0.08’%3E%3Cpath d=‘M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z’/%3E%3C/g%3E%3C/g%3E%3C/svg%3E”);
}

/* Stars background */
body::before {
content: ‘’;
position: fixed;
inset: 0;
background-image:
radial-gradient(1px 1px at 10% 15%, rgba(255,255,255,0.3) 0%, transparent 100%),
radial-gradient(1px 1px at 25% 40%, rgba(255,255,255,0.2) 0%, transparent 100%),
radial-gradient(1px 1px at 40% 5%, rgba(255,255,255,0.3) 0%, transparent 100%),
radial-gradient(1px 1px at 55% 70%, rgba(255,255,255,0.15) 0%, transparent 100%),
radial-gradient(1px 1px at 70% 20%, rgba(255,255,255,0.25) 0%, transparent 100%),
radial-gradient(1px 1px at 85% 55%, rgba(255,255,255,0.2) 0%, transparent 100%),
radial-gradient(1px 1px at 92% 10%, rgba(255,255,255,0.3) 0%, transparent 100%),
radial-gradient(1px 1px at 15% 85%, rgba(255,255,255,0.2) 0%, transparent 100%),
radial-gradient(1px 1px at 60% 90%, rgba(255,255,255,0.15) 0%, transparent 100%);
pointer-events: none;
z-index: 0;
}

.app { position: relative; z-index: 1; max-width: 900px; margin: 0 auto; padding: 20px 16px 60px; }

/* ── HEADER ── */
.header {
text-align: center;
padding: 36px 20px 24px;
position: relative;
}
.header::before {
content: ‘⚔’;
position: absolute; top: 8px; left: 50%; transform: translateX(-50%);
font-size: 14px; color: var(–gold-dim); opacity: 0.5;
}
.header h1 {
font-family: ‘Cinzel’, serif;
font-size: clamp(28px, 6vw, 48px);
font-weight: 900;
color: var(–gold);
text-shadow: 0 0 30px rgba(240,192,64,0.5), 0 2px 4px rgba(0,0,0,0.8);
letter-spacing: 0.08em;
line-height: 1.1;
}
.header .subtitle {
font-family: ‘Crimson Text’, serif;
font-style: italic;
color: var(–text-dim);
font-size: 15px;
margin-top: 6px;
letter-spacing: 0.05em;
}

/* ── CHARACTER PANEL ── */
.char-panel {
background: var(–bg-panel);
border: 1px solid var(–border);
border-radius: 12px;
padding: 20px 24px;
margin-bottom: 20px;
box-shadow: var(–shadow-glow);
display: grid;
grid-template-columns: auto 1fr auto;
gap: 16px;
align-items: center;
}
.char-avatar {
width: 64px; height: 64px;
border: 2px solid var(–gold);
border-radius: 50%;
display: flex; align-items: center; justify-content: center;
font-size: 30px;
background: radial-gradient(circle, #2d1b69 0%, #1a0f3a 100%);
box-shadow: 0 0 16px rgba(240,192,64,0.3);
flex-shrink: 0;
}
.char-info { min-width: 0; }
.char-name {
font-family: ‘Cinzel’, serif;
font-size: 18px;
font-weight: 600;
color: var(–text-main);
}
.char-title { font-style: italic; color: var(–purple); font-size: 13px; margin-bottom: 8px; }
.xp-bar-wrap { }
.xp-label { font-size: 12px; color: var(–text-dim); margin-bottom: 4px; letter-spacing: 0.05em; }
.xp-bar {
height: 12px;
background: rgba(124,58,237,0.15);
border: 1px solid var(–xp-bar);
border-radius: 6px;
overflow: hidden;
position: relative;
}
.xp-fill {
height: 100%;
background: linear-gradient(90deg, var(–xp-bar), var(–xp-fill), #d8b4fe);
border-radius: 6px;
transition: width 0.6s cubic-bezier(0.34, 1.56, 0.64, 1);
position: relative;
}
.xp-fill::after {
content: ‘’;
position: absolute;
top: 2px; left: 4px; right: 4px;
height: 3px;
background: rgba(255,255,255,0.25);
border-radius: 2px;
}
.char-stats { display: flex; flex-direction: column; gap: 6px; align-items: flex-end; }
.stat-badge {
background: var(–bg-card);
border: 1px solid var(–border);
border-radius: 8px;
padding: 4px 10px;
font-family: ‘Cinzel’, serif;
font-size: 12px;
text-align: center;
white-space: nowrap;
}
.stat-badge span { display: block; color: var(–text-dim); font-size: 10px; letter-spacing: 0.08em; }
.stat-badge strong { color: var(–gold); font-size: 14px; }
.streak-badge { border-color: var(–amber) !important; }
.streak-badge strong { color: var(–amber) !important; }

/* ── TABS ── */
.tabs {
display: flex; gap: 4px;
margin-bottom: 16px;
background: var(–bg-panel);
border: 1px solid var(–border);
border-radius: 10px;
padding: 4px;
}
.tab-btn {
flex: 1;
padding: 8px 12px;
background: transparent;
border: none;
border-radius: 7px;
color: var(–text-dim);
font-family: ‘Cinzel’, serif;
font-size: 12px;
letter-spacing: 0.06em;
cursor: pointer;
transition: all 0.2s;
}
.tab-btn:hover { color: var(–text-main); background: rgba(124,92,191,0.1); }
.tab-btn.active {
background: linear-gradient(135deg, #3b1f8c, #5b3ab0);
color: var(–purple-bright);
box-shadow: 0 0 10px rgba(124,92,191,0.3);
}

.tab-panel { display: none; }
.tab-panel.active { display: block; }

/* ── ADD QUEST FORM ── */
.add-form {
background: var(–bg-panel);
border: 1px solid var(–border);
border-radius: 12px;
padding: 20px;
margin-bottom: 20px;
box-shadow: var(–shadow-glow);
}
.form-title {
font-family: ‘Cinzel’, serif;
font-size: 14px;
color: var(–gold);
letter-spacing: 0.08em;
margin-bottom: 14px;
display: flex; align-items: center; gap: 8px;
}
.form-row { display: flex; gap: 10px; flex-wrap: wrap; margin-bottom: 10px; }
.form-row:last-child { margin-bottom: 0; }
.field { display: flex; flex-direction: column; gap: 5px; flex: 1; min-width: 140px; }
.field label { font-size: 11px; color: var(–text-dim); letter-spacing: 0.08em; font-family: ‘Cinzel’, serif; }
.field input, .field select, .field textarea {
background: var(–bg-deep);
border: 1px solid var(–border);
border-radius: 7px;
color: var(–text-main);
font-family: ‘Crimson Text’, serif;
font-size: 15px;
padding: 8px 12px;
outline: none;
transition: border-color 0.2s, box-shadow 0.2s;
width: 100%;
}
.field input:focus, .field select:focus, .field textarea:focus {
border-color: var(–border-glow);
box-shadow: 0 0 8px rgba(124,92,191,0.25);
}
.field select option { background: var(–bg-deep); }
.field textarea { resize: vertical; min-height: 60px; }

.btn {
padding: 10px 20px;
border: none;
border-radius: 8px;
font-family: ‘Cinzel’, serif;
font-size: 12px;
letter-spacing: 0.08em;
cursor: pointer;
transition: all 0.2s;
white-space: nowrap;
}
.btn-primary {
background: linear-gradient(135deg, #5b3ab0, #7c5cbf);
color: var(–purple-bright);
border: 1px solid var(–border-glow);
box-shadow: 0 0 12px rgba(124,92,191,0.2);
}
.btn-primary:hover { background: linear-gradient(135deg, #7c5cbf, #9d7fd4); transform: translateY(-1px); box-shadow: 0 0 18px rgba(124,92,191,0.4); }
.btn-gold {
background: linear-gradient(135deg, #a87c20, #c9962a);
color: #fffbe6;
border: 1px solid var(–gold);
box-shadow: 0 0 10px rgba(240,192,64,0.2);
}
.btn-gold:hover { background: linear-gradient(135deg, #c9962a, #f0c040); transform: translateY(-1px); }
.btn-sm { padding: 5px 10px; font-size: 10px; }
.btn-danger { background: rgba(127,29,29,0.5); color: var(–red); border: 1px solid var(–red-dim); }
.btn-danger:hover { background: rgba(127,29,29,0.8); }
.btn-success { background: rgba(22,101,52,0.5); color: var(–green); border: 1px solid var(–green-dim); }
.btn-success:hover { background: rgba(22,101,52,0.8); }

/* ── QUEST LIST ── */
.quest-filters {
display: flex; gap: 8px; flex-wrap: wrap;
margin-bottom: 14px;
}
.filter-btn {
padding: 5px 12px;
border-radius: 20px;
border: 1px solid var(–border);
background: transparent;
color: var(–text-dim);
font-family: ‘Cinzel’, serif;
font-size: 10px;
letter-spacing: 0.06em;
cursor: pointer;
transition: all 0.2s;
}
.filter-btn.active, .filter-btn:hover {
border-color: var(–border-glow);
color: var(–purple-bright);
background: rgba(124,92,191,0.1);
}

.quest-list { display: flex; flex-direction: column; gap: 10px; }
.quest-empty {
text-align: center;
color: var(–text-faint);
font-style: italic;
padding: 40px 20px;
font-size: 15px;
}
.quest-empty .icon { font-size: 36px; display: block; margin-bottom: 12px; opacity: 0.4; }

.quest-card {
background: var(–bg-card);
border: 1px solid var(–border);
border-radius: 10px;
padding: 14px 16px;
display: grid;
grid-template-columns: auto 1fr auto;
gap: 12px;
align-items: start;
transition: all 0.25s;
position: relative;
overflow: hidden;
animation: cardIn 0.3s ease forwards;
}
@keyframes cardIn {
from { opacity: 0; transform: translateY(8px); }
to   { opacity: 1; transform: translateY(0); }
}
.quest-card::before {
content: ‘’;
position: absolute;
left: 0; top: 0; bottom: 0;
width: 3px;
border-radius: 3px 0 0 3px;
}
.quest-card.priority-high::before { background: var(–red); }
.quest-card.priority-medium::before { background: var(–amber); }
.quest-card.priority-low::before { background: var(–green); }
.quest-card:hover { border-color: var(–border-glow); box-shadow: var(–shadow-glow); }
.quest-card.done { opacity: 0.45; }
.quest-card.done .quest-title { text-decoration: line-through; color: var(–text-faint); }

.quest-check {
width: 22px; height: 22px;
border: 2px solid var(–border-glow);
border-radius: 50%;
display: flex; align-items: center; justify-content: center;
cursor: pointer;
transition: all 0.2s;
flex-shrink: 0;
margin-top: 2px;
font-size: 12px;
background: transparent;
color: transparent;
}
.quest-check:hover { border-color: var(–green); background: rgba(74,222,128,0.1); }
.quest-card.done .quest-check {
background: var(–green-dim);
border-color: var(–green);
color: var(–green);
}

.quest-body { min-width: 0; }
.quest-title { font-size: 16px; font-weight: 600; color: var(–text-main); margin-bottom: 3px; }
.quest-desc { font-size: 13px; color: var(–text-dim); font-style: italic; margin-bottom: 6px; }
.quest-meta { display: flex; gap: 8px; flex-wrap: wrap; align-items: center; }
.meta-tag {
font-family: ‘Cinzel’, serif;
font-size: 9px;
letter-spacing: 0.08em;
padding: 2px 7px;
border-radius: 10px;
border: 1px solid;
white-space: nowrap;
}
.tag-xp { border-color: var(–xp-bar); color: var(–purple); background: rgba(124,58,237,0.1); }
.tag-due { border-color: var(–border); color: var(–text-dim); }
.tag-due.overdue { border-color: var(–red-dim); color: var(–red); }
.tag-priority-high { border-color: var(–red-dim); color: var(–red); background: rgba(127,29,29,0.1); }
.tag-priority-medium { border-color: #92400e; color: var(–amber); background: rgba(146,64,14,0.1); }
.tag-priority-low { border-color: var(–green-dim); color: var(–green); background: rgba(22,101,52,0.1); }

.quest-actions { display: flex; gap: 6px; flex-shrink: 0; }

/* ── REMINDERS ── */
.reminder-card {
background: var(–bg-card);
border: 1px solid var(–border);
border-radius: 10px;
padding: 14px 16px;
display: flex; gap: 12px; align-items: center;
transition: all 0.25s;
animation: cardIn 0.3s ease forwards;
}
.reminder-card:hover { border-color: var(–border-glow); box-shadow: var(–shadow-glow); }
.reminder-icon { font-size: 22px; flex-shrink: 0; }
.reminder-body { flex: 1; min-width: 0; }
.reminder-title { font-size: 16px; font-weight: 600; }
.reminder-time { font-size: 12px; color: var(–amber); font-family: ‘Cinzel’, serif; letter-spacing: 0.05em; }

/* ── ACHIEVEMENTS ── */
.achievements-grid {
display: grid;
grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
gap: 12px;
}
.achievement-card {
background: var(–bg-card);
border: 1px solid var(–border);
border-radius: 10px;
padding: 16px;
text-align: center;
transition: all 0.25s;
}
.achievement-card.unlocked {
border-color: var(–gold-dim);
box-shadow: 0 0 12px rgba(240,192,64,0.15);
}
.achievement-card:not(.unlocked) { filter: grayscale(1); opacity: 0.4; }
.achievement-icon { font-size: 32px; margin-bottom: 8px; display: block; }
.achievement-name {
font-family: ‘Cinzel’, serif;
font-size: 11px;
letter-spacing: 0.06em;
color: var(–gold);
margin-bottom: 4px;
}
.achievement-desc { font-size: 12px; color: var(–text-dim); font-style: italic; }
.achievement-date { font-size: 10px; color: var(–text-faint); margin-top: 6px; font-family: ‘Cinzel’, serif; }

/* ── TOAST / LEVEL UP ── */
.toast-container {
position: fixed;
top: 20px; right: 20px;
z-index: 9999;
display: flex; flex-direction: column; gap: 10px;
pointer-events: none;
}
.toast {
background: var(–bg-panel);
border: 1px solid var(–border-glow);
border-radius: 10px;
padding: 12px 18px;
max-width: 280px;
box-shadow: 0 0 24px rgba(124,92,191,0.4);
animation: toastIn 0.4s cubic-bezier(0.34,1.56,0.64,1) forwards;
font-size: 14px;
}
.toast.gold {
border-color: var(–gold);
box-shadow: var(–shadow-gold);
}
.toast-title {
font-family: ‘Cinzel’, serif;
font-size: 12px;
letter-spacing: 0.08em;
color: var(–gold);
margin-bottom: 4px;
}
.toast.gold .toast-title { color: var(–gold); }
.toast-msg { color: var(–text-main); font-style: italic; }
@keyframes toastIn {
from { opacity: 0; transform: translateX(40px) scale(0.9); }
to   { opacity: 1; transform: translateX(0) scale(1); }
}
@keyframes toastOut {
to { opacity: 0; transform: translateX(40px) scale(0.9); }
}

/* ── LEVEL UP OVERLAY ── */
.levelup-overlay {
position: fixed; inset: 0; z-index: 10000;
background: rgba(0,0,0,0.85);
display: flex; align-items: center; justify-content: center;
animation: fadeIn 0.3s ease;
}
@keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
.levelup-box {
text-align: center;
padding: 48px 40px;
position: relative;
}
.levelup-glow {
position: absolute; inset: -40px;
background: radial-gradient(ellipse, rgba(240,192,64,0.15) 0%, transparent 70%);
pointer-events: none;
}
.levelup-symbol { font-size: 72px; display: block; margin-bottom: 16px; animation: pulse 1s ease infinite alternate; }
@keyframes pulse { from { transform: scale(1); } to { transform: scale(1.12); } }
.levelup-headline {
font-family: ‘Cinzel’, serif;
font-size: 42px;
font-weight: 900;
color: var(–gold);
text-shadow: 0 0 40px rgba(240,192,64,0.7);
letter-spacing: 0.1em;
margin-bottom: 8px;
}
.levelup-sub { font-size: 18px; color: var(–purple-bright); font-style: italic; margin-bottom: 6px; }
.levelup-title { font-family: ‘Cinzel’, serif; font-size: 14px; color: var(–amber); letter-spacing: 0.1em; margin-bottom: 28px; }
.levelup-dismiss {
padding: 12px 32px;
background: linear-gradient(135deg, #a87c20, #f0c040);
border: none; border-radius: 8px;
font-family: ‘Cinzel’, serif;
font-size: 14px;
letter-spacing: 0.08em;
color: #1a0f0f;
cursor: pointer;
font-weight: 700;
box-shadow: 0 0 20px rgba(240,192,64,0.4);
transition: transform 0.2s;
}
.levelup-dismiss:hover { transform: scale(1.05); }

/* Scrollbar */
::-webkit-scrollbar { width: 6px; }
::-webkit-scrollbar-track { background: var(–bg-deep); }
::-webkit-scrollbar-thumb { background: var(–border); border-radius: 3px; }

@media (max-width: 600px) {
.char-panel { grid-template-columns: auto 1fr; }
.char-stats { flex-direction: row; align-items: flex-start; grid-column: 1 / -1; }
.quest-card { grid-template-columns: auto 1fr; }
.quest-actions { grid-column: 2; }
}
</style>

</head>
<body>

<div class="app">
  <header class="header">
    <h1>⚔ Quest Log ⚔</h1>
    <p class="subtitle">Chronicle of deeds great and small</p>
  </header>

  <!-- Character Panel -->

  <div class="char-panel" id="charPanel">
    <div class="char-avatar" id="charAvatar">🧙</div>
    <div class="char-info">
      <div class="char-name">Adventurer</div>
      <div class="char-title" id="charTitle">Wandering Novice</div>
      <div class="xp-bar-wrap">
        <div class="xp-label" id="xpLabel">0 / 100 XP — Level 1</div>
        <div class="xp-bar"><div class="xp-fill" id="xpFill" style="width:0%"></div></div>
      </div>
    </div>
    <div class="char-stats">
      <div class="stat-badge">
        <strong id="totalDone">0</strong>
        <span>QUESTS DONE</span>
      </div>
      <div class="stat-badge streak-badge">
        <strong id="streakCount">0</strong>🔥
        <span>DAY STREAK</span>
      </div>
    </div>
  </div>

  <!-- Tabs -->

  <div class="tabs">
    <button class="tab-btn active" onclick="switchTab('quests')">📜 Quests</button>
    <button class="tab-btn" onclick="switchTab('reminders')">🔔 Omens</button>
    <button class="tab-btn" onclick="switchTab('achievements')">🏆 Feats</button>
  </div>

  <!-- QUESTS TAB -->

  <div class="tab-panel active" id="tab-quests">
    <!-- Add Quest Form -->
    <div class="add-form">
      <div class="form-title">✦ Inscribe a New Quest</div>
      <div class="form-row">
        <div class="field" style="flex:2">
          <label>QUEST TITLE</label>
          <input type="text" id="qTitle" placeholder="Name thy deed...">
        </div>
        <div class="field">
          <label>PRIORITY</label>
          <select id="qPriority">
            <option value="medium">⚔ Medium</option>
            <option value="high">🔥 High — Urgent</option>
            <option value="low">🌿 Low — In time</option>
          </select>
        </div>
      </div>
      <div class="form-row">
        <div class="field" style="flex:2">
          <label>DESCRIPTION (optional)</label>
          <input type="text" id="qDesc" placeholder="A brief account of the quest...">
        </div>
        <div class="field">
          <label>DUE DATE (optional)</label>
          <input type="date" id="qDue">
        </div>
        <div class="field">
          <label>XP REWARD</label>
          <select id="qXp">
            <option value="25">⭐ 25 XP — Minor</option>
            <option value="50" selected>⭐⭐ 50 XP — Standard</option>
            <option value="100">⭐⭐⭐ 100 XP — Major</option>
            <option value="200">💎 200 XP — Epic</option>
          </select>
        </div>
      </div>
      <div class="form-row">
        <button class="btn btn-gold" onclick="addQuest()">+ Add Quest</button>
      </div>
    </div>

```
<!-- Filters -->
<div class="quest-filters">
  <button class="filter-btn active" onclick="setFilter('all',this)">All</button>
  <button class="filter-btn" onclick="setFilter('active',this)">Active</button>
  <button class="filter-btn" onclick="setFilter('done',this)">Completed</button>
  <button class="filter-btn" onclick="setFilter('high',this)">🔥 Urgent</button>
</div>

<div class="quest-list" id="questList"></div>
```

  </div>

  <!-- REMINDERS TAB -->

  <div class="tab-panel" id="tab-reminders">
    <div class="add-form">
      <div class="form-title">🔔 Scribe an Omen</div>
      <div class="form-row">
        <div class="field" style="flex:2">
          <label>REMINDER</label>
          <input type="text" id="rTitle" placeholder="What must not be forgotten...">
        </div>
        <div class="field">
          <label>ICON</label>
          <select id="rIcon">
            <option value="🔔">🔔 Bell</option>
            <option value="⚗">⚗ Potion</option>
            <option value="📜">📜 Scroll</option>
            <option value="🗡">🗡 Blade</option>
            <option value="🌙">🌙 Moon</option>
            <option value="🧿">🧿 Amulet</option>
            <option value="🐉">🐉 Dragon</option>
            <option value="💊">💊 Elixir</option>
          </select>
        </div>
      </div>
      <div class="form-row">
        <div class="field">
          <label>DATE</label>
          <input type="date" id="rDate">
        </div>
        <div class="field">
          <label>TIME</label>
          <input type="time" id="rTime">
        </div>
        <div class="field">
          <label>NOTES (optional)</label>
          <input type="text" id="rNote" placeholder="Details...">
        </div>
      </div>
      <div class="form-row">
        <button class="btn btn-gold" onclick="addReminder()">+ Add Omen</button>
      </div>
    </div>
    <div class="quest-list" id="reminderList"></div>
  </div>

  <!-- ACHIEVEMENTS TAB -->

  <div class="tab-panel" id="tab-achievements">
    <div class="achievements-grid" id="achievementGrid"></div>
  </div>
</div>

<!-- Toast Container -->

<div class="toast-container" id="toastContainer"></div>

<script>
// ──────────────────────────────────────────────
//  STORAGE
// ──────────────────────────────────────────────
const STORAGE_KEY = 'questlog_v2';

function loadState() {
  try {
    const raw = localStorage.getItem(STORAGE_KEY);
    if (raw) return JSON.parse(raw);
  } catch(e) {}
  return {
    quests: [],
    reminders: [],
    xp: 0,
    level: 1,
    totalDone: 0,
    lastLogin: null,
    streak: 0,
    unlockedAchievements: []
  };
}

function saveState() {
  localStorage.setItem(STORAGE_KEY, JSON.stringify(state));
}

// ──────────────────────────────────────────────
//  GAME DATA
// ──────────────────────────────────────────────
const LEVEL_TITLES = [
  '', 'Wandering Novice','Apprentice Seeker','Bold Wayfarer',
  'Seasoned Explorer','Knight Errant','Champion of the Realm',
  'Arcane Duelist','Warlord of the Wilds','Grand Crusader','Legendary Hero',
  'Mythic Paragon','Eternal Sovereign'
];
const LEVEL_AVATARS = ['','🧙','🧝','⚔️','🛡','🐉','👑','🌟','⚡','🔱','🌌','💫','🎖'];
const XP_TABLE = [0,100,220,380,600,900,1300,1850,2600,3600,5000,7000,10000];

const ACHIEVEMENTS = [
  { id:'first_quest', icon:'📜', name:'The First Scroll', desc:'Complete your first quest', check: s => s.totalDone >= 1 },
  { id:'quests_5',    icon:'⚔️', name:'Blade Blooded',   desc:'Complete 5 quests',         check: s => s.totalDone >= 5 },
  { id:'quests_25',   icon:'🛡', name:'Veteran',          desc:'Complete 25 quests',         check: s => s.totalDone >= 25 },
  { id:'quests_50',   icon:'👑', name:'Champion',         desc:'Complete 50 quests',         check: s => s.totalDone >= 50 },
  { id:'level_3',     icon:'⭐', name:'Rising Star',      desc:'Reach Level 3',              check: s => s.level >= 3 },
  { id:'level_5',     icon:'🌟', name:'Illustrious',      desc:'Reach Level 5',              check: s => s.level >= 5 },
  { id:'level_10',    icon:'🌌', name:'Legend',           desc:'Reach Level 10',             check: s => s.level >= 10 },
  { id:'streak_3',    icon:'🔥', name:'Flame Keeper',     desc:'Maintain a 3-day streak',    check: s => s.streak >= 3 },
  { id:'streak_7',    icon:'🐉', name:'Dragon Devotion',  desc:'Maintain a 7-day streak',    check: s => s.streak >= 7 },
  { id:'streak_30',   icon:'☀️', name:'Sun Forged',       desc:'Maintain a 30-day streak',   check: s => s.streak >= 30 },
  { id:'epic_quest',  icon:'💎', name:'Epic Conqueror',   desc:'Complete an epic (200 XP) quest', check: s => s.quests.some(q => q.done && q.xp >= 200) },
  { id:'night_owl',   icon:'🦉', name:'Night Owl',        desc:'Add a quest after 10 PM',    check: s => s._nightOwl },
];

// ──────────────────────────────────────────────
//  INIT
// ──────────────────────────────────────────────
let state = loadState();
let questFilter = 'all';

function init() {
  checkStreak();
  renderChar();
  renderQuests();
  renderReminders();
  renderAchievements();
}

// ──────────────────────────────────────────────
//  STREAK
// ──────────────────────────────────────────────
function checkStreak() {
  const today = new Date().toDateString();
  if (!state.lastLogin) {
    state.lastLogin = today;
    state.streak = 1;
  } else if (state.lastLogin !== today) {
    const last = new Date(state.lastLogin);
    const now  = new Date(today);
    const diff = (now - last) / (1000 * 60 * 60 * 24);
    if (diff <= 1.5) {
      state.streak = (state.streak || 0) + 1;
    } else {
      state.streak = 1;
    }
    state.lastLogin = today;
    saveState();
  }
}

// ──────────────────────────────────────────────
//  XP & LEVELING
// ──────────────────────────────────────────────
function xpForLevel(lvl) { return XP_TABLE[Math.min(lvl, XP_TABLE.length - 1)]; }

function addXp(amount) {
  state.xp += amount;
  const maxLevel = LEVEL_TITLES.length - 1;
  let leveled = false;
  while (state.level < maxLevel && state.xp >= xpForLevel(state.level + 1)) {
    state.level++;
    leveled = true;
  }
  saveState();
  renderChar();
  if (leveled) showLevelUp();
}

// ──────────────────────────────────────────────
//  RENDER CHARACTER
// ──────────────────────────────────────────────
function renderChar() {
  const lvl = state.level;
  const maxLvl = LEVEL_TITLES.length - 1;
  const curXp = state.xp;
  const thisLvlXp = xpForLevel(lvl);
  const nextLvlXp = lvl < maxLvl ? xpForLevel(lvl + 1) : thisLvlXp;
  const pct = lvl >= maxLvl ? 100 : Math.min(100, ((curXp - thisLvlXp) / (nextLvlXp - thisLvlXp)) * 100);

  document.getElementById('charAvatar').textContent = LEVEL_AVATARS[Math.min(lvl, LEVEL_AVATARS.length-1)];
  document.getElementById('charTitle').textContent = LEVEL_TITLES[Math.min(lvl, LEVEL_TITLES.length-1)];
  document.getElementById('xpLabel').textContent = lvl >= maxLvl
    ? `Max Level — ${curXp} XP total`
    : `${curXp - thisLvlXp} / ${nextLvlXp - thisLvlXp} XP — Level ${lvl}`;
  document.getElementById('xpFill').style.width = pct + '%';
  document.getElementById('totalDone').textContent = state.totalDone;
  document.getElementById('streakCount').textContent = state.streak || 0;
}

// ──────────────────────────────────────────────
//  TABS
// ──────────────────────────────────────────────
function switchTab(name) {
  document.querySelectorAll('.tab-panel').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
  document.getElementById('tab-' + name).classList.add('active');
  event.target.classList.add('active');
}

// ──────────────────────────────────────────────
//  QUESTS
// ──────────────────────────────────────────────
function addQuest() {
  const title = document.getElementById('qTitle').value.trim();
  if (!title) { toast('⚠ A quest needs a name, adventurer!', false); return; }

  const hour = new Date().getHours();
  const quest = {
    id: Date.now(),
    title,
    desc: document.getElementById('qDesc').value.trim(),
    priority: document.getElementById('qPriority').value,
    due: document.getElementById('qDue').value,
    xp: parseInt(document.getElementById('qXp').value),
    done: false,
    createdAt: new Date().toISOString()
  };
  if (hour >= 22) state._nightOwl = true;

  state.quests.unshift(quest);
  saveState();
  renderQuests();
  checkAchievements();

  document.getElementById('qTitle').value = '';
  document.getElementById('qDesc').value = '';
  document.getElementById('qDue').value = '';
  toast('📜 Quest inscribed in the log!', false);
}

function completeQuest(id) {
  const q = state.quests.find(x => x.id === id);
  if (!q || q.done) return;
  q.done = true;
  q.completedAt = new Date().toISOString();
  state.totalDone++;
  saveState();
  addXp(q.xp);
  toast(`⚔ Quest complete! +${q.xp} XP`, true);
  renderQuests();
  checkAchievements();
}

function uncompleteQuest(id) {
  const q = state.quests.find(x => x.id === id);
  if (!q || !q.done) return;
  q.done = false;
  delete q.completedAt;
  state.totalDone = Math.max(0, state.totalDone - 1);
  state.xp = Math.max(0, state.xp - q.xp);
  saveState();
  renderChar();
  renderQuests();
}

function deleteQuest(id) {
  state.quests = state.quests.filter(x => x.id !== id);
  saveState();
  renderQuests();
}

function setFilter(f, el) {
  questFilter = f;
  document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
  el.classList.add('active');
  renderQuests();
}

function renderQuests() {
  const list = document.getElementById('questList');
  let quests = [...state.quests];
  if (questFilter === 'active') quests = quests.filter(q => !q.done);
  else if (questFilter === 'done') quests = quests.filter(q => q.done);
  else if (questFilter === 'high') quests = quests.filter(q => q.priority === 'high' && !q.done);

  if (!quests.length) {
    list.innerHTML = `<div class="quest-empty"><span class="icon">⚔️</span>${questFilter === 'done' ? 'No completed quests yet. Venture forth!' : 'The quest board is empty. Inscribe your first deed!'}</div>`;
    return;
  }

  const today = new Date(); today.setHours(0,0,0,0);
  list.innerHTML = quests.map(q => {
    let dueTag = '';
    if (q.due) {
      const dueDate = new Date(q.due + 'T00:00:00');
      const overdue = !q.done && dueDate < today;
      const label = overdue ? `⚠ Overdue: ${q.due}` : `📅 ${q.due}`;
      dueTag = `<span class="meta-tag tag-due ${overdue ? 'overdue' : ''}">${label}</span>`;
    }
    const checkContent = q.done ? '✓' : '';
    const undoBtn = q.done ? `<button class="btn btn-sm" onclick="uncompleteQuest(${q.id})" title="Undo">↩</button>` : '';
    const completeBtn = !q.done ? `<button class="btn btn-sm btn-success" onclick="completeQuest(${q.id})">✓ Complete</button>` : '';
    return `
    <div class="quest-card priority-${q.priority} ${q.done ? 'done' : ''}">
      <div class="quest-check" onclick="${q.done ? 'uncompleteQuest' : 'completeQuest'}(${q.id})">${checkContent}</div>
      <div class="quest-body">
        <div class="quest-title">${escHtml(q.title)}</div>
        ${q.desc ? `<div class="quest-desc">${escHtml(q.desc)}</div>` : ''}
        <div class="quest-meta">
          <span class="meta-tag tag-xp">+${q.xp} XP</span>
          <span class="meta-tag tag-priority-${q.priority}">${q.priority.toUpperCase()}</span>
          ${dueTag}
        </div>
      </div>
      <div class="quest-actions">
        ${completeBtn}${undoBtn}
        <button class="btn btn-sm btn-danger" onclick="deleteQuest(${q.id})">✕</button>
      </div>
    </div>`;
  }).join('');
}

// ──────────────────────────────────────────────
//  REMINDERS
// ──────────────────────────────────────────────
function addReminder() {
  const title = document.getElementById('rTitle').value.trim();
  if (!title) { toast('⚠ An omen without words?', false); return; }
  const reminder = {
    id: Date.now(),
    title,
    icon: document.getElementById('rIcon').value,
    date: document.getElementById('rDate').value,
    time: document.getElementById('rTime').value,
    note: document.getElementById('rNote').value.trim()
  };
  state.reminders.unshift(reminder);
  saveState();
  renderReminders();
  document.getElementById('rTitle').value = '';
  document.getElementById('rDate').value = '';
  document.getElementById('rTime').value = '';
  document.getElementById('rNote').value = '';
  toast('🔔 Omen recorded in the stars!', false);
}

function deleteReminder(id) {
  state.reminders = state.reminders.filter(x => x.id !== id);
  saveState();
  renderReminders();
}

function renderReminders() {
  const list = document.getElementById('reminderList');
  if (!state.reminders.length) {
    list.innerHTML = `<div class="quest-empty"><span class="icon">🔔</span>No omens set. The stars await your inscription.</div>`;
    return;
  }
  list.innerHTML = state.reminders.map(r => {
    const timeStr = [r.date, r.time].filter(Boolean).join(' @ ') || 'No time set';
    return `
    <div class="reminder-card">
      <div class="reminder-icon">${r.icon}</div>
      <div class="reminder-body">
        <div class="reminder-title">${escHtml(r.title)}</div>
        <div class="reminder-time">${timeStr}</div>
        ${r.note ? `<div style="font-size:13px;color:var(--text-dim);font-style:italic;margin-top:2px">${escHtml(r.note)}</div>` : ''}
      </div>
      <button class="btn btn-sm btn-danger" onclick="deleteReminder(${r.id})">✕</button>
    </div>`;
  }).join('');
}

// ──────────────────────────────────────────────
//  ACHIEVEMENTS
// ──────────────────────────────────────────────
function checkAchievements() {
  ACHIEVEMENTS.forEach(a => {
    if (!state.unlockedAchievements.includes(a.id) && a.check(state)) {
      state.unlockedAchievements.push(a.id);
      state[`_ach_${a.id}_date`] = new Date().toLocaleDateString();
      saveState();
      setTimeout(() => toast(`🏆 Feat Unlocked: ${a.name}!`, true), 400);
      renderAchievements();
    }
  });
}

function renderAchievements() {
  const grid = document.getElementById('achievementGrid');
  grid.innerHTML = ACHIEVEMENTS.map(a => {
    const unlocked = state.unlockedAchievements.includes(a.id);
    const date = state[`_ach_${a.id}_date`] || '';
    return `
    <div class="achievement-card ${unlocked ? 'unlocked' : ''}">
      <span class="achievement-icon">${a.icon}</span>
      <div class="achievement-name">${a.name}</div>
      <div class="achievement-desc">${a.desc}</div>
      ${unlocked && date ? `<div class="achievement-date">Earned ${date}</div>` : ''}
    </div>`;
  }).join('');
}

// ──────────────────────────────────────────────
//  TOASTS
// ──────────────────────────────────────────────
function toast(msg, isGold = false) {
  const container = document.getElementById('toastContainer');
  const el = document.createElement('div');
  el.className = 'toast' + (isGold ? ' gold' : '');
  el.innerHTML = `<div class="toast-title">${isGold ? '✦ GLORY ✦' : '📣 UPDATE'}</div><div class="toast-msg">${msg}</div>`;
  container.appendChild(el);
  setTimeout(() => {
    el.style.animation = 'toastOut 0.3s ease forwards';
    setTimeout(() => el.remove(), 300);
  }, 3000);
}

// ──────────────────────────────────────────────
//  LEVEL UP
// ──────────────────────────────────────────────
function showLevelUp() {
  const lvl = state.level;
  const overlay = document.createElement('div');
  overlay.className = 'levelup-overlay';
  overlay.innerHTML = `
    <div class="levelup-box">
      <div class="levelup-glow"></div>
      <span class="levelup-symbol">⚔️</span>
      <div class="levelup-headline">LEVEL ${lvl}!</div>
      <div class="levelup-sub">You grow ever more formidable...</div>
      <div class="levelup-title">${LEVEL_TITLES[Math.min(lvl, LEVEL_TITLES.length-1)]}</div>
      <button class="levelup-dismiss" onclick="this.closest('.levelup-overlay').remove()">Continue Your Journey</button>
    </div>`;
  document.body.appendChild(overlay);
}

// ──────────────────────────────────────────────
//  UTILS
// ──────────────────────────────────────────────
function escHtml(str) {
  return str.replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;');
}

init();
</script>

</body>
</html>

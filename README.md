<!DOCTYPE html>

<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MODO · CX → Legales | Flujo PTM v2</title>
<link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@400;500;600&family=IBM+Plex+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0e0f11;
    --surface: #16181c;
    --surface2: #1e2128;
    --border: #2a2d35;
    --border2: #363a44;
    --text: #e8eaf0;
    --text2: #8b909e;
    --text3: #555a68;
    --accent: #4a9eff;
    --accent2: #2d7dd6;
    --green: #2eb88a;
    --green-bg: #0d2e22;
    --yellow: #e6a817;
    --yellow-bg: #2a2000;
    --red: #e85555;
    --red-bg: #2a1212;
    --purple: #8b5cf6;
    --purple-bg: #1a1030;
    --slack-purple: #4a154b;
    --slack-bg: #1a0d1b;
    --mono: 'IBM Plex Mono', monospace;
    --sans: 'IBM Plex Sans', sans-serif;
  }

- { margin: 0; padding: 0; box-sizing: border-box; }

body {
background: var(–bg);
color: var(–text);
font-family: var(–sans);
font-size: 13px;
line-height: 1.5;
min-height: 100vh;
}

/* ── HEADER ── */
header {
border-bottom: 1px solid var(–border);
padding: 14px 24px;
display: flex;
align-items: center;
gap: 16px;
background: var(–surface);
}
.logo {
font-family: var(–mono);
font-weight: 600;
font-size: 14px;
color: var(–accent);
letter-spacing: .04em;
}
.sep { color: var(–border2); }
.subtitle { color: var(–text2); font-size: 12px; }
.demo-badge {
margin-left: auto;
background: var(–green-bg);
color: var(–green);
border: 1px solid #1a4d38;
padding: 3px 10px;
border-radius: 20px;
font-family: var(–mono);
font-size: 11px;
letter-spacing: .06em;
}

/* ── FLOW LEGEND ── */
.flow-bar {
background: var(–surface2);
border-bottom: 1px solid var(–border);
padding: 10px 24px;
display: flex;
align-items: center;
gap: 6px;
font-size: 11px;
color: var(–text3);
flex-wrap: wrap;
}
.flow-step {
display: flex;
align-items: center;
gap: 5px;
color: var(–text2);
font-size: 11px;
}
.flow-step .icon { font-size: 13px; }
.flow-arrow { color: var(–border2); font-size: 12px; }
.flow-step.active { color: var(–accent); }
.flow-step.zapier { color: var(–yellow); }
.flow-step.sf { color: #5ba4f5; }
.flow-step.gap { color: var(–red); }
.flow-divider {
width: 1px; height: 16px;
background: var(–border);
margin: 0 8px;
}
.flow-label {
font-size: 9px;
font-family: var(–mono);
text-transform: uppercase;
letter-spacing: .06em;
opacity: .5;
}

/* ── LAYOUT ── */
.layout {
display: grid;
grid-template-columns: 220px 1fr 1fr;
height: calc(100vh - 88px);
}

/* ── SIDEBAR: JIRA BOARD ── */
.sidebar {
border-right: 1px solid var(–border);
background: var(–surface);
overflow-y: auto;
display: flex;
flex-direction: column;
}
.sidebar-header {
padding: 12px 14px 8px;
font-family: var(–mono);
font-size: 10px;
color: var(–text3);
letter-spacing: .08em;
text-transform: uppercase;
border-bottom: 1px solid var(–border);
position: sticky;
top: 0;
background: var(–surface);
z-index: 2;
}
.board-col { padding: 10px 0; }
.col-label {
padding: 0 14px 6px;
font-size: 10px;
font-family: var(–mono);
color: var(–text3);
letter-spacing: .06em;
text-transform: uppercase;
display: flex;
align-items: center;
justify-content: space-between;
}
.col-count {
background: var(–border);
color: var(–text2);
border-radius: 10px;
padding: 1px 6px;
font-size: 10px;
}
.ticket-card {
margin: 0 10px 6px;
padding: 8px 10px;
border-radius: 6px;
border: 1px solid var(–border);
background: var(–surface2);
cursor: pointer;
transition: border-color .15s, background .15s;
position: relative;
}
.ticket-card:hover { border-color: var(–border2); background: #22252d; }
.ticket-card.active {
border-color: var(–accent);
background: #0d1a2e;
}
.ticket-id {
font-family: var(–mono);
font-size: 10px;
color: var(–accent);
margin-bottom: 3px;
}
.ticket-name { font-size: 11px; color: var(–text); line-height: 1.35; }
.ticket-date { font-size: 10px; color: var(–text3); margin-top: 4px; }
.ticket-status {
display: inline-flex;
align-items: center;
gap: 4px;
font-size: 9px;
font-family: var(–mono);
padding: 2px 6px;
border-radius: 3px;
margin-top: 5px;
letter-spacing: .04em;
}
.status-dot { width: 5px; height: 5px; border-radius: 50%; }

/* ── MAIN: SLACK THREAD ── */
.slack-panel {
border-right: 1px solid var(–border);
display: flex;
flex-direction: column;
background: var(–slack-bg);
}
.panel-header {
padding: 11px 16px;
border-bottom: 1px solid var(–border);
display: flex;
align-items: center;
gap: 8px;
background: var(–surface);
flex-shrink: 0;
}
.panel-title {
font-size: 12px;
font-weight: 600;
color: var(–text);
}
.panel-sub { font-size: 11px; color: var(–text3); margin-left: auto; }
.channel-badge {
font-family: var(–mono);
font-size: 10px;
color: #b988bd;
background: #2d1230;
padding: 2px 7px;
border-radius: 3px;
}

.thread-scroll {
flex: 1;
overflow-y: auto;
padding: 16px 14px;
display: flex;
flex-direction: column;
gap: 0;
}

/* Slack message */
.msg {
display: flex;
gap: 10px;
padding: 6px 0;
animation: fadeSlide .3s ease forwards;
}
@keyframes fadeSlide {
from { opacity: 0; transform: translateY(6px); }
to { opacity: 1; transform: translateY(0); }
}
.msg-avatar {
width: 30px;
height: 30px;
border-radius: 6px;
flex-shrink: 0;
display: flex;
align-items: center;
justify-content: center;
font-size: 13px;
font-weight: 600;
}
.avatar-bot { background: #4a154b; color: #e8b4ec; }
.avatar-cx { background: #1d3461; color: #7eb8f7; }
.avatar-exp { background: #1a2e1a; color: #6dba6d; }
.avatar-sys { background: #1e1a0e; color: #c8a030; }

.msg-body { flex: 1; min-width: 0; }
.msg-meta {
display: flex;
align-items: baseline;
gap: 6px;
margin-bottom: 2px;
}
.msg-author { font-weight: 600; font-size: 12px; }
.msg-time { font-size: 10px; color: var(–text3); font-family: var(–mono); }
.msg-app { font-size: 9px; color: #8b5cf6; background: #1a1030; padding: 1px 5px; border-radius: 3px; font-family: var(–mono); }
.msg-text { font-size: 12px; color: var(–text); line-height: 1.55; }
.msg-text strong { color: #fff; }
.msg-text em { color: var(–text2); font-style: normal; }

/* Slack Block Kit style card */
.block-card {
margin-top: 8px;
border-left: 3px solid var(–purple);
background: var(–surface2);
border-radius: 0 6px 6px 0;
padding: 10px 12px;
font-size: 11px;
}
.block-card.green { border-left-color: var(–green); }
.block-card.yellow { border-left-color: var(–yellow); }
.block-card.accent { border-left-color: var(–accent); }

.block-title {
font-weight: 600;
font-size: 12px;
color: #fff;
margin-bottom: 6px;
}
.block-field { color: var(–text2); margin-bottom: 2px; }
.block-field span { color: var(–text); }

/* Slack action buttons */
.slack-actions {
display: flex;
flex-wrap: wrap;
gap: 6px;
margin-top: 10px;
}
.slack-btn {
padding: 5px 12px;
border-radius: 4px;
border: 1px solid var(–border2);
background: var(–surface2);
color: var(–text);
font-size: 11px;
font-family: var(–sans);
cursor: pointer;
transition: all .15s;
font-weight: 500;
}
.slack-btn:hover { background: var(–border); border-color: #555; }
.slack-btn.primary {
background: var(–accent2);
border-color: var(–accent);
color: #fff;
}
.slack-btn.primary:hover { background: var(–accent); }
.slack-btn.danger {
background: #2a0f0f;
border-color: #5a2020;
color: var(–red);
}
.slack-btn.success {
background: var(–green-bg);
border-color: #1a4d38;
color: var(–green);
}
.slack-btn:disabled {
opacity: .4;
cursor: not-allowed;
}

/* Inline form inside thread */
.inline-form {
margin-top: 10px;
background: #111318;
border: 1px solid var(–border2);
border-radius: 6px;
padding: 12px;
}
.form-row {
display: grid;
grid-template-columns: 1fr 1fr;
gap: 8px;
margin-bottom: 8px;
}
.form-row.full { grid-template-columns: 1fr; }
.form-label {
font-size: 10px;
color: var(–text3);
font-family: var(–mono);
text-transform: uppercase;
letter-spacing: .05em;
margin-bottom: 3px;
}
.form-select, .form-input {
width: 100%;
background: var(–surface2);
border: 1px solid var(–border);
color: var(–text);
padding: 5px 8px;
border-radius: 4px;
font-size: 11px;
font-family: var(–sans);
outline: none;
transition: border-color .15s;
}
.form-select:focus, .form-input:focus { border-color: var(–accent); }
.form-select option { background: var(–surface2); }

/* Salesforce data pill */
.sf-pill {
display: inline-flex;
align-items: center;
gap: 5px;
background: #0d1e3a;
border: 1px solid #1a3a6e;
color: #5ba4f5;
padding: 3px 8px;
border-radius: 3px;
font-size: 10px;
font-family: var(–mono);
margin-top: 4px;
}
.sf-dot { width: 5px; height: 5px; background: #5ba4f5; border-radius: 50%; }

/* System message */
.sys-msg {
display: flex;
align-items: center;
gap: 8px;
padding: 4px 0;
font-size: 10px;
color: var(–text3);
font-family: var(–mono);
}
.sys-line { flex: 1; height: 1px; background: var(–border); }

/* Thread reply composer */
.thread-composer {
padding: 10px 14px;
border-top: 1px solid var(–border);
flex-shrink: 0;
background: var(–surface);
}
.composer-inner {
display: flex;
align-items: center;
gap: 8px;
background: var(–surface2);
border: 1px solid var(–border2);
border-radius: 6px;
padding: 6px 10px;
}
.composer-input {
flex: 1;
background: none;
border: none;
color: var(–text2);
font-size: 12px;
font-family: var(–sans);
outline: none;
}
.composer-hint { font-size: 10px; color: var(–text3); }

/* ── RIGHT: JIRA DETAIL + ZAPIER LOG ── */
.jira-panel {
display: flex;
flex-direction: column;
background: var(–surface);
overflow: hidden;
}
.jira-ticket {
flex: 1;
overflow-y: auto;
padding: 16px;
}
.jira-id {
font-family: var(–mono);
font-size: 11px;
color: var(–accent);
margin-bottom: 6px;
}
.jira-title {
font-size: 14px;
font-weight: 600;
color: var(–text);
margin-bottom: 12px;
line-height: 1.4;
}
.jira-meta-grid {
display: grid;
grid-template-columns: 1fr 1fr;
gap: 8px;
margin-bottom: 14px;
}
.jira-meta-item { }
.jira-meta-label {
font-size: 10px;
color: var(–text3);
font-family: var(–mono);
text-transform: uppercase;
letter-spacing: .05em;
margin-bottom: 2px;
}
.jira-meta-value { font-size: 12px; color: var(–text); }

.jira-status-row {
display: flex;
align-items: center;
gap: 8px;
padding: 10px 0;
border-top: 1px solid var(–border);
border-bottom: 1px solid var(–border);
margin-bottom: 12px;
}
.jira-status-label { font-size: 11px; color: var(–text2); }
.jira-status-badge {
display: flex;
align-items: center;
gap: 5px;
padding: 3px 10px;
border-radius: 4px;
font-size: 11px;
font-weight: 500;
font-family: var(–mono);
transition: all .4s ease;
}

/* Zapier log */
.zapier-log {
border-top: 1px solid var(–border);
background: var(–bg);
flex-shrink: 0;
max-height: 220px;
overflow-y: auto;
}
.zapier-header {
padding: 8px 14px;
border-bottom: 1px solid var(–border);
font-family: var(–mono);
font-size: 10px;
color: var(–text3);
letter-spacing: .08em;
text-transform: uppercase;
display: flex;
align-items: center;
gap: 8px;
position: sticky;
top: 0;
background: var(–bg);
}
.zapier-dot {
width: 6px; height: 6px;
border-radius: 50%;
background: var(–yellow);
animation: pulse 1.5s infinite;
}
@keyframes pulse {
0%, 100% { opacity: 1; }
50% { opacity: .3; }
}
.log-entry {
display: flex;
align-items: flex-start;
gap: 8px;
padding: 5px 14px;
border-bottom: 1px solid var(–border);
animation: fadeSlide .3s ease forwards;
font-size: 10px;
font-family: var(–mono);
}
.log-time { color: var(–text3); flex-shrink: 0; }
.log-arrow { color: var(–accent); flex-shrink: 0; }
.log-text { color: var(–text2); line-height: 1.4; }
.log-text .hl { color: var(–green); }
.log-text .hl-y { color: var(–yellow); }
.log-text .hl-b { color: var(–accent); }

/* Jira comments */
.jira-comments { margin-top: 4px; }
.jira-comment {
padding: 8px 10px;
border-radius: 5px;
background: var(–surface2);
border: 1px solid var(–border);
margin-bottom: 6px;
font-size: 11px;
animation: fadeSlide .3s ease forwards;
}
.jira-comment-meta {
font-size: 10px;
color: var(–text3);
font-family: var(–mono);
margin-bottom: 3px;
}
.jira-comment-body { color: var(–text2); line-height: 1.45; }
.jira-comment-body span { color: var(–text); }

/* Scrollbars */
::-webkit-scrollbar { width: 4px; }
::-webkit-scrollbar-track { background: transparent; }
::-webkit-scrollbar-thumb { background: var(–border2); border-radius: 2px; }

.squad-btn {
width: 100%;
padding: 8px 12px;
border-radius: 5px;
border: 1px solid var(–border);
background: var(–surface2);
color: var(–text);
font-size: 12px;
font-family: var(–sans);
cursor: pointer;
text-align: left;
transition: all .15s;
font-weight: 500;
}
.squad-btn:hover {
background: #22252d;
border-color: var(–accent);
color: var(–accent);
}

/* Tooltip for missing integration */
.missing-badge {
display: inline-flex;
align-items: center;
gap: 4px;
background: #2a1800;
border: 1px solid #4d3000;
color: var(–yellow);
padding: 2px 7px;
border-radius: 3px;
font-size: 10px;
font-family: var(–mono);
cursor: help;
}

.step-indicator {
font-size: 10px;
color: var(–text3);
font-family: var(–mono);
padding: 6px 14px;
background: var(–surface2);
border-bottom: 1px solid var(–border);
display: flex;
align-items: center;
gap: 6px;
}
.step-num {
background: var(–accent);
color: #000;
width: 14px; height: 14px;
border-radius: 3px;
display: flex; align-items: center; justify-content: center;
font-size: 9px;
font-weight: 600;
flex-shrink: 0;
}
.step-num.done {
background: var(–green);
}
</style>

</head>
<body>

<header>
  <div class="logo">MODO</div>
  <div class="sep">·</div>
  <div class="subtitle">CX → Legales · Flujo PTM</div>
  <div class="demo-badge">● DEMO v2</div>
</header>

<div class="flow-bar">
  <span class="flow-label">Datos</span>
  <div class="flow-step sf"><span class="icon">☁️</span> Salesforce</div>
  <div class="flow-arrow">→</div>
  <div class="flow-step zapier"><span class="icon">⚡</span> Zapier (puente)</div>
  <div class="flow-arrow">→</div>
  <div class="flow-step active"><span class="icon">💬</span> Slack</div>

  <div class="flow-divider"></div>
  <span class="flow-label">Acciones</span>
  <div class="flow-step active"><span class="icon">💬</span> Slack (experto)</div>
  <div class="flow-arrow">→</div>
  <div class="flow-step zapier"><span class="icon">⚡</span> Zapier</div>
  <div class="flow-arrow">→</div>
  <div class="flow-step"><span class="icon">📋</span> Jira (auto)</div>

  <div class="flow-divider"></div>
  <div class="missing-badge" title="Backoffice no tiene integración Slack ni Zapier — gap actual. Datos disponibles solo en SF como workaround.">⚠ Backoffice: sin integración</div>
</div>

<div class="layout">

  <!-- SIDEBAR: JIRA BOARD -->

  <div class="sidebar">
    <div class="sidebar-header">📋 Jira Board — LCX-CX</div>

```
<div class="board-col">
  <div class="col-label">
    Tareas por asignar
    <span class="col-count" id="cnt-new">1</span>
  </div>
  <div class="ticket-card active" id="card-1670" onclick="selectTicket('1670')">
    <div class="ticket-id">LCX-1670</div>
    <div class="ticket-name">Daniela Inés Mamani — 31402279</div>
    <div class="ticket-date">📅 15 may 2026</div>
    <div class="ticket-status" id="badge-1670" style="background:#1a1030; color:#8b5cf6;">
      <div class="status-dot" style="background:#8b5cf6;"></div> Tareas por asignar
    </div>
  </div>
</div>

<div class="board-col">
  <div class="col-label">
    En proceso CX
    <span class="col-count">0</span>
  </div>
  <div style="padding: 6px 14px; font-size:10px; color: var(--text3);">Sin casos</div>
</div>

<div class="board-col">
  <div class="col-label">
    En revisión LCA
    <span class="col-count">1</span>
  </div>
  <div class="ticket-card" onclick="selectTicket('1632')">
    <div class="ticket-id">LCX-1632</div>
    <div class="ticket-name">German Sequeira Wolf — 39917238</div>
    <div class="ticket-date">📅 4 may 2026</div>
    <div class="ticket-status" style="background:#0d2e22; color:#2eb88a;">
      <div class="status-dot" style="background:#2eb88a;"></div> En revisión LCA
    </div>
  </div>
</div>

<div class="board-col">
  <div class="col-label">
    Finalizado
    <span class="col-count">0</span>
  </div>
  <div style="padding: 6px 14px; font-size:10px; color: var(--text3);">Sin casos</div>
</div>
```

  </div>

  <!-- SLACK THREAD -->

  <div class="slack-panel">
    <div class="panel-header">
      <span style="font-size:16px;">💬</span>
      <div>
        <div class="panel-title">Hilo — LCX-1670</div>
      </div>
      <div class="channel-badge">#lca-cx</div>
      <div class="panel-sub" id="step-label" style="color: var(--text3); font-size:10px; font-family: var(--mono);">Paso 1 de 4</div>
    </div>

```
<div class="thread-scroll" id="thread">

  <!-- Paso 0: Zapier consulta Salesforce -->
  <div class="sys-msg" style="margin-bottom:4px;">
    <div class="sys-line"></div>
    <span style="display:flex; align-items:center; gap:5px; white-space:nowrap;">
      <span style="color:var(--yellow);">⚡ Zapier</span>
      <span>→ consulta</span>
      <span style="color:#5ba4f5;">☁️ Salesforce</span>
      <span>→ obtiene datos de LCX-1670</span>
    </span>
    <div class="sys-line"></div>
  </div>

  <!-- Mensaje inicial del bot -->
  <div class="msg">
    <div class="msg-avatar avatar-bot">🤖</div>
    <div class="msg-body">
      <div class="msg-meta">
        <span class="msg-author" style="color:#b988bd;">DFCO BOT</span>
        <span class="msg-app">APP</span>
        <span class="msg-time">14:28</span>
      </div>
      <div class="msg-text">
        Hola <strong>@expertos-pps</strong> ! Tenemos un nuevo caso:<br>
        <strong>[PTM] Daniela Inés Mamani — 31402279 — 4210832/26</strong><br>
        ¿Nos ayudan a revisarlo? 🗂 &nbsp;📅 Respuesta ideal antes del: <strong>2026-05-15</strong>
      </div>
      <div class="block-card" style="margin-top:8px;">
        <div class="block-title">📋 Datos del caso — LCX-1670</div>
        <div class="block-field">Monto: <span>$108.316</span></div>
        <div class="block-field">Comercio: <span>AZUL SUPERMERCADOS</span></div>
        <div class="block-field">Fecha pago: <span>2026-02-24</span></div>
        <div style="margin-top:8px; padding:6px 8px; background:#0d1525; border:1px solid #1a3a6e; border-radius:4px; font-size:10px; font-family:var(--mono); color:#5ba4f5; display:flex; align-items:center; gap:6px;">
          <span style="color:var(--yellow);">⚡</span>
          Datos traídos por Zapier desde <strong style="color:#7ab8f5;">Salesforce</strong>
          <span style="color:var(--text3); margin-left:auto;">☁️ → ⚡ → 💬</span>
        </div>
        <div style="margin-top:5px; padding:5px 8px; background:#1a1500; border:1px solid #3d3000; border-radius:4px; font-size:10px; font-family:var(--mono); color:#a07820;">
          ⚠ Datos de Backoffice no disponibles — sin integración directa
        </div>
        <div class="slack-actions" id="actions-main" style="margin-top:10px;">
          <button class="slack-btn primary" onclick="startFlow()">✋ Tomar el caso</button>
          <button class="slack-btn" onclick="showDerivar()">↪ Derivar a otro experto</button>
        </div>

        <!-- Panel derivar -->
        <div id="derivar-panel" style="display:none; margin-top:10px; background:#111318; border:1px solid var(--border2); border-radius:6px; padding:12px;">
          <div class="form-label" style="margin-bottom:8px;">¿A qué squad derivás el caso?</div>
          <div style="display:flex; flex-direction:column; gap:6px;" id="squad-list">
            <button class="squad-btn" onclick="derivarA('PTM')">📦 PTM</button>
            <button class="squad-btn" onclick="derivarA('MODO+')">⭐ MODO+</button>
            <button class="squad-btn" onclick="derivarA('P2P')">↔️ P2P</button>
            <button class="squad-btn" onclick="derivarA('GX')">🌐 GX</button>
            <button class="squad-btn" onclick="derivarA('TRUST')">🔒 TRUST</button>
          </div>
          <button class="slack-btn" style="margin-top:8px; font-size:10px; color:var(--text3);" onclick="hideDerivar()">Cancelar</button>
        </div>
      </div>
    </div>
  </div>

</div>

<div class="thread-composer">
  <div class="composer-inner">
    <span style="font-size:14px; color: var(--text3);">💬</span>
    <input class="composer-input" placeholder="Responder en el hilo…" id="composer" disabled>
    <span class="composer-hint">↵ enviar</span>
  </div>
</div>
```

  </div>

  <!-- JIRA + ZAPIER -->

  <div class="jira-panel">
    <div class="panel-header">
      <span style="font-size:15px;">📋</span>
      <div class="panel-title">Jira — LCX-1670</div>
      <div style="margin-left:auto; font-size:10px; font-family: var(--mono); color: var(--text3);">LCX-CX Board</div>
    </div>

```
<div class="jira-ticket">
  <div class="jira-id">LCX-1670</div>
  <div class="jira-title">[PTM] Daniela Inés Mamani — 31402279 — 4210832/26</div>

  <div class="jira-meta-grid">
    <div class="jira-meta-item">
      <div class="jira-meta-label">Fecha límite</div>
      <div class="jira-meta-value">2026-05-15</div>
    </div>
    <div class="jira-meta-item">
      <div class="jira-meta-label">Monto</div>
      <div class="jira-meta-value">$108.316</div>
    </div>
    <div class="jira-meta-item">
      <div class="jira-meta-label">Comercio</div>
      <div class="jira-meta-value">AZUL SUPERMERCADOS</div>
    </div>
    <div class="jira-meta-item">
      <div class="jira-meta-label">Fecha pago</div>
      <div class="jira-meta-value">2026-02-24</div>
    </div>
  </div>

  <div class="jira-status-row">
    <span class="jira-status-label">Estado →</span>
    <div class="jira-status-badge" id="jira-status" style="background:#1a1030; color:#8b5cf6;">
      <div class="status-dot" style="background:#8b5cf6; width:6px; height:6px; border-radius:50%;"></div>
      Tareas por asignar
    </div>
  </div>

  <div class="jira-comments" id="jira-comments">
    <div style="font-size:10px; color: var(--text3); font-family: var(--mono); margin-bottom:8px; text-transform:uppercase; letter-spacing:.06em;">Actividad automática via Zapier</div>
    <div style="font-size:11px; color: var(--text3); font-style: italic;">Las actualizaciones del hilo de Slack aparecerán aquí automáticamente.</div>
  </div>
</div>

<!-- ZAPIER LOG -->
<div class="zapier-log">
  <div class="zapier-header">
    <div class="zapier-dot"></div>
    ⚡ Zapier — log de eventos
  </div>
  <div id="zapier-log">
    <div class="log-entry">
      <span class="log-time">14:27</span>
      <span class="log-arrow">→</span>
      <span class="log-text"><span class="hl-y">Zapier trigger</span>: nuevo caso PTM detectado en Jira · <span class="hl-b">LCX-1670</span></span>
    </div>
    <div class="log-entry">
      <span class="log-time">14:27</span>
      <span class="log-arrow">→</span>
      <span class="log-text">Zapier consulta <span class="hl-b">☁️ Salesforce</span> → busca caso por DNI 31402279</span>
    </div>
    <div class="log-entry">
      <span class="log-time">14:28</span>
      <span class="log-arrow">→</span>
      <span class="log-text"><span class="hl">Salesforce respondió</span>: Monto $108.316 · Comercio AZUL SUPERMERCADOS · Fecha 2026-02-24</span>
    </div>
    <div class="log-entry">
      <span class="log-time">14:28</span>
      <span class="log-arrow">→</span>
      <span class="log-text">Zapier postea datos enriquecidos en <span class="hl-b">💬 Slack #lca-cx</span></span>
    </div>
    <div class="log-entry" style="border-left: 2px solid #3d2000; margin-left:0;">
      <span class="log-time">14:28</span>
      <span class="log-arrow" style="color:var(--yellow);">⚠</span>
      <span class="log-text" style="color:#a07820;">Backoffice: sin integración Zapier/Slack — datos omitidos</span>
    </div>
  </div>
</div>
```

  </div>

</div>

<script>
let flowStep = 0;
let currentTime = 1429;

function getTime() {
  currentTime++;
  let h = Math.floor(currentTime / 100);
  let m = currentTime % 100;
  if (m >= 60) { h++; m = 0; currentTime = h * 100; }
  return `${h}:${m.toString().padStart(2,'0')}`;
}

function addMsg(avatarClass, avatarContent, authorStyle, authorName, badge, time, textHtml, extra) {
  const t = document.getElementById('thread');
  const div = document.createElement('div');
  div.className = 'msg';
  div.innerHTML = `
    <div class="msg-avatar ${avatarClass}">${avatarContent}</div>
    <div class="msg-body">
      <div class="msg-meta">
        <span class="msg-author" style="${authorStyle}">${authorName}</span>
        ${badge ? `<span class="msg-app">${badge}</span>` : ''}
        <span class="msg-time">${time}</span>
      </div>
      <div class="msg-text">${textHtml}</div>
      ${extra || ''}
    </div>
  `;
  t.appendChild(div);
  t.scrollTop = t.scrollHeight;
  return div;
}

function addSysMsg(text) {
  const t = document.getElementById('thread');
  const div = document.createElement('div');
  div.className = 'sys-msg';
  div.innerHTML = `<div class="sys-line"></div><span>${text}</span><div class="sys-line"></div>`;
  t.appendChild(div);
  t.scrollTop = t.scrollHeight;
}

function addZapierLog(text) {
  const log = document.getElementById('zapier-log');
  const div = document.createElement('div');
  div.className = 'log-entry';
  div.innerHTML = `<span class="log-time">${getTime()}</span><span class="log-arrow">→</span><span class="log-text">${text}</span>`;
  log.appendChild(div);
  log.scrollTop = log.scrollHeight;
}

function addJiraComment(meta, body) {
  const c = document.getElementById('jira-comments');
  const div = document.createElement('div');
  div.className = 'jira-comment';
  div.innerHTML = `<div class="jira-comment-meta">${meta}</div><div class="jira-comment-body">${body}</div>`;
  c.appendChild(div);
}

function updateJiraStatus(text, bg, color, dotColor) {
  const s = document.getElementById('jira-status');
  s.style.background = bg;
  s.style.color = color;
  s.innerHTML = `<div class="status-dot" style="background:${dotColor}; width:6px; height:6px; border-radius:50%;"></div> ${text}`;
  const b = document.getElementById('badge-1670');
  if (b) {
    b.style.background = bg;
    b.style.color = color;
    b.innerHTML = `<div class="status-dot" style="background:${dotColor};"></div> ${text}`;
  }
}

// PASO 1: experto toma el caso
function startFlow() {
  if (flowStep !== 0) return;
  flowStep = 1;

  document.getElementById('actions-main').innerHTML = '<span style="color: var(--green); font-size:11px; font-family: var(--mono);">✓ Caso tomado por vos</span>';

  const t = getTime();
  addSysMsg('Experto tomó el caso · ' + t);

  addMsg('avatar-exp', '👤', 'color:#6dba6d;', 'María E. (Experta PPS)', null, t,
    '✋ Tomo el caso. Revisando ahora.',
    `<div class="block-card green" style="margin-top:8px;">
      <div class="block-title">Paso 2 — Completar contexto del caso</div>
      <div class="block-field" style="margin-bottom:8px;">Completá desde acá — se enviará directo a Legales y actualizará Jira 👇</div>
      <div class="inline-form" id="context-form">
        <div class="form-row">
          <div>
            <div class="form-label">¿Reclamo en MODO?</div>
            <select class="form-select" id="f-reclamo">
              <option value="">Seleccionar</option>
              <option>Sí</option>
              <option>No</option>
            </select>
          </div>
          <div>
            <div class="form-label">N° Ticket MODO</div>
            <input class="form-input" id="f-ticket" placeholder="ej. TKT-00123">
          </div>
        </div>
        <div class="form-row">
          <div>
            <div class="form-label">¿Error resp. de MODO?</div>
            <select class="form-select" id="f-resp">
              <option value="">Seleccionar</option>
              <option>Sí</option>
              <option>No</option>
              <option>Pendiente</option>
            </select>
          </div>
          <div>
            <div class="form-label">¿Contactamos comercio?</div>
            <select class="form-select" id="f-comercio">
              <option value="">Seleccionar</option>
              <option>Sí</option>
              <option>No</option>
            </select>
          </div>
        </div>
        <div class="form-row">
          <div>
            <div class="form-label">Adquirente</div>
            <input class="form-input" id="f-adq" placeholder="ej. Prisma">
          </div>
          <div>
            <div class="form-label">Observaciones</div>
            <input class="form-input" id="f-obs" placeholder="Detalle breve">
          </div>
        </div>
        <div class="slack-actions" style="margin-top:4px;">
          <button class="slack-btn primary" onclick="submitContext()">Enviar contexto a Legales →</button>
          <button class="slack-btn" onclick="skipContext()">Completar más tarde</button>
        </div>
      </div>
    </div>`
  );

  // Jira se actualiza
  setTimeout(() => {
    updateJiraStatus('En proceso CX', '#0d1e3a', '#4a9eff', '#4a9eff');
    addZapierLog('Trigger: <span class="hl-b">botón "Tomar caso"</span> clickeado en Slack por María E.');
    addZapierLog('Jira <span class="hl-b">LCX-1670</span> → estado: <span class="hl">En proceso CX</span>');
    addJiraComment('⚡ Zapier · automático · ' + t, 'Caso tomado por <span>María E. (Experta PPS)</span> desde Slack.');
    document.getElementById('step-label').textContent = 'Paso 2 de 4';
  }, 600);
}

function skipCase() {
  showDerivar();
}
function showDerivar() {
  if (flowStep !== 0) return;
  document.getElementById('derivar-panel').style.display = 'block';
}
function hideDerivar() {
  document.getElementById('derivar-panel').style.display = 'none';
}
function derivarA(squad) {
  if (flowStep !== 0) return;
  flowStep = 99; // bloquear otras acciones

  document.getElementById('actions-main').innerHTML =
    `<span style="color:var(--yellow); font-size:11px; font-family:var(--mono);">↪ Derivado a squad ${squad}</span>`;
  document.getElementById('derivar-panel').style.display = 'none';

  const t = getTime();
  addSysMsg(`Caso derivado a ${squad} · ${t}`);

  addMsg('avatar-bot', '🤖', 'color:#b988bd;', 'DFCO BOT', 'APP', t,
    `↪ El caso <strong>LCX-1670</strong> fue derivado al squad <strong>${squad}</strong>.`,
    `<div class="block-card yellow" style="margin-top:8px;">
      <div class="block-title">Derivación registrada</div>
      <div class="block-field">Squad destino: <span>${squad}</span></div>
      <div class="block-field">Derivado desde: <span>CX · Experta PPS</span></div>
      <div class="block-field">Hora: <span>${t}</span></div>
    </div>`
  );

  setTimeout(() => {
    updateJiraStatus(`Derivado → ${squad}`, '#2a2000', '#e6a817', '#e6a817');
    addZapierLog(`Trigger: caso derivado en Slack · squad destino: <span class="hl-y">${squad}</span>`);
    addZapierLog(`Jira <span class="hl-b">LCX-1670</span> → estado actualizado: <span class="hl-y">Derivado → ${squad}</span>`);
    addJiraComment(`⚡ Zapier · automático · ${t}`, `Caso derivado al squad <span>${squad}</span> por CX desde Slack.`);
  }, 500);
}
function skipContext() {
  alert('Demo: se puede retomar desde el hilo más tarde.');
}

// PASO 2: experto completa el formulario inline
function submitContext() {
  if (flowStep !== 1) return;
  flowStep = 2;

  const reclamo = document.getElementById('f-reclamo').value || 'Sí';
  const ticket = document.getElementById('f-ticket').value || 'TKT-04872';
  const resp = document.getElementById('f-resp').value || 'Pendiente';
  const comercio = document.getElementById('f-comercio').value || 'Sí';
  const adq = document.getElementById('f-adq').value || 'Prisma';
  const obs = document.getElementById('f-obs').value || 'Débito pendiente de acreditación';

  document.getElementById('context-form').innerHTML = '<span style="color: var(--green); font-size:11px; font-family: var(--mono);">✓ Contexto enviado a Legales</span>';

  const t = getTime();

  addMsg('avatar-bot', '🤖', 'color:#b988bd;', 'DFCO BOT', 'APP', t,
    'Contexto recibido ✓ — enviado a <strong>@legales-lca</strong>',
    `<div class="block-card accent" style="margin-top:8px;">
      <div class="block-title">📋 Contexto completado por CX</div>
      <div class="block-field">¿Reclamo en MODO? <span>${reclamo}</span></div>
      <div class="block-field">N° Ticket MODO: <span>${ticket}</span></div>
      <div class="block-field">¿Resp. de MODO? <span>${resp}</span></div>
      <div class="block-field">¿Contacto comercio? <span>${comercio}</span></div>
      <div class="block-field">Adquirente: <span>${adq}</span></div>
      <div class="block-field">Observaciones: <span>${obs}</span></div>
    </div>`
  );

  setTimeout(() => {
    addMsg('avatar-exp', '⚖️', 'color:#c8a030;', 'Legales LCA', null, getTime(),
      'Recibido, analizando el caso.',
      `<div class="slack-actions" style="margin-top:8px;" id="lca-actions">
        <button class="slack-btn success" onclick="legalApprove()">✓ Aprobar — sin responsabilidad MODO</button>
        <button class="slack-btn danger" onclick="legalReject()">✗ Observar caso</button>
      </div>`
    );
    document.getElementById('step-label').textContent = 'Paso 3 de 4';
  }, 800);

  // Jira se actualiza con los datos del form
  setTimeout(() => {
    updateJiraStatus('En revisión LCA', '#0d2e22', '#2eb88a', '#2eb88a');
    addZapierLog('Form completado en Slack → campos mapeados a Jira <span class="hl-b">LCX-1670</span>');
    addZapierLog('Jira → campos actualizados: Reclamo, Ticket, Responsabilidad, Comercio, Adquirente, Obs.');
    addZapierLog('Jira <span class="hl-b">LCX-1670</span> → estado: <span class="hl">En revisión LCA</span>');
    addJiraComment('⚡ Zapier · automático · ' + t,
      `¿Reclamo MODO? <span>${reclamo}</span> · Ticket: <span>${ticket}</span> · Resp: <span>${resp}</span> · Comercio: <span>${comercio}</span> · Adq: <span>${adq}</span> · Obs: <span>${obs}</span>`);
  }, 400);
}

// PASO 3: Legales responde
function legalApprove() {
  if (flowStep !== 2) return;
  flowStep = 3;
  document.getElementById('lca-actions').innerHTML = '<span style="color: var(--green); font-size:11px; font-family: var(--mono);">✓ Aprobado sin responsabilidad MODO</span>';

  const t = getTime();
  addSysMsg('Legales cerró el caso · ' + t);

  addMsg('avatar-bot', '🤖', 'color:#b988bd;', 'DFCO BOT', 'APP', t,
    '✅ Caso <strong>LCX-1670</strong> cerrado por Legales — sin responsabilidad de MODO.',
    `<div class="block-card green" style="margin-top:8px;">
      <div class="block-title">✓ Caso finalizado</div>
      <div class="block-field">Resolución: <span>Sin responsabilidad MODO</span></div>
      <div class="block-field">Cerrado por: <span>Legales LCA</span></div>
      <div class="block-field">Fecha: <span>${t} · ${new Date().toLocaleDateString('es-AR')}</span></div>
      <div class="slack-actions" style="margin-top:8px;">
        <button class="slack-btn" onclick="notifyCx()" id="notify-btn">📣 Notificar a CX</button>
      </div>
    </div>`
  );

  setTimeout(() => {
    updateJiraStatus('Finalizado', '#0d2e22', '#2eb88a', '#2eb88a');
    addZapierLog('Trigger: <span class="hl-b">botón "Aprobar"</span> clickeado por Legales en Slack');
    addZapierLog('Jira <span class="hl-b">LCX-1670</span> → estado: <span class="hl">Finalizado</span>');
    addJiraComment('⚡ Zapier · automático · ' + t, 'Caso cerrado por <span>Legales LCA</span>. Resolución: <span>Sin responsabilidad MODO</span>.');
    document.getElementById('step-label').textContent = 'Paso 4 de 4';
  }, 500);
}

function legalReject() {
  if (flowStep !== 2) return;
  flowStep = 3;
  document.getElementById('lca-actions').innerHTML = '<span style="color: var(--red); font-size:11px; font-family: var(--mono);">⚠ Caso observado</span>';
  const t = getTime();
  addMsg('avatar-exp', '⚖️', 'color:#c8a030;', 'Legales LCA', null, t,
    '⚠ Caso observado. Se necesita más información sobre el débito.',
    `<div class="slack-actions" style="margin-top:8px;">
      <button class="slack-btn primary" onclick="alert('Demo: CX respondería acá con info adicional.')">Agregar información →</button>
    </div>`
  );
  updateJiraStatus('En revisión LCA · Observado', '#2a1200', '#e6a817', '#e6a817');
  addZapierLog('Caso observado por Legales · estado Jira actualizado: <span class="hl-y">Observado</span>');
  document.getElementById('step-label').textContent = 'Paso 4 de 4';
}

function notifyCx() {
  document.getElementById('notify-btn').disabled = true;
  document.getElementById('notify-btn').textContent = '✓ Notificación enviada';
  const t = getTime();
  addMsg('avatar-bot', '🤖', 'color:#b988bd;', 'DFCO BOT', 'APP', t,
    '📣 <strong>@lca-cx</strong> — El caso <strong>LCX-1670</strong> fue resuelto por Legales. Sin acción adicional requerida. ✅',
    ``
  );
  addZapierLog('Notificación de cierre enviada a <span class="hl-b">#lca-cx</span> via bot');
}

function selectTicket(id) {
  document.querySelectorAll('.ticket-card').forEach(c => c.classList.remove('active'));
  if (id === '1670') document.getElementById('card-1670')?.classList.add('active');
}
</script>

</body>
</html>

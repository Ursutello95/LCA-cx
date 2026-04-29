<!DOCTYPE html>

<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MODO · CX → Legales | Flujo PTM</title>
<link href="https://fonts.googleapis.com/css2?family=Red+Hat+Display:wght@400;500;600;700;900&family=Red+Hat+Text:wght@400;500;600&display=swap" rel="stylesheet">
<style>
:root {
  --g: #2d6a2d; --gm: #3d8c3d; --gl: #e8f4e8; --gp: #f2f9f2;
  --bg: #f5f8f5; --white: #fff; --border: #dce8dc; --borderS: #b8d4b8;
  --text: #1a2e1a; --muted: #5a7a5a; --warn: #c45a00; --wbg: #fff4ec; --wb: #f0c090;
  --jblue: #0052cc; --jbg: #e8f0ff; --ok: #1a6b3a; --okbg: #e6f5ed;
  --s1c: #6b7280; --s1bg: #f3f4f6; --s1br: #d1d5db;
  --s2c: #b45309; --s2bg: #fef3c7; --s2br: #fcd34d;
  --s3c: #1d4ed8; --s3bg: #dbeafe; --s3br: #93c5fd;
  --s4c: #166534; --s4bg: #dcfce7; --s4br: #86efac;
  --r: 12px; --rs: 8px;
}
* { margin:0; padding:0; box-sizing:border-box; }
body { font-family:'Red Hat Text',sans-serif; background:var(--bg); color:var(--text); min-height:100vh; }

.topbar {
background:var(–g); padding:0 28px; height:54px;
display:flex; align-items:center; justify-content:space-between;
position:sticky; top:0; z-index:100;
box-shadow:0 2px 10px rgba(45,106,45,.3);
}
.topbar-left { display:flex; align-items:center; gap:14px; }
.wordmark { font-family:‘Red Hat Display’,sans-serif; font-weight:900; font-size:21px; color:#fff; letter-spacing:-.5px; }
.topbar-div { width:1px; height:18px; background:rgba(255,255,255,.3); }
.topbar-sub { font-size:13px; color:rgba(255,255,255,.7); font-weight:500; }
.demo-badge { background:rgba(255,255,255,.15); border:1px solid rgba(255,255,255,.25); color:#fff; padding:4px 12px; border-radius:100px; font-size:11px; font-weight:700; letter-spacing:1px; text-transform:uppercase; font-family:‘Red Hat Display’,sans-serif; }

.container { max-width:1100px; margin:0 auto; padding:32px 22px 48px; }

.fh { margin-bottom:24px; }
.fh h1 { font-family:‘Red Hat Display’,sans-serif; font-weight:900; font-size:clamp(24px,4vw,36px); color:var(–g); letter-spacing:-1px; line-height:1.1; margin-bottom:6px; }
.fh p { font-size:14px; color:var(–muted); }

/* Jira board mini */
.board {
display:grid; grid-template-columns:repeat(4,1fr); gap:10px;
margin-bottom:24px; background:var(–white);
border:1.5px solid var(–border); border-radius:var(–r);
padding:16px; box-shadow:0 2px 8px rgba(45,106,45,.05);
}
.board-col { display:flex; flex-direction:column; gap:8px; }
.board-col-header {
font-family:‘Red Hat Display’,sans-serif; font-weight:800; font-size:11px;
text-transform:uppercase; letter-spacing:.8px; padding:5px 10px;
border-radius:6px; display:flex; align-items:center; justify-content:space-between;
}
.bh1 { background:var(–s1bg); color:var(–s1c); border:1px solid var(–s1br); }
.bh2 { background:var(–s2bg); color:var(–s2c); border:1px solid var(–s2br); }
.bh3 { background:var(–s3bg); color:var(–s3c); border:1px solid var(–s3br); }
.bh4 { background:var(–s4bg); color:var(–s4c); border:1px solid var(–s4br); }

.board-card {
background:var(–bg); border:1.5px solid var(–border); border-radius:8px;
padding:10px 11px; font-size:12px; transition:all .4s ease;
position:relative; overflow:hidden;
}
.board-card.active-card {
border-color: var(–g);
box-shadow: 0 0 0 3px rgba(45,106,45,.15);
background: var(–gp);
}
.board-card.moving {
animation: cardMove .5s ease;
}
.bc-title { font-weight:700; color:var(–text); font-family:‘Red Hat Display’,sans-serif; font-size:11px; line-height:1.3; margin-bottom:6px; }
.bc-tag { display:inline-block; padding:2px 7px; border-radius:4px; font-size:10px; font-weight:700; font-family:‘Red Hat Display’,sans-serif; margin-bottom:5px; }
.tag-ptm { background:#fde8e8; color:#c0392b; }
.bc-date { font-size:10px; color:var(–muted); display:flex; align-items:center; gap:3px; }
.bc-id { font-size:10px; color:var(–jblue); font-weight:700; margin-top:4px; }
.bc-status-dot { width:7px; height:7px; border-radius:50%; display:inline-block; margin-right:4px; }

.zapier-bridge {
display:flex; align-items:center; justify-content:center; gap:10px;
padding:11px 18px; background:var(–white); border:1.5px dashed var(–borderS);
border-radius:var(–r); margin-bottom:20px; font-size:13px; color:var(–muted); font-weight:500;
}
.zbadge { background:#FF4A00; color:#fff; padding:3px 9px; border-radius:5px; font-weight:800; font-size:11px; letter-spacing:1px; font-family:‘Red Hat Display’,sans-serif; }
.zauto { font-size:11px; color:var(–muted); margin-left:6px; }

/* Transition log */
.transition-log {
background:var(–white); border:1.5px solid var(–border); border-radius:var(–r);
padding:14px 18px; margin-bottom:20px; min-height:48px;
}
.tl-title { font-family:‘Red Hat Display’,sans-serif; font-weight:700; font-size:12px; color:var(–muted); text-transform:uppercase; letter-spacing:.5px; margin-bottom:10px; }
.tl-items { display:flex; flex-direction:column; gap:6px; }
.tl-item {
display:flex; align-items:center; gap:8px; font-size:12px;
animation: slideD .3s ease;
}
.tl-time { font-size:10px; color:var(–muted); min-width:40px; font-family:‘Red Hat Display’,sans-serif; }
.tl-arrow { color:var(–borderS); }
.tl-from { padding:2px 8px; border-radius:4px; font-weight:700; font-size:11px; font-family:‘Red Hat Display’,sans-serif; }
.tl-to { padding:2px 8px; border-radius:4px; font-weight:700; font-size:11px; font-family:‘Red Hat Display’,sans-serif; }
.tl-via { font-size:10px; color:var(–muted); background:#f3f4f6; padding:1px 6px; border-radius:4px; }
.tl-empty { color:var(–muted); font-size:12px; font-style:italic; }

.grid { display:grid; grid-template-columns:1fr 1fr; gap:18px; }
@media(max-width:760px){ .grid{grid-template-columns:1fr;} }

.card { background:var(–white); border:1.5px solid var(–border); border-radius:var(–r); overflow:hidden; box-shadow:0 2px 8px rgba(45,106,45,.06); }
.ch { display:flex; align-items:center; gap:9px; padding:13px 17px; border-bottom:1.5px solid var(–border); font-family:‘Red Hat Display’,sans-serif; font-weight:700; font-size:13px; }
.ch.slack { background:#f9f0f9; color:#4a154b; }
.ch.jira { background:var(–jbg); color:var(–jblue); }
.aicon { width:20px; height:20px; border-radius:4px; display:flex; align-items:center; justify-content:center; font-size:12px; }
.aicon.s { background:#4a154b; }
.aicon.j { background:var(–jblue); }
.cb { padding:16px; }

.smsg { background:#faf5fa; border:1px solid #e8d8e8; border-left:3px solid #E01E5A; border-radius:var(–rs); padding:11px 13px; margin-bottom:14px; }
.smeta { display:flex; align-items:center; gap:7px; margin-bottom:5px; }
.sbot { font-weight:700; font-size:13px; color:#4a154b; font-family:‘Red Hat Display’,sans-serif; }
.satag { background:#4a154b; color:#fff; font-size:9px; padding:1px 5px; border-radius:3px; font-weight:700; }
.stime { color:#999; font-size:11px; }
.stextm { font-size:13px; line-height:1.6; color:#1d1c1d; }
.mention { color:#1264a3; font-weight:600; }
.slink { color:#1264a3; font-size:12px; text-decoration:none; }
.deadline { color:var(–warn); font-weight:700; }

.cxform { background:var(–gp); border:1.5px solid var(–border); border-radius:var(–rs); padding:15px; }
.cxtitle { font-family:‘Red Hat Display’,sans-serif; font-size:13px; font-weight:700; color:var(–g); margin-bottom:13px; display:flex; align-items:center; gap:5px; }
.fg { margin-bottom:11px; }
.fl { font-size:10px; color:var(–muted); margin-bottom:4px; display:block; font-weight:700; letter-spacing:.4px; text-transform:uppercase; font-family:‘Red Hat Display’,sans-serif; }
.fs,.fi { width:100%; background:var(–white); border:1.5px solid var(–borderS); border-radius:7px; padding:8px 11px; color:var(–text); font-family:‘Red Hat Text’,sans-serif; font-size:13px; outline:none; transition:border-color .2s, box-shadow .2s; appearance:none; }
.fs:focus,.fi:focus { border-color:var(–g); box-shadow:0 0 0 3px rgba(45,106,45,.1); }
.frow { display:grid; grid-template-columns:1fr 1fr; gap:9px; }

.drop-zone { border:2px dashed var(–borderS); border-radius:var(–rs); padding:14px; text-align:center; cursor:pointer; transition:all .2s; background:var(–white); position:relative; }
.drop-zone:hover,.drop-zone.over { border-color:var(–g); background:var(–gp); }
.drop-zone input[type=file] { position:absolute; inset:0; opacity:0; cursor:pointer; width:100%; height:100%; }
.dicon { font-size:20px; margin-bottom:4px; }
.dlabel { font-size:13px; font-weight:700; color:var(–g); font-family:‘Red Hat Display’,sans-serif; }
.dhint { font-size:11px; color:var(–muted); margin-top:2px; }
.flist { margin-top:8px; display:flex; flex-direction:column; gap:5px; }
.fitem { display:flex; align-items:center; gap:7px; background:var(–white); border:1px solid var(–border); border-radius:7px; padding:6px 10px; animation:slideD .2s ease; }
.fico { font-size:14px; flex-shrink:0; }
.finf { flex:1; min-width:0; }
.fname { font-size:12px; font-weight:600; white-space:nowrap; overflow:hidden; text-overflow:ellipsis; }
.fsize { font-size:10px; color:var(–muted); }
.frem { background:none; border:none; color:var(–muted); cursor:pointer; font-size:13px; padding:2px 5px; border-radius:4px; transition:all .15s; }
.frem:hover { background:#fee; color:#c00; }

.btn-sub { width:100%; background:var(–g); border:none; border-radius:var(–rs); padding:12px; color:#fff; font-family:‘Red Hat Display’,sans-serif; font-weight:700; font-size:14px; cursor:pointer; transition:all .2s; margin-top:13px; display:flex; align-items:center; justify-content:center; gap:7px; }
.btn-sub:hover { background:var(–gm); transform:translateY(-1px); box-shadow:0 6px 16px rgba(45,106,45,.25); }
.btn-sub:active { transform:translateY(0); }

/* Jira panel */
.jt { background:var(–bg); border:1.5px solid var(–border); border-radius:var(–rs); padding:13px; margin-bottom:13px; }
.jid { font-size:11px; color:var(–jblue); background:var(–jbg); padding:3px 8px; border-radius:4px; display:inline-block; margin-bottom:7px; font-weight:700; font-family:‘Red Hat Display’,sans-serif; }
.jtitle { font-size:14px; font-weight:700; margin-bottom:11px; color:var(–text); font-family:‘Red Hat Display’,sans-serif; line-height:1.3; }
.jf { display:flex; gap:7px; margin-bottom:7px; font-size:12px; align-items:flex-start; }
.jfl { color:var(–muted); min-width:110px; font-weight:700; font-size:10px; padding-top:2px; font-family:‘Red Hat Display’,sans-serif; text-transform:uppercase; letter-spacing:.3px; }
.jfv { color:var(–text); font-weight:500; }

/* Status badge - big */
.jstat-wrap { display:flex; align-items:center; gap:8px; flex-wrap:wrap; }
.jstat { display:inline-flex; align-items:center; gap:5px; padding:4px 12px; border-radius:6px; font-size:12px; font-weight:800; font-family:‘Red Hat Display’,sans-serif; letter-spacing:.3px; transition:all .5s ease; }
.st1 { background:var(–s1bg); color:var(–s1c); border:1.5px solid var(–s1br); }
.st2 { background:var(–s2bg); color:var(–s2c); border:1.5px solid var(–s2br); }
.st3 { background:var(–s3bg); color:var(–s3c); border:1.5px solid var(–s3br); }
.st4 { background:var(–s4bg); color:var(–s4c); border:1.5px solid var(–s4br); }
.auto-label { font-size:10px; color:var(–muted); font-style:italic; }

.jcomment { background:var(–bg); border:1.5px solid var(–border); border-radius:var(–rs); padding:13px; display:none; animation:slideD .4s ease; margin-bottom:11px; }
.jcomment.on { display:block; }
.jch { font-size:11px; color:var(–muted); margin-bottom:9px; font-family:‘Red Hat Display’,sans-serif; font-weight:700; display:flex; align-items:center; gap:5px; flex-wrap:wrap; }
.abadge { background:var(–gl); color:var(–g); padding:2px 6px; border-radius:4px; font-size:10px; font-weight:700; }
.cl { display:flex; gap:7px; padding:5px 0; border-bottom:1px solid var(–border); font-size:12px; }
.cl:last-child { border:none; }
.ck { color:var(–muted); min-width:150px; font-size:10px; font-weight:700; font-family:‘Red Hat Display’,sans-serif; text-transform:uppercase; letter-spacing:.3px; padding-top:1px; }
.cv { color:var(–text); font-weight:600; }
.cy { color:var(–warn); }
.cn { color:var(–ok); }

.jatt { display:none; margin-top:9px; padding-top:9px; border-top:1px solid var(–border); }
.jatt.on { display:block; }
.jattl { font-size:11px; font-weight:700; color:var(–muted); text-transform:uppercase; letter-spacing:.3px; font-family:‘Red Hat Display’,sans-serif; margin-bottom:7px; }
.chips { display:flex; flex-wrap:wrap; gap:5px; }
.chip { display:flex; align-items:center; gap:4px; background:var(–white); border:1px solid var(–borderS); border-radius:6px; padding:4px 9px; font-size:11px; font-weight:600; color:var(–jblue); cursor:pointer; transition:all .15s; }
.chip:hover { background:var(–jbg); }

.jacts { display:none; gap:7px; margin-top:3px; }
.jacts.on { display:flex; }
.bjira { flex:1; padding:10px; border-radius:var(–rs); border:none; font-family:‘Red Hat Display’,sans-serif; font-weight:700; font-size:13px; cursor:pointer; transition:all .2s; }
.bapprove { background:var(–g); color:#fff; }
.bapprove:hover { background:var(–gm); transform:translateY(-1px); }
.bcomm { background:var(–white); color:var(–text); border:1.5px solid var(–borderS); }
.bcomm:hover { border-color:var(–g); color:var(–g); }

@keyframes pulse { 0%,100%{opacity:1} 50%{opacity:.3} }
.pulse { animation:pulse 1.5s ease infinite; }
@keyframes slideD { from{opacity:0;transform:translateY(-6px)} to{opacity:1;transform:translateY(0)} }
@keyframes cardMove { 0%{transform:scale(1)} 50%{transform:scale(1.03)} 100%{transform:scale(1)} }

footer { text-align:center; color:var(–muted); font-size:11px; margin-top:36px; padding-top:18px; border-top:1px solid var(–border); }
footer strong { color:var(–g); font-family:‘Red Hat Display’,sans-serif; }
</style>

</head>
<body>

<div class="topbar">
  <div class="topbar-left">
    <div class="wordmark">MODO</div>
    <div class="topbar-div"></div>
    <div class="topbar-sub">CX → Legales · Flujo PTM</div>
  </div>
  <div class="demo-badge">● Demo</div>
</div>

<div class="container">

  <div class="fh">
    <h1>Cambio de estado automático en Jira</h1>
    <p>Cada acción en Slack mueve el ticket por el board automáticamente vía Zapier</p>
  </div>

  <!-- Mini Jira board -->

  <div class="board">
    <div class="board-col">
      <div class="board-col-header bh1">Tareas por asignar <span id="cnt1">9</span></div>
      <div class="board-card active-card" id="bc-main">
        <div class="bc-tag tag-ptm">PTM</div>
        <div class="bc-title">Daniela Inés Mamani — 31402279 — 4210832/26</div>
        <div class="bc-date">📅 15 may 2026</div>
        <div class="bc-id">LCX-1670</div>
      </div>
    </div>
    <div class="board-col">
      <div class="board-col-header bh2">EN PROCESO CX <span id="cnt2">0</span></div>
      <div id="col2-empty" style="font-size:11px;color:var(--muted);padding:8px;font-style:italic;">Sin casos</div>
    </div>
    <div class="board-col">
      <div class="board-col-header bh3">En revisión LCA <span id="cnt3">20</span></div>
      <div class="board-card" style="opacity:.5">
        <div class="bc-tag" style="background:#e0eaff;color:var(--jblue)">PROMOS</div>
        <div class="bc-title">German Sequeira Wolf — 39917238</div>
        <div class="bc-date">📅 4 may 2026</div>
        <div class="bc-id">LCX-1632</div>
      </div>
    </div>
    <div class="board-col">
      <div class="board-col-header bh4">Finalizado <span>0</span></div>
      <div style="font-size:11px;color:var(--muted);padding:8px;font-style:italic;">Sin casos</div>
    </div>
  </div>

  <!-- Transition log -->

  <div class="transition-log">
    <div class="tl-title">📋 Historial de transiciones automáticas — LCX-1670</div>
    <div class="tl-items" id="tlItems">
      <div class="tl-empty">Las transiciones aparecerán aquí a medida que avanzás el flujo</div>
    </div>
  </div>

  <!-- Zapier bridge -->

  <div class="zapier-bridge">
    <span>Acción en Slack</span><span>→</span>
    <span class="zbadge">ZAPIER</span>
    <span>→</span>
    <span>Transición automática en Jira</span>
    <span class="zauto">(sin intervención manual)</span>
  </div>

  <!-- Grid -->

  <div class="grid">

```
<!-- SLACK -->
<div class="card">
  <div class="ch slack"><div class="aicon s">💬</div>Slack — #lca-cx</div>
  <div class="cb">

    <div class="smsg">
      <div class="smeta">
        <span class="sbot">DFCO BOT</span>
        <span class="satag">APP</span>
        <span class="stime">14:28</span>
      </div>
      <div class="stextm">
        Hola <span class="mention">@expertos-pps</span> ! Tenemos un nuevo caso:<br>
        <strong>[PTM] Daniela Inés Mamani — 31402279 — 4210832/26</strong><br>
        ¿Nos ayudan a revisarlo? 🗂<br>
        <span style="font-size:12px">📅 Respuesta ideal antes del: <span class="deadline">2026-05-07</span></span><br>
        <a class="slink" href="#">🔗 LCX-1670</a>
      </div>
    </div>

    <div class="cxform">
      <div class="cxtitle">📋 Contexto para Legales — LCX-1670</div>

      <div class="frow">
        <div class="fg">
          <label class="fl">¿Reclamo en MODO?</label>
          <select class="fs" id="f1" onchange="onFirstField()"><option value="">Seleccionar</option><option>Sí</option><option>No</option></select>
        </div>
        <div class="fg">
          <label class="fl">N° Ticket MODO</label>
          <input class="fi" id="f2" type="text" placeholder="ej: TK-00234">
        </div>
      </div>

      <div class="fg">
        <label class="fl">¿Error fue responsabilidad de MODO?</label>
        <select class="fs" id="f3"><option value="">Seleccionar</option><option>Sí</option><option>No</option><option>Pendiente de análisis</option></select>
      </div>

      <div class="frow">
        <div class="fg">
          <label class="fl">¿Contactamos al comercio?</label>
          <select class="fs" id="f4"><option value="">Seleccionar</option><option>Sí</option><option>No</option></select>
        </div>
        <div class="fg">
          <label class="fl">Adquirente</label>
          <input class="fi" id="f5" type="text" placeholder="ej: Prisma">
        </div>
      </div>

      <div class="fg">
        <label class="fl">Observaciones</label>
        <input class="fi" id="f6" type="text" placeholder="Contexto adicional relevante...">
      </div>

      <div class="fg">
        <label class="fl">📎 Adjuntar pruebas del caso</label>
        <div class="drop-zone" id="dz">
          <input type="file" id="fi" multiple accept="image/*,.pdf,.doc,.docx,.xls,.xlsx" onchange="addFiles(this.files)">
          <div class="dicon">📁</div>
          <div class="dlabel">Adjuntar imágenes o documentos</div>
          <div class="dhint">Capturas, PDFs, comprobantes · Arrastrá o hacé clic</div>
        </div>
        <div class="flist" id="fl"></div>
      </div>

      <button class="btn-sub" onclick="send()">
        <span>Enviar contexto a Legales</span><span>→</span>
      </button>
    </div>

  </div>
</div>

<!-- JIRA -->
<div class="card">
  <div class="ch jira"><div class="aicon j">📋</div>Jira — LCX-CX / LCX-1670</div>
  <div class="cb">

    <div class="jt">
      <div class="jid">LCX-1670</div>
      <div class="jtitle">[PTM] Daniela Inés Mamani — 31402279 — 4210832/26</div>
      <div class="jf"><span class="jfl">Fecha límite</span><span class="jfv" style="color:var(--warn);font-weight:700">2026-05-07</span></div>
      <div class="jf"><span class="jfl">Monto</span><span class="jfv">$108.316</span></div>
      <div class="jf"><span class="jfl">Comercio</span><span class="jfv">AZUL SUPERMERCADOS</span></div>
      <div class="jf"><span class="jfl">Fecha pago</span><span class="jfv">2026-02-24</span></div>
      <div class="jf">
        <span class="jfl">Estado</span>
        <div class="jstat-wrap">
          <span class="jstat st1" id="jst"><span class="pulse">●</span> Tareas por asignar</span>
          <span class="auto-label" id="autoLabel"></span>
        </div>
      </div>
    </div>

    <div class="jcomment" id="jc">
      <div class="jch">💬 Comentario automático <span class="abadge">via Zapier</span><span style="margin-left:auto;font-size:10px" id="ct"></span></div>
      <div class="cl"><span class="ck">¿Reclamo en MODO?</span><span class="cv" id="r1">—</span></div>
      <div class="cl"><span class="ck">N° Ticket MODO</span><span class="cv" id="r2">—</span></div>
      <div class="cl"><span class="ck">¿Resp. de MODO?</span><span class="cv" id="r3">—</span></div>
      <div class="cl"><span class="ck">¿Contacto comercio?</span><span class="cv" id="r4">—</span></div>
      <div class="cl"><span class="ck">Adquirente</span><span class="cv" id="r5">—</span></div>
      <div class="cl"><span class="ck">Observaciones</span><span class="cv" id="r6">—</span></div>
      <div class="jatt" id="ja">
        <div class="jattl">📎 Adjuntos <span id="ac"></span></div>
        <div class="chips" id="achips"></div>
      </div>
    </div>

    <div class="jacts" id="jacts">
      <button class="bjira bapprove" onclick="approve()">✓ Aprobar y cerrar</button>
      <button class="bjira bcomm">+ Agregar comentario</button>
    </div>

  </div>
</div>
```

  </div>

  <footer><strong>MODO</strong> · CX → Legales · Flujo PTM automatizado via Slack + Zapier + Jira</footer>

</div>

<script>
let files = [], firstFieldDone = false;

// Drag & drop
const dz = document.getElementById('dz');
dz.addEventListener('dragover', e => { e.preventDefault(); dz.classList.add('over'); });
dz.addEventListener('dragleave', () => dz.classList.remove('over'));
dz.addEventListener('drop', e => { e.preventDefault(); dz.classList.remove('over'); addFiles(e.dataTransfer.files); });

function addFiles(list) {
  Array.from(list).forEach(f => { if (!files.find(x => x.name === f.name)) files.push(f); });
  renderFiles();
}
function icon(n) {
  const e = n.split('.').pop().toLowerCase();
  if (['jpg','jpeg','png','gif','webp'].includes(e)) return '🖼️';
  if (e==='pdf') return '📄';
  if (['doc','docx'].includes(e)) return '📝';
  if (['xls','xlsx'].includes(e)) return '📊';
  return '📎';
}
function sz(b) { if(b<1024)return b+' B'; if(b<1048576)return (b/1024).toFixed(0)+' KB'; return (b/1048576).toFixed(1)+' MB'; }
function renderFiles() {
  const fl = document.getElementById('fl'); fl.innerHTML='';
  files.forEach((f,i) => {
    const d=document.createElement('div'); d.className='fitem';
    d.innerHTML=`<span class="fico">${icon(f.name)}</span><div class="finf"><div class="fname">${f.name}</div><div class="fsize">${sz(f.size)}</div></div><button class="frem" onclick="rmFile(${i})">✕</button>`;
    fl.appendChild(d);
  });
}
function rmFile(i) { files.splice(i,1); renderFiles(); }

function now() { const d=new Date(); return d.getHours()+':'+String(d.getMinutes()).padStart(2,'0'); }

function addTransition(from, fromClass, to, toClass, via) {
  const tl = document.getElementById('tlItems');
  // remove empty state
  const empty = tl.querySelector('.tl-empty');
  if (empty) empty.remove();

  const item = document.createElement('div');
  item.className = 'tl-item';
  item.innerHTML = `
    <span class="tl-time">${now()}</span>
    <span class="tl-from ${fromClass}">${from}</span>
    <span class="tl-arrow">→</span>
    <span class="tl-to ${toClass}">${to}</span>
    <span class="tl-via">${via}</span>
  `;
  tl.appendChild(item);
}

function moveCardToCol(colId, emptyId) {
  // remove from current position
  const card = document.getElementById('bc-main');
  if (!card) return;
  card.classList.add('moving');

  setTimeout(() => {
    const col = document.getElementById(colId);
    const empty = document.getElementById(emptyId);
    if (empty) empty.remove();
    col.appendChild(card);
    card.classList.remove('moving');
    card.classList.add('active-card');
  }, 300);
}

// Step 1: CX opens form → EN PROCESO CX
function onFirstField() {
  if (firstFieldDone) return;
  const val = document.getElementById('f1').value;
  if (!val) return;
  firstFieldDone = true;

  // Update Jira status
  const jst = document.getElementById('jst');
  jst.className = 'jstat st2';
  jst.innerHTML = '⟳ EN PROCESO CX';
  document.getElementById('autoLabel').textContent = '← Zapier (automático)';

  // Update board counts
  document.getElementById('cnt1').textContent = '8';
  document.getElementById('cnt2').textContent = '1';

  // Move card on board
  const card = document.getElementById('bc-main');
  const col2 = document.querySelector('.board .board-col:nth-child(3)'); // EN PROCESO CX col
  // find col2 by cnt2
  const cols = document.querySelectorAll('.board-col');
  card.classList.add('moving');
  setTimeout(() => {
    cols[1].appendChild(card);
    card.classList.remove('moving');
  }, 300);

  // Add to transition log
  addTransition('Tareas por asignar','st1','EN PROCESO CX','st2','Zapier · CX abrió formulario');
}

// Step 2: CX submits → En revisión LCA
function send() {
  const v1=document.getElementById('f1').value, v3=document.getElementById('f3').value, v4=document.getElementById('f4').value;
  if (!v1||!v3||!v4) { alert('Completá los campos obligatorios.'); return; }
  const v2=document.getElementById('f2').value||'—', v5=document.getElementById('f5').value||'—', v6=document.getElementById('f6').value||'—';

  setTimeout(() => {
    // Update Jira status
    const jst = document.getElementById('jst');
    jst.className = 'jstat st3';
    jst.innerHTML = '📋 En revisión LCA';
    document.getElementById('autoLabel').textContent = '← Zapier (automático)';

    // Update board
    document.getElementById('cnt2').textContent = '0';
    document.getElementById('cnt3').textContent = '21';
    const card = document.getElementById('bc-main');
    const cols = document.querySelectorAll('.board-col');
    card.classList.add('moving');
    setTimeout(() => { cols[2].appendChild(card); card.classList.remove('moving'); }, 300);

    // Transition log
    addTransition('EN PROCESO CX','st2','En revisión LCA','st3','Zapier · CX envió contexto');

    // Fill comment
    document.getElementById('ct').textContent = now();
    document.getElementById('r1').textContent=v1; document.getElementById('r1').className='cv '+(v1==='Sí'?'cy':'cn');
    document.getElementById('r2').textContent=v2;
    document.getElementById('r3').textContent=v3; document.getElementById('r3').className='cv '+(v3==='Sí'?'cy':v3==='No'?'cn':'cv');
    document.getElementById('r4').textContent=v4; document.getElementById('r4').className='cv '+(v4==='Sí'?'cn':'cv');
    document.getElementById('r5').textContent=v5;
    document.getElementById('r6').textContent=v6;

    if (files.length > 0) {
      document.getElementById('ac').textContent='('+files.length+')';
      const chips=document.getElementById('achips'); chips.innerHTML='';
      files.forEach(f=>{ const c=document.createElement('div'); c.className='chip'; c.innerHTML=icon(f.name)+' '+f.name; chips.appendChild(c); });
      document.getElementById('ja').classList.add('on');
    }

    document.getElementById('jc').classList.add('on');
    document.getElementById('jacts').classList.add('on');
  }, 800);
}

// Step 3: Legales approves → Finalizado
function approve() {
  const jst = document.getElementById('jst');
  jst.className = 'jstat st4';
  jst.innerHTML = '✓ Finalizado';
  document.getElementById('autoLabel').textContent = '← Legales cerró el caso';

  document.getElementById('cnt3').textContent = '20';

  const card = document.getElementById('bc-main');
  const cols = document.querySelectorAll('.board-col');
  card.classList.add('moving');
  setTimeout(() => {
    // remove empty from col4
    const col4 = cols[3];
    const emp = col4.querySelector('div[style]');
    if(emp) emp.remove();
    col4.appendChild(card);
    card.classList.remove('moving');
  }, 300);

  addTransition('En revisión LCA','st3','Finalizado','st4','Legales · Descargo aprobado');
}
</script>

</body>
</html>

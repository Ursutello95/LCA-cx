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
.demo-badge {
background:rgba(255,255,255,.15); border:1px solid rgba(255,255,255,.25);
color:#fff; padding:4px 12px; border-radius:100px; font-size:11px;
font-weight:700; letter-spacing:1px; text-transform:uppercase;
font-family:‘Red Hat Display’,sans-serif;
}

.container { max-width:1100px; margin:0 auto; padding:32px 22px 48px; }

.fh { margin-bottom:28px; }
.fh h1 { font-family:‘Red Hat Display’,sans-serif; font-weight:900; font-size:clamp(24px,4vw,36px); color:var(–g); letter-spacing:-1px; line-height:1.1; margin-bottom:6px; }
.fh p { font-size:14px; color:var(–muted); }

.steps { display:flex; align-items:center; gap:6px; margin-bottom:24px; flex-wrap:wrap; }
.step {
display:flex; align-items:center; gap:5px;
background:var(–white); border:1.5px solid var(–border);
padding:5px 13px; border-radius:100px; font-size:12px; font-weight:700;
color:var(–muted); font-family:‘Red Hat Display’,sans-serif; transition:all .3s;
}
.step.active { border-color:var(–g); background:var(–gl); color:var(–g); }
.step.done { border-color:var(–gm); background:var(–g); color:#fff; }
.step-arr { color:var(–borderS); font-size:13px; }

.success-bar {
display:none; background:var(–okbg); border:1.5px solid #a8d8b8;
border-radius:var(–r); padding:14px 18px; margin-bottom:20px;
align-items:center; gap:12px; animation:slideD .4s ease;
}
.success-bar.on { display:flex; }
.sicon { font-size:20px; flex-shrink:0; }
.stxt { font-size:13px; line-height:1.5; }
.stxt strong { color:var(–ok); font-family:‘Red Hat Display’,sans-serif; }

.zbr {
display:flex; align-items:center; justify-content:center; gap:10px;
padding:11px 18px; background:var(–white); border:1.5px dashed var(–borderS);
border-radius:var(–r); margin-bottom:20px; font-size:13px; color:var(–muted); font-weight:500;
}
.zbadge { background:#FF4A00; color:#fff; padding:3px 9px; border-radius:5px; font-weight:800; font-size:11px; letter-spacing:1px; font-family:‘Red Hat Display’,sans-serif; }

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
.satag { background:#4a154b; color:#fff; font-size:9px; padding:1px 5px; border-radius:3px; font-weight:700; letter-spacing:.5px; }
.stime { color:#999; font-size:11px; }
.stextm { font-size:13px; line-height:1.6; color:#1d1c1d; }
.mention { color:#1264a3; font-weight:600; }
.slink { color:#1264a3; font-size:12px; text-decoration:none; }
.deadline { color:var(–warn); font-weight:700; }

.cxform { background:var(–gp); border:1.5px solid var(–border); border-radius:var(–rs); padding:15px; }
.cxtitle { font-family:‘Red Hat Display’,sans-serif; font-size:13px; font-weight:700; color:var(–g); margin-bottom:13px; display:flex; align-items:center; gap:5px; }
.fg { margin-bottom:11px; }
.fl { font-size:10px; color:var(–muted); margin-bottom:4px; display:block; font-weight:700; letter-spacing:.4px; text-transform:uppercase; font-family:‘Red Hat Display’,sans-serif; }
.fs,.fi {
width:100%; background:var(–white); border:1.5px solid var(–borderS);
border-radius:7px; padding:8px 11px; color:var(–text);
font-family:‘Red Hat Text’,sans-serif; font-size:13px; outline:none;
transition:border-color .2s, box-shadow .2s; appearance:none;
}
.fs:focus,.fi:focus { border-color:var(–g); box-shadow:0 0 0 3px rgba(45,106,45,.1); }
.frow { display:grid; grid-template-columns:1fr 1fr; gap:9px; }

/* File upload */
.drop-zone {
border:2px dashed var(–borderS); border-radius:var(–rs);
padding:16px; text-align:center; cursor:pointer;
transition:all .2s; background:var(–white); position:relative;
}
.drop-zone:hover,.drop-zone.over { border-color:var(–g); background:var(–gp); }
.drop-zone.over { transform:scale(1.01); }
.drop-zone input[type=file] { position:absolute; inset:0; opacity:0; cursor:pointer; width:100%; height:100%; }
.dicon { font-size:22px; margin-bottom:5px; }
.dlabel { font-size:13px; font-weight:700; color:var(–g); font-family:‘Red Hat Display’,sans-serif; }
.dhint { font-size:11px; color:var(–muted); margin-top:3px; }

.flist { margin-top:9px; display:flex; flex-direction:column; gap:5px; }
.fitem { display:flex; align-items:center; gap:7px; background:var(–white); border:1px solid var(–border); border-radius:7px; padding:6px 10px; animation:slideD .2s ease; }
.fico { font-size:15px; flex-shrink:0; }
.finf { flex:1; min-width:0; }
.fname { font-size:12px; font-weight:600; color:var(–text); white-space:nowrap; overflow:hidden; text-overflow:ellipsis; }
.fsize { font-size:10px; color:var(–muted); }
.frem { background:none; border:none; color:var(–muted); cursor:pointer; font-size:13px; padding:2px 5px; border-radius:4px; flex-shrink:0; transition:all .15s; }
.frem:hover { background:#fee; color:#c00; }

.btn-sub {
width:100%; background:var(–g); border:none; border-radius:var(–rs);
padding:12px; color:#fff; font-family:‘Red Hat Display’,sans-serif;
font-weight:700; font-size:14px; cursor:pointer; transition:all .2s;
margin-top:13px; display:flex; align-items:center; justify-content:center; gap:7px;
}
.btn-sub:hover { background:var(–gm); transform:translateY(-1px); box-shadow:0 6px 16px rgba(45,106,45,.25); }
.btn-sub:active { transform:translateY(0); }

/* Jira side */
.jt { background:var(–bg); border:1.5px solid var(–border); border-radius:var(–rs); padding:13px; margin-bottom:13px; }
.jid { font-size:11px; color:var(–jblue); background:var(–jbg); padding:3px 8px; border-radius:4px; display:inline-block; margin-bottom:7px; font-weight:700; font-family:‘Red Hat Display’,sans-serif; }
.jtitle { font-size:14px; font-weight:700; margin-bottom:11px; color:var(–text); font-family:‘Red Hat Display’,sans-serif; line-height:1.3; }
.jf { display:flex; gap:7px; margin-bottom:6px; font-size:12px; align-items:flex-start; }
.jfl { color:var(–muted); min-width:110px; font-weight:700; font-size:10px; padding-top:1px; font-family:‘Red Hat Display’,sans-serif; text-transform:uppercase; letter-spacing:.3px; }
.jfv { color:var(–text); font-weight:500; }
.jstat { display:inline-flex; align-items:center; gap:4px; padding:3px 10px; border-radius:100px; font-size:11px; font-weight:700; font-family:‘Red Hat Display’,sans-serif; letter-spacing:.3px; }
.pend { background:var(–wbg); color:var(–warn); border:1px solid var(–wb); }
.rdy { background:var(–okbg); color:var(–ok); border:1px solid #a8d8b8; }

.jcomment { background:var(–bg); border:1.5px solid var(–border); border-radius:var(–rs); padding:13px; display:none; animation:slideD .4s ease; margin-bottom:11px; }
.jcomment.on { display:block; }
.jch { font-size:11px; color:var(–muted); margin-bottom:9px; font-family:‘Red Hat Display’,sans-serif; font-weight:700; display:flex; align-items:center; gap:5px; }
.abadge { background:var(–gl); color:var(–g); padding:2px 6px; border-radius:4px; font-size:10px; font-weight:700; }
.cl { display:flex; gap:7px; padding:5px 0; border-bottom:1px solid var(–border); font-size:12px; }
.cl:last-child { border:none; }
.ck { color:var(–muted); min-width:150px; font-size:10px; font-weight:700; font-family:‘Red Hat Display’,sans-serif; text-transform:uppercase; letter-spacing:.3px; padding-top:1px; }
.cv { color:var(–text); font-weight:600; }
.cy { color:var(–warn); }
.cn { color:var(–ok); }

.jatt { display:none; margin-top:9px; padding-top:9px; border-top:1px solid var(–border); }
.jatt.on { display:block; }
.jattl { font-size:11px; font-weight:700; color:var(–muted); text-transform:uppercase; letter-spacing:.3px; font-family:‘Red Hat Display’,sans-serif; margin-bottom:7px; display:flex; align-items:center; gap:4px; }
.chips { display:flex; flex-wrap:wrap; gap:5px; }
.chip { display:flex; align-items:center; gap:4px; background:var(–white); border:1px solid var(–borderS); border-radius:6px; padding:4px 9px; font-size:11px; font-weight:600; color:var(–jblue); cursor:pointer; transition:all .15s; }
.chip:hover { background:var(–jbg); border-color:var(–jblue); }

.jacts { display:none; gap:7px; margin-top:3px; }
.jacts.on { display:flex; }
.bjira { flex:1; padding:10px; border-radius:var(–rs); border:none; font-family:‘Red Hat Display’,sans-serif; font-weight:700; font-size:13px; cursor:pointer; transition:all .2s; }
.bapprove { background:var(–g); color:#fff; }
.bapprove:hover { background:var(–gm); transform:translateY(-1px); }
.bcomm { background:var(–white); color:var(–text); border:1.5px solid var(–borderS); }
.bcomm:hover { border-color:var(–g); color:var(–g); }

@keyframes pulse { 0%,100%{opacity:1} 50%{opacity:.3} }
.pulse { animation:pulse 1.5s ease infinite; }
@keyframes slideD { from{opacity:0;transform:translateY(-7px)} to{opacity:1;transform:translateY(0)} }

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
    <h1>Contexto de caso sin fricciones</h1>
    <p>CX completa el formulario en Slack → Jira se actualiza automáticamente para Legales</p>
  </div>

  <div class="steps">
    <div class="step done" id="s1">✓ Bot notifica</div>
    <div class="step-arr">→</div>
    <div class="step active" id="s2">⟳ CX completa</div>
    <div class="step-arr">→</div>
    <div class="step" id="s3">Zapier sincroniza</div>
    <div class="step-arr">→</div>
    <div class="step" id="s4">Legales aprueba</div>
  </div>

  <div class="success-bar" id="sb">
    <div class="sicon">✅</div>
    <div class="stxt">
      <strong>Jira actualizado automáticamente.</strong>
      El caso LCX-1670 está listo para Legales — contexto completo y adjuntos incluidos.
    </div>
  </div>

  <div class="zbr">
    <span>Slack responde</span><span>→</span>
    <span class="zbadge">ZAPIER</span>
    <span>→</span>
    <span>Jira se actualiza + adjuntos subidos</span>
  </div>

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
          <select class="fs" id="f1"><option value="">Seleccionar</option><option>Sí</option><option>No</option></select>
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
        <label class="fl">Observaciones para Legales</label>
        <input class="fi" id="f6" type="text" placeholder="Contexto adicional relevante...">
      </div>

      <div class="fg">
        <label class="fl">📎 Adjuntar pruebas del caso</label>
        <div class="drop-zone" id="dz">
          <input type="file" id="fi" multiple accept="image/*,.pdf,.doc,.docx,.xls,.xlsx">
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
      <div class="jf"><span class="jfl">Estado</span>
        <span class="jstat pend" id="jst"><span class="pulse">●</span> Pendiente contexto CX</span>
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
let files = [];

const dz = document.getElementById('dz');
const fi = document.getElementById('fi');

dz.addEventListener('dragover', e => { e.preventDefault(); dz.classList.add('over'); });
dz.addEventListener('dragleave', () => dz.classList.remove('over'));
dz.addEventListener('drop', e => { e.preventDefault(); dz.classList.remove('over'); addFiles(e.dataTransfer.files); });
fi.addEventListener('change', () => addFiles(fi.files));

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

function sz(b) {
  if (b<1024) return b+' B';
  if (b<1048576) return (b/1024).toFixed(0)+' KB';
  return (b/1048576).toFixed(1)+' MB';
}

function renderFiles() {
  const fl = document.getElementById('fl');
  fl.innerHTML = '';
  files.forEach((f, i) => {
    const d = document.createElement('div');
    d.className = 'fitem';
    d.innerHTML = `<span class="fico">${icon(f.name)}</span><div class="finf"><div class="fname">${f.name}</div><div class="fsize">${sz(f.size)}</div></div><button class="frem" onclick="rmFile(${i})">✕</button>`;
    fl.appendChild(d);
  });
}

function rmFile(i) { files.splice(i,1); renderFiles(); }

function send() {
  const v1=document.getElementById('f1').value, v3=document.getElementById('f3').value, v4=document.getElementById('f4').value;
  if (!v1||!v3||!v4) { alert('Completá los campos obligatorios.'); return; }
  const v2=document.getElementById('f2').value||'—', v5=document.getElementById('f5').value||'—', v6=document.getElementById('f6').value||'—';

  document.getElementById('s2').className='step done'; document.getElementById('s2').textContent='✓ CX completó';
  document.getElementById('s3').className='step active'; document.getElementById('s3').textContent='⟳ Zapier sincroniza';

  setTimeout(() => {
    document.getElementById('s3').className='step done'; document.getElementById('s3').textContent='✓ Zapier sincronizó';
    document.getElementById('s4').className='step active';

    const now = new Date();
    document.getElementById('ct').textContent = now.getHours()+':'+String(now.getMinutes()).padStart(2,'0');

    document.getElementById('r1').textContent=v1; document.getElementById('r1').className='cv '+(v1==='Sí'?'cy':'cn');
    document.getElementById('r2').textContent=v2;
    document.getElementById('r3').textContent=v3; document.getElementById('r3').className='cv '+(v3==='Sí'?'cy':v3==='No'?'cn':'cv');
    document.getElementById('r4').textContent=v4; document.getElementById('r4').className='cv '+(v4==='Sí'?'cn':'cv');
    document.getElementById('r5').textContent=v5;
    document.getElementById('r6').textContent=v6;

    if (files.length > 0) {
      document.getElementById('ac').textContent='('+files.length+')';
      const chips = document.getElementById('achips');
      chips.innerHTML='';
      files.forEach(f => { const c=document.createElement('div'); c.className='chip'; c.innerHTML=icon(f.name)+' '+f.name; chips.appendChild(c); });
      document.getElementById('ja').classList.add('on');
    }

    document.getElementById('jst').className='jstat rdy'; document.getElementById('jst').textContent='✓ Listo para Legales';
    document.getElementById('jc').classList.add('on');
    document.getElementById('jacts').classList.add('on');
    document.getElementById('sb').classList.add('on');
  }, 1200);
}

function approve() {
  document.getElementById('s4').className='step done'; document.getElementById('s4').textContent='✓ Legales aprobó';
  document.getElementById('jst').textContent='✓ Cerrado';
  alert('✅ Caso LCX-1670 cerrado. Descargo enviado al BCRA.');
}
</script>

</body>
</html>

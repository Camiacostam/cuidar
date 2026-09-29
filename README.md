[cuidar_responsive.html](https://github.com/user-attachments/files/32813988/cuidar_responsive.html)
# cuidar
pagina para residencial de ancianos 
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>CUIDAR | Plataforma de cuidados</title>
<style>
:root{
  --violet-950:#625773; --violet-900:#655779; --violet-800:#817198;
  --violet-700:#9B8BB2; --violet-600:#B5A7C9; --violet-500:#C9BDD9;
  --violet-300:#E0D8EA; --violet-200:#EBE5F2; --violet-100:#F3EFF7;
  --violet-50:#FBF9FD; --lilac:#F0EAF6; --pink:#F8EAF0; --mint:#EAF4EE;
  --blue:#EDF2F8; --peach:#FBF1E7; --ink:#3F3A49; --muted:#898292;
  --line:#EEE9F2; --white:#fff; --shadow:0 8px 28px rgba(81,71,101,.055);
}
*{box-sizing:border-box}
body{margin:0;background:#f8f6fb;color:var(--ink);font:14px/1.45 Inter,ui-sans-serif,system-ui,-apple-system,BlinkMacSystemFont,"Segoe UI",sans-serif}
button,input,select{font:inherit} button{cursor:pointer}
.app{display:grid;grid-template-columns:230px minmax(0,1fr);min-height:100vh}
.sidebar{background:var(--violet-950);color:#fff;padding:24px 16px;display:flex;flex-direction:column;gap:28px}
.brand{display:flex;gap:11px;align-items:center;padding:0 8px;font-weight:750;font-size:16px}
.brand-mark{width:40px;height:40px;border-radius:14px;background:#E8DFF2;color:var(--violet-900);display:grid;place-items:center}.brand-mark svg{width:29px;height:29px}
.nav{display:grid;gap:6px}.nav button{border:0;color:#eee8f4;background:transparent;text-align:left;padding:12px 14px;border-radius:12px;display:flex;gap:12px;align-items:center}
.nav button.active,.nav button:hover{background:#817491;color:#fff}
.nav .ico{width:20px;text-align:center;font-size:17px}
.side-bottom{margin-top:auto;border-top:1px solid #5c4a72;padding:18px 8px 0;display:flex;gap:10px;align-items:center;font-size:12px;color:#eee8f4}
.avatar{width:36px;height:36px;display:grid;place-items:center;border-radius:50%;background:var(--violet-200);color:var(--violet-900);font-weight:700;flex-shrink:0}
main{min-width:0;padding:28px clamp(16px,3vw,38px) 42px}
.topbar{display:flex;justify-content:space-between;gap:16px;align-items:center;margin-bottom:25px}
.eyebrow{color:var(--violet-700);font-size:12px;font-weight:700;letter-spacing:.07em;text-transform:uppercase}
h1{font-size:clamp(24px,2.4vw,32px);line-height:1.15;margin:5px 0 7px;color:var(--violet-950);letter-spacing:-.04em}
.sub{color:var(--muted);margin:0}
.top-actions{display:flex;align-items:center;gap:10px}
.date-chip,.icon-btn{border:1px solid var(--line);background:#fff;color:var(--violet-900);padding:10px 13px;border-radius:12px}
.icon-btn{font-size:17px}
.page{display:none}.page.active{display:block}
.stats{display:grid;grid-template-columns:repeat(4,minmax(0,1fr));gap:14px;margin-bottom:20px}
.stat,.card{background:#fff;border:1px solid var(--line);border-radius:18px;box-shadow:var(--shadow)}
.stat{padding:17px;display:flex;align-items:center;gap:13px}
.stat-icon{width:44px;height:44px;border-radius:14px;display:grid;place-items:center;font-size:20px}
.stat strong{display:block;font-size:25px;line-height:1.1;color:var(--violet-950)}
.stat small{display:block;color:var(--muted);margin-top:5px}
.tone-lilac{background:var(--violet-100)}.tone-pink{background:var(--pink)}.tone-mint{background:var(--mint)}.tone-blue{background:var(--blue)}.tone-peach{background:var(--peach)}
.dashboard-grid{display:grid;grid-template-columns:1.2fr 1fr;gap:18px}
.card{padding:20px;min-width:0}
.card-head{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-bottom:15px}
h2{font-size:17px;color:var(--violet-950);margin:0;letter-spacing:-.02em}
h3{font-size:14px;margin:0;color:var(--violet-950)}
.link-btn{background:transparent;border:0;color:var(--violet-700);font-weight:700;font-size:12px}
.task-list{display:grid;gap:9px}
.task{display:flex;align-items:center;gap:11px;padding:11px;border:1px solid var(--line);border-radius:13px}
.task .avatar{width:34px;height:34px;font-size:11px}
.task-info{flex:1;min-width:0}.task-info strong{display:block;font-size:13px}.task-info small{color:var(--muted);font-size:12px}
.status{font-size:11px;font-weight:700;padding:5px 9px;border-radius:999px;white-space:nowrap}
.done{background:var(--mint);color:#34775c}.pending{background:var(--peach);color:#a65b2c}.soon{background:var(--blue);color:#496b99}.paused{background:var(--violet-100);color:var(--violet-700)}
.alert{margin-top:18px;padding:14px 16px;border:1px solid #ead8f4;background:#f7f0fb;border-radius:14px;display:flex;gap:12px;align-items:center}
.alert strong{display:block;color:var(--violet-950)}.alert small{color:var(--muted)}
.btn{border:0;border-radius:12px;background:var(--violet-800);color:white;padding:11px 16px;font-weight:700}
.btn:hover{background:var(--violet-950)}.btn.secondary{background:var(--violet-100);color:var(--violet-900)}
.btn.outline{background:#fff;color:var(--violet-800);border:1px solid var(--violet-300)}
.toolbar{display:flex;gap:10px;flex-wrap:wrap;margin-bottom:17px}
.search{flex:1;min-width:180px;border:1px solid var(--line);border-radius:12px;padding:12px 14px;background:white}
select,input[type=date],input[type=text],input[type=number]{border:1px solid var(--line);border-radius:11px;padding:11px 12px;background:white;color:var(--ink);max-width:100%}
.residents-grid{display:grid;grid-template-columns:repeat(3,minmax(0,1fr));gap:15px}
.resident-card{padding:17px;background:#fff;border:1px solid var(--line);border-radius:17px;box-shadow:var(--shadow)}
.resident-top{display:flex;gap:11px;align-items:center;margin-bottom:15px}.resident-top .avatar{width:45px;height:45px}
.resident-top p{margin:3px 0 0;color:var(--muted);font-size:12px}
.resident-meta{display:flex;gap:6px;flex-wrap:wrap;margin-bottom:14px}
.pill{background:var(--violet-100);color:var(--violet-800);padding:4px 8px;border-radius:8px;font-size:11px}
.resident-foot{display:flex;justify-content:space-between;align-items:center;border-top:1px solid var(--line);padding-top:12px;margin-top:12px}
.tabs{display:flex;gap:6px;border-bottom:1px solid var(--line);margin-bottom:20px;overflow:auto}
.tabs button{border:0;background:transparent;color:var(--muted);padding:12px 15px;white-space:nowrap;border-bottom:2px solid transparent}
.tabs button.active{color:var(--violet-800);border-color:var(--violet-700);font-weight:750}
.med-layout{display:grid;grid-template-columns:1.3fr .8fr;gap:18px}
.med-slots{display:grid;grid-template-columns:repeat(4,minmax(0,1fr));gap:10px}
.slot{border:1px solid var(--line);border-radius:14px;overflow:hidden}
.slot-head{padding:11px;background:var(--violet-100);font-weight:750;color:var(--violet-900);font-size:12px}
.slot-body{padding:12px;min-height:125px}
.med-item{font-size:12px;padding:8px 0;border-bottom:1px solid #f0ebf5}.med-item:last-child{border:0}
.med-item small{display:block;color:var(--muted);margin-top:3px}
.med-item input{accent-color:var(--violet-700)}
.form-grid{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:12px}
.field{display:grid;gap:6px}.field label{font-size:12px;font-weight:700;color:var(--muted)}
.field.full{grid-column:1/-1}
.table-wrap{overflow-x:auto}
table{width:100%;border-collapse:collapse;min-width:520px}
th,td{text-align:left;padding:13px 12px;border-bottom:1px solid var(--line);font-size:13px}
th{font-size:11px;text-transform:uppercase;letter-spacing:.04em;color:var(--muted);font-weight:700}
.voice-box{display:flex;align-items:center;gap:14px;padding:20px;background:var(--violet-50);border:1px solid var(--violet-200);border-radius:16px;margin-bottom:16px}
.mic{width:60px;height:60px;border:0;border-radius:50%;background:var(--violet-800);color:#fff;font-size:24px;box-shadow:0 0 0 8px var(--violet-100)}
.mic.recording{background:#b95778;animation:pulse 1.3s infinite}
@keyframes pulse{50%{box-shadow:0 0 0 13px #f5e4ee}}
.mobile-nav{display:none}
.notice{font-size:12px;color:var(--muted);margin-top:12px}
.check-row{display:flex;align-items:center;gap:10px;padding:13px 0;border-bottom:1px solid var(--line)}
.check-row input{accent-color:var(--violet-700);width:18px;height:18px}
@media(max-width:1100px){.app{grid-template-columns:190px minmax(0,1fr)}.stats{grid-template-columns:repeat(2,minmax(0,1fr))}.residents-grid{grid-template-columns:repeat(2,minmax(0,1fr))}.med-slots{grid-template-columns:repeat(2,minmax(0,1fr))}}
@media(max-width:760px){.app{display:block}.sidebar{display:none}main{padding:20px 14px 95px}.topbar{align-items:flex-start}.top-actions .date-chip{display:none}.dashboard-grid,.med-layout{grid-template-columns:1fr}.stats{gap:10px}.stat{padding:13px;gap:9px}.stat-icon{width:37px;height:37px}.stat strong{font-size:22px}.stat small{font-size:11px}.residents-grid{grid-template-columns:1fr}.card{padding:16px}.mobile-nav{display:flex;position:fixed;bottom:0;left:0;right:0;z-index:20;background:#fff;border-top:1px solid var(--line);justify-content:space-around;padding:9px 4px calc(9px + env(safe-area-inset-bottom));box-shadow:0 -5px 20px #34264f12}.mobile-nav button{border:0;background:transparent;color:var(--muted);font-size:10px;display:grid;gap:3px;justify-items:center}.mobile-nav button span{font-size:19px}.mobile-nav button.active{color:var(--violet-800);font-weight:800}.form-grid{grid-template-columns:1fr}.field.full{grid-column:auto}.topbar h1{font-size:25px}.med-slots{grid-template-columns:repeat(2,minmax(0,1fr))}}
@media(max-width:390px){.stats{grid-template-columns:repeat(2,minmax(0,1fr))}.stat{display:block}.stat-icon{margin-bottom:8px}.med-slots{grid-template-columns:1fr}.topbar{gap:8px}.icon-btn{padding:9px}}

/* Ajustes visuales de marca CUIDAR */
.brand{letter-spacing:-.02em}
.stat,.card,.resident-card{box-shadow:0 6px 24px rgba(98,87,115,.045)}
.btn{background:#9282A9}
.btn:hover{background:#756687}
.mic{background:#9B8BB2;box-shadow:0 0 0 8px #F3EFF7}
.nav button.active,.nav button:hover{background:#827591}
</style>
</head>
<body>
<div class="app">
<aside class="sidebar">
  <div class="brand"><div class="brand-mark"><svg viewBox="0 0 48 48" aria-hidden="true"><path d="M24 39S7 29 7 17.5C7 9 18 6 24 15c6-9 17-6 17 2.5C41 29 24 39 24 39Z" fill="none" stroke="currentColor" stroke-width="3.5" stroke-linecap="round" stroke-linejoin="round"/><path d="M13 24h8l4-7 5 14 4-7h3" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"/></svg></div><div>CUIDAR<small style="display:block;font-size:10px;font-weight:500;color:#ded5e9">Cuidado con calidez</small></div></div>
  <nav class="nav" id="sideNav">
    <button class="active" data-page="inicio"><span class="ico">⌂</span> Inicio</button>
    <button data-page="residentes"><span class="ico">♙</span> Residentes</button>
    <button data-page="medicacion"><span class="ico">◉</span> Medicación</button>
    <button data-page="cuidados"><span class="ico">♡</span> Cuidados y baños</button>
    <button data-page="signos"><span class="ico">⌁</span> Signos vitales</button>
    <button data-page="historial"><span class="ico">▤</span> Historial</button>
    <button data-page="admin"><span class="ico">⚙</span> Administración</button>
  </nav>
  <div class="side-bottom"><div class="avatar">LF</div><div><strong style="display:block;color:white">Lucía Fernández</strong>Cuidadora · Turno mañana</div></div>
</aside>
<main>
<header class="topbar"><div><div class="eyebrow">CUIDAR · Plataforma de cuidados</div><h1 id="pageTitle">Buen día, Lucía <span style="font-size:20px">☀️</span></h1><p class="sub" id="pageSub">Un espacio claro y cálido para organizar los cuidados de cada día.</p></div><div class="top-actions"><span class="date-chip" id="todayDate"></span><button class="icon-btn" title="Notificaciones" onclick="alert('No tenés nuevas notificaciones.')">♧</button></div></header>

<section class="page active" id="page-inicio">
  <div class="stats">
    <div class="stat"><div class="stat-icon tone-lilac">♙</div><div><strong>22</strong><small>Residentes activos</small></div></div>
    <div class="stat"><div class="stat-icon tone-pink">◉</div><div><strong id="pendingCount">4</strong><small>Tomas pendientes</small></div></div>
    <div class="stat"><div class="stat-icon tone-blue">♧</div><div><strong id="bathCount">3</strong><small>Baños para hoy</small></div></div>
    <div class="stat"><div class="stat-icon tone-mint">♡</div><div><strong>2</strong><small>Controles de signos</small></div></div>
  </div>
  <div class="dashboard-grid">
    <div class="card"><div class="card-head"><h2>Medicación de hoy</h2><button class="link-btn" onclick="go('medicacion')">Ver plan completo →</button></div><div class="task-list" id="medTasks"></div></div>
    <div class="card"><div class="card-head"><h2>Cuidados programados</h2><button class="link-btn" onclick="go('cuidados')">Ver agenda →</button></div><div class="task-list" id="careTasks"></div></div>
    <div class="card"><div class="card-head"><h2>Movilizaciones e ingresos/egresos</h2><button class="link-btn" onclick="go('historial')">Ver registro →</button></div>
      <div class="task-list"><div class="task"><div class="avatar">AM</div><div class="task-info"><strong>Ana Martínez</strong><small>08:15 · Movilización a comedor</small></div><span class="status done">Realizado</span></div><div class="task"><div class="avatar">RB</div><div class="task-info"><strong>Rosa Blanes</strong><small>09:10 · Ingreso de visita</small></div><span class="status done">Registrado</span></div><div class="task"><div class="avatar">LP</div><div class="task-info"><strong>Luis Pérez</strong><small>10:30 · Movilización pendiente</small></div><span class="status pending">Pendiente</span></div></div>
    </div>
    <div class="card"><div class="card-head"><h2>Registro rápido por voz</h2><span class="pill">Prototipo</span></div><div class="voice-box"><button class="mic" id="micBtn" onclick="toggleVoice()">🎙</button><div><strong id="voiceTitle">Tocá para dictar</strong><p class="sub" id="voiceDesc">Ej.: “Rosa Blanes, presión 120 sobre 80, pulso 72”.</p></div></div><div class="notice">La transcripción requiere permiso de micrófono y confirmación del personal antes de guardar.</div><button class="btn secondary" onclick="go('signos')">Abrir registro de signos</button></div>
  </div>
  <div class="alert"><span style="font-size:20px">ⓘ</span><div style="flex:1"><strong>Rosa Blanes · Toma de la mañana pendiente</strong><small>Revisá la ficha y confirmá la administración antes de marcarla como realizada.</small></div><button class="btn outline" onclick="go('medicacion')">Ver ficha</button></div>
</section>

<section class="page" id="page-residentes">
  <div class="toolbar"><input class="search" id="residentSearch" placeholder="Buscar residente por nombre…" oninput="filterResidents()"><select id="residentFilter" onchange="filterResidents()"><option value="">Todos los residentes</option><option>Medicación pendiente</option><option>Signos vitales</option></select><button class="btn" onclick="alert('En el producto final: alta de residente con permisos de administración.')">＋ Nuevo residente</button></div>
  <div class="residents-grid" id="residentCards"></div>
</section>

<section class="page" id="page-medicacion">
  <div class="card" style="margin-bottom:18px"><div class="card-head"><div><h2>Ficha de medicación</h2><p class="sub" style="margin-top:5px">Vista de referencia de tomas y tratamientos activos.</p></div><select id="medResident" onchange="renderMedResident()"><option>Rosa Blanes</option><option>Ana Martínez</option><option>José Silva</option><option>Marta Correa</option></select></div>
  <div class="resident-top"><div class="avatar">RB</div><div><h3 id="medName">Rosa Blanes</h3><p>87 años · Habitación 3 · Diabetes · Hipertensión</p></div><span class="status pending" style="margin-left:auto">1 pendiente</span></div>
  <div class="tabs"><button class="active" onclick="switchTab(this,'tabPill')">Pastillero</button><button onclick="switchTab(this,'tabTreatment')">Tratamientos especiales</button><button onclick="switchTab(this,'tabMedHistory')">Historial de cambios</button></div>
  <div id="tabPill"><div class="med-slots" id="medSlots"></div><p class="notice">Referencia visual ilustrativa. Verificar siempre la prescripción vigente, identidad, dosis y vía con el registro oficial del centro.</p></div>
  <div id="tabTreatment" style="display:none"><div class="task"><div class="stat-icon tone-pink">💊</div><div class="task-info"><strong>Amoxicilina 500 mg</strong><small>Lunes a viernes · 08:00 y 20:00 · Fuera del pastillero</small></div><span class="status pending">Temporal</span></div><p class="notice">Las fechas de inicio y fin deben quedar visibles y validadas por personal autorizado.</p></div>
  <div id="tabMedHistory" style="display:none"><div class="table-wrap"><table><thead><tr><th>Fecha</th><th>Cambio</th><th>Realizado por</th></tr></thead><tbody><tr><td>14/09/2026</td><td>Se actualiza horario nocturno</td><td>Administración</td></tr><tr><td>01/09/2026</td><td>Alta de tratamiento temporal</td><td>Enfermería</td></tr></tbody></table></div></div>
  </div>
</section>

<section class="page" id="page-cuidados">
  <div class="toolbar"><input type="date" id="careDate"><select><option>Todos los turnos</option><option>Mañana</option><option>Tarde</option><option>Noche</option></select><button class="btn" onclick="alert('Agenda actualizada en este prototipo.')">Ver agenda</button></div>
  <div class="card"><div class="card-head"><h2>Baños y cuidados personales</h2><span class="pill">Plan diario</span></div><div id="bathList"></div><p class="notice">Si se realiza un baño fuera de agenda, registrá el motivo y quién lo realizó.</p></div>
  <div class="card" style="margin-top:18px"><h2 style="margin-bottom:14px">Registrar cuidado no programado</h2><div class="form-grid"><div class="field"><label>Residente</label><select id="bathResident"><option>Rosa Blanes</option><option>Ana Martínez</option><option>José Silva</option><option>Marta Correa</option></select></div><div class="field"><label>Tipo de cuidado</label><select id="bathType"><option>Baño completo</option><option>Higiene parcial</option><option>Cambio de ropa</option><option>Cuidado de piel</option></select></div><div class="field full"><label>Observaciones</label><input type="text" id="bathNote" placeholder="Motivo, observaciones…"></div></div><button class="btn" style="margin-top:14px" onclick="addBath()">Guardar registro</button></div>
</section>

<section class="page" id="page-signos">
  <div class="med-layout"><div class="card"><div class="card-head"><h2>Registro de signos vitales</h2><span class="pill">Confirmación requerida</span></div><div class="field" style="margin-bottom:15px"><label>Residente</label><select id="vitalResident"><option>Rosa Blanes</option><option>Ana Martínez</option><option>José Silva</option><option>Marta Correa</option></select></div><div class="voice-box"><button class="mic" id="micBtn2" onclick="toggleVoice()">🎙</button><div><strong>Dictado de medición</strong><p class="sub">“Rosa Blanes, presión 120 sobre 80, pulso 72, temperatura 36.5”.</p></div></div><div class="form-grid"><div class="field"><label>Presión sistólica (mmHg)</label><input id="sys" type="number" placeholder="120"></div><div class="field"><label>Presión diastólica (mmHg)</label><input id="dia" type="number" placeholder="80"></div><div class="field"><label>Pulso (lpm)</label><input id="pulse" type="number" placeholder="72"></div><div class="field"><label>Temperatura (°C)</label><input id="temp" type="number" step=".1" placeholder="36.5"></div><div class="field full"><label>Observaciones</label><input id="vitalNote" type="text" placeholder="Observaciones opcionales"></div></div><button class="btn" style="margin-top:15px" onclick="saveVital()">Confirmar y guardar medición</button><p class="notice">El micrófono es una demostración de interfaz. En producción se necesitaría reconocimiento de voz, revisión de transcripción y controles de privacidad.</p></div>
  <div class="card"><div class="card-head"><h2>Últimas mediciones</h2><button class="link-btn" onclick="go('historial')">Ver historial</button></div><div class="task-list" id="vitalRecent"></div></div></div>
</section>

<section class="page" id="page-historial">
  <div class="toolbar"><select><option>Todos los residentes</option><option>Rosa Blanes</option><option>Ana Martínez</option></select><select><option>Todos los registros</option><option>Medicación</option><option>Baños</option><option>Signos vitales</option><option>Movilizaciones</option></select><input type="date"></div>
  <div class="card"><div class="card-head"><h2>Actividad reciente</h2><button class="btn secondary" onclick="alert('Exportación disponible en una versión conectada a datos reales.')">Exportar reporte</button></div><div class="table-wrap"><table><thead><tr><th>Fecha y hora</th><th>Residente</th><th>Registro</th><th>Responsable</th><th>Estado</th></tr></thead><tbody id="historyRows"><tr><td>Hoy · 09:10</td><td>Rosa Blanes</td><td>Ingreso de visita</td><td>Lucía Fernández</td><td><span class="status done">Registrado</span></td></tr><tr><td>Hoy · 08:15</td><td>Ana Martínez</td><td>Movilización</td><td>Lucía Fernández</td><td><span class="status done">Realizado</span></td></tr><tr><td>Hoy · 08:00</td><td>José Silva</td><td>Medicación mañana</td><td>Enfermería</td><td><span class="status done">Confirmado</span></td></tr></tbody></table></div></div>
</section>

<section class="page" id="page-admin">
  <div class="card"><div class="card-head"><div><h2>Administración de medicación</h2><p class="sub" style="margin-top:5px">Solo perfiles autorizados pueden modificar indicaciones.</p></div><select id="adminResident"><option>Rosa Blanes</option><option>Ana Martínez</option><option>José Silva</option></select></div>
  <div class="form-grid"><div class="field"><label>Medicamento</label><input id="drug" type="text" placeholder="Nombre del medicamento"></div><div class="field"><label>Dosis</label><input id="dose" type="text" placeholder="Ej. 500 mg"></div><div class="field"><label>Horario</label><select id="schedule"><option>Mañana · 08:00</option><option>Almuerzo · 12:00</option><option>Tarde · 16:00</option><option>Noche · 20:00</option><option>Personalizado</option></select></div><div class="field"><label>Estado</label><select id="drugStatus"><option>Activo</option><option>Suspensión temporal</option><option>Finalizado</option></select></div><div class="field"><label>Desde</label><input type="date" id="startDate"></div><div class="field"><label>Hasta</label><input type="date" id="endDate"></div><div class="field full"><label>Motivo / referencia de indicación</label><input id="reason" type="text" placeholder="Referencia de la indicación validada"></div></div><button class="btn" style="margin-top:16px" onclick="saveDrug()">Guardar cambio y registrar en historial</button><div class="notice">Este prototipo no reemplaza una prescripción médica ni valida dosis. Los cambios reales deben estar respaldados por una indicación profesional y auditoría.</div></div>
  <div class="card" style="margin-top:18px"><div class="card-head"><h2>Historial de cambios recientes</h2></div><div class="table-wrap"><table><thead><tr><th>Fecha</th><th>Residente</th><th>Detalle</th><th>Usuario</th></tr></thead><tbody id="adminHistory"><tr><td>14/09/2026</td><td>Rosa Blanes</td><td>Actualización de horario nocturno</td><td>Administración</td></tr></tbody></table></div></div>
</section>
</main>
</div>
<nav class="mobile-nav" id="mobileNav"><button class="active" data-page="inicio"><span>⌂</span>Inicio</button><button data-page="residentes"><span>♙</span>Residentes</button><button data-page="medicacion"><span>◉</span>Medicación</button><button data-page="cuidados"><span>♡</span>Cuidados</button><button data-page="signos"><span>⌁</span>Signos</button></nav>
<script>
const residents=[
{name:'Ana Martínez',initials:'AM',room:'Hab. 1',tags:['Movilidad asistida'],pending:false},
{name:'José Silva',initials:'JS',room:'Hab. 2',tags:['Hipertensión'],pending:false},
{name:'Rosa Blanes',initials:'RB',room:'Hab. 3',tags:['Diabetes','Hipertensión'],pending:true},
{name:'Marta Correa',initials:'MC',room:'Hab. 4',tags:['Movilidad asistida'],pending:true},
{name:'Luis Pérez',initials:'LP',room:'Hab. 5',tags:['Control de signos'],pending:true},
{name:'Laura González',initials:'LG',room:'Hab. 6',tags:['Riesgo de caída'],pending:false}
];
let baths=[{name:'Marta Correa',time:'08:00',done:true},{name:'Ana Martínez',time:'09:00',done:true},{name:'José Silva',time:'10:00',done:true},{name:'Rosa Blanes',time:'11:00',done:false},{name:'Luis Pérez',time:'12:00',done:false}];
let vitals=[];
const meds={
'Rosa Blanes':[['Losartán 50 mg','Metformina 850 mg','Omeprazol 20 mg'],['Metformina 850 mg'],['Losartán 50 mg'],['Atorvastatina 20 mg']],
'Ana Martínez':[['Enalapril 10 mg'],['Vitamina D'],['—'],['Enalapril 10 mg']],
'José Silva':[['Losartán 50 mg'],['—'],['—'],['Omeprazol 20 mg']],
'Marta Correa':[['Levotiroxina 50 mcg'],['—'],['Calcio 500 mg'],['—']]
};
function dateLabel(){return new Intl.DateTimeFormat('es-UY',{weekday:'long',day:'numeric',month:'long',year:'numeric'}).format(new Date())}
document.getElementById('todayDate').textContent=dateLabel();
function go(page){document.querySelectorAll('.page').forEach(p=>p.classList.remove('active'));document.getElementById('page-'+page).classList.add('active');document.querySelectorAll('[data-page]').forEach(b=>b.classList.toggle('active',b.dataset.page===page));const titles={inicio:['Buen día, Lucía ☀️','Un espacio claro y cálido para organizar los cuidados de cada día.'],residentes:['Residentes','Consultá fichas y necesidades individuales.'],medicacion:['Medicación','Pastilleros, tratamientos y confirmación de tomas.'],cuidados:['Cuidados y baños','Agenda de higiene y registro de cuidados.'],signos:['Signos vitales','Registro manual o asistido por voz.'],historial:['Historial de actividad','Trazabilidad de los cuidados realizados.'],admin:['Administración','Gestión de medicación y auditoría de cambios.']};document.getElementById('pageTitle').textContent=titles[page][0];document.getElementById('pageSub').textContent=titles[page][1];window.scrollTo({top:0,behavior:'smooth'})}
document.querySelectorAll('[data-page]').forEach(b=>b.addEventListener('click',()=>go(b.dataset.page)));
function renderTasks(){const names=[['Ana Martínez','08:00','Completada'],['José Silva','08:00','Completada'],['Laura González','08:00','Completada'],['Rosa Blanes','08:00','Pendiente'],['Marta Correa','12:00','Próxima']];document.getElementById('medTasks').innerHTML=names.map((x,i)=>`<div class="task"><div class="avatar">${x[0].split(' ').map(s=>s[0]).join('')}</div><div class="task-info"><strong>${x[0]}</strong><small>${x[1]} · Toma programada</small></div><span class="status ${x[2]==='Completada'?'done':x[2]==='Pendiente'?'pending':'soon'}">${x[2]}</span></div>`).join('');document.getElementById('careTasks').innerHTML=baths.slice(0,4).map(x=>`<div class="task"><div class="avatar">${x.name.split(' ').map(s=>s[0]).join('')}</div><div class="task-info"><strong>${x.name}</strong><small>${x.time} · Baño / higiene</small></div><span class="status ${x.done?'done':'pending'}">${x.done?'Completado':'Pendiente'}</span></div>`).join('')}
function renderResidents(){document.getElementById('residentCards').innerHTML=residents.map(r=>`<article class="resident-card" data-name="${r.name.toLowerCase()}" data-pending="${r.pending}"><div class="resident-top"><div class="avatar">${r.initials}</div><div><h3>${r.name}</h3><p>${r.room} · Residente activo</p></div></div><div class="resident-meta">${r.tags.map(t=>`<span class="pill">${t}</span>`).join('')}</div><div style="font-size:12px;color:var(--muted)">Medicación de hoy</div><div style="margin-top:7px"><span class="status ${r.pending?'pending':'done'}">${r.pending?'Toma pendiente':'Al día'}</span></div><div class="resident-foot"><small style="color:var(--muted)">Ficha individual</small><button class="link-btn" onclick="document.getElementById('medResident').value='${r.name}';renderMedResident();go('medicacion')">Ver ficha →</button></div></article>`).join('')}
function filterResidents(){let q=document.getElementById('residentSearch').value.toLowerCase(),f=document.getElementById('residentFilter').value;document.querySelectorAll('.resident-card').forEach(c=>c.style.display=c.dataset.name.includes(q)&&(!f||(f==='Medicación pendiente'?c.dataset.pending==='true':true))?'':'none')}
function renderMedResident(){let n=document.getElementById('medResident').value;document.getElementById('medName').textContent=n;let list=meds[n]||meds['Rosa Blanes'];let labels=['Mañana · 08:00','Almuerzo · 12:00','Tarde · 16:00','Noche · 20:00'];document.getElementById('medSlots').innerHTML=list.map((slot,i)=>`<div class="slot"><div class="slot-head">${labels[i]}</div><div class="slot-body">${slot.map((m,j)=>m==='—'?'<div class="med-item" style="color:var(--muted)">Sin toma programada</div>':`<div class="med-item"><label><input type="checkbox" onchange="this.closest('.med-item').style.opacity=this.checked?'.45':'1'"> ${m}</label><small>${i===0&&j===0?'Según indicación vigente':'Dosis registrada'}</small></div>`).join('')}</div></div>`).join('')}
function switchTab(btn,id){btn.parentElement.querySelectorAll('button').forEach(b=>b.classList.remove('active'));btn.classList.add('active');['tabPill','tabTreatment','tabMedHistory'].forEach(t=>document.getElementById(t).style.display=t===id?'block':'none')}
function renderBaths(){document.getElementById('bathList').innerHTML=baths.map((b,i)=>`<div class="check-row"><input type="checkbox" ${b.done?'checked':''} onchange="baths[${i}].done=this.checked;renderBaths();renderTasks();document.getElementById('bathCount').textContent=baths.filter(x=>!x.done).length"><div style="flex:1"><strong>${b.name}</strong><div class="sub" style="font-size:12px">${b.time} · Higiene programada</div></div><span class="status ${b.done?'done':'pending'}">${b.done?'Completado':'Pendiente'}</span></div>`).join('')}
function addBath(){let name=document.getElementById('bathResident').value,type=document.getElementById('bathType').value,note=document.getElementById('bathNote').value;baths.unshift({name,time:new Date().toLocaleTimeString('es-UY',{hour:'2-digit',minute:'2-digit'}),done:true});renderBaths();renderTasks();document.getElementById('bathCount').textContent=baths.filter(x=>!x.done).length;document.getElementById('bathNote').value='';alert(`Registro guardado en este prototipo: ${type} · ${name}${note?' · '+note:''}`)}
function toggleVoice(){let btn=document.getElementById('micBtn'),btn2=document.getElementById('micBtn2'),title=document.getElementById('voiceTitle'),desc=document.getElementById('voiceDesc');let active=btn.classList.toggle('recording');btn2.classList.toggle('recording',active);if(title){title.textContent=active?'Escuchando… (demo)':'Tocá para dictar';desc.textContent=active?'Demostración visual: no se está guardando audio. Confirmá cualquier dato antes de registrarlo.':'Ej.: “Rosa Blanes, presión 120 sobre 80, pulso 72”.'}else{alert(active?'Modo demostración activado. El navegador no está transcribiendo audio en esta maqueta.':'Modo demostración detenido. Ingresá los valores y confirmalos manualmente.')}if(!active&&title){btn.classList.remove('recording');btn2.classList.remove('recording')}}
function saveVital(){let s=document.getElementById('sys').value,d=document.getElementById('dia').value,p=document.getElementById('pulse').value,t=document.getElementById('temp').value,n=document.getElementById('vitalResident').value;if(!s&&!d&&!p&&!t){alert('Ingresá al menos un valor antes de guardar.');return}vitals.unshift({name:n,time:new Date().toLocaleTimeString('es-UY',{hour:'2-digit',minute:'2-digit'}),values:`${s&&d?s+'/'+d+' mmHg · ':''}${p?'Pulso '+p+' · ':''}${t?'Temp. '+t+' °C':''}`});renderVitals();['sys','dia','pulse','temp','vitalNote'].forEach(id=>document.getElementById(id).value='');alert('Medición agregada al historial de esta demostración.')}
function renderVitals(){document.getElementById('vitalRecent').innerHTML=(vitals.length?vitals:[{name:'Rosa Blanes',time:'08:00',values:'120/80 mmHg · Pulso 72 · Temp. 36.5 °C'},{name:'Ana Martínez',time:'08:15',values:'118/76 mmHg · Pulso 70 · Temp. 36.4 °C'}]).map(v=>`<div class="task"><div class="avatar">${v.name.split(' ').map(s=>s[0]).join('')}</div><div class="task-info"><strong>${v.name}</strong><small>${v.time} · ${v.values}</small></div></div>`).join('')}
function saveDrug(){let drug=document.getElementById('drug').value;if(!drug){alert('Ingresá el nombre del medicamento.');return}let row=document.createElement('tr');row.innerHTML=`<td>${new Date().toLocaleDateString('es-UY')}</td><td>${document.getElementById('adminResident').value}</td><td>${drug} · ${document.getElementById('drugStatus').value} · ${document.getElementById('reason').value||'Sin detalle'}</td><td>Lucía Fernández</td>`;document.getElementById('adminHistory').prepend(row);document.getElementById('drug').value='';document.getElementById('dose').value='';document.getElementById('reason').value='';alert('Cambio añadido al historial local de esta maqueta. No se ha modificado ninguna medicación real.')}
renderTasks();renderResidents();renderMedResident();renderBaths();renderVitals();
</script>
</body>
</html>

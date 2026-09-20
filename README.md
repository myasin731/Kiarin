<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Jurnal Mengajar &amp; Nilai Siswa</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:ital,wght@0,400;0,500;0,600;0,800;1,400&display=swap" rel="stylesheet">
<style>
:root{
  --ink:#10241C; --ink-soft:#4A6257; --ink-faint:#7D9389;
  --spine:#0E3A28; --spine-2:#134B36; --spine-ink:#CFE6DA;
  --green:#23A06B; --green-deep:#17724D; --green-mist:#E4F2EA; --green-line:#CBE2D5;
  --paper:#F6FAF7; --sheet:#FFFFFF;
  --hadir:#17724D; --izin:#2B6CB0; --sakit:#B57D0A; --alpa:#C0453B;
  --line:#E2ECE6; --line-strong:#CBDCD3;
  --shadow:0 1px 2px rgba(16,36,28,.06), 0 8px 24px -16px rgba(16,36,28,.28);
  --r:14px; --r-sm:9px;
  --sb:264px; --sb-collapsed:76px;
}
@media (prefers-color-scheme: dark){
  :root:not([data-theme="light"]){
    --ink:#E7F0EA; --ink-soft:#A7BDB2; --ink-faint:#7C958A;
    --spine:#0A1712; --spine-2:#12241C; --spine-ink:#B9D4C5;
    --green:#3BBE85; --green-deep:#6FD6A6; --green-mist:#16261E; --green-line:#26402F;
    --hadir:#5FCB9A; --izin:#7AB3ED; --sakit:#E0B44A; --alpa:#EE8379;
    --paper:#0B1410; --sheet:#111E18;
    --line:#1E3128; --line-strong:#2A4335;
    --shadow:0 1px 2px rgba(0,0,0,.4), 0 10px 30px -18px rgba(0,0,0,.8);
  }
}
:root[data-theme="dark"]{
  --ink:#E7F0EA; --ink-soft:#A7BDB2; --ink-faint:#7C958A;
  --spine:#0A1712; --spine-2:#12241C; --spine-ink:#B9D4C5;
  --green:#3BBE85; --green-deep:#6FD6A6; --green-mist:#16261E; --green-line:#26402F;
  --hadir:#5FCB9A; --izin:#7AB3ED; --sakit:#E0B44A; --alpa:#EE8379;
  --paper:#0B1410; --sheet:#111E18;
  --line:#1E3128; --line-strong:#2A4335;
  --shadow:0 1px 2px rgba(0,0,0,.4), 0 10px 30px -18px rgba(0,0,0,.8);
}
*{box-sizing:border-box}
html,body{margin:0;padding:0}
body{
  background:var(--paper); color:var(--ink);
  font-family:"Plus Jakarta Sans", ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, sans-serif;
  font-size:15px; line-height:1.55; -webkit-font-smoothing:antialiased;
  font-variant-numeric:tabular-nums;
}
h1,h2,h3,h4{margin:0; line-height:1.22; letter-spacing:-.015em}
p{margin:0}
button,input,select,textarea{font:inherit; color:inherit}
:focus-visible{outline:2.5px solid var(--green); outline-offset:2px; border-radius:4px}
@media (prefers-reduced-motion: reduce){ *{transition:none !important; animation:none !important} }

/* ---------- Kerangka ---------- */
.app{display:flex; min-height:100dvh}

/* ---------- Sidebar ---------- */
.sidebar{
  width:var(--sb); flex:0 0 var(--sb); background:var(--spine); color:var(--spine-ink);
  display:flex; flex-direction:column; position:sticky; top:0; height:100dvh;
  transition:width .22s ease, flex-basis .22s ease; z-index:60;
}
body.collapsed .sidebar{width:var(--sb-collapsed); flex-basis:var(--sb-collapsed)}
.brand{display:flex; align-items:center; gap:11px; padding:20px 18px 16px; min-height:74px}
.brand-mark{
  width:38px; height:38px; flex:0 0 38px; border-radius:11px; background:var(--green);
  display:grid; place-items:center; color:#04150E; font-weight:800; font-size:15px; overflow:hidden;
}
.brand-mark img{width:100%; height:100%; object-fit:cover; display:block}
.brand-text{min-width:0}
.brand-text b{display:block; font-size:14.5px; font-weight:800; color:#fff; white-space:nowrap; overflow:hidden; text-overflow:ellipsis}
.brand-text span{display:block; font-size:12px; color:rgba(207,230,218,.72); white-space:nowrap; overflow:hidden; text-overflow:ellipsis}
body.collapsed .brand-text{display:none}

.nav{padding:6px 10px; display:flex; flex-direction:column; gap:2px; overflow-y:auto; flex:1}
.nav-lab{font-size:11.5px; color:rgba(207,230,218,.5); padding:14px 10px 6px; font-weight:600}
body.collapsed .nav-lab{opacity:0; height:12px; padding:0; overflow:hidden}
.nav a{
  display:flex; align-items:center; gap:12px; padding:10px 12px; border-radius:10px;
  color:rgba(207,230,218,.85); text-decoration:none; font-size:14.5px; font-weight:500;
  position:relative; white-space:nowrap;
}
.nav a:hover{background:rgba(255,255,255,.06); color:#fff}
.nav a.on{background:var(--spine-2); color:#fff; font-weight:600}
.nav a.on::before{
  content:""; position:absolute; left:-10px; top:9px; bottom:9px; width:4px;
  background:var(--green); border-radius:0 4px 4px 0;
}
.nav svg{flex:0 0 20px}
body.collapsed .nav a{justify-content:center; padding:11px 0}
body.collapsed .nav a span{display:none}

.sb-foot{padding:10px; border-top:1px solid rgba(255,255,255,.08)}
.sb-btn{
  width:100%; display:flex; align-items:center; gap:12px; padding:10px 12px; border-radius:10px;
  background:transparent; border:0; color:rgba(207,230,218,.8); cursor:pointer; font-size:14px; text-align:left;
}
.sb-btn:hover{background:rgba(255,255,255,.07); color:#fff}
body.collapsed .sb-btn{justify-content:center}
body.collapsed .sb-btn span{display:none}
body.collapsed .sb-btn svg{transform:rotate(180deg)}

.scrim{display:none}

/* ---------- Area utama ---------- */
.main{flex:1; min-width:0; display:flex; flex-direction:column}
.topbar{
  position:sticky; top:0; z-index:40; background:color-mix(in srgb, var(--paper) 88%, transparent);
  backdrop-filter:blur(10px); border-bottom:1px solid var(--line);
}
.topbar-in{display:flex; align-items:center; gap:14px; padding:14px 26px; max-width:1180px}
.burger{display:none; background:var(--sheet); border:1px solid var(--line-strong); border-radius:10px; padding:8px; cursor:pointer}
.head-id{display:flex; align-items:center; gap:13px; min-width:0; flex:1}
.head-logo{width:42px; height:42px; flex:0 0 42px; border-radius:12px; background:var(--green-mist); border:1px solid var(--green-line); display:grid; place-items:center; overflow:hidden; color:var(--green-deep); font-weight:800}
.head-logo img{width:100%;height:100%;object-fit:cover;display:block}
.head-txt{min-width:0}
.head-txt h1{font-size:19px; font-weight:800; white-space:nowrap; overflow:hidden; text-overflow:ellipsis}
.head-meta{font-size:12.8px; color:var(--ink-soft); white-space:nowrap; overflow:hidden; text-overflow:ellipsis}
.head-meta i{font-style:normal; color:var(--ink-faint); padding:0 6px}

/* ---------- Tombol ---------- */
.btn{
  display:inline-flex; align-items:center; justify-content:center; gap:8px; cursor:pointer;
  border-radius:10px; border:1px solid transparent; padding:9px 15px; font-size:14px; font-weight:600;
  background:var(--sheet); color:var(--ink); border-color:var(--line-strong);
  transition:transform .08s ease, background .15s ease, box-shadow .15s ease;
}
.btn:hover{background:var(--green-mist)}
.btn:active{transform:translateY(1px)}
.btn-primary{background:var(--green); color:#04150E; border-color:transparent; box-shadow:0 1px 0 rgba(0,0,0,.06)}
.btn-primary:hover{background:var(--green-deep); color:#fff}
.btn-primary.saving{opacity:.75; pointer-events:none}
.btn-primary.done{background:var(--green-deep); color:#fff}
.btn-ghost{background:transparent; border-color:transparent; color:var(--ink-soft); padding:7px 10px}
.btn-ghost:hover{background:var(--green-mist); color:var(--ink)}
.btn-danger{color:var(--alpa); border-color:var(--line-strong); background:transparent}
.btn-danger:hover{background:color-mix(in srgb, var(--alpa) 12%, transparent)}
.btn-sm{padding:6px 11px; font-size:13px; border-radius:9px}
.btn[disabled]{opacity:.45; pointer-events:none}

/* ---------- Konten ---------- */
.view{padding:24px 26px 120px; max-width:1180px; width:100%}
.page-head{display:flex; align-items:flex-end; justify-content:space-between; gap:16px; flex-wrap:wrap; margin-bottom:20px}
.page-head h2{font-size:26px; font-weight:800; letter-spacing:-.025em}
.page-head p{font-size:14px; color:var(--ink-soft); margin-top:4px; max-width:62ch}

.sheet{
  background:var(--sheet); border:1px solid var(--line); border-radius:var(--r);
  box-shadow:var(--shadow); overflow:hidden;
}
.sheet + .sheet{margin-top:18px}
.sheet-hd{padding:16px 20px; border-bottom:1px solid var(--line); display:flex; align-items:center; justify-content:space-between; gap:12px; flex-wrap:wrap}
.sheet-hd h3{font-size:16px; font-weight:700}
.sheet-hd p{font-size:13px; color:var(--ink-soft); margin-top:2px}
.sheet-bd{padding:20px}
.grid2{display:grid; grid-template-columns:1.35fr .9fr; gap:18px; align-items:start}
.grid-stats{display:grid; grid-template-columns:repeat(4,1fr); gap:0; border:1px solid var(--line); border-radius:var(--r); background:var(--sheet); overflow:hidden; box-shadow:var(--shadow)}
.stat{padding:16px 18px; border-right:1px solid var(--line)}
.stat:last-child{border-right:0}
.stat b{display:block; font-size:26px; font-weight:800; letter-spacing:-.03em; line-height:1.1}
.stat span{display:block; font-size:12.6px; color:var(--ink-soft); margin-top:3px}
.stat em{font-style:normal; font-size:15px; color:var(--ink-soft); font-weight:600}

/* Rel jadwal */
.rail{list-style:none; margin:0; padding:0}
.rail li{display:flex; gap:16px; padding:14px 20px; border-bottom:1px solid var(--line)}
.rail li:last-child{border-bottom:0}
.rail .jam{
  flex:0 0 58px; text-align:center; border-radius:10px; padding:6px 4px;
  background:var(--green-mist); border:1px solid var(--green-line); color:var(--green-deep);
}
.rail .jam b{display:block; font-size:17px; font-weight:800; line-height:1.1}
.rail .jam span{display:block; font-size:10.5px; letter-spacing:.02em}
.rail .isi{min-width:0; flex:1}
.rail .isi b{display:block; font-size:15px; font-weight:700}
.rail .isi span{display:block; font-size:13px; color:var(--ink-soft)}
.rail .aksi{display:flex; align-items:center}
.now{background:var(--green-mist)}

/* Tabel */
.tbl-wrap{overflow-x:auto; -webkit-overflow-scrolling:touch}
table{border-collapse:collapse; width:100%; min-width:520px; font-size:14px}
th,td{padding:10px 12px; text-align:left; border-bottom:1px solid var(--line); white-space:nowrap}
th{font-size:12.5px; font-weight:700; color:var(--ink-soft); background:var(--green-mist); position:sticky; top:0}
tbody tr:hover{background:color-mix(in srgb, var(--green-mist) 55%, transparent)}
td.num,th.num{text-align:center}
.cell-in{width:62px; text-align:center; padding:6px 4px; border:1px solid var(--line-strong); border-radius:7px; background:var(--sheet)}
.cell-in:focus{border-color:var(--green); background:var(--green-mist)}

/* Formulir */
.fset{border:0; margin:0; padding:22px 20px; border-bottom:1px solid var(--line)}
.fset:last-of-type{border-bottom:0}
.fset > legend{padding:0; display:flex; align-items:center; gap:10px; margin-bottom:14px}
.fset legend b{font-size:15.5px; font-weight:700}
.fset legend small{display:block; font-size:12.6px; color:var(--ink-soft); font-weight:400}
.step{width:26px; height:26px; flex:0 0 26px; border-radius:8px; background:var(--green-deep); color:#fff; display:grid; place-items:center; font-size:13px; font-weight:700}
.row{display:grid; gap:14px; grid-template-columns:repeat(auto-fit,minmax(200px,1fr))}
.row + .row{margin-top:14px}
.f{display:flex; flex-direction:column; gap:6px; min-width:0}
.f label{font-size:13px; font-weight:600; color:var(--ink-soft)}
.f input,.f select,.f textarea{
  width:100%; padding:10px 12px; border-radius:var(--r-sm); border:1px solid var(--line-strong);
  background:var(--sheet); color:var(--ink);
}
.f textarea{resize:vertical; min-height:84px; line-height:1.6}
.f input:focus,.f select:focus,.f textarea:focus{border-color:var(--green); box-shadow:0 0 0 3px color-mix(in srgb, var(--green) 18%, transparent); outline:none}
.f .hint{font-size:12px; color:var(--ink-faint)}
.full{grid-column:1/-1}

/* Presensi */
.presensi{display:grid; grid-template-columns:repeat(auto-fit,minmax(130px,1fr)); gap:12px}
.pres{border:1px solid var(--line-strong); border-radius:var(--r-sm); padding:12px; display:flex; flex-direction:column; gap:7px; border-left-width:4px}
.pres label{font-size:13px; font-weight:700}
.pres input{width:100%; padding:9px 10px; border-radius:8px; border:1px solid var(--line-strong); background:var(--sheet); text-align:center; font-size:17px; font-weight:700}
.pres.h{border-left-color:var(--hadir)} .pres.h label{color:var(--hadir)}
.pres.i{border-left-color:var(--izin)} .pres.i label{color:var(--izin)}
.pres.s{border-left-color:var(--sakit)} .pres.s label{color:var(--sakit)}
.pres.a{border-left-color:var(--alpa)} .pres.a label{color:var(--alpa)}
.pres-sum{margin-top:12px; font-size:13.5px; color:var(--ink-soft); display:flex; gap:16px; flex-wrap:wrap}
.pres-sum b{color:var(--ink)}

/* Bar simpan */
.savebar{
  position:sticky; bottom:0; background:color-mix(in srgb, var(--sheet) 94%, transparent);
  backdrop-filter:blur(8px); border-top:1px solid var(--line);
  padding:13px 20px; display:flex; gap:10px; justify-content:flex-end; align-items:center; flex-wrap:wrap;
}
.savebar .note{margin-right:auto; font-size:13px; color:var(--ink-soft)}

/* Chip & badge */
.chips{display:flex; flex-wrap:wrap; gap:7px}
.chip{display:inline-flex; align-items:center; gap:6px; padding:5px 10px; border-radius:20px; background:var(--green-mist); border:1px solid var(--green-line); font-size:12.8px; font-weight:600; color:var(--green-deep)}
.chip button{background:none;border:0;cursor:pointer;color:inherit;opacity:.6;padding:0;display:grid;place-items:center}
.chip button:hover{opacity:1}
.badge{display:inline-block; padding:3px 9px; border-radius:20px; font-size:12px; font-weight:700}
.b-a{background:color-mix(in srgb, var(--hadir) 16%, transparent); color:var(--hadir)}
.b-b{background:color-mix(in srgb, var(--izin) 16%, transparent); color:var(--izin)}
.b-c{background:color-mix(in srgb, var(--sakit) 18%, transparent); color:var(--sakit)}
.b-d{background:color-mix(in srgb, var(--alpa) 14%, transparent); color:var(--alpa)}

/* Riwayat */
.entry{display:flex; gap:16px; padding:16px 20px; border-bottom:1px solid var(--line)}
.entry:last-child{border-bottom:0}
.tgl{flex:0 0 62px; text-align:center; border-right:1px solid var(--line); padding-right:12px}
.tgl b{display:block; font-size:24px; font-weight:800; line-height:1}
.tgl span{display:block; font-size:11.5px; color:var(--ink-soft)}
.entry-bd{min-width:0; flex:1}
.entry-bd h4{font-size:15.5px; font-weight:700}
.entry-bd .sub{font-size:13px; color:var(--ink-soft); margin-top:2px}
.entry-bd .snip{font-size:13.6px; color:var(--ink-soft); margin-top:8px; display:-webkit-box; -webkit-line-clamp:2; -webkit-box-orient:vertical; overflow:hidden}
.entry-act{display:flex; flex-direction:column; gap:6px; align-items:flex-end}
.detail{margin-top:14px; padding-top:14px; border-top:1px dashed var(--line-strong); display:grid; gap:14px}
.detail h5{font-size:13px; color:var(--ink-soft); font-weight:700; margin:0 0 3px}
.detail p{font-size:14px; white-space:pre-wrap}
.pres-line{display:flex; gap:10px; flex-wrap:wrap}
.pill{font-size:12.5px; font-weight:700; padding:4px 10px; border-radius:8px}

/* Kosong */
.empty{padding:44px 24px; text-align:center}
.empty svg{color:var(--green); opacity:.55}
.empty h4{font-size:17px; font-weight:700; margin:12px 0 6px}
.empty p{font-size:14px; color:var(--ink-soft); max-width:46ch; margin:0 auto 18px}

/* Panel edit header */
.editor{border-top:1px solid var(--line); background:var(--sheet)}
.editor-in{padding:18px 26px 20px; max-width:1180px}
.editor h3{font-size:15px; font-weight:700; margin-bottom:2px}
.editor > .editor-in > p{font-size:13px; color:var(--ink-soft); margin-bottom:14px}
.logo-pick{display:flex; align-items:center; gap:12px}
.logo-prev{width:52px;height:52px;border-radius:12px;background:var(--green-mist);border:1px solid var(--green-line);display:grid;place-items:center;overflow:hidden;color:var(--green-deep);font-weight:800}
.logo-prev img{width:100%;height:100%;object-fit:cover;display:block}

/* Toast */
.toasts{position:fixed; left:50%; transform:translateX(-50%); bottom:20px; z-index:200; display:flex; flex-direction:column; gap:8px; align-items:center; pointer-events:none}
.toast{background:var(--spine); color:#fff; padding:10px 16px; border-radius:10px; font-size:14px; font-weight:600; box-shadow:0 10px 30px -10px rgba(0,0,0,.5); max-width:90vw}
.toast.bad{background:var(--alpa)}

/* Modal */
.modal{position:fixed; inset:0; z-index:150; display:none; align-items:center; justify-content:center; padding:18px; background:rgba(10,23,18,.5)}
.modal.on{display:flex}
.modal-box{background:var(--sheet); border-radius:var(--r); width:100%; max-width:440px; box-shadow:0 24px 60px -20px rgba(0,0,0,.5); max-height:88dvh; overflow:auto}
.modal-hd{padding:16px 20px; border-bottom:1px solid var(--line); font-weight:700}
.modal-bd{padding:18px 20px; display:grid; gap:14px}
.modal-ft{padding:14px 20px; border-top:1px solid var(--line); display:flex; gap:10px; justify-content:flex-end}

.hr{height:1px; background:var(--line); margin:18px 0}
.muted{color:var(--ink-soft); font-size:13.5px}
.right{margin-left:auto}
.wrap-act{display:flex; gap:9px; flex-wrap:wrap; align-items:center}

/* Responsif */
@media (max-width:980px){
  .grid2{grid-template-columns:1fr}
  .grid-stats{grid-template-columns:repeat(2,1fr)}
  .stat:nth-child(2){border-right:0}
  .stat:nth-child(-n+2){border-bottom:1px solid var(--line)}
}
@media (max-width:820px){
  .sidebar{position:fixed; left:0; top:0; transform:translateX(-100%); transition:transform .24s ease; width:274px; flex-basis:274px}
  body.drawer .sidebar{transform:none; box-shadow:0 0 60px rgba(0,0,0,.4)}
  body.collapsed .sidebar{width:274px; flex-basis:274px}
  body.collapsed .brand-text, body.collapsed .nav a span, body.collapsed .sb-btn span{display:block}
  body.collapsed .nav a{justify-content:flex-start; padding:10px 12px}
  .scrim{display:block; position:fixed; inset:0; background:rgba(10,23,18,.45); z-index:55; opacity:0; pointer-events:none; transition:opacity .2s}
  body.drawer .scrim{opacity:1; pointer-events:auto}
  .burger{display:grid}
  .sb-foot{display:none}
  .topbar-in{padding:12px 16px}
  .view{padding:18px 16px 110px}
  .editor-in{padding:16px}
  .page-head h2{font-size:22px}
  .sheet-bd,.fset{padding:16px}
  .rail li{padding:12px 16px}
  .entry{padding:14px 16px; gap:12px}
  .tgl{flex-basis:50px; padding-right:9px}
  .savebar{padding:12px 16px}
  .savebar .btn{flex:1}
  .savebar .note{width:100%; margin-bottom:2px}
}
@media (max-width:520px){
  .grid-stats{grid-template-columns:1fr}
  .stat{border-right:0; border-bottom:1px solid var(--line)}
  .stat:last-child{border-bottom:0}
  .entry{flex-wrap:wrap}
  .entry-act{flex-direction:row; width:100%; justify-content:flex-end}
}
@media print{
  .sidebar,.topbar,.savebar,.entry-act,.scrim,.toasts,.editor{display:none !important}
  body{background:#fff}
  .sheet{box-shadow:none; border-color:#ccc}
  .view{padding:0; max-width:100%}
}

.login-gate{position:fixed;inset:0;z-index:9999;display:grid;place-items:center;background:linear-gradient(135deg,#0b2e20,#17724d 55%,#23a06b);padding:20px}.login-card{width:min(430px,100%);background:rgba(255,255,255,.97);border-radius:24px;padding:30px;box-shadow:0 25px 70px rgba(0,0,0,.25)}.login-brand{width:58px;height:58px;border-radius:17px;background:#23a06b;display:grid;place-items:center;font-weight:900;font-size:20px;margin-bottom:18px}.login-card h2{font-size:25px}.login-card p{color:#5a6d63;font-size:13px;margin-top:5px}.login-card .f{margin-top:14px}.login-card,.login-card label,.login-card h2{color:#10241c}.login-card input::placeholder{color:#7d9389;-webkit-text-fill-color:#7d9389}.login-card input{color:#10241c;-webkit-text-fill-color:#10241c;caret-color:#10241c;width:100%;padding:12px 13px;border:1px solid #cbdcd3;border-radius:11px;background:#fff}.login-pass{position:relative}.login-pass input{padding-right:46px}.login-eye{position:absolute;right:7px;top:6px;font-size:18px;line-height:1;color:#10241c;z-index:2;border:0;background:transparent;padding:7px;cursor:pointer}.login-error{min-height:20px;color:#b42318;font-size:13px;margin-top:9px}.auth-user{display:flex;align-items:center;gap:8px}.role-pill{font-size:11px;padding:3px 7px;border-radius:999px;background:var(--green-mist);color:var(--green-deep);border:1px solid var(--green-line)}.doc-drop{border:1.5px dashed var(--green-line);padding:22px;border-radius:12px;text-align:center;background:var(--green-mist)}
</style>
</head>
<body>
<div class="login-gate" id="loginGate"><form class="login-card" id="loginForm" onsubmit="return jgSubmit(event)" novalidate><div class="login-brand">JG</div><h2>Jurnal & Nilai Guru</h2><p>Silakan masuk untuk mengakses data jurnal, siswa, dan nilai.</p><div class="f"><label>Username</label><input id="loginUser" autocomplete="username" required placeholder="Username"></div><div class="f"><label>Password</label><div class="login-pass"><input id="loginPass" type="password" autocomplete="current-password" required placeholder="Password"><button class="login-eye" type="button" id="togglePass" onclick="return jgTogglePass()" aria-label="Tampilkan password" title="Tampilkan password">👁️</button></div></div><div class="login-error" id="loginError"></div><button class="btn btn-primary" style="width:100%;margin-top:8px" id="loginBtn">Masuk</button><p style="margin-top:15px;font-size:11px">Akun awal: <b>admin / Admin123!</b> atau <b>guru / Guru123!</b>.</p><p style="margin-top:6px;font-size:10px;opacity:.6">versi login v4</p></form></div>
<div class="app" id="appRoot">
  <aside class="sidebar" id="sidebar" aria-label="Menu utama">
    <div class="brand">
      <div class="brand-mark" id="sbLogo">JM</div>
      <div class="brand-text">
        <b id="sbTitle">Jurnal Mengajar</b>
        <span id="sbSub">Kurikulum Merdeka</span>
      </div>
    </div>
    <nav class="nav" id="nav"></nav>
    <div class="sb-foot">
      <button class="sb-btn" id="collapseBtn" type="button">
        <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M15 6l-6 6 6 6"/></svg>
        <span>Ciutkan menu</span>
      </button>
    </div>
  </aside>
  <div class="scrim" id="scrim"></div>

  <div class="main">
    <header class="topbar">
      <div class="topbar-in">
        <button class="burger" id="burger" type="button" aria-label="Buka menu">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.9" stroke-linecap="round"><path d="M4 7h16M4 12h16M4 17h16"/></svg>
        </button>
        <div class="head-id">
          <div class="head-logo" id="hdLogo">JM</div>
          <div class="head-txt">
            <h1 id="hdTitle">Jurnal Mengajar</h1>
            <div class="head-meta" id="hdMeta"></div>
          </div>
        </div>
        <button class="btn btn-sm" id="editHeadBtn" type="button">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M12 20h9"/><path d="M16.5 3.5a2.1 2.1 0 013 3L7 19l-4 1 1-4z"/></svg>
          Ubah header
        </button><div class="auth-user"><span class="role-pill" id="rolePill">-</span><button class="btn btn-sm" id="logoutBtn" type="button">Keluar</button></div></div><div class="editor" id="editor" hidden></div>
    </header>
    <main class="view" id="view"></main>
  </div>
</div>

<div class="toasts" id="toasts"></div>
<div class="modal" id="modal"><div class="modal-box" id="modalBox"></div></div>

<script>
/* === LOGIN BOOT v3 — berdiri sendiri, tidak bergantung pada script utama === */
window.JG_VERSION="v3";
(function(){
  try{ localStorage.setItem("__t","1"); localStorage.removeItem("__t"); }
  catch(e){
    var mem={}; var fake={getItem:function(k){return Object.prototype.hasOwnProperty.call(mem,k)?mem[k]:null},setItem:function(k,v){mem[k]=String(v)},removeItem:function(k){delete mem[k]},clear:function(){mem={}}};
    try{ Object.defineProperty(window,"localStorage",{value:fake,configurable:true}); }catch(_){}
  }
  window.jgShowError=function(msg){var el=document.getElementById("loginError");if(el)el.textContent=msg;};
  window.addEventListener("error",function(ev){ window.jgShowError("Error skrip: "+(ev.message||"tidak diketahui")+(ev.lineno?" (baris "+ev.lineno+")":"")); });
  window.addEventListener("unhandledrejection",function(ev){ var r=ev.reason; window.jgShowError("Error: "+((r&&r.message)||r)); });
  window.jgTogglePass=function(){
    var p=document.getElementById("loginPass"),b=document.getElementById("togglePass");
    if(!p)return false; var show=p.type==="password";
    p.type=show?"text":"password"; b.textContent=show?"🙈":"👁️";
    b.setAttribute("aria-label",show?"Sembunyikan password":"Tampilkan password"); b.title=b.getAttribute("aria-label"); return false;
  };
  window.jgSubmit=function(ev){
    if(ev&&ev.preventDefault)ev.preventDefault();
    if(typeof doLogin==="function"){ doLogin(); }
    else{ window.jgShowError("Skrip utama gagal dimuat. Pastikan sudah Deploy > New version, lalu muat ulang (Ctrl+F5)."); }
    return false;
  };
})();
</script>
<script type="text/plain" id="jgMainSrc">
/* ============ Utilitas ============ */
const $ = (s, r=document) => r.querySelector(s);
const $$ = (s, r=document) => Array.from(r.querySelectorAll(s));
const uid = () => Date.now().toString(36) + Math.random().toString(36).slice(2,7);
const esc = (s) => String(s==null?"":s).replace(/[&<>"']/g, c => ({"&":"&amp;","<":"&lt;",">":"&gt;","\"":"&quot;","'":"&#39;"}[c]));
const HARI = ["Minggu","Senin","Selasa","Rabu","Kamis","Jumat","Sabtu"];
const BLN = ["Jan","Feb","Mar","Apr","Mei","Jun","Jul","Agu","Sep","Okt","Nov","Des"];
const BLN_P = ["Januari","Februari","Maret","April","Mei","Juni","Juli","Agustus","September","Oktober","November","Desember"];
const iso = (d) => { const x = new Date(d); return new Date(x.getTime() - x.getTimezoneOffset()*60000).toISOString().slice(0,10); };
const hariDari = (tgl) => HARI[new Date(tgl + "T00:00:00").getDay()];
const tglPanjang = (t) => { const d = new Date(t+"T00:00:00"); return `${HARI[d.getDay()]}, ${d.getDate()} ${BLN_P[d.getMonth()]} ${d.getFullYear()}`; };
const num = (v) => { const n = parseFloat(v); return isNaN(n) ? 0 : n; };

function icon(name, size=20){
  const p = {
    dashboard:'<path d="M3 10.5L12 3l9 7.5"/><path d="M5 9.7V20h14V9.7"/><path d="M9.5 20v-5.5h5V20"/>',
    jurnal:'<path d="M4 4.5A1.5 1.5 0 015.5 3H18a1 1 0 011 1v15"/><path d="M6 17h13v3.5H6A1.5 1.5 0 014.5 19V6"/><path d="M8 7.5h7M8 11h7"/>',
    riwayat:'<circle cx="12" cy="12" r="8.5"/><path d="M12 7.5V12l3 1.8"/>',
    nilai:'<path d="M4 4h16v16H4z"/><path d="M4 9.5h16M9.5 9.5V20"/><path d="M13 13.5h4M13 16.5h4"/>',
    kelas:'<circle cx="9" cy="8.5" r="3"/><path d="M3.5 19c0-3 2.5-5 5.5-5s5.5 2 5.5 5"/><path d="M16 6.2a3 3 0 010 5.6"/><path d="M17.5 14.4c1.9.6 3 2.4 3 4.6"/>',
    jadwal:'<rect x="3.5" y="5" width="17" height="15.5" rx="2"/><path d="M3.5 10h17M8.5 3v4M15.5 3v4"/>',
    setelan:'<circle cx="12" cy="12" r="3"/><path d="M19.4 14a1.6 1.6 0 00.3 1.8l.1.1a2 2 0 11-2.8 2.8l-.1-.1a1.6 1.6 0 00-1.8-.3 1.6 1.6 0 00-1 1.5V20a2 2 0 11-4 0v-.1A1.6 1.6 0 008 18.3a1.6 1.6 0 00-1.8.3l-.1.1a2 2 0 11-2.8-2.8l.1-.1a1.6 1.6 0 00.3-1.8 1.6 1.6 0 00-1.5-1H2a2 2 0 110-4h.1A1.6 1.6 0 003.7 8a1.6 1.6 0 00-.3-1.8l-.1-.1a2 2 0 112.8-2.8l.1.1a1.6 1.6 0 001.8.3H8a1.6 1.6 0 001-1.5V2a2 2 0 114 0v.1a1.6 1.6 0 001 1.5 1.6 1.6 0 001.8-.3l.1-.1a2 2 0 112.8 2.8l-.1.1a1.6 1.6 0 00-.3 1.8V8a1.6 1.6 0 001.5 1H22a2 2 0 110 4h-.1a1.6 1.6 0 00-1.5 1z"/>',
    plus:'<path d="M12 5v14M5 12h14"/>',
    trash:'<path d="M4 7h16M10 11v6M14 11v6"/><path d="M6 7l1 12.5a1.5 1.5 0 001.5 1.4h7a1.5 1.5 0 001.5-1.4L18 7"/><path d="M9 7V4.6A1.6 1.6 0 0110.6 3h2.8A1.6 1.6 0 0115 4.6V7"/>',
    edit:'<path d="M12 20h9"/><path d="M16.5 3.5a2.1 2.1 0 013 3L7 19l-4 1 1-4z"/>',
    close:'<path d="M6 6l12 12M18 6L6 18"/>',
    check:'<path d="M5 12.5l4.5 4.5L19 7.5"/>',
    print:'<path d="M6.5 9V3.5h11V9"/><rect x="3.5" y="9" width="17" height="7.5" rx="1.5"/><path d="M6.5 14h11v6.5h-11z"/>',
    unduh:'<path d="M12 3.5v11M7.5 10.5L12 15l4.5-4.5"/><path d="M4.5 18.5v2h15v-2"/>',
    salin:'<rect x="8.5" y="8.5" width="12" height="12" rx="2"/><path d="M15.5 5.5A2 2 0 0013.5 3.5h-8a2 2 0 00-2 2v8a2 2 0 002 2"/>',
    book:'<path d="M4 5.5A2 2 0 016 3.5h13v15H6a2 2 0 00-2 2z"/><path d="M4 18.5A2 2 0 016 20.5h13"/>'
  }[name] || '';
  return `<svg width="${size}" height="${size}" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">${p}</svg>`;
}

function toast(msg, bad=false){
  const t = document.createElement("div");
  t.className = "toast" + (bad ? " bad" : "");
  t.textContent = msg;
  $("#toasts").appendChild(t);
  setTimeout(() => t.remove(), 2600);
}

/* ============ Status aplikasi ============ */
const LS = "guru-jurnal-v1";
const state = {
  profile: { judul:"Jurnal Mengajar", guru:"", nip:"", sekolah:"", tahunAjaran:"2026/2027", semester:"Ganjil", logo:"" },
  kelas: [],      // {id,nama,mapel:[],siswa:[{id,nama,nis}]}
  jurnal: [],     // entri jurnal
  nilai: [],      // {id,kelasId,mapel,penilaian:[{id,nama,bobot}],skor:{siswaId:{penilaianId:nilai}}}
  jadwal: [],     // {id,hari,jamKe,mulai,selesai,kelasId,mapel}
  view: "dashboard",
  auth: null,
  draft: null,    // id jurnal yang sedang diedit
  nilaiSel: { kelasId:"", mapel:"" },
  auth: null
};

/* ============ Penyimpanan ============ */
/* Versi Google Apps Script: semua data disimpan di localStorage peramban.
   Code.gs hanya bertugas menyajikan (hosting) halaman ini. */
function gas(fn,...args){return new Promise((resolve,reject)=>{if(!(window.google&&google.script&&google.script.run)){reject(new Error("Web App Apps Script tidak aktif."));return;}google.script.run.withSuccessHandler(resolve).withFailureHandler(reject)[fn](...args);});}
const Repo={ok:false,dl:null,async init(){this.ok=!!(window.google&&google.script&&google.script.run)},async loadAll(){if(!this.ok){loadLocal();return;}const r=await gas("getAppData");if(r&&r.ok&&r.hasData){Object.assign(state.profile,r.data.profile||{});state.kelas=r.data.kelas||[];state.jurnal=r.data.jurnal||[];state.nilai=r.data.nilai||[];state.jadwal=r.data.jadwal||[];saveLocal();}else if(localStorage.getItem(LS)){loadLocal();await gas("saveAppData",{profile:state.profile,kelas:state.kelas,jurnal:state.jurnal,nilai:state.nilai,jadwal:state.jadwal});}}};

function saveLocal(){
  try{
    localStorage.setItem(LS, JSON.stringify({
      profile:state.profile, kelas:state.kelas, jurnal:state.jurnal, nilai:state.nilai, jadwal:state.jadwal
    }));
  }catch(e){}
}
function loadLocal(mergeOnly){
  try{
    const raw = localStorage.getItem(LS);
    if (!raw) return;
    const d = JSON.parse(raw);
    if (mergeOnly && (state.kelas.length || state.jurnal.length)) return;
    Object.assign(state.profile, d.profile || {});
    state.kelas = d.kelas || []; state.jurnal = d.jurnal || [];
    state.nilai = d.nilai || []; state.jadwal = d.jadwal || [];
  }catch(e){}
}

async function putDoc(kind,obj){saveLocal();if(Repo.ok){const r=await gas("saveEntity",kind,obj.id,obj);if(r&&r.ok===false)throw new Error(r.message||"Gagal menyimpan");}}
async function delDoc(kind,id){saveLocal();if(Repo.ok){const r=await gas("deleteEntity",kind,id);if(r&&r.ok===false)throw new Error(r.message||"Gagal menghapus");}}
async function saveProfile(){saveLocal();if(Repo.ok){const r=await gas("saveProfile",state.profile);if(r&&r.ok===false)throw new Error(r.message||"Gagal menyimpan profil");}}
async function saveJadwal(){saveLocal();if(Repo.ok){const r=await gas("saveJadwal",state.jadwal);if(r&&r.ok===false)throw new Error(r.message||"Gagal menyimpan jadwal");}}

/* Tombol simpan dengan umpan balik */
async function withSave(btn, fn, okMsg){
  const html = btn.innerHTML;
  btn.classList.add("saving");
  btn.innerHTML = `<svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="9" opacity=".3"/><path d="M21 12a9 9 0 00-9-9"><animateTransform attributeName="transform" type="rotate" from="0 12 12" to="360 12 12" dur=".8s" repeatCount="indefinite"/></path></svg> Menyimpan…`;
  try{
    const r = await fn();
    if (r === false){ btn.classList.remove("saving"); btn.innerHTML = html; return false; }
    btn.classList.remove("saving"); btn.classList.add("done");
    btn.innerHTML = icon("check",16) + " Tersimpan";
    if (okMsg) toast(okMsg);
    setTimeout(() => { btn.classList.remove("done"); btn.innerHTML = html; }, 1600);
  }catch(e){
    btn.classList.remove("saving"); btn.innerHTML = html;
    toast("Belum tersimpan. " + (e.message || "Coba lagi."), true);
    return false;
  }
}

/* ============ Header ============ */
const MENU = [
  { id:"dashboard", label:"Dashboard",       ic:"dashboard", grup:"Ringkasan" },
  { id:"jurnal",    label:"Jurnal mengajar", ic:"jurnal",    grup:"Kegiatan harian" },
  { id:"riwayat",   label:"Riwayat jurnal",  ic:"riwayat" },
  { id:"nilai",     label:"Data nilai siswa",ic:"nilai",     grup:"Data kelas" },
  { id:"kelas",     label:"Kelas & siswa",   ic:"kelas" },
  { id:"jadwal",    label:"Jadwal mengajar", ic:"jadwal" },
  { id:"dokumen",   label:"Dokumen Drive", ic:"book", grup:"Lainnya" },
  { id:"setelan",   label:"Pengaturan",      ic:"setelan",   grup:"Lainnya" }
];

function renderNav(){
  $("#nav").innerHTML = MENU.map(m =>
    (m.grup ? `<div class="nav-lab">${m.grup}</div>` : "") +
    `<a href="#${m.id}" data-go="${m.id}" title="${m.label}" class="${state.view===m.id?"on":""}">${icon(m.ic)}<span>${m.label}</span></a>`
  ).join("");
}

function inisial(){
  const s = state.profile.sekolah || state.profile.judul || "JM";
  return s.trim().split(/\s+/).slice(0,2).map(w => w[0]).join("").toUpperCase() || "JM";
}
function renderHeader(){
  const p = state.profile;
  $("#hdTitle").textContent = p.judul || "Jurnal Mengajar";
  $("#sbTitle").textContent = p.judul || "Jurnal Mengajar";
  $("#sbSub").textContent = p.sekolah || "Kurikulum Merdeka";
  const meta = [p.guru && ("Guru: " + p.guru), p.sekolah, p.tahunAjaran && ("T.A. " + p.tahunAjaran), p.semester && ("Semester " + p.semester)].filter(Boolean);
  $("#hdMeta").innerHTML = meta.map(esc).join('<i>·</i>') || '<span class="muted">Lengkapi identitas lewat tombol “Ubah header”.</span>';
  const mark = p.logo ? `<img src="${esc(p.logo)}" alt="Logo sekolah">` : inisial();
  $("#hdLogo").innerHTML = mark; $("#sbLogo").innerHTML = mark;
  document.title = (p.judul || "Jurnal Mengajar") + (p.sekolah ? " — " + p.sekolah : "");
}

function toggleEditor(force){
  const box = $("#editor");
  const show = force !== undefined ? force : box.hidden;
  if (!show){ box.hidden = true; return; }
  const p = state.profile;
  box.innerHTML = `<div class="editor-in">
    <h3>Identitas halaman</h3>
    <p>Perubahan di sini muncul di header, sidebar, dan cetakan jurnal.</p>
    <div class="row">
      <div class="f"><label for="e_judul">Judul halaman</label><input id="e_judul" value="${esc(p.judul)}" placeholder="Jurnal Mengajar"></div>
      <div class="f"><label for="e_guru">Nama guru</label><input id="e_guru" value="${esc(p.guru)}" placeholder="Nama lengkap dan gelar"></div>
      <div class="f"><label for="e_nip">NIP / NUPTK</label><input id="e_nip" value="${esc(p.nip)}" placeholder="Opsional"></div>
    </div>
    <div class="row">
      <div class="f"><label for="e_sekolah">Nama sekolah</label><input id="e_sekolah" value="${esc(p.sekolah)}" placeholder="SMP Negeri 1 …"></div>
      <div class="f"><label for="e_ta">Tahun ajaran</label><input id="e_ta" value="${esc(p.tahunAjaran)}" placeholder="2026/2027"></div>
      <div class="f"><label for="e_sem">Semester</label><select id="e_sem"><option ${p.semester==="Ganjil"?"selected":""}>Ganjil</option><option ${p.semester==="Genap"?"selected":""}>Genap</option></select></div>
    </div>
    <div class="row" style="margin-top:14px">
      <div class="f full">
        <label>Logo sekolah</label>
        <div class="logo-pick">
          <div class="logo-prev" id="logoPrev">${p.logo ? `<img src="${esc(p.logo)}" alt="">` : inisial()}</div>
          <input type="file" id="logoFile" accept="image/*" hidden>
          <button class="btn btn-sm" type="button" data-act="pick-logo">Pilih gambar</button>
          ${p.logo ? `<button class="btn btn-sm btn-danger" type="button" data-act="drop-logo">Hapus logo</button>` : ""}
          <span class="hint">Gambar dikecilkan otomatis ke 128 px.</span>
        </div>
      </div>
    </div>
    <div class="wrap-act" style="margin-top:18px; justify-content:flex-end">
      <button class="btn" type="button" data-act="close-editor">Batal</button>
      <button class="btn btn-primary" type="button" data-act="save-header">Simpan header</button>
    </div>
  </div>`;
  box.hidden = false;
}

function resizeImg(file, cb){
  const rd = new FileReader();
  rd.onload = () => {
    const img = new Image();
    img.onload = () => {
      const c = document.createElement("canvas"); c.width = c.height = 128;
      const ctx = c.getContext("2d");
      const s = Math.min(img.width, img.height);
      ctx.drawImage(img, (img.width-s)/2, (img.height-s)/2, s, s, 0, 0, 128, 128);
      cb(c.toDataURL("image/png"));
    };
    img.onerror = () => toast("Gambar tidak bisa dibaca.", true);
    img.src = rd.result;
  };
  rd.onerror = () => toast("Gagal membaca berkas.", true);
  rd.readAsDataURL(file);
}

/* ============ Grafik ============ */
function donut(parts, total){
  const R = 52, C = 2*Math.PI*R; let off = 0;
  const segs = parts.filter(p => p.v > 0).map(p => {
    const frac = total ? p.v/total : 0, len = frac*C;
    const s = `<circle cx="70" cy="70" r="${R}" fill="none" stroke="${p.c}" stroke-width="18"
      stroke-dasharray="${len.toFixed(2)} ${(C-len).toFixed(2)}" stroke-dashoffset="${(-off).toFixed(2)}"
      transform="rotate(-90 70 70)" stroke-linecap="butt"><title>${p.n}: ${p.v}</title></circle>`;
    off += len; return s;
  }).join("");
  const pct = total ? Math.round((parts[0].v/total)*100) : 0;
  return `<svg viewBox="0 0 140 140" width="140" height="140" role="img" aria-label="Komposisi kehadiran">
    <circle cx="70" cy="70" r="${R}" fill="none" stroke="var(--line)" stroke-width="18"/>
    ${segs}
    <text x="70" y="66" text-anchor="middle" font-size="26" font-weight="800" fill="var(--ink)">${pct}%</text>
    <text x="70" y="84" text-anchor="middle" font-size="11" fill="var(--ink-soft)">hadir</text>
  </svg>`;
}
function bars(data){
  if (!data.length) return `<p class="muted">Belum ada data presensi.</p>`;
  const W = 100/data.length;
  return `<svg viewBox="0 0 100 58" preserveAspectRatio="none" width="100%" height="140" role="img" aria-label="Persentase kehadiran per pertemuan">
    ${[0,25,50].map(y => `<line x1="0" y1="${4+y*0.16}" x2="100" y2="${4+y*0.16}" stroke="var(--line)" stroke-width=".35"/>`).join("")}
    ${data.map((d,i) => {
      const h = Math.max(1.5, d.p*0.44);
      const x = i*W + W*0.22, w = W*0.56;
      return `<rect x="${x.toFixed(2)}" y="${(48-h).toFixed(2)}" width="${w.toFixed(2)}" height="${h.toFixed(2)}" rx=".9" fill="var(--green)"><title>${d.l}: ${d.p}% hadir</title></rect>`;
    }).join("")}
    <line x1="0" y1="48" x2="100" y2="48" stroke="var(--line-strong)" stroke-width=".4"/>
  </svg>
  <div style="display:flex;font-size:11px;color:var(--ink-soft);margin-top:4px">
    ${data.map(d => `<div style="flex:1;text-align:center">${esc(d.l)}</div>`).join("")}
  </div>`;
}

/* ============ Bantuan data ============ */
const kelasById = (id) => state.kelas.find(k => k.id === id);
const namaKelas = (id) => (kelasById(id) || {}).nama || "—";
const allMapel = () => [...new Set(state.kelas.flatMap(k => k.mapel || []))].sort();
function totalPresensi(list){
  return list.reduce((a, j) => ({ h:a.h+num(j.hadir), i:a.i+num(j.izin), s:a.s+num(j.sakit), a:a.a+num(j.alpa) }), {h:0,i:0,s:0,a:0});
}
function predikat(n){
  if (n >= 90) return ["A","b-a"]; if (n >= 80) return ["B","b-b"];
  if (n >= 70) return ["C","b-c"]; if (n > 0) return ["D","b-d"]; return ["—",""];
}
function rataNilai(rec, siswaId){
  const sk = (rec.skor || {})[siswaId] || {};
  let tot = 0, bob = 0;
  (rec.penilaian || []).forEach(p => {
    const v = sk[p.id];
    if (v === "" || v == null) return;
    const b = num(p.bobot) || 1;
    tot += num(v)*b; bob += b;
  });
  return bob ? +(tot/bob).toFixed(1) : 0;
}

/* ============ Tampilan: Dashboard ============ */
function viewDashboard(){
  const hariIni = HARI[new Date().getDay()];
  const tgl = iso(new Date());
  const jadwalHariIni = state.jadwal.filter(j => j.hari === hariIni).sort((a,b) => num(a.jamKe) - num(b.jamKe));
  const bulanIni = state.jurnal.filter(j => (j.tanggal||"").slice(0,7) === tgl.slice(0,7));
  const t = totalPresensi(state.jurnal);
  const totSiswa = state.kelas.reduce((a,k) => a + (k.siswa||[]).length, 0);
  const totAll = t.h+t.i+t.s+t.a;
  const rata = totAll ? Math.round(t.h/totAll*100) : 0;
  const terakhir = [...state.jurnal].sort((a,b) => (a.tanggal||"").localeCompare(b.tanggal||"")).slice(-7)
    .map(j => { const tt = num(j.hadir)+num(j.izin)+num(j.sakit)+num(j.alpa);
      return { l: (j.tanggal||"").slice(8,10)+"/"+(j.tanggal||"").slice(5,7), p: tt ? Math.round(num(j.hadir)/tt*100) : 0 }; });

  return `
  <div class="page-head">
    <div>
      <h2>Selamat mengajar${state.profile.guru ? ", " + esc(state.profile.guru.split(" ")[0]) : ""}</h2>
      <p>${tglPanjang(tgl)}${state.profile.semester ? " · Semester " + esc(state.profile.semester) : ""}</p>
    </div>
    <div class="wrap-act">
      <button class="btn btn-primary" data-go="jurnal">${icon("plus",17)} Tulis jurnal hari ini</button>
    </div>
  </div>

  <div class="grid-stats">
    <div class="stat"><b>${bulanIni.length}</b><span>Jurnal bulan ${BLN_P[new Date().getMonth()]}</span></div>
    <div class="stat"><b>${jadwalHariIni.length}</b><span>Jam mengajar hari ini</span></div>
    <div class="stat"><b>${rata}<em>%</em></b><span>Rata-rata kehadiran</span></div>
    <div class="stat"><b>${totSiswa}</b><span>Siswa terdaftar di ${state.kelas.length} kelas</span></div>
  </div>

  <div class="grid2" style="margin-top:18px">
    <section class="sheet">
      <div class="sheet-hd">
        <div><h3>Jadwal ${esc(hariIni)}</h3><p>Ketuk satu jam pelajaran untuk langsung mengisi jurnalnya.</p></div>
        <button class="btn btn-sm" data-go="jadwal">Atur jadwal</button>
      </div>
      ${jadwalHariIni.length ? `<ul class="rail">${jadwalHariIni.map(j => `
        <li>
          <div class="jam"><b>${esc(j.jamKe)}</b><span>jam ke-</span></div>
          <div class="isi">
            <b>${esc(j.mapel || "Mata pelajaran")}</b>
            <span>${esc(namaKelas(j.kelasId))}${j.mulai ? " · " + esc(j.mulai) + (j.selesai ? "–" + esc(j.selesai) : "") : ""}</span>
          </div>
          <div class="aksi"><button class="btn btn-sm" data-act="isi-jadwal" data-id="${j.id}">Isi jurnal</button></div>
        </li>`).join("")}</ul>`
      : `<div class="empty">${icon("jadwal",40)}<h4>Belum ada jadwal untuk ${esc(hariIni)}</h4>
          <p>Susun jadwal sekali saja, lalu setiap hari formulir jurnal terisi otomatis.</p>
          <button class="btn btn-primary" data-go="jadwal">Susun jadwal</button></div>`}
    </section>

    <section class="sheet">
      <div class="sheet-hd"><div><h3>Kehadiran siswa</h3><p>Dihitung dari seluruh jurnal yang tercatat.</p></div></div>
      <div class="sheet-bd">
        <div style="display:flex;gap:18px;align-items:center;flex-wrap:wrap">
          ${donut([
            {n:"Hadir", v:t.h, c:"var(--hadir)"}, {n:"Izin", v:t.i, c:"var(--izin)"},
            {n:"Sakit", v:t.s, c:"var(--sakit)"}, {n:"Alpa", v:t.a, c:"var(--alpa)"}
          ], totAll)}
          <div style="flex:1;min-width:140px;display:grid;gap:7px">
            ${[["Hadir",t.h,"var(--hadir)"],["Izin",t.i,"var(--izin)"],["Sakit",t.s,"var(--sakit)"],["Alpa",t.a,"var(--alpa)"]].map(([n,v,c]) =>
              `<div style="display:flex;align-items:center;gap:9px;font-size:13.5px">
                 <span style="width:10px;height:10px;border-radius:3px;background:${c};flex:0 0 10px"></span>
                 <span style="flex:1">${n}</span><b>${v}</b></div>`).join("")}
          </div>
        </div>
        <div class="hr"></div>
        <h4 style="font-size:13.5px;font-weight:700;margin-bottom:8px">Tujuh pertemuan terakhir</h4>
        ${bars(terakhir)}
      </div>
    </section>
  </div>

  <section class="sheet" style="margin-top:18px">
    <div class="sheet-hd"><div><h3>Jurnal terbaru</h3></div><button class="btn btn-sm" data-go="riwayat">Lihat semua</button></div>
    ${state.jurnal.length ? [...state.jurnal].sort((a,b) => (b.tanggal||"").localeCompare(a.tanggal||"")).slice(0,3).map(j => entryHTML(j, false)).join("")
      : `<div class="empty">${icon("book",40)}<h4>Jurnal masih kosong</h4><p>Catatan pertama Anda akan muncul di sini beserta ringkasan presensinya.</p>
         <button class="btn btn-primary" data-go="jurnal">Tulis jurnal pertama</button></div>`}
  </section>

  <section class="sheet" style="margin-top:18px"><div class="sheet-hd"><div><h3>Rekap nilai kelas</h3><p>Rata-rata siswa dihitung dari seluruh kolom penilaian yang tersedia.</p></div></div><div class="sheet-bd"><div class="tbl-wrap"><table><thead><tr><th>Posisi</th><th>Nama siswa</th><th>NIS</th><th>Rata-rata</th><th>Predikat</th></tr></thead><tbody>${(()=>{const recs=state.nilai||[];let rec=recs[0],k=rec?kelasById(rec.kelasId):null;if(!rec||!k)return '<tr><td colspan="5" class="muted">Belum ada data nilai untuk ditampilkan.</td></tr>';return (k.siswa||[]).map(s=>({s,r:rataNilai(rec,s.id)})).filter(x=>x.r>0).sort((a,b)=>b.r-a.r).slice(0,10).map((x,i)=>`<tr><td>${i+1}</td><td>${esc(x.s.nama)}</td><td>${esc(x.s.nis||'')}</td><td><b>${x.r}</b></td><td>${esc(predikat(x.r)[0])}</td></tr>`).join('')||'<tr><td colspan="5" class="muted">Belum ada nilai yang terisi.</td></tr>'})()}</tbody></table></div></div></section>`;
}

/* ============ Tampilan: Formulir Jurnal ============ */
function viewJurnal(){
  const ed = state.draft ? state.jurnal.find(j => j.id === state.draft) : null;
  const d = ed || {
    tanggal: iso(new Date()), sekolah: state.profile.sekolah, semester: state.profile.semester,
    kelasId: state.kelas[0] ? state.kelas[0].id : "", mapel: "", jamKe: "", tp:"", materi:"",
    pendahuluan:"", inti:"", penutup:"", hadir:"", izin:"0", sakit:"0", alpa:"0",
    kendala:"", respons:"", tugas:"", rencana:""
  };
  const opsiKelas = state.kelas.map(k => `<option value="${k.id}" ${d.kelasId===k.id?"selected":""}>${esc(k.nama)}</option>`).join("");
  const mapelList = allMapel();

  return `
  <div class="page-head">
    <div>
      <h2>${ed ? "Ubah jurnal" : "Jurnal mengajar"}</h2>
      <p>${ed ? "Anda sedang menyunting catatan " + tglPanjang(d.tanggal) + "." : "Satu formulir untuk satu pertemuan. Isi seperlunya — kolom yang kosong tidak akan dicetak."}</p>
    </div>
    <div class="wrap-act">
      ${state.jadwal.length ? `<button class="btn" data-act="prefill">${icon("jadwal",17)} Ambil dari jadwal</button>` : ""}
      ${ed ? `<button class="btn" data-act="batal-edit">Buat jurnal baru</button>` : ""}
    </div>
  </div>

  <form class="sheet" id="formJurnal" autocomplete="off">
    <fieldset class="fset">
      <legend><div><b>Identitas pembelajaran</b><small>Menentukan ke mana catatan ini diarsipkan.</small></div></legend>
      <div class="row">
        <div class="f"><label for="j_sekolah">Nama sekolah</label><input id="j_sekolah" value="${esc(d.sekolah)}" placeholder="SMP Negeri 1 …"></div>
        <div class="f"><label for="j_mapel">Mata pelajaran</label>
          <input id="j_mapel" list="dlMapel" value="${esc(d.mapel)}" placeholder="Matematika">
          <datalist id="dlMapel">${mapelList.map(m => `<option value="${esc(m)}">`).join("")}</datalist>
        </div>
        <div class="f"><label for="j_kelas">Kelas</label>
          <select id="j_kelas">${opsiKelas || `<option value="">Belum ada kelas</option>`}</select>
          ${state.kelas.length ? "" : `<span class="hint">Tambahkan kelas di menu Kelas &amp; siswa.</span>`}
        </div>
      </div>
      <div class="row">
        <div class="f"><label for="j_semester">Semester</label>
          <select id="j_semester"><option ${d.semester==="Ganjil"?"selected":""}>Ganjil</option><option ${d.semester==="Genap"?"selected":""}>Genap</option></select></div>
        <div class="f"><label for="j_tanggal">Tanggal</label><input type="date" id="j_tanggal" value="${esc(d.tanggal)}"></div>
        <div class="f"><label for="j_hari">Hari</label><input id="j_hari" value="${esc(d.hari || hariDari(d.tanggal))}" readonly></div>
        <div class="f"><label for="j_jam">Jam pelajaran ke-</label><input id="j_jam" value="${esc(d.jamKe)}" placeholder="3–4"></div>
      </div>
    </fieldset>

    <fieldset class="fset">
      <legend><div><b>Tujuan / capaian pembelajaran</b><small>Target kompetensi yang dituju pertemuan ini (TP/CP).</small></div></legend>
      <div class="f"><textarea id="j_tp" placeholder="Peserta didik mampu …">${esc(d.tp)}</textarea></div>
    </fieldset>

    <fieldset class="fset">
      <legend><div><b>Materi pembelajaran</b><small>Pokok bahasan atau topik hari ini.</small></div></legend>
      <div class="f"><textarea id="j_materi" style="min-height:70px" placeholder="Bab 3 — Sistem persamaan linear dua variabel">${esc(d.materi)}</textarea></div>
    </fieldset>

    <fieldset class="fset">
      <legend><div><b>Kegiatan pembelajaran</b><small>Uraian singkat aktivitas kelas, berurutan.</small></div></legend>
      <div class="f"><label for="j_pend"><span class="step" style="display:inline-grid;vertical-align:-7px;margin-right:6px">1</span> Pendahuluan</label>
        <textarea id="j_pend" style="min-height:70px" placeholder="Salam, doa, apersepsi, penyampaian tujuan.">${esc(d.pendahuluan)}</textarea></div>
      <div class="f" style="margin-top:14px"><label for="j_inti"><span class="step" style="display:inline-grid;vertical-align:-7px;margin-right:6px">2</span> Kegiatan inti</label>
        <textarea id="j_inti" placeholder="Diskusi kelompok, penyelidikan, presentasi hasil, penguatan konsep.">${esc(d.inti)}</textarea></div>
      <div class="f" style="margin-top:14px"><label for="j_tutup"><span class="step" style="display:inline-grid;vertical-align:-7px;margin-right:6px">3</span> Penutup</label>
        <textarea id="j_tutup" style="min-height:70px" placeholder="Simpulan bersama, refleksi, penyampaian tugas, doa penutup.">${esc(d.penutup)}</textarea></div>
    </fieldset>

    <fieldset class="fset">
      <legend><div><b>Presensi siswa</b><small>Jumlah siswa menurut keterangan kehadiran.</small></div></legend>
      <div class="presensi">
        <div class="pres h"><label for="p_h">Hadir</label><input type="number" min="0" id="p_h" value="${esc(d.hadir)}" placeholder="0"></div>
        <div class="pres i"><label for="p_i">Izin</label><input type="number" min="0" id="p_i" value="${esc(d.izin)}" placeholder="0"></div>
        <div class="pres s"><label for="p_s">Sakit</label><input type="number" min="0" id="p_s" value="${esc(d.sakit)}" placeholder="0"></div>
        <div class="pres a"><label for="p_a">Alpa</label><input type="number" min="0" id="p_a" value="${esc(d.alpa)}" placeholder="0"></div>
      </div>
      <div class="pres-sum" id="presSum"></div>
    </fieldset>

    <fieldset class="fset">
      <legend><div><b>Catatan &amp; refleksi</b><small>Bagian yang paling berguna saat menyusun laporan akhir semester.</small></div></legend>
      <div class="row">
        <div class="f full"><label for="j_kendala">Hambatan / kendala KBM</label>
          <textarea id="j_kendala" style="min-height:70px" placeholder="Proyektor mati, waktu terpotong upacara, dsb.">${esc(d.kendala)}</textarea></div>
      </div>
      <div class="row">
        <div class="f full"><label for="j_respons">Respons siswa</label>
          <textarea id="j_respons" style="min-height:70px" placeholder="Antusias saat kerja kelompok, kesulitan pada soal cerita.">${esc(d.respons)}</textarea></div>
      </div>
      <div class="row">
        <div class="f full"><label for="j_tugas">Penilaian / tugas (PR)</label>
          <textarea id="j_tugas" style="min-height:70px" placeholder="Kuis 5 soal, PR LKS halaman 42, dikumpulkan pertemuan berikutnya.">${esc(d.tugas)}</textarea></div>
      </div>
      <div class="row">
        <div class="f full"><label for="j_rencana">Rencana perbaikan / solusi</label>
          <textarea id="j_rencana" style="min-height:70px" placeholder="Menyiapkan lembar kerja cadangan tanpa proyektor.">${esc(d.rencana)}</textarea></div>
      </div>
    </fieldset>

    <div class="savebar">
      <span class="note" id="saveNote">${Repo.ok ? "Tersimpan otomatis di akun Anda." : "Tersimpan di peramban perangkat ini."}</span>
      <button type="button" class="btn" data-act="reset-form">Kosongkan</button>
      <button type="button" class="btn btn-primary" data-act="simpan-jurnal">${icon("check",17)} Simpan jurnal</button>
    </div>
  </form>`;
}

function hitungPresensi(){
  const el = $("#presSum"); if (!el) return;
  const h = num($("#p_h").value), i = num($("#p_i").value), s = num($("#p_s").value), a = num($("#p_a").value);
  const t = h+i+s+a;
  const k = kelasById($("#j_kelas") ? $("#j_kelas").value : "");
  const jml = k ? (k.siswa||[]).length : 0;
  el.innerHTML = `<span>Total tercatat: <b>${t}</b> siswa</span>
    ${jml ? `<span>Terdaftar di kelas: <b>${jml}</b></span>` : ""}
    <span>Persentase hadir: <b>${t ? Math.round(h/t*100) : 0}%</b></span>
    ${jml && t && t !== jml ? `<span style="color:var(--sakit)">Selisih ${Math.abs(jml-t)} siswa dari daftar kelas.</span>` : ""}`;
}

function bacaForm(){
  const tanggal = $("#j_tanggal").value || iso(new Date());
  return {
    id: state.draft || uid(),
    tanggal, hari: hariDari(tanggal),
    sekolah: $("#j_sekolah").value.trim(), mapel: $("#j_mapel").value.trim(),
    kelasId: $("#j_kelas").value, semester: $("#j_semester").value, jamKe: $("#j_jam").value.trim(),
    tp: $("#j_tp").value.trim(), materi: $("#j_materi").value.trim(),
    pendahuluan: $("#j_pend").value.trim(), inti: $("#j_inti").value.trim(), penutup: $("#j_tutup").value.trim(),
    hadir: num($("#p_h").value), izin: num($("#p_i").value), sakit: num($("#p_s").value), alpa: num($("#p_a").value),
    kendala: $("#j_kendala").value.trim(), respons: $("#j_respons").value.trim(),
    tugas: $("#j_tugas").value.trim(), rencana: $("#j_rencana").value.trim(),
    dibuat: new Date().toISOString()
  };
}

/* ============ Tampilan: Riwayat ============ */
function entryHTML(j, expandable=true){
  const tgl = j.tanggal || "";
  const d = tgl ? new Date(tgl+"T00:00:00") : new Date();
  const t = num(j.hadir)+num(j.izin)+num(j.sakit)+num(j.alpa);
  return `<article class="entry" data-entry="${j.id}">
    <div class="tgl"><b>${d.getDate()}</b><span>${BLN[d.getMonth()]} ${String(d.getFullYear()).slice(2)}</span><span>${(j.hari||"").slice(0,3)}</span></div>
    <div class="entry-bd">
      <h4>${esc(j.mapel || "Tanpa mata pelajaran")} — ${esc(namaKelas(j.kelasId))}</h4>
      <div class="sub">Jam ke-${esc(j.jamKe || "—")} · ${esc(j.semester || "")} ${j.sekolah ? "· " + esc(j.sekolah) : ""}</div>
      <div class="pres-line" style="margin-top:9px">
        <span class="pill b-a">H ${num(j.hadir)}</span><span class="pill b-b">I ${num(j.izin)}</span>
        <span class="pill b-c">S ${num(j.sakit)}</span><span class="pill b-d">A ${num(j.alpa)}</span>
        <span class="pill" style="color:var(--ink-soft)">${t ? Math.round(num(j.hadir)/t*100) : 0}% hadir</span>
      </div>
      ${j.materi ? `<div class="snip">${esc(j.materi)}</div>` : ""}
      <div class="detail" hidden></div>
    </div>
    ${expandable ? `<div class="entry-act">
      <button class="btn btn-sm btn-ghost" data-act="buka" data-id="${j.id}">Rincian</button>
      <button class="btn btn-sm btn-ghost" data-act="edit-jurnal" data-id="${j.id}">${icon("edit",15)} Ubah</button>
      <button class="btn btn-sm btn-ghost" data-act="hapus-jurnal" data-id="${j.id}">${icon("trash",15)} Hapus</button>
    </div>` : `<div class="entry-act"><button class="btn btn-sm btn-ghost" data-act="buka" data-id="${j.id}">Rincian</button></div>`}
  </article>`;
}
function detailHTML(j){
  const blok = [["Tujuan / capaian pembelajaran", j.tp], ["Materi pembelajaran", j.materi],
    ["Pendahuluan", j.pendahuluan], ["Kegiatan inti", j.inti], ["Penutup", j.penutup],
    ["Hambatan / kendala", j.kendala], ["Respons siswa", j.respons],
    ["Penilaian / tugas", j.tugas], ["Rencana perbaikan", j.rencana]].filter(b => b[1]);
  if (!blok.length) return `<p class="muted">Tidak ada uraian tambahan pada catatan ini.</p>`;
  return blok.map(([h, v]) => `<div><h5>${h}</h5><p>${esc(v)}</p></div>`).join("");
}

function viewRiwayat(){
  const fk = state.fRiwayat || { kelasId:"", mapel:"", bulan:"", semester:"" };
  let list = [...state.jurnal];
  if (fk.kelasId) list = list.filter(j => j.kelasId === fk.kelasId);
  if (fk.mapel) list = list.filter(j => j.mapel === fk.mapel);
  if (fk.bulan) list = list.filter(j => (j.tanggal||"").slice(0,7) === fk.bulan);
  if (fk.semester) list = list.filter(j => j.semester === fk.semester);
  list.sort((a,b) => (b.tanggal||"").localeCompare(a.tanggal||""));
  const t = totalPresensi(list);
  const bulanOpsi = [...new Set(state.jurnal.map(j => (j.tanggal||"").slice(0,7)).filter(Boolean))].sort().reverse();

  return `
  <div class="page-head">
    <div><h2>Riwayat jurnal</h2><p>${state.jurnal.length} catatan tersimpan. Gunakan saringan untuk menyiapkan laporan per kelas atau per bulan.</p></div>
    <div class="wrap-act">
      <button class="btn" data-act="cetak">${icon("print",17)} Cetak</button><button class="btn" data-act="pdf-jurnal">PDF</button><button class="btn" data-act="excel-jurnal">Excel</button>
      <button class="btn btn-primary" data-go="jurnal">${icon("plus",17)} Jurnal baru</button>
    </div>
  </div>

  <section class="sheet">
    <div class="sheet-bd" style="padding-bottom:16px">
      <div class="row">
        <div class="f"><label for="r_kelas">Kelas</label><select id="r_kelas" data-filter="kelasId">
          <option value="">Semua kelas</option>${state.kelas.map(k => `<option value="${k.id}" ${fk.kelasId===k.id?"selected":""}>${esc(k.nama)}</option>`).join("")}</select></div>
        <div class="f"><label for="r_mapel">Mata pelajaran</label><select id="r_mapel" data-filter="mapel">
          <option value="">Semua mapel</option>${[...new Set(state.jurnal.map(j => j.mapel).filter(Boolean))].sort().map(m => `<option ${fk.mapel===m?"selected":""}>${esc(m)}</option>`).join("")}</select></div>
        <div class="f"><label for="r_semester">Semester</label><select id="r_semester" data-filter="semester"><option value="">Semua semester</option><option value="Ganjil" ${fk.semester==="Ganjil"?"selected":""}>Ganjil</option><option value="Genap" ${fk.semester==="Genap"?"selected":""}>Genap</option></select></div>
        <div class="f"><label for="r_bulan">Bulan</label><select id="r_bulan" data-filter="bulan">
          <option value="">Semua bulan</option>${bulanOpsi.map(b => `<option value="${b}" ${fk.bulan===b?"selected":""}>${BLN_P[+b.slice(5,7)-1]} ${b.slice(0,4)}</option>`).join("")}</select></div>
      </div>
      ${list.length ? `<div class="pres-line" style="margin-top:14px">
        <span class="pill b-a">Hadir ${t.h}</span><span class="pill b-b">Izin ${t.i}</span>
        <span class="pill b-c">Sakit ${t.s}</span><span class="pill b-d">Alpa ${t.a}</span>
        <span class="pill" style="color:var(--ink-soft)">${list.length} pertemuan</span></div>` : ""}
    </div>
  </section>

  <section class="sheet" style="margin-top:18px">
    ${list.length ? list.map(j => entryHTML(j)).join("")
      : `<div class="empty">${icon("riwayat",40)}<h4>Tidak ada catatan yang cocok</h4>
         <p>Longgarkan saringan di atas, atau tulis jurnal baru untuk pertemuan hari ini.</p>
         <button class="btn btn-primary" data-go="jurnal">Tulis jurnal</button></div>`}
  </section>`;
}

/* ============ Tampilan: Nilai ============ */
function recNilai(kelasId, mapel){
  return state.nilai.find(n => n.kelasId === kelasId && n.mapel === mapel);
}
function viewNilai(){
  const sel = state.nilaiSel;
  if (!sel.kelasId && state.kelas.length) sel.kelasId = state.kelas[0].id;
  const k = kelasById(sel.kelasId);
  const mapelK = k ? (k.mapel || []) : [];
  if (!sel.mapel && mapelK.length) sel.mapel = mapelK[0];
  const rec = k && sel.mapel ? recNilai(k.id, sel.mapel) : null;
  const siswa = k ? (k.siswa || []) : [];

  const head = `
  <div class="page-head">
    <div><h2>Data nilai siswa</h2><p>Pilih kelas dan mata pelajaran, lalu isi nilai langsung di tabel. Rata-rata dihitung mengikuti bobot tiap penilaian.</p></div>
    <div class="wrap-act">
      ${rec ? `<button class="btn" data-act="tambah-penilaian">${icon("plus",17)} Kolom penilaian</button><button class="btn" data-act="preset-nilai">Paket NH/PH/Praktik/STS/PAS</button>` : ""}
      ${rec && Repo.dl ? `<button class="btn" data-act="unduh-nilai">${icon("unduh",17)} CSV</button><button class="btn" data-act="pdf-nilai">PDF</button><button class="btn" data-act="excel-nilai">Excel</button>` : ""}
    </div>
  </div>
  <section class="sheet">
    <div class="sheet-bd" style="padding-bottom:16px">
      <div class="row">
        <div class="f"><label for="n_kelas">Kelas</label><select id="n_kelas" data-nsel="kelasId">
          ${state.kelas.length ? state.kelas.map(x => `<option value="${x.id}" ${sel.kelasId===x.id?"selected":""}>${esc(x.nama)}</option>`).join("") : `<option value="">Belum ada kelas</option>`}
        </select></div>
        <div class="f"><label for="n_mapel">Mata pelajaran</label><select id="n_mapel" data-nsel="mapel">
          ${mapelK.length ? mapelK.map(m => `<option ${sel.mapel===m?"selected":""}>${esc(m)}</option>`).join("") : `<option value="">Belum ada mapel</option>`}
        </select></div>
      </div>
    </div>
  </section>`;

  if (!k || !siswa.length){
    return head + `<section class="sheet" style="margin-top:18px"><div class="empty">${icon("kelas",40)}
      <h4>Daftar siswa belum ada</h4><p>Nilai butuh daftar siswa. Tambahkan kelas dan nama siswanya lebih dulu.</p>
      <button class="btn btn-primary" data-go="kelas">Kelola kelas &amp; siswa</button></div></section>`;
  }
  if (!sel.mapel){
    return head + `<section class="sheet" style="margin-top:18px"><div class="empty">${icon("nilai",40)}
      <h4>Kelas ${esc(k.nama)} belum punya mata pelajaran</h4><p>Tambahkan mata pelajaran pada kelas ini, lalu kolom nilainya bisa disusun.</p>
      <button class="btn btn-primary" data-go="kelas">Tambah mata pelajaran</button></div></section>`;
  }
  if (!rec){
    return head + `<section class="sheet" style="margin-top:18px"><div class="empty">${icon("nilai",40)}
      <h4>Mulai penilaian ${esc(sel.mapel)} di ${esc(k.nama)}</h4>
      <p>Buat kolom pertama, misalnya “Ulangan Harian 1”, lalu isi nilai ${siswa.length} siswa di tabel.</p>
      <button class="btn btn-primary" data-act="tambah-penilaian">${icon("plus",17)} Buat kolom penilaian</button></div></section>`;
  }

  const pen = rec.penilaian || [];
  const rows = siswa.map((s, i) => {
    const r = rataNilai(rec, s.id); const [p, cls] = predikat(r);
    return `<tr>
      <td class="num">${i+1}</td>
      <td style="white-space:normal;min-width:150px">${esc(s.nama)}</td>
      <td class="muted">${esc(s.nis || "—")}</td>
      ${pen.map(pp => `<td class="num"><input class="cell-in" type="number" min="0" max="100" step="0.5"
        data-skor="${s.id}" data-pen="${pp.id}" value="${esc(((rec.skor||{})[s.id]||{})[pp.id] ?? "")}" aria-label="Nilai ${esc(s.nama)} ${esc(pp.nama)}"></td>`).join("")}
      <td class="num"><b>${r || "—"}</b></td>
      <td class="num"><span class="badge ${cls}">${p}</span></td>
    </tr>`;
  }).join("");

  const nilaiSemua = siswa.map(s => rataNilai(rec, s.id)).filter(v => v > 0);
  const rataKelas = nilaiSemua.length ? +(nilaiSemua.reduce((a,b) => a+b, 0)/nilaiSemua.length).toFixed(1) : 0;

  return head + `
  <section class="sheet" style="margin-top:18px">
    <div class="sheet-hd">
      <div><h3>${esc(sel.mapel)} — ${esc(k.nama)}</h3>
        <p>${siswa.length} siswa · ${pen.length} penilaian · rata-rata kelas ${rataKelas || "—"}</p></div>
      <div class="wrap-act">
        <button class="btn btn-sm" data-act="atur-kolom">Atur kolom</button>
        <button class="btn btn-sm btn-primary" data-act="simpan-nilai">${icon("check",16)} Simpan nilai</button>
      </div>
    </div>
    <div class="tbl-wrap">
      <table>
        <thead><tr>
          <th class="num" style="width:44px">No</th><th>Nama siswa</th><th>NIS</th>
          ${pen.map(p => `<th class="num">${esc(p.nama)}${num(p.bobot) && num(p.bobot) !== 1 ? `<br><span style="font-weight:500">bobot ${p.bobot}</span>` : ""}</th>`).join("")}
          <th class="num">Rata-rata</th><th class="num">Predikat</th>
        </tr></thead>
        <tbody>${rows}</tbody>
      </table>
    </div>
    <div class="sheet-bd" style="border-top:1px solid var(--line)"><div style="display:grid;grid-template-columns:repeat(5,1fr);gap:10px">${['NH','PH','Praktik','STS','PAS'].map(cat=>{const vals=siswa.map(s=>{const ps=(rec.penilaian||[]).filter(p=>String(p.nama).toUpperCase().startsWith(cat.toUpperCase()));const vv=ps.map(p=>num(((rec.skor||{})[s.id]||{})[p.id])).filter(v=>v>0);return vv.length?vv.reduce((a,b)=>a+b,0)/vv.length:0}).filter(v=>v>0);const av=vals.length?(vals.reduce((a,b)=>a+b,0)/vals.length).toFixed(1):'—';return `<div class="stat"><b>${av}</b><span>Rata-rata ${cat}</span></div>`}).join('')}</div></div>
    <div class="savebar">
      <span class="note">Perubahan tersimpan otomatis beberapa detik setelah Anda berhenti mengetik.</span>
      <button class="btn btn-primary" data-act="simpan-nilai">${icon("check",17)} Simpan nilai</button>
    </div>
  </section>`;
}

/* ============ Tampilan: Kelas & Siswa ============ */
function viewKelas(){
  return `
  <div class="page-head">
    <div><h2>Kelas &amp; siswa</h2><p>Daftar ini menjadi sumber pilihan kelas pada jurnal dan baris pada tabel nilai.</p></div>
    <button class="btn btn-primary" data-act="tambah-kelas">${icon("plus",17)} Tambah kelas</button>
  </div>
  ${state.kelas.length ? state.kelas.map(k => `
    <section class="sheet">
      <div class="sheet-hd">
        <div><h3>${esc(k.nama)}</h3><p>${(k.siswa||[]).length} siswa · ${(k.mapel||[]).length} mata pelajaran</p></div>
        <div class="wrap-act">
          <button class="btn btn-sm" data-act="tambah-siswa" data-id="${k.id}">${icon("plus",15)} Siswa</button>
          <button class="btn btn-sm" data-act="ubah-kelas" data-id="${k.id}">${icon("edit",15)} Ubah nama</button>
          <button class="btn btn-sm btn-danger" data-act="hapus-kelas" data-id="${k.id}">${icon("trash",15)}</button>
        </div>
      </div>
      <div class="sheet-bd">
        <label style="font-size:13px;font-weight:600;color:var(--ink-soft);display:block;margin-bottom:8px">Mata pelajaran yang Anda ampu di kelas ini</label>
        <div class="chips">
          ${(k.mapel||[]).map(m => `<span class="chip">${esc(m)}<button data-act="hapus-mapel" data-id="${k.id}" data-val="${esc(m)}" aria-label="Hapus ${esc(m)}">${icon("close",13)}</button></span>`).join("")}
          <button class="chip" style="cursor:pointer" data-act="tambah-mapel" data-id="${k.id}">${icon("plus",13)} Tambah</button>
        </div>
      </div>
      ${(k.siswa||[]).length ? `<div class="tbl-wrap"><table>
        <thead><tr><th class="num" style="width:44px">No</th><th>Nama siswa</th><th>NIS</th><th class="num" style="width:60px"></th></tr></thead>
        <tbody>${k.siswa.map((s,i) => `<tr>
          <td class="num">${i+1}</td><td style="white-space:normal">${esc(s.nama)}</td><td class="muted">${esc(s.nis||"—")}</td>
          <td class="num"><button class="btn btn-sm btn-ghost" data-act="hapus-siswa" data-id="${k.id}" data-val="${s.id}" aria-label="Hapus ${esc(s.nama)}">${icon("trash",15)}</button></td>
        </tr>`).join("")}</tbody></table></div>`
        : `<div class="empty" style="padding:28px 20px">${icon("kelas",34)}<h4>Belum ada siswa di ${esc(k.nama)}</h4>
           <p>Tempelkan daftar nama sekaligus — satu nama per baris.</p>
           <button class="btn btn-primary" data-act="tambah-siswa" data-id="${k.id}">Tambah siswa</button></div>`}
    </section>`).join("")
  : `<section class="sheet"><div class="empty">${icon("kelas",40)}<h4>Belum ada kelas</h4>
      <p>Mulai dengan satu kelas yang Anda ampu, misalnya “VIII A”. Anda bisa menambah yang lain kapan saja.</p>
      <button class="btn btn-primary" data-act="tambah-kelas">Tambah kelas pertama</button></div></section>`}`;
}

/* ============ Tampilan: Jadwal ============ */
function viewJadwal(){
  const perHari = HARI.slice(1,7);
  return `
  <div class="page-head">
    <div><h2>Jadwal mengajar</h2><p>Jadwal mingguan tetap. Dashboard menampilkan hari berjalan, dan formulir jurnal bisa mengambil isinya sekali klik.</p></div>
    <button class="btn btn-primary" data-act="tambah-jadwal">${icon("plus",17)} Tambah jam</button>
  </div>
  ${perHari.map(h => {
    const items = state.jadwal.filter(j => j.hari === h).sort((a,b) => num(a.jamKe) - num(b.jamKe));
    if (!items.length) return "";
    return `<section class="sheet">
      <div class="sheet-hd"><div><h3>${h}</h3><p>${items.length} jam pelajaran</p></div></div>
      <ul class="rail">${items.map(j => `<li>
        <div class="jam"><b>${esc(j.jamKe)}</b><span>jam ke-</span></div>
        <div class="isi"><b>${esc(j.mapel || "—")}</b><span>${esc(namaKelas(j.kelasId))}${j.mulai ? " · " + esc(j.mulai) + (j.selesai ? "–" + esc(j.selesai) : "") : ""}</span></div>
        <div class="aksi"><button class="btn btn-sm btn-ghost" data-act="hapus-jadwal" data-id="${j.id}">${icon("trash",15)}</button></div>
      </li>`).join("")}</ul>
    </section>`;
  }).join("")}
  ${state.jadwal.length ? "" : `<section class="sheet"><div class="empty">${icon("jadwal",40)}
    <h4>Jadwal masih kosong</h4><p>Masukkan jam mengajar Anda satu per satu. Cukup sekali di awal semester.</p>
    <button class="btn btn-primary" data-act="tambah-jadwal">Tambah jam pertama</button></div></section>`}`;
}

/* ============ Tampilan: Pengaturan ============ */
function viewSetelan(){
  return `
  <div class="page-head"><div><h2>Pengaturan</h2><p>Tampilan, cadangan data, dan penyimpanan.</p></div></div>

  <section class="sheet">
    <div class="sheet-hd"><div><h3>Identitas</h3><p>Sama dengan panel “Ubah header” di bagian atas halaman.</p></div>
      <button class="btn btn-sm" data-act="buka-editor">Ubah identitas</button></div>
    <div class="sheet-bd">
      <div class="row">
        <div><span class="muted">Nama guru</span><div style="font-weight:600">${esc(state.profile.guru || "—")}</div></div>
        <div><span class="muted">NIP / NUPTK</span><div style="font-weight:600">${esc(state.profile.nip || "—")}</div></div>
        <div><span class="muted">Sekolah</span><div style="font-weight:600">${esc(state.profile.sekolah || "—")}</div></div>
        <div><span class="muted">Tahun ajaran</span><div style="font-weight:600">${esc(state.profile.tahunAjaran || "—")} · ${esc(state.profile.semester || "—")}</div></div>
      </div>
    </div>
  </section>

  <section class="sheet">
    <div class="sheet-hd"><div><h3>Tampilan</h3><p>Mengikuti perangkat secara bawaan.</p></div></div>
    <div class="sheet-bd wrap-act">
      ${[["auto","Ikuti perangkat"],["light","Terang"],["dark","Gelap"]].map(([v,l]) =>
        `<button class="btn btn-sm ${(localStorage.getItem("tema")||"auto")===v ? "btn-primary" : ""}" data-act="tema" data-val="${v}">${l}</button>`).join("")}
    </div>
  </section>

  <section class="sheet">
    <div class="sheet-hd"><div><h3>Cadangan data</h3>
      <p>${Repo.ok ? "Data tersimpan di akun Anda dan hanya Anda yang bisa membukanya." : "Data tersimpan di peramban perangkat ini. Unduh cadangan secara berkala."}</p></div></div>
    <div class="sheet-bd wrap-act">
      <button class="btn" data-act="ekspor">${icon("unduh",17)} Unduh cadangan (JSON)</button>
      <button class="btn" data-act="impor">Pulihkan dari cadangan</button>
      <input type="file" id="imporFile" accept="application/json,.json" hidden>
      <button class="btn btn-danger right" data-act="reset">Hapus semua data</button>
    </div>
  </section>

  <section class="sheet">
    <div class="sheet-hd"><div><h3>Isi cepat</h3><p>Membuat dua kelas contoh beserta jadwal agar Anda bisa mencoba alurnya.</p></div></div>
    <div class="sheet-bd"><button class="btn" data-act="contoh">Muat data contoh</button></div>
  </section>`;
}

/* ============ Tampilan: Dokumen Drive ============ */
function viewDokumen(){return `<div class="page-head"><div><h2>Dokumen Google Drive</h2><p>Unggah dokumen pendukung pembelajaran ke folder Drive aplikasi.</p></div><button class="btn btn-primary" data-act="refresh-dokumen">Refresh</button></div><section class="sheet"><div class="sheet-bd"><div class="doc-drop"><input type="file" id="docFile" hidden><button class="btn btn-primary" data-act="pilih-dokumen">${icon("plus",17)} Pilih & Upload Dokumen</button><p style="margin-top:8px;color:var(--ink-soft);font-size:12px">Maksimal 25 MB per file.</p></div></div></section><section class="sheet" style="margin-top:18px"><div class="sheet-hd"><div><h3>Dokumen tersimpan</h3><p id="docStatus">Memuat...</p></div></div><div class="tbl-wrap"><table><thead><tr><th>Nama</th><th>Ukuran</th><th>Diperbarui</th><th>Aksi</th></tr></thead><tbody id="docBody"><tr><td colspan="4">Memuat...</td></tr></tbody></table></div></section>`}
async function loadDocuments(){if(!Repo.ok)return;const r=await gas("listDocuments",localStorage.getItem("jg_token"));const b=$("#docBody");if(!b)return;if(!r.ok){b.innerHTML=`<tr><td colspan="4">${esc(r.message)}</td></tr>`;return;}b.innerHTML=r.files.length?r.files.map(f=>`<tr><td style="white-space:normal"><a href="${esc(f.url)}" target="_blank">${esc(f.name)}</a></td><td>${Math.round((f.size||0)/1024)} KB</td><td>${new Date(f.updated).toLocaleString("id-ID")}</td><td>${state.auth?.role==='Admin'?`<button class="btn btn-sm btn-danger" data-act="hapus-dokumen" data-id="${f.id}">${icon("trash",14)}</button>`:`<a class="btn btn-sm" href="${esc(f.url)}" target="_blank">Buka</a>`}</td></tr>`).join(""):`<tr><td colspan="4">Belum ada dokumen.</td></tr>`;$("#docStatus").textContent=`${r.files.length} dokumen`}
/* ============ Perutean ============ */
const VIEWS = { dashboard:viewDashboard, jurnal:viewJurnal, riwayat:viewRiwayat, nilai:viewNilai, kelas:viewKelas, jadwal:viewJadwal, setelan:viewSetelan,dokumen:viewDokumen };
function render(){
  $("#view").innerHTML = (VIEWS[state.view] || viewDashboard)();
  renderNav(); renderHeader(); if(state.view==="dokumen"&&state.auth)setTimeout(loadDocuments,50);
  if (state.view === "jurnal"){
    hitungPresensi();
    ["#p_h","#p_i","#p_s","#p_a","#j_kelas"].forEach(s => { const e = $(s); if (e) e.addEventListener("input", hitungPresensi); });
    const t = $("#j_tanggal"); if (t) t.addEventListener("change", () => { $("#j_hari").value = hariDari(t.value); });
  }
  window.scrollTo({ top:0, behavior:"instant" in window ? "instant" : "auto" });
}
function go(v){
  state.view = v;
  if (v !== "jurnal") state.draft = null;
  history.replaceState(null, "", "#" + v);
  document.body.classList.remove("drawer");
  render();
}

/* ============ Modal ============ */
function modal({ title, body, ok="Simpan", onOk }){
  const box = $("#modalBox");
  box.innerHTML = `<div class="modal-hd">${title}</div><div class="modal-bd">${body}</div>
    <div class="modal-ft"><button class="btn" data-act="tutup-modal">Batal</button>
    <button class="btn btn-primary" id="modalOk">${ok}</button></div>`;
  $("#modal").classList.add("on");
  const first = box.querySelector("input,select,textarea"); if (first) setTimeout(() => first.focus(), 40);
  $("#modalOk").onclick = async () => {
    const r = await withSave($("#modalOk"), async () => await onOk(box));
    if (r !== false) setTimeout(closeModal, 380);
  };
  box.onkeydown = (e) => { if (e.key === "Enter" && e.target.tagName !== "TEXTAREA") { e.preventDefault(); $("#modalOk").click(); } };
}
function closeModal(){ $("#modal").classList.remove("on"); $("#modalBox").innerHTML = ""; }

/* ============ Aksi ============ */
const ACT = {
  async "save-header"(){
    const p = state.profile;
    p.judul = $("#e_judul").value.trim() || "Jurnal Mengajar";
    p.guru = $("#e_guru").value.trim(); p.nip = $("#e_nip").value.trim();
    p.sekolah = $("#e_sekolah").value.trim(); p.tahunAjaran = $("#e_ta").value.trim(); p.semester = $("#e_sem").value;
    await saveProfile(); renderHeader(); toggleEditor(false); toast("Header diperbarui");
  },
  "close-editor"(){ toggleEditor(false); },
  "buka-editor"(){ toggleEditor(true); window.scrollTo({top:0}); },
  "pick-logo"(){ $("#logoFile").click(); },
  async "drop-logo"(){ state.profile.logo = ""; await saveProfile(); renderHeader(); toggleEditor(true); },

  async "simpan-jurnal"(el){
    const d = bacaForm();
    if (!d.mapel && !d.materi){ toast("Isi minimal mata pelajaran atau materi.", true); $("#j_mapel").focus(); return; }
    await withSave(el, async () => {
      const i = state.jurnal.findIndex(j => j.id === d.id);
      if (i >= 0) state.jurnal[i] = d; else state.jurnal.push(d);
      await putDoc("jurnal", d);
      state.draft = null;
    }, "Jurnal tersimpan");
    setTimeout(() => go("riwayat"), 900);
  },
  "reset-form"(){ state.draft = null; render(); },
  "batal-edit"(){ state.draft = null; render(); },
  "edit-jurnal"(el){ state.draft = el.dataset.id; go("jurnal"); },
  async "hapus-jurnal"(el){
    const j = state.jurnal.find(x => x.id === el.dataset.id);
    if (!confirm(`Hapus jurnal ${tglPanjang(j.tanggal)} — ${j.mapel || "tanpa mapel"}?`)) return;
    state.jurnal = state.jurnal.filter(x => x.id !== j.id);
    await delDoc("jurnal", j.id); render(); toast("Jurnal dihapus");
  },
  "buka"(el){
    const art = el.closest(".entry"); const det = art.querySelector(".detail");
    const j = state.jurnal.find(x => x.id === el.dataset.id);
    if (det.hidden){ det.innerHTML = detailHTML(j); det.hidden = false; el.textContent = "Tutup"; }
    else { det.hidden = true; el.textContent = "Rincian"; }
  },
  "cetak"(){ window.print(); },
  "prefill"(){
    const hariIni = HARI[new Date().getDay()];
    const opsi = state.jadwal.filter(j => j.hari === hariIni).sort((a,b)=>num(a.jamKe)-num(b.jamKe));
    const daftar = opsi.length ? opsi : state.jadwal;
    modal({
      title: "Ambil dari jadwal",
      body: `<div class="f"><label for="pf">Pilih jam pelajaran</label><select id="pf">
        ${daftar.map(j => `<option value="${j.id}">${esc(j.hari)} · jam ke-${esc(j.jamKe)} · ${esc(j.mapel)} (${esc(namaKelas(j.kelasId))})</option>`).join("")}
      </select></div>`,
      ok: "Terapkan",
      onOk: (box) => {
        const j = state.jadwal.find(x => x.id === box.querySelector("#pf").value);
        if (!j) return false;
        $("#j_mapel").value = j.mapel || ""; $("#j_kelas").value = j.kelasId || ""; $("#j_jam").value = j.jamKe || "";
        const k = kelasById(j.kelasId); if (k && !num($("#p_h").value)) $("#p_h").value = (k.siswa||[]).length || "";
        hitungPresensi(); toast("Formulir terisi dari jadwal");
      }
    });
  },
  "isi-jadwal"(el){
    const j = state.jadwal.find(x => x.id === el.dataset.id); if (!j) return;
    state.draft = null; go("jurnal");
    setTimeout(() => {
      $("#j_mapel").value = j.mapel || ""; $("#j_kelas").value = j.kelasId || ""; $("#j_jam").value = j.jamKe || "";
      const k = kelasById(j.kelasId); if (k) $("#p_h").value = (k.siswa||[]).length || "";
      hitungPresensi(); $("#j_tp").focus();
    }, 60);
  },

  /* Kelas */
  "tambah-kelas"(){
    modal({ title:"Kelas baru",
      body:`<div class="f"><label for="k_nama">Nama kelas</label><input id="k_nama" placeholder="VIII A"></div>
            <div class="f"><label for="k_mapel">Mata pelajaran (pisahkan dengan koma)</label><input id="k_mapel" placeholder="Matematika, Informatika"></div>`,
      ok:"Tambah kelas",
      onOk: async (box) => {
        const nama = box.querySelector("#k_nama").value.trim();
        if (!nama){ toast("Nama kelas belum diisi.", true); return false; }
        const k = { id:uid(), nama, mapel: box.querySelector("#k_mapel").value.split(",").map(s=>s.trim()).filter(Boolean), siswa:[] };
        state.kelas.push(k); await putDoc("kelas", k); render(); toast("Kelas " + nama + " ditambahkan");
      }});
  },
  "ubah-kelas"(el){
    const k = kelasById(el.dataset.id);
    modal({ title:"Ubah nama kelas", body:`<div class="f"><label for="k_nama2">Nama kelas</label><input id="k_nama2" value="${esc(k.nama)}"></div>`,
      onOk: async (box) => {
        const v = box.querySelector("#k_nama2").value.trim(); if (!v) return false;
        k.nama = v; await putDoc("kelas", k); render();
      }});
  },
  async "hapus-kelas"(el){
    const k = kelasById(el.dataset.id);
    if (!confirm(`Hapus kelas ${k.nama} beserta ${(k.siswa||[]).length} siswa dan nilainya? Jurnal yang sudah ditulis tetap tersimpan.`)) return;
    state.kelas = state.kelas.filter(x => x.id !== k.id);
    const hapusNilai = state.nilai.filter(n => n.kelasId === k.id);
    state.nilai = state.nilai.filter(n => n.kelasId !== k.id);
    state.jadwal = state.jadwal.filter(j => j.kelasId !== k.id);
    await delDoc("kelas", k.id);
    for (const n of hapusNilai) await delDoc("nilai", n.id);
    await saveJadwal(); render(); toast("Kelas dihapus");
  },
  "tambah-mapel"(el){
    const k = kelasById(el.dataset.id);
    modal({ title:"Mata pelajaran di " + k.nama,
      body:`<div class="f"><label for="m_nama">Nama mata pelajaran</label><input id="m_nama" placeholder="Matematika"></div>`,
      ok:"Tambah",
      onOk: async (box) => {
        const v = box.querySelector("#m_nama").value.trim(); if (!v) return false;
        k.mapel = k.mapel || []; if (!k.mapel.includes(v)) k.mapel.push(v);
        await putDoc("kelas", k); render();
      }});
  },
  async "hapus-mapel"(el){
    const k = kelasById(el.dataset.id);
    k.mapel = (k.mapel||[]).filter(m => m !== el.dataset.val);
    await putDoc("kelas", k); render();
  },
  "tambah-siswa"(el){
    const k = kelasById(el.dataset.id);
    modal({ title:"Tambah siswa ke " + k.nama,
      body:`<div class="f"><label for="s_list">Daftar nama</label>
        <textarea id="s_list" style="min-height:140px" placeholder="Satu nama per baris:
Ahmad Fauzi
Bunga Lestari, 2024001
Citra Dewi"></textarea>
        <span class="hint">Tambahkan NIS setelah koma bila ada.</span></div>`,
      ok:"Tambah",
      onOk: async (box) => {
        const baris = box.querySelector("#s_list").value.split("\n").map(s => s.trim()).filter(Boolean);
        if (!baris.length) return false;
        k.siswa = k.siswa || [];
        baris.forEach(b => { const [nama, nis] = b.split(",").map(s => (s||"").trim()); if (nama) k.siswa.push({ id:uid(), nama, nis: nis || "" }); });
        await putDoc("kelas", k); render(); toast(baris.length + " siswa ditambahkan");
      }});
  },
  async "hapus-siswa"(el){
    const k = kelasById(el.dataset.id);
    k.siswa = (k.siswa||[]).filter(s => s.id !== el.dataset.val);
    await putDoc("kelas", k); render();
  },

  /* Nilai */
  "tambah-penilaian"(){
    const sel = state.nilaiSel;
    if (!sel.kelasId || !sel.mapel){ toast("Pilih kelas dan mata pelajaran dulu.", true); return; }
    modal({ title:"Kolom penilaian baru",
      body:`<div class="f"><label for="pn_nama">Nama penilaian</label><input id="pn_nama" placeholder="Ulangan Harian 1"></div>
            <div class="f"><label for="pn_bobot">Bobot</label><input id="pn_bobot" type="number" min="0.5" step="0.5" value="1">
            <span class="hint">Bobot 2 berarti penilaian ini dihitung dua kali lipat pada rata-rata.</span></div>`,
      ok:"Tambah kolom",
      onOk: async (box) => {
        const nama = box.querySelector("#pn_nama").value.trim(); if (!nama) return false;
        let rec = recNilai(sel.kelasId, sel.mapel);
        if (!rec){ rec = { id:uid(), kelasId:sel.kelasId, mapel:sel.mapel, penilaian:[], skor:{} }; state.nilai.push(rec); }
        rec.penilaian.push({ id:uid(), nama, bobot: num(box.querySelector("#pn_bobot").value) || 1 });
        await putDoc("nilai", rec); render();
      }});
  },
  async "preset-nilai"(){const sel=state.nilaiSel;if(!sel.kelasId||!sel.mapel){toast('Pilih kelas dan mata pelajaran dulu.',true);return}let rec=recNilai(sel.kelasId,sel.mapel);if(!rec){rec={id:uid(),kelasId:sel.kelasId,mapel:sel.mapel,penilaian:[],skor:{}};state.nilai.push(rec)}const add=(nama)=>{if(!rec.penilaian.some(p=>p.nama.toLowerCase()===nama.toLowerCase()))rec.penilaian.push({id:uid(),nama,bobot:1})};for(let i=1;i<=10;i++)add('NH '+i);for(let i=1;i<=5;i++)add('PH '+i);for(let i=1;i<=2;i++)add('Praktik '+i);add('STS');add('PAS');await putDoc('nilai',rec);render();toast('Paket penilaian standar dibuat')},
  "atur-kolom"(){
    const rec = recNilai(state.nilaiSel.kelasId, state.nilaiSel.mapel); if (!rec) return;
    modal({ title:"Kolom penilaian", ok:"Selesai",
      body: rec.penilaian.length ? rec.penilaian.map(p => `
        <div style="display:flex;gap:9px;align-items:flex-end">
          <div class="f" style="flex:1"><label>Nama</label><input data-pn="${p.id}" value="${esc(p.nama)}"></div>
          <div class="f" style="width:84px"><label>Bobot</label><input type="number" min="0.5" step="0.5" data-pb="${p.id}" value="${esc(p.bobot)}"></div>
          <button class="btn btn-sm btn-danger" data-act="hapus-kolom" data-id="${p.id}" style="margin-bottom:1px">${icon("trash",15)}</button>
        </div>`).join("") : `<p class="muted">Belum ada kolom penilaian.</p>`,
      onOk: async (box) => {
        box.querySelectorAll("[data-pn]").forEach(i => { const p = rec.penilaian.find(x => x.id === i.dataset.pn); if (p) p.nama = i.value.trim() || p.nama; });
        box.querySelectorAll("[data-pb]").forEach(i => { const p = rec.penilaian.find(x => x.id === i.dataset.pb); if (p) p.bobot = num(i.value) || 1; });
        await putDoc("nilai", rec); render();
      }});
  },
  async "hapus-kolom"(el){
    const rec = recNilai(state.nilaiSel.kelasId, state.nilaiSel.mapel); if (!rec) return;
    if (!confirm("Hapus kolom penilaian ini beserta seluruh nilainya?")) return;
    rec.penilaian = rec.penilaian.filter(p => p.id !== el.dataset.id);
    Object.values(rec.skor || {}).forEach(s => delete s[el.dataset.id]);
    await putDoc("nilai", rec); closeModal(); render();
  },
  async "simpan-nilai"(el){
    const rec = recNilai(state.nilaiSel.kelasId, state.nilaiSel.mapel); if (!rec) return;
    await withSave(el, async () => { await putDoc("nilai", rec); }, "Nilai tersimpan");
    const b = $("#view tbody"); if (b) setTimeout(render, 900);
  },
  async "unduh-nilai"(){
    const rec = recNilai(state.nilaiSel.kelasId, state.nilaiSel.mapel);
    const k = kelasById(state.nilaiSel.kelasId); if (!rec || !k) return;
    const head = ["No","Nama","NIS", ...rec.penilaian.map(p => p.nama), "Rata-rata","Predikat"];
    const rows = (k.siswa||[]).map((s,i) => {
      const r = rataNilai(rec, s.id);
      return [i+1, s.nama, s.nis||"", ...rec.penilaian.map(p => ((rec.skor||{})[s.id]||{})[p.id] ?? ""), r || "", predikat(r)[0]];
    });
    const csv = [head, ...rows].map(r => r.map(c => `"${String(c).replace(/"/g,'""')}"`).join(",")).join("\n");
    await unduh(`Nilai ${k.nama} ${rec.mapel}.csv`, "\uFEFF" + csv);
  },

  async "pdf-jurnal"(){const rows=state.jurnal.map(j=>`<tr><td>${esc(j.tanggal)}</td><td>${esc(namaKelas(j.kelasId))}</td><td>${esc(j.mapel)}</td><td>${esc(j.materi)}</td><td>${num(j.hadir)}</td><td>${num(j.izin)}</td><td>${num(j.sakit)}</td><td>${num(j.alpa)}</td></tr>`).join("");const body=`<table><tr><th>Tanggal</th><th>Kelas</th><th>Mapel</th><th>Materi</th><th>H</th><th>I</th><th>S</th><th>A</th></tr>${rows}</table>`;const r=await gas("exportReportPDF",localStorage.getItem("jg_token"),{title:"Laporan Jurnal Mengajar",meta:`${state.profile.guru||""} · ${state.profile.sekolah||""}`,bodyHtml:body});if(r.ok)window.open(r.url,"_blank");else toast(r.message,true);},
  async "excel-jurnal"(){const rows=[["Tanggal","Kelas","Mapel","Materi","Hadir","Izin","Sakit","Alpa"],...state.jurnal.map(j=>[j.tanggal,namaKelas(j.kelasId),j.mapel,j.materi,num(j.hadir),num(j.izin),num(j.sakit),num(j.alpa)])];const r=await gas("exportReportExcel",localStorage.getItem("jg_token"),{title:"Laporan Jurnal Mengajar",rows});if(r.ok)window.open(r.url,"_blank");else toast(r.message,true);},
  async "pdf-nilai"(){const rec=recNilai(state.nilaiSel.kelasId,state.nilaiSel.mapel),k=kelasById(state.nilaiSel.kelasId);if(!rec||!k)return;const rows=(k.siswa||[]).map(s=>`<tr><td>${esc(s.nama)}</td><td>${esc(s.nis||"")}</td>${rec.penilaian.map(p=>`<td>${esc(((rec.skor||{})[s.id]||{})[p.id]??"")}</td>`).join("")}<td>${rataNilai(rec,s.id)||""}</td></tr>`).join("");const body=`<table><tr><th>Nama</th><th>NIS</th>${rec.penilaian.map(p=>`<th>${esc(p.nama)}</th>`).join("")}<th>Rata-rata</th></tr>${rows}</table>`;const r=await gas("exportReportPDF",localStorage.getItem("jg_token"),{title:`Nilai ${k.nama} - ${rec.mapel}`,meta:`${state.profile.guru||""} · ${state.profile.sekolah||""}`,bodyHtml:body});if(r.ok)window.open(r.url,"_blank");else toast(r.message,true);},
  async "excel-nilai"(){const rec=recNilai(state.nilaiSel.kelasId,state.nilaiSel.mapel),k=kelasById(state.nilaiSel.kelasId);if(!rec||!k)return;const rows=[["Nama","NIS",...rec.penilaian.map(p=>p.nama),"Rata-rata","Predikat"],...(k.siswa||[]).map(s=>[s.nama,s.nis||"",...rec.penilaian.map(p=>((rec.skor||{})[s.id]||{})[p.id]??""),rataNilai(rec,s.id)||"",predikat(rataNilai(rec,s.id))[0]])];const r=await gas("exportReportExcel",localStorage.getItem("jg_token"),{title:`Nilai ${k.nama} - ${rec.mapel}`,rows});if(r.ok)window.open(r.url,"_blank");else toast(r.message,true);},
  /* Jadwal */
  "tambah-jadwal"(){
    if (!state.kelas.length){ toast("Tambahkan kelas terlebih dahulu.", true); go("kelas"); return; }
    modal({ title:"Tambah jam mengajar",
      body:`<div class="f"><label for="jd_hari">Hari</label><select id="jd_hari">${HARI.slice(1,7).map(h => `<option ${h===HARI[new Date().getDay()]?"selected":""}>${h}</option>`).join("")}</select></div>
        <div class="f"><label for="jd_jam">Jam pelajaran ke-</label><input id="jd_jam" placeholder="1–2"></div>
        <div class="f"><label for="jd_kelas">Kelas</label><select id="jd_kelas">${state.kelas.map(k => `<option value="${k.id}">${esc(k.nama)}</option>`).join("")}</select></div>
        <div class="f"><label for="jd_mapel">Mata pelajaran</label><input id="jd_mapel" list="dlMapel2" placeholder="Matematika">
          <datalist id="dlMapel2">${allMapel().map(m => `<option value="${esc(m)}">`).join("")}</datalist></div>
        <div class="row"><div class="f"><label for="jd_mulai">Mulai</label><input type="time" id="jd_mulai"></div>
        <div class="f"><label for="jd_selesai">Selesai</label><input type="time" id="jd_selesai"></div></div>`,
      ok:"Tambah",
      onOk: async (box) => {
        const jamKe = box.querySelector("#jd_jam").value.trim(); if (!jamKe){ toast("Isi jam pelajaran ke-.", true); return false; }
        state.jadwal.push({ id:uid(), hari: box.querySelector("#jd_hari").value, jamKe,
          kelasId: box.querySelector("#jd_kelas").value, mapel: box.querySelector("#jd_mapel").value.trim(),
          mulai: box.querySelector("#jd_mulai").value, selesai: box.querySelector("#jd_selesai").value });
        await saveJadwal(); render();
      }});
  },
  async "hapus-jadwal"(el){
    state.jadwal = state.jadwal.filter(j => j.id !== el.dataset.id);
    await saveJadwal(); render();
  },

  "pilih-dokumen"(){$("#docFile").click();},
  async "refresh-dokumen"(){await loadDocuments();},
  async "hapus-dokumen"(el){if(state.auth?.role!=="Admin")return;if(!confirm("Hapus dokumen ini dari Drive?"))return;const r=await gas("deleteDocument",localStorage.getItem("jg_token"),el.dataset.id);if(!r.ok)toast(r.message,true);else{toast("Dokumen dihapus");loadDocuments();}},
  /* Pengaturan */
  "tema"(el){
    const v = el.dataset.val;
    localStorage.setItem("tema", v);
    if (v === "auto") document.documentElement.removeAttribute("data-theme");
    else document.documentElement.setAttribute("data-theme", v);
    render();
  },
  async "ekspor"(){
    const data = JSON.stringify({ versi:1, diekspor:new Date().toISOString(), profile:state.profile,
      kelas:state.kelas, jurnal:state.jurnal, nilai:state.nilai, jadwal:state.jadwal }, null, 2);
    await unduh(`Cadangan jurnal ${iso(new Date())}.json`, data);
  },
  "impor"(){ $("#imporFile").click(); },
  async "reset"(){
    if (!confirm("Hapus seluruh kelas, siswa, jurnal, nilai, dan jadwal? Tindakan ini tidak bisa dibatalkan.")) return;
    for (const j of state.jurnal) await delDoc("jurnal", j.id);
    for (const k of state.kelas) await delDoc("kelas", k.id);
    for (const n of state.nilai) await delDoc("nilai", n.id);
    state.jurnal = []; state.kelas = []; state.nilai = []; state.jadwal = [];
    await saveJadwal(); saveLocal(); render(); toast("Semua data dihapus");
  },
  async "contoh"(){
    if (state.kelas.length && !confirm("Data contoh akan ditambahkan di samping data yang ada. Lanjutkan?")) return;
    const nama8 = ["Ahmad Fauzi","Bunga Lestari","Citra Dewi","Dimas Prakoso","Elang Saputra","Fitri Handayani","Gilang Ramadhan","Hana Safitri"];
    const nama9 = ["Indra Wijaya","Julia Rahmawati","Krisna Adi","Laila Nurhaliza","Maulana Yusuf","Nadia Puspita"];
    const a = { id:uid(), nama:"VIII A", mapel:["Matematika","Informatika"], siswa:nama8.map((n,i) => ({id:uid(), nama:n, nis:"2024"+String(i+1).padStart(3,"0")})) };
    const b = { id:uid(), nama:"IX B", mapel:["Matematika"], siswa:nama9.map((n,i) => ({id:uid(), nama:n, nis:"2023"+String(i+1).padStart(3,"0")})) };
    state.kelas.push(a, b); await putDoc("kelas", a); await putDoc("kelas", b);
    state.jadwal.push(
      { id:uid(), hari:"Senin", jamKe:"1–2", kelasId:a.id, mapel:"Matematika", mulai:"07:15", selesai:"08:35" },
      { id:uid(), hari:"Senin", jamKe:"5–6", kelasId:b.id, mapel:"Matematika", mulai:"10:00", selesai:"11:20" },
      { id:uid(), hari:"Rabu",  jamKe:"3–4", kelasId:a.id, mapel:"Informatika", mulai:"08:35", selesai:"09:55" }
    );
    await saveJadwal();
    const hari = new Date(); hari.setDate(hari.getDate()-2);
    const j = { id:uid(), tanggal: iso(hari), hari: HARI[hari.getDay()], sekolah: state.profile.sekolah || "SMP Negeri 1 Bengkulu",
      mapel:"Matematika", kelasId:a.id, semester: state.profile.semester, jamKe:"1–2",
      tp:"Peserta didik mampu menyusun dan menyelesaikan sistem persamaan linear dua variabel dari masalah kontekstual.",
      materi:"SPLDV — metode substitusi dan eliminasi.",
      pendahuluan:"Salam dan doa, mengecek kehadiran, apersepsi lewat soal harga dua jenis jajanan di kantin.",
      inti:"Siswa bekerja berpasangan menyelesaikan tiga masalah kontekstual, lalu dua kelompok mempresentasikan hasil di papan.",
      penutup:"Menyimpulkan perbedaan kedua metode, refleksi singkat, dan pemberian PR tiga soal.",
      hadir:7, izin:0, sakit:1, alpa:0,
      kendala:"Waktu berkurang 10 menit karena pergantian ruang.",
      respons:"Antusias pada soal kontekstual, masih ragu menentukan variabel.",
      tugas:"PR LKS halaman 42 nomor 1–3, dikumpulkan pertemuan berikutnya.",
      rencana:"Memberi satu contoh pemodelan variabel sebelum latihan mandiri.", dibuat:new Date().toISOString() };
    state.jurnal.push(j); await putDoc("jurnal", j);
    render(); toast("Data contoh dimuat");
  },
  "tutup-modal"(){ closeModal(); }
};

async function unduh(nama, isi){
  if (Repo.dl){
    try { await Repo.dl.save({ filename:nama, data:isi }); toast("Berkas disiapkan"); return; }
    catch(e){ /* pengguna menolak atau gagal */ }
  }
  try{
    const url = URL.createObjectURL(new Blob([isi], {type:"text/plain;charset=utf-8"}));
    const a = document.createElement("a"); a.href = url; a.download = nama; a.click();
    setTimeout(() => URL.revokeObjectURL(url), 2000);
  }catch(e){ toast("Unduhan tidak tersedia di tampilan ini.", true); }
}

/* ============ Pendengar peristiwa ============ */
document.addEventListener("click", (e) => {
  const go_ = e.target.closest("[data-go]");
  if (go_){ e.preventDefault(); go(go_.dataset.go); return; }
  const a = e.target.closest("[data-act]");
  if (a && ACT[a.dataset.act]){ e.preventDefault(); ACT[a.dataset.act](a); return; }
  if (e.target.id === "modal") closeModal();
});
document.addEventListener("keydown", (e) => { if (e.key === "Escape"){ closeModal(); if (document.body.classList.contains("drawer")) document.body.classList.remove("drawer"); } });

$("#burger").onclick = () => document.body.classList.toggle("drawer");
$("#scrim").onclick = () => document.body.classList.remove("drawer");
$("#editHeadBtn").onclick = () => toggleEditor();
$("#collapseBtn").onclick = () => {
  document.body.classList.toggle("collapsed");
  localStorage.setItem("sbCollapsed", document.body.classList.contains("collapsed") ? "1" : "0");
  $("#collapseBtn").querySelector("span").textContent = document.body.classList.contains("collapsed") ? "Bentangkan" : "Ciutkan menu";
};

/* saringan riwayat & pilihan nilai */
document.addEventListener("change", async (e) => {
  const f = e.target.closest("[data-filter]");
  if (f){ state.fRiwayat = state.fRiwayat || {}; state.fRiwayat[f.dataset.filter] = f.value; render(); return; }
  const n = e.target.closest("[data-nsel]");
  if (n){
    state.nilaiSel[n.dataset.nsel] = n.value;
    if (n.dataset.nsel === "kelasId") state.nilaiSel.mapel = "";
    render(); return;
  }
  if (e.target.id === "logoFile" && e.target.files[0]){
    resizeImg(e.target.files[0], async (d) => { state.profile.logo = d; await saveProfile(); renderHeader(); toggleEditor(true); toast("Logo diperbarui"); });
  }
  if (e.target.id === "imporFile" && e.target.files[0]){
    const rd = new FileReader();
    rd.onload = async () => {
      try{
        const d = JSON.parse(rd.result);
        if (!confirm("Ganti seluruh data saat ini dengan isi cadangan?")) return;
        Object.assign(state.profile, d.profile || {});
        state.kelas = d.kelas || []; state.jurnal = d.jurnal || []; state.nilai = d.nilai || []; state.jadwal = d.jadwal || [];
        await saveProfile(); await saveJadwal();
        for (const k of state.kelas) await putDoc("kelas", k);
        for (const j of state.jurnal) await putDoc("jurnal", j);
        for (const n2 of state.nilai) await putDoc("nilai", n2);
        render(); toast("Cadangan dipulihkan");
      }catch(err){ toast("Berkas cadangan tidak terbaca.", true); }
    };
    rd.readAsText(e.target.files[0]);
  }
});

/* input nilai: simpan otomatis */
let tSave;
document.addEventListener("input", (e) => {
  const c = e.target.closest("[data-skor]");
  if (!c) return;
  const rec = recNilai(state.nilaiSel.kelasId, state.nilaiSel.mapel); if (!rec) return;
  rec.skor = rec.skor || {};
  rec.skor[c.dataset.skor] = rec.skor[c.dataset.skor] || {};
  let v = c.value === "" ? "" : Math.max(0, Math.min(100, num(c.value)));
  rec.skor[c.dataset.skor][c.dataset.pen] = v;
  clearTimeout(tSave);
  tSave = setTimeout(async () => { await putDoc("nilai", rec); toast("Nilai tersimpan otomatis"); }, 1400);
});

window.addEventListener("hashchange", () => {
  const v = location.hash.slice(1);
  if (VIEWS[v] && v !== state.view){ state.view = v; render(); }
});

async function doLogin(){const b=$("#loginBtn"),e=$("#loginError");b.disabled=true;b.textContent="Memeriksa...";e.textContent="";try{const u=$("#loginUser").value.trim(),p=$("#loginPass").value;if(!u||!p){e.textContent="Username dan password wajib diisi.";return;}const r=await gas("loginUser",u,p);if(!r||!r.ok){e.textContent=(r&&r.message)||"Login gagal.";return;}state.auth=r.user;localStorage.setItem("jg_token",r.token);$("#rolePill").textContent=r.user.role+" · "+r.user.name;try{render();$("#loginGate").style.display="none";toast("Selamat datang, "+r.user.name)}catch(renderErr){console.error(renderErr);state.auth=null;localStorage.removeItem("jg_token");throw new Error("Login berhasil, tetapi halaman utama gagal ditampilkan: "+(renderErr.message||renderErr));}}catch(x){console.error(x);e.textContent=x.message||"Koneksi gagal. Silakan muat ulang halaman."}finally{b.disabled=false;b.textContent="Masuk"}}
async function startLogin(){if(!Repo.ok){$("#loginGate").style.display="grid";return}const t=localStorage.getItem("jg_token");if(t){try{const r=await gas("validateSession",t);if(r.ok){state.auth=r.user;$("#loginGate").style.display="none";$("#rolePill").textContent=r.user.role+" · "+r.user.name;return}}catch(e){}}$("#loginGate").style.display="grid"}
$("#logoutBtn").onclick=async()=>{const t=localStorage.getItem("jg_token");if(t&&Repo.ok)await gas("logoutUser",t);localStorage.removeItem("jg_token");state.auth=null;$("#loginGate").style.display="grid"};
document.addEventListener("change",async e=>{if(e.target.id==="docFile"&&e.target.files[0]){const f=e.target.files[0];if(f.size>25*1024*1024){toast("File terlalu besar (maks. 25 MB).",true);return}const rd=new FileReader();rd.onload=async()=>{try{const r=await gas("uploadDocument",localStorage.getItem("jg_token"),{fileName:f.name,mimeType:f.type||"application/octet-stream",fileData:String(rd.result).split(",")[1]});if(!r.ok)throw new Error(r.message);toast("Dokumen berhasil diunggah");loadDocuments()}catch(x){toast(x.message,true)}};rd.readAsDataURL(f)}});
/* ============ Mulai ============ */
(function initTema(){
  const t = localStorage.getItem("tema");
  if (t && t !== "auto") document.documentElement.setAttribute("data-theme", t);
  if (localStorage.getItem("sbCollapsed") === "1") document.body.classList.add("collapsed");
})();

(async function start(){loadLocal();const v=location.hash.slice(1);if(VIEWS[v])state.view=v;render();await Repo.init();if(Repo.ok){await Repo.loadAll();render();await startLogin()}else{$("#loginError").textContent="Buka melalui Google Apps Script Web App agar login dan penyimpanan Spreadsheet aktif."}if(state.auth&&!state.profile.guru&&!state.kelas.length)toggleEditor(true)})();
</script>
<script>
/* === LOADER v4: memeriksa skrip utama sebelum dijalankan & menampilkan diagnosis bila rusak === */
(function(){
  var EXP_LEN=77539, EXP_LINES=1175;
  var el=document.getElementById("jgMainSrc"); var code=el?el.textContent:"";
  function vis(t){return String(t).replace(/[^\x20-\x7e]/g,function(c){return "\\u"+("0000"+c.charCodeAt(0).toString(16)).slice(-4);});}
  function show(text){
    var card=document.getElementById("loginForm"); if(!card)return;
    var pre=document.getElementById("jgDiag");
    if(!pre){pre=document.createElement("pre");pre.id="jgDiag";pre.style.cssText="white-space:pre-wrap;word-break:break-all;font:11px/1.4 monospace;background:#fff4f2;color:#7a1d12;border:1px solid #f0b8b0;border-radius:8px;padding:8px;margin-top:10px;max-height:190px;overflow:auto;user-select:all";card.appendChild(pre);}
    pre.textContent=text;
  }
  function diagnose(err){
    var lines=code.split("\n"), soft=/end of input|Unterminated|missing \)|Unexpected token '?[)}]'?/i, bad=-1, i, j;
    for(i=5;i<=lines.length;i+=5){
      try{new Function(lines.slice(0,i).join("\n"));}catch(e){ if(!soft.test(e.message)){ bad=i; break; } }
    }
    if(bad>0){ for(j=Math.max(1,bad-5);j<=bad;j++){ try{new Function(lines.slice(0,j).join("\n"));}catch(e){ if(!soft.test(e.message)){ bad=j; break; } } } }
    var out=["DIAGNOSIS v4","Pesan: "+err.message,"Panjang skrip diterima: "+code.length+" (seharusnya "+EXP_LEN+")","Jumlah baris diterima: "+(lines.length-1)+" (seharusnya "+EXP_LINES+")"];
    if(bad>0){ out.push("Baris bermasalah: "+bad+" dari skrip utama"); for(j=Math.max(1,bad-2);j<=bad;j++){ out.push(j+": "+vis(lines[j-1]).slice(0,260)); } }
    show(out.join("\n"));
    window.jgShowError("Skrip utama rusak saat diterima browser. Salin kotak diagnosis di bawah dan kirim ke pengembang.");
  }
  if(!code){ window.jgShowError("Skrip utama tidak ditemukan."); return; }
  try{ new Function(code); }
  catch(e){ if(!(e instanceof EvalError)){ diagnose(e); return; } }
  var s=document.createElement("script"); s.textContent=code; document.body.appendChild(s);
})();
</script>
</body>
</html>

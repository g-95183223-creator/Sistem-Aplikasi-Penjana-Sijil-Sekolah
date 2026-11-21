<!DOCTYPE html>
<html lang="ms">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Sistem Aplikasi Penjana Sijil Sekolah</title>
<style>
:root{--bg:#f6f5f1;--sf:#fff;--tx:#1d1d1b;--mt:#6b6a63;--bd:#dcdad0;--ac:#1f5f8b;--ac2:#fff;color-scheme:light;box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]){--bg:#17171a;--sf:#222226;--tx:#eeede8;--mt:#a09f98;--bd:#3a3a40;--ac:#6fb1dc;--ac2:#111;color-scheme:dark}}
:root[data-theme="dark"]{--bg:#17171a;--sf:#222226;--tx:#eeede8;--mt:#a09f98;--bd:#3a3a40;--ac:#6fb1dc;--ac2:#111;color-scheme:dark}
*{box-sizing:border-box}
body{margin:0;background:var(--bg);color:var(--tx);font:15px/1.5 system-ui,-apple-system,"Segoe UI",sans-serif}
header{display:flex;flex-wrap:wrap;gap:10px;align-items:center;justify-content:space-between;padding:14px 18px;background:var(--sf);border-bottom:1px solid var(--bd)}
h1{font-size:18px;margin:0}
main{max-width:1100px;margin:0 auto;padding:16px;display:grid;gap:16px}
.tabs{display:flex;gap:6px;flex-wrap:wrap}
button,select,input,textarea{font:inherit;color:var(--tx)}
.tab{padding:8px 14px;border:1px solid var(--bd);background:var(--sf);border-radius:8px;cursor:pointer}
.tab.on{background:var(--ac);color:var(--ac2);border-color:var(--ac)}
.grid{display:grid;grid-template-columns:minmax(0,360px) minmax(0,1fr);gap:16px}
@media(max-width:800px){.grid{grid-template-columns:1fr}}
.card{background:var(--sf);border:1px solid var(--bd);border-radius:12px;padding:16px}
label{display:block;font-size:13px;color:var(--mt);margin:10px 0 4px}
input,select,textarea{width:100%;padding:8px 10px;border:1px solid var(--bd);border-radius:8px;background:var(--bg)}
input[type=checkbox]{width:auto}
textarea{min-height:90px;resize:vertical}
.btn{padding:9px 14px;border-radius:8px;border:1px solid var(--ac);background:var(--ac);color:var(--ac2);cursor:pointer;font-weight:600}
.btn.sec{background:transparent;color:var(--ac)}
.btn:disabled{opacity:.4;cursor:not-allowed}
.row{display:flex;gap:8px;flex-wrap:wrap;align-items:center;margin-top:12px}
.hint{font-size:12px;color:var(--mt)}
.err{color:#c0392b;font-size:13px}
[hidden]{display:none!important}
.stage{overflow-x:auto}
.cert{width:760px;height:540px;margin:0 auto;padding:22px;position:relative;background:#fffdf7;color:#2a2418;text-align:center;font-family:Georgia,"Times New Roman",serif}
.cert .in{height:100%;border:4px double var(--cc);padding:22px 40px;display:flex;flex-direction:column;justify-content:space-between;align-items:center}
.cert h2{margin:0;font-size:20px;letter-spacing:2px;color:var(--cc);text-transform:uppercase}
.cert .jn{font-size:32px;margin:6px 0;color:var(--cc);font-weight:bold;letter-spacing:3px}
.cert .nm{font-size:32px;font-style:italic;border-bottom:1px solid #9a927f;padding:0 30px 4px;margin:6px 0}
.cert p{margin:3px 0;font-size:14px}
.cert img{max-height:60px;max-width:160px}
.cert.p{width:540px;height:760px}
.cert .sn{position:absolute;bottom:5px;left:0;right:0;text-align:center;font:11px Arial,sans-serif;letter-spacing:1px;color:#6b6455}
.cert.p .in{padding:36px 34px 30px}
.cert .hd{width:100%}
.cert.p .hd{padding-bottom:14px;border-bottom:2px solid var(--cc)}
.cert.p .hd img{max-height:90px;max-width:220px;margin-bottom:6px}
.cert.p .hd h2{font-size:22px;line-height:1.3;letter-spacing:1px}
.cert.p .hd p{line-height:1.4;max-width:380px;margin:4px auto 0}
.cert.p .md{flex:1;display:flex;flex-direction:column;justify-content:center;width:100%}
.cert.p .jn{font-size:24px;line-height:1.3;letter-spacing:2px;margin:0 0 18px}
.cert.p .nm{font-size:30px;margin:12px 0;padding:0 10px 6px}
.cert.p .md p{font-size:15px;margin:6px 0}
.cert.p .sg{padding-top:10px}
.cert.p .sg div{min-width:170px}
.sg{display:flex;justify-content:space-around;width:100%;font-size:13px}
.sg div{border-top:1px solid #2a2418;padding-top:4px;min-width:200px}
.nav{display:flex;gap:10px;align-items:center;justify-content:center;margin-top:10px}
.chk{max-height:200px;overflow:auto;border:1px solid var(--bd);border-radius:8px;padding:6px 10px;margin-top:8px}
.chk label{display:flex;gap:8px;align-items:center;margin:4px 0;color:var(--tx);font-size:14px;cursor:pointer}
table{width:100%;border-collapse:collapse;font-size:14px}
th,td{text-align:left;padding:7px 8px;border-bottom:1px solid var(--bd)}
.tbl{overflow-x:auto}
#login{max-width:440px;margin:40px auto}
#login h2{text-align:center;font-size:21px;line-height:1.3;margin:0 0 6px;color:var(--ac)}
#login .sub{text-align:center;font-size:12px;color:var(--mt);margin:0 0 16px;padding-bottom:14px;border-bottom:1px solid var(--bd)}
#pa{display:none}
@media print{
 body>*:not(#pa){display:none!important}
 #pa{display:block}
 .cert,.cert.p{page-break-after:always;margin:0;width:100%;height:100vh}
 @page{size:A4 landscape;margin:0}
}
</style>
</head>
<body>
<header>
 <h1>🎓 Sistem Aplikasi Penjana Sijil Sekolah</h1>
 <div class="row" id="who" style="margin:0" hidden><span id="whoT" class="hint"></span><button class="btn sec" id="out">Log keluar</button></div>
</header>

<main>
<section id="login" class="card">
 <h2>🎓 Sistem Aplikasi Penjana Sijil Sekolah</h2>
 <p class="sub">Sila log masuk untuk menjana dan mengurus sijil</p>
 <div id="lgn" style="text-align:center;margin-bottom:12px"></div>
 <strong>Log masuk</strong>
 <label>Peranan</label>
 <select id="role"><option value="guru">Guru</option><option value="admin">Admin</option></select>
 <div id="fg"><label>Nama guru</label><input id="gn" placeholder="cth. Cikgu Rohana"></div>
 <div id="fa" hidden><label>Kata laluan admin</label><input id="pw" type="password" autocomplete="current-password">
  <p class="hint">Kata laluan awal prototaip: <b>admin123</b>. Tukar di tab Tetapan.</p></div>
 <div class="row"><button class="btn" id="go">Masuk</button><span id="le" class="err"></span></div>
</section>

<div id="app" hidden>
 <div class="tabs" style="margin-bottom:16px">
  <button class="tab on" data-v="jana">Jana sijil</button>
  <button class="tab" data-v="opt">Tetapan sijil</button>
  <button class="tab adm" data-v="log">Rekod guru</button>
  <button class="tab adm" data-v="logo">Logo sekolah</button>
  <button class="tab adm" data-v="tpl">Templat sijil</button>
  <button class="tab adm" data-v="set">Tetapan</button>
 </div>

 <section id="v-jana" class="grid">
  <div class="card">
   <label>Jenis sijil</label>
   <select id="jenis"></select>
   <label>Penerima (satu nama setiap baris)</label>
   <textarea id="nama">Ahmad bin Ali
Nurul Aisyah binti Hasan
Cikgu Rohana binti Ismail</textarea>
   <label>Pencapaian / nama acara</label>
   <input id="acara" value="Johan Pertandingan Pidato Peringkat Daerah 2026">
   <label>Tarikh</label><input id="tarikh" type="date">
   <label>Templat sijil (ikut jenis dipilih)</label>
   <select id="tpl"></select>
   <label>Penandatangan 1</label>
   <input id="s1n" value="Puan Hajah Salmah binti Omar"><input id="s1j" value="Pengetua" style="margin-top:6px">
   <label>Penandatangan 2 (pilihan)</label>
   <input id="s2n"><input id="s2j" value="Guru Penasihat" style="margin-top:6px">
   <div class="row"><button class="btn" id="jana">Jana sijil &amp; rekod</button></div>
  </div>
  <div class="card">
   <div class="stage"><div id="prev"></div></div>
   <div class="nav"><button class="btn sec" id="pv">◀</button><span id="pg" class="hint"></span><button class="btn sec" id="nx">▶</button></div>
   <hr style="border:0;border-top:1px solid var(--bd);margin:16px 0">
   <strong>Pilih sijil untuk dicetak</strong>
   <p class="hint" id="cinfo">Tekan “Jana sijil &amp; rekod” dahulu.</p>
   <div class="chk" id="chk" hidden></div>
   <div class="row">
    <button class="btn sec" id="all">Pilih semua</button>
    <button class="btn" id="cs">Cetak dipilih</button>
    <button class="btn" id="ca">Cetak semua</button>
   </div>
   <div class="row"><button class="btn sec" id="pdfs">Simpan PDF dipilih</button><button class="btn sec" id="pdfa">Simpan PDF semua</button><span id="pmsg" class="hint"></span>
   </div>
   <p class="hint">Dalam dialog cetak, pilih “Save as PDF” dan susun atur Landskap.</p>
  </div>
 </section>

 <section id="v-opt" hidden class="grid">
 <div class="card">
  <strong>Tetapan sijil</strong>
  <label>Saiz &amp; orientasi kertas</label>
  <select id="so"><option value="landscape">A4 Landskap</option><option value="portrait">A4 Potret</option></select>
  <label>Mod penyertaan</label>
  <select id="sm"><option>Bersemuka</option><option>Secara Talian</option><option>Hibrid</option></select>
  <label id="stl">Tempat</label><input id="st" placeholder="cth. Dewan Besar SK Methodist (ACS) Ipoh">
  <label>Anjuran</label><input id="sa" placeholder="cth. Panitia Bahasa Melayu">
  <label style="display:flex;gap:8px;align-items:center;color:var(--tx);margin-top:16px"><input type="checkbox" id="sc" checked> Papar nombor siri pada sijil</label>
  <label>Awalan nombor siri (ditentukan guru)</label><input id="sp" value="SKMA/2026/">
  <label>Nombor mula</label><input id="sz" type="number" min="1" value="1">
  <label>Bilangan digit</label><select id="sd"><option>3</option><option selected>4</option><option>5</option></select>
  <p class="hint" id="sx"></p>
  <p class="hint">Kosongkan medan yang tidak diperlukan; ia tidak akan dipaparkan pada sijil. Tetapan ini digunakan semasa menjana dan mencetak.</p>
  <div class="row"><button class="btn" id="kej">Teruskan ke Jana sijil</button></div>
 </div>
 <div class="card"><strong>Pratonton</strong><div class="stage"><div id="oprev"></div></div></div>
</section>

 <section id="v-log" hidden class="card">
  <strong>Rekod sijil dijana oleh guru</strong>
  <div class="tbl"><table><thead><tr><th>Masa</th><th>Guru</th><th>Jenis</th><th>Acara</th><th>Dijana</th><th>Dicetak</th><th>No. siri</th></tr></thead><tbody id="log"></tbody></table></div>
  <div class="row"><button class="btn sec" id="clr">Kosongkan rekod</button></div>
 </section>

 <section id="v-logo" hidden class="grid">
  <div class="card">
   <strong>Muat naik logo sekolah</strong>
   <label>Fail imej (PNG / JPG, ideal berlatar lutsinar)</label>
   <input id="lf" type="file" accept="image/png,image/jpeg,image/webp">
   <div class="row"><button class="btn sec" id="lrm">Buang logo</button><span id="lm" class="hint"></span></div>
   <label>Nama sekolah</label><input id="sk">
   <label>Alamat / tagline</label><input id="ad">
   <div class="row"><button class="btn" id="simpan">Simpan</button><span id="ok" class="hint"></span></div>
  </div>
  <div class="card"><strong>Pratonton pada sijil</strong><div class="stage"><div id="lprev"></div></div></div>
 </section>

 <section id="v-tpl" hidden class="grid">
 <div class="card">
  <strong>Jenis sijil</strong>
  <div class="tbl"><table><tbody id="jl"></tbody></table></div>
  <div class="row"><input id="jn" placeholder="Nama jenis baharu, cth. Kehadiran Cemerlang" style="flex:1;min-width:160px"><button class="btn" id="ja">Tambah</button></div>
  <p class="hint">Untuk menyunting, ubah nama dalam kotak kemudian tekan Enter atau klik di luar kotak. Jenis yang dipadam menjadikan templatnya terpakai untuk semua jenis.</p>
  <hr style="border:0;border-top:1px solid var(--bd);margin:16px 0">
  <strong>Urus templat sijil</strong>
  <div class="tbl"><table><thead><tr><th>Nama</th><th>Jenis</th><th></th></tr></thead><tbody id="tl"></tbody></table></div>
  <hr style="border:0;border-top:1px solid var(--bd);margin:16px 0">
  <strong id="th">Templat baharu</strong>
  <label>Nama templat</label><input id="tn" value="Templat baharu">
  <label>Untuk jenis penyertaan</label><select id="tj"></select>
  <label>Warna</label><input id="tw" type="color" value="#1f5f8b" style="height:40px;padding:2px">
  <label>Gaya bingkai</label><select id="tg"><option value="dua">Bingkai berganda</option><option value="tebal">Bingkai tebal</option><option value="sempang">Bingkai putus-putus</option><option value="halus">Bingkai halus</option><option value="tiada">Tanpa bingkai</option></select>
  <label>Tajuk (guna {JENIS} untuk nama jenis)</label><input id="tt" value="SIJIL {JENIS}">
  <label>Ayat pembuka</label><input id="tp" value="Dengan ini diperakukan bahawa">
  <label>Ayat sambungan</label><input id="te" value="telah layak menerima sijil ini atas pencapaian">
  <label>Imej latar (pilihan)</label><input id="tb" type="file" accept="image/*">
  <div class="row"><button class="btn" id="ts">Simpan templat</button><button class="btn sec" id="tnw">Templat baharu</button><button class="btn sec" id="tbr">Buang imej latar</button><span id="tm" class="hint"></span></div>
 </div>
 <div class="card"><strong>Pratonton templat</strong><div class="stage"><div id="tprev"></div></div></div>
</section>

 <section id="v-set" hidden class="card" style="max-width:420px">
  <strong>Tukar kata laluan admin</strong>
  <label>Kata laluan baharu (min. 6 aksara)</label><input id="np" type="password">
  <div class="row"><button class="btn" id="spw">Simpan kata laluan</button><span id="pm" class="hint"></span></div>
  <p class="hint">Prototaip: data disimpan dalam pelayar ini sahaja, jadi rekod hanya dilihat pada peranti yang sama. Sistem sebenar perlu pelayan, pangkalan data dan kata laluan yang dienkripsi.</p>
 </section>
</div>
</main>
<div id="pa"></div>

<script>
const $=id=>document.getElementById(id);
const ld=(k,d)=>{try{const v=localStorage.getItem(k);return v?JSON.parse(v):d}catch(e){return d}};
const sv=(k,v)=>{try{localStorage.setItem(k,JSON.stringify(v))}catch(e){}};
let S=ld("sj_s",{sk:"SK METHODIST (ACS) IPOH",ad:"JALAN PERHENTIAN MEDAN KIDD, 30200 IPOH, PERAK",logo:""}),LOG=ld("sj_l",[]),PW=ld("sj_p","admin123");
if(S.sk==="SK Taman Pelangi"){S.sk="SK METHODIST (ACS) IPOH";S.ad="JALAN PERHENTIAN MEDAN KIDD, 30200 IPOH, PERAK"}
const DEF=[
{id:"t1",n:"1. Klasik emas",jenis:"Semua",warna:"#8a6a1f",gaya:"dua",tajuk:"SIJIL {JENIS}",pembuka:"Dengan ini diperakukan bahawa",penutup:"telah layak menerima sijil ini atas pencapaian",bg:""},
{id:"t2",n:"2. Biru moden",jenis:"Semua",warna:"#1f5f8b",gaya:"tebal",tajuk:"SIJIL {JENIS}",pembuka:"Dengan ini diperakukan bahawa",penutup:"telah layak menerima sijil ini atas pencapaian",bg:""},
{id:"t3",n:"3. Hijau tradisional",jenis:"Semua",warna:"#2d6a4f",gaya:"halus",tajuk:"SIJIL {JENIS}",pembuka:"Dengan ini diperakukan bahawa",penutup:"telah layak menerima sijil ini atas pencapaian",bg:""},
{id:"t4",n:"4. Marun elegan",jenis:"Semua",warna:"#8b1f3a",gaya:"sempang",tajuk:"SIJIL {JENIS}",pembuka:"Dengan ini diperakukan bahawa",penutup:"telah layak menerima sijil ini atas pencapaian",bg:""}];
let T=ld("sj_t",DEF);if(T.length===4&&T[1].id==="t2"&&T[1].jenis==="Penyertaan")T=DEF;
let J=ld("sj_j",["Penghargaan","Penyertaan","Kecemerlangan","Perkhidmatan Cemerlang"]);
let user=null,idx=0,batch=[],cur=null,bno=[],N=ld("sj_n",0);
const esc=s=>String(s).replace(/[&<>"]/g,c=>({"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;"}[c]));
$("tarikh").valueAsDate=new Date();

// ---- Jenama log masuk
function brand(){$("lgn").innerHTML=(S.logo?`<img src="${S.logo}" alt="Logo sekolah" style="max-height:90px;max-width:200px">`:'<div style="font-size:48px">🏫</div>')+`<div style="font-weight:700;margin-top:6px">${esc(S.sk)}</div><div class="hint">${esc(S.ad)}</div>`}
brand();
// ---- Log masuk
$("role").onchange=()=>{const a=$("role").value==="admin";$("fa").hidden=!a;$("fg").hidden=a;$("le").textContent=""};
$("go").onclick=()=>{
 if($("role").value==="admin"){
  if($("pw").value!==PW){$("le").textContent="Kata laluan salah.";return}
  user={r:"admin",n:"Admin"};
 }else{
  const n=$("gn").value.trim();if(!n){$("le").textContent="Sila isi nama guru.";return}
  user={r:"guru",n};
 }
 $("login").hidden=true;$("app").hidden=false;$("who").hidden=false;
 $("whoT").textContent=user.n+" ("+user.r+")";
 document.querySelectorAll(".adm").forEach(b=>b.hidden=user.r!=="admin");
 $("pw").value="";view("jana");fillJ();fillTpl();drawLog();render();fillSet();tlist();jlist();tprev();
};
$("out").onclick=()=>{user=null;batch=[];cur=null;$("app").hidden=true;$("login").hidden=false;$("who").hidden=true;resetBatch()};
$("pw").addEventListener("keydown",e=>{if(e.key==="Enter")$("go").click()});

// ---- Sijil
const names=()=>$("nama").value.split("\n").map(s=>s.trim()).filter(Boolean);
const tgl=()=>new Date($("tarikh").value||Date.now()).toLocaleDateString("ms-MY",{day:"numeric",month:"long",year:"numeric"});
function cert(n,t,no){t=t||curT();const P=$("so").value==="portrait";
 const sg=(a,b)=>a?`<div>${esc(a)}<br>${esc(b)}</div>`:"";
 const lg=S.logo?`<img src="${S.logo}" alt="">`:`<div style="font-size:30px">🏫</div>`;
 return `<div class="cert ${$("so").value==="portrait"?"p":""}" style="--cc:${t.warna};${t.bg?`background-image:url(${t.bg});background-size:cover;`:""}"><div class="in" style="border:${bd(t.gaya)}">
 <div class="hd">${lg}<h2>${esc(S.sk)}</h2><p style="color:#6b6455;font-size:12px">${esc(S.ad)}</p></div>
 <div class="md"><div class="jn">${esc(t.tajuk.replace("{JENIS}",$("jenis").value.toUpperCase()))}</div><p>${esc(t.pembuka)}</p>
 <div class="nm" style="white-space:nowrap;font-size:${fit(n||"Nama penerima",P?30:32,P)}px">${esc(n||"Nama penerima")}</div>
 <p>${esc(t.penutup)}</p><p><b>${esc($("acara").value)}</b></p>${extra()}<p>${tgl()}</p></div>
 <div class="sg">${sg($("s1n").value,$("s1j").value)}${sg($("s2n").value,$("s2j").value)}</div></div>${$("sc").checked?`<div class="sn">No. Siri: ${esc(no||fmt(st0()))}</div>`:""}</div>`}
function render(){
 const l=names();if(idx>=l.length)idx=Math.max(0,l.length-1);
 $("prev").innerHTML=cert(l[idx],null,sno(idx));if($("oprev"))$("oprev").innerHTML=cert(l[idx],null,sno(idx));$("pg").textContent=l.length?`${idx+1} / ${l.length}`:"Tiada nama";
}
document.querySelectorAll("#v-jana input,#v-jana select,#v-jana textarea").forEach(e=>e.addEventListener("input",()=>{render();if(e.id==="nama")resetBatch()}));
$("pv").onclick=()=>{idx=Math.max(0,idx-1);render()};
$("nx").onclick=()=>{idx=Math.min(names().length-1,idx+1);render()};

function resetBatch(){batch=[];bno=[];cur=null;$("chk").hidden=true;$("chk").innerHTML="";$("cinfo").textContent="Tekan “Jana sijil & rekod” dahulu."}
$("jana").onclick=()=>{
 batch=names();if(!batch.length){alert("Sila masukkan sekurang-kurangnya satu nama.");return}
 
 cur={m:new Date().toLocaleString("ms-MY"),g:user.n,j:$("jenis").value,a:$("acara").value,n:batch.length,p:0,s:rng(0,batch.length)};
 LOG.unshift(cur);sv("sj_l",LOG.slice(0,200));drawLog();
 $("chk").innerHTML=batch.map((n,i)=>`<label><input type="checkbox" value="${i}" checked> ${esc(n)}</label>`).join("");
 $("chk").hidden=false;["all","cs","ca"].forEach(i=>$(i).disabled=false);
 $("cinfo").textContent=batch.length+" sijil dijana dan direkodkan. Pilih nama untuk dicetak, atau cetak semua.";
};
const boxes=()=>[...$("chk").querySelectorAll("input")];
$("all").onclick=()=>{ens();const b=boxes(),on=b.some(x=>!x.checked);b.forEach(x=>x.checked=on);$("all").textContent=on?"Nyahpilih semua":"Pilih semua"};
function cetak(ids){
 if(!ids.length){alert("Tiada sijil dipilih.");return}
 $("pa").innerHTML=ids.map((i,k)=>cert(batch[i],null,fmt(st0()+k))).join("");
 if(cur){cur.p+=ids.length;cur.s=rng(0,ids.length);sv("sj_l",LOG.slice(0,200));drawLog()}
 pgStyle();printed=false;window.print();setTimeout(()=>{if(!printed)msg("Dialog cetak disekat oleh paparan ini. Sila guna “Simpan PDF”, kemudian cetak fail PDF tersebut.")},900);
}
let printed=false;window.addEventListener("beforeprint",()=>{printed=true});
function ens(){if(!batch.length)$("jana").onclick();return batch.length>0}
const sel=()=>boxes().filter(x=>x.checked).map(x=>+x.value);
const msg=t=>{$("pmsg").textContent=t};
let _lib;
function loadLib(){if(_lib)return _lib;_lib=new Promise((res,rej)=>{let n=0;["https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js","https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"].forEach(u=>{const s=document.createElement("script");s.src=u;s.onload=()=>{if(++n===2)res()};s.onerror=()=>rej(new Error("lib"));document.head.appendChild(s)})});_lib.catch(()=>{_lib=null});return _lib}
async function pdf(onlySel){
 if(!ens())return;
 const ids=onlySel?sel():batch.map((_,i)=>i);
 if(!ids.length){msg("Tiada sijil dipilih.");return}
 let host;
 try{
  const dl=window.claude&&await claude.use("downloads");
  if(!dl){msg("Simpan PDF tidak tersedia dalam paparan ini.");return}
  msg("Menyediakan PDF ("+ids.length+" sijil)…");
  await loadLib();
  const P=$("so").value==="portrait",pw=P?210:297,ph=P?297:210;
  host=document.createElement("div");host.style.cssText="position:fixed;left:-10000px;top:0";document.body.appendChild(host);
  const doc=new window.jspdf.jsPDF({orientation:P?"portrait":"landscape",unit:"mm",format:"a4"});
  for(let k=0;k<ids.length;k++){
   host.innerHTML=cert(batch[ids[k]],null,fmt(st0()+k));
   const cv=await html2canvas(host.firstElementChild,{scale:2,backgroundColor:"#fffdf7"});
   if(k)doc.addPage("a4",P?"portrait":"landscape");
   doc.addImage(cv.toDataURL("image/jpeg",0.92),"JPEG",0,0,pw,ph);
  }
  host.remove();host=null;
  if(cur){cur.p+=ids.length;cur.s=rng(0,ids.length);sv("sj_l",LOG.slice(0,200));drawLog()}
  await dl.save({filename:"sijil_"+$("jenis").value.replace(/\W+/g,"_")+".pdf",data:doc.output("blob")});
  msg("PDF disimpan ✓");
 }catch(e){if(host)host.remove();msg(e&&e.code==="declined"?"Simpan dibatalkan.":"Gagal menyediakan PDF. Sila cuba lagi.")}
}
$("pdfs").onclick=()=>pdf(true);
$("pdfa").onclick=()=>pdf(false);
$("cs").onclick=()=>{if(ens())cetak(sel())};
$("ca").onclick=()=>{if(ens())cetak(batch.map((_,i)=>i))};

// ---- Admin
function drawLog(){$("log").innerHTML=LOG.length?LOG.map(r=>`<tr><td>${esc(r.m)}</td><td>${esc(r.g)}</td><td>${esc(r.j)}</td><td>${esc(r.a)}</td><td>${r.n}</td><td>${r.p}</td><td>${esc(r.s||"-")}</td></tr>`).join(""):'<tr><td colspan="7" class="hint">Belum ada rekod.</td></tr>'}
$("clr").onclick=()=>{LOG=[];cur=null;sv("sj_l",LOG);drawLog()};
function fillSet(){$("sk").value=S.sk;$("ad").value=S.ad;showLogo()}
function showLogo(){$("lprev").innerHTML=cert("Nama Penerima");brand()}
$("simpan").onclick=()=>{S.sk=$("sk").value;S.ad=$("ad").value;sv("sj_s",S);$("ok").textContent="Disimpan ✓";showLogo();render()};
$("lf").onchange=e=>{
 const f=e.target.files[0];if(!f)return;
 const r=new FileReader();
 r.onload=()=>{const im=new Image();im.onload=()=>{
  const k=Math.min(1,300/Math.max(im.width,im.height)),c=document.createElement("canvas");
  c.width=im.width*k;c.height=im.height*k;c.getContext("2d").drawImage(im,0,0,c.width,c.height);
  S.logo=c.toDataURL("image/png");sv("sj_s",S);$("lm").textContent="Logo disimpan ✓";showLogo();render()};
  im.src=r.result};
 r.readAsDataURL(f);
};
$("lrm").onclick=()=>{S.logo="";sv("sj_s",S);$("lf").value="";$("lm").textContent="Logo dibuang.";showLogo();render()};
$("spw").onclick=()=>{const p=$("np").value;if(p.length<6){$("pm").textContent="Terlalu pendek.";return}PW=p;sv("sj_p",PW);$("np").value="";$("pm").textContent="Kata laluan dikemas kini ✓"};

// ---- Tetapan sijil
function extra(){const m=$("sm").value,t=$("st").value.trim(),a=$("sa").value.trim();let h="";
 if(m==="Secara Talian")h+=`<p>Secara talian${t?" melalui "+esc(t):""}</p>`;
 else if(t)h+=`<p>Bertempat di ${esc(t)}${m==="Hibrid"?" dan secara talian":""}</p>`;
 else if(m==="Hibrid")h+="<p>Secara hibrid</p>";
 if(a)h+=`<p>Anjuran ${esc(a)}</p>`;return h}
function pgStyle(){let s=$("pgs");if(!s){s=document.createElement("style");s.id="pgs";document.head.appendChild(s)}s.textContent="@page{size:A4 "+$("so").value+";margin:0}"}
["so","sm","st","sa","sp","sz","sd","sc"].forEach(i=>$(i).addEventListener("input",()=>{$("stl").textContent={"Bersemuka":"Tempat","Secara Talian":"Platform (cth. Google Meet)","Hibrid":"Tempat (dan secara talian)"}[$("sm").value];render()}));
$("kej").onclick=()=>view("jana");

// ---- Templat
// ---- Nombor siri & saiz nama
const _c=document.createElement("canvas").getContext("2d");
function fit(t,max,p){const w=p?400:560;_c.font=`italic ${max}px Georgia,"Times New Roman",serif`;const m=_c.measureText(t).width||1;return Math.max(11,Math.min(max,Math.floor(max*w/m)))}
const st0=()=>Math.max(1,parseInt($("sz").value)||1);
const fmt=k=>$("sp").value+String(k).padStart(+$("sd").value,"0");
const rng=(a,n)=>n>1?fmt(st0()+a)+" – "+fmt(st0()+a+n-1):fmt(st0()+a);
const sno=i=>fmt(st0()+i);
function sx(){$("sx").textContent="Contoh: "+fmt(st0())+", "+fmt(st0()+1)+", "+fmt(st0()+2)+" … Nombor bertambah satu bagi setiap sijil yang dicetak, bermula dari nombor mula."}
["sp","sz","sd"].forEach(i=>$(i).addEventListener("input",sx));sx();

// ---- Jenis sijil
function fillJ(){const a=$("jenis").value,b=$("tj").value;
 $("jenis").innerHTML=J.map(x=>`<option>${esc(x)}</option>`).join("");
 $("tj").innerHTML=["Semua",...J].map(x=>`<option>${esc(x)}</option>`).join("");
 if(J.includes(a))$("jenis").value=a;if(b==="Semua"||J.includes(b))$("tj").value=b}
function jlist(){$("jl").innerHTML=J.map((x,i)=>`<tr><td><input data-i="${i}" value="${esc(x)}"></td><td style="width:90px"><button class="btn sec" data-d="${i}">Padam</button></td></tr>`).join("")}
function jsave(){sv("sj_j",J);sv("sj_t",T);fillJ();fillTpl();jlist();tlist();render();tprev()}
$("jl").onchange=e=>{const i=+e.target.dataset.i,v=e.target.value.trim(),o=J[i];if(!v||v==="Semua"||J.includes(v)){e.target.value=o;return}J[i]=v;T.forEach(x=>{if(x.jenis===o)x.jenis=v});jsave()};
$("jl").onclick=e=>{const b=e.target.closest("button");if(!b||J.length<2)return;const i=+b.dataset.d,o=J[i];J.splice(i,1);T.forEach(x=>{if(x.jenis===o)x.jenis="Semua"});jsave()};
$("ja").onclick=()=>{const v=$("jn").value.trim();if(!v||v==="Semua"||J.includes(v))return;J.push(v);$("jn").value="";jsave()};

let editId=null,dbg="";
const bd=g=>({dua:"4px double",tebal:"7px solid",sempang:"3px dashed",halus:"1px solid",tiada:"0 solid"}[g]||"4px double")+" var(--cc)";
function curT(){return T.find(x=>x.id===$("tpl").value)||T[0]}
function fillTpl(){const j=$("jenis").value,old=$("tpl").value,l=T.filter(x=>x.jenis===j||x.jenis==="Semua");$("tpl").innerHTML=(l.length?l:T).map(x=>`<option value="${x.id}">${esc(x.n)}</option>`).join("");if([...$("tpl").options].some(o=>o.value===old))$("tpl").value=old}
$("jenis").addEventListener("input",()=>{fillTpl();render()});
function draft(){return{id:editId||"t"+Date.now(),n:$("tn").value||"Templat baharu",jenis:$("tj").value,warna:$("tw").value,gaya:$("tg").value,tajuk:$("tt").value,pembuka:$("tp").value,penutup:$("te").value,bg:dbg}}
function tprev(){$("tprev").innerHTML=cert("Nama Penerima",draft())}
function tlist(){$("tl").innerHTML=T.map(x=>`<tr><td>${esc(x.n)}</td><td>${esc(x.jenis)}</td><td><button class="btn sec" data-e="${x.id}">Sunting</button> <button class="btn sec" data-d="${x.id}">Padam</button></td></tr>`).join("")}
$("tl").onclick=e=>{const b=e.target.closest("button");if(!b)return;
 if(b.dataset.d){if(T.length<2){alert("Sekurang-kurangnya satu templat diperlukan.");return}
  T=T.filter(x=>x.id!==b.dataset.d);if(editId===b.dataset.d)editId=null;sv("sj_t",T);tlist();fillTpl();render();return}
 const x=T.find(y=>y.id===b.dataset.e);if(!x)return;
 editId=x.id;dbg=x.bg||"";$("tn").value=x.n;$("tj").value=x.jenis;$("tw").value=x.warna;$("tg").value=x.gaya;$("tt").value=x.tajuk;$("tp").value=x.pembuka;$("te").value=x.penutup;$("th").textContent="Sunting: "+x.n;tprev()};
["tn","tj","tw","tg","tt","tp","te"].forEach(i=>$(i).addEventListener("input",tprev));
$("ts").onclick=()=>{const d=draft(),i=T.findIndex(x=>x.id===d.id);if(i>=0)T[i]=d;else T.push(d);editId=d.id;sv("sj_t",T);tlist();fillTpl();render();$("th").textContent="Sunting: "+d.n;$("tm").textContent="Templat disimpan ✓"};
$("tnw").onclick=()=>{editId=null;dbg="";$("th").textContent="Templat baharu";$("tn").value="Templat baharu";$("tm").textContent="";tprev()};
$("tbr").onclick=()=>{dbg="";$("tb").value="";tprev()};
$("tb").onchange=e=>{const f=e.target.files[0];if(!f)return;const r=new FileReader();r.onload=()=>{const im=new Image();im.onload=()=>{const k=Math.min(1,1200/im.width),c=document.createElement("canvas");c.width=im.width*k;c.height=im.height*k;c.getContext("2d").drawImage(im,0,0,c.width,c.height);dbg=c.toDataURL("image/jpeg",.8);tprev()};im.src=r.result};r.readAsDataURL(f)};

function view(v){["jana","opt","log","logo","tpl","set"].forEach(x=>$("v-"+x).hidden=x!==v);document.querySelectorAll(".tab").forEach(t=>t.classList.toggle("on",t.dataset.v===v))}
document.querySelectorAll(".tab").forEach(t=>t.onclick=()=>view(t.dataset.v));
</script>
</body>
</html>


<html lang="id">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Battle of the Nations</title>
<style>
:root{--bg:#e6efe0;--card:rgba(255,255,255,.9);--tx:#1d2a1a;--mu:#5b6b55;--ac:#2f9e44;--ac2:#0288d1;--bd:#c5d4bd;--bad:#d32f2f;color-scheme:light}
@media(prefers-color-scheme:dark){:root{--bg:#0c130a;--card:rgba(28,40,24,.92);--tx:#e8f0e3;--mu:#9aab93;--ac:#51cf66;--ac2:#4dabf7;--bd:#33432f;--bad:#ef5350;color-scheme:dark}}
*{box-sizing:border-box;-webkit-tap-highlight-color:transparent}
body{margin:0;background:var(--bg);color:var(--tx);font-family:system-ui,sans-serif;max-width:480px;margin:0 auto;padding:12px 12px 70px;min-height:100vh}
button,input{font:inherit}
button{cursor:pointer;border:0;border-radius:12px;padding:11px 14px;font-weight:600}
button:active{transform:scale(.96)}
.hero{text-align:center;padding:22px 12px;border-radius:18px;color:#fff;margin-bottom:12px;background:linear-gradient(135deg,#1b5e20,#0288d1,#6a1b9a);background-size:300% 300%;animation:bg 8s ease infinite}
.hero h1{margin:0;font-size:22px}.hero p{margin:6px 0 0;opacity:.9;font-size:13px}
@keyframes bg{50%{background-position:100% 50%}}
.card{background:var(--card);border:1px solid var(--bd);border-radius:16px;padding:14px;margin-bottom:10px}
.mu{color:var(--mu);font-size:13px}
.btn{background:linear-gradient(135deg,var(--ac),var(--ac2));color:#fff;width:100%;margin-top:10px}
.btn-red{background:linear-gradient(135deg,#e03131,#c2255c);color:#fff}
.btn-gray{background:#495057;color:#fff}
.btn-blue{background:linear-gradient(135deg,#1971c2,#7048e8);color:#fff;width:100%;margin-top:8px}
input{width:100%;padding:12px;border-radius:12px;border:1px solid var(--bd);background:var(--bg);color:var(--tx);margin-top:6px}
.stats{display:grid;grid-template-columns:repeat(3,1fr);gap:6px;text-align:center;font-size:13px;margin-top:10px}
.stats div{background:rgba(0,0,0,.06);border-radius:10px;padding:6px 2px}.stats b{display:block;font-size:15px}
.tabs{display:flex;gap:5px;margin-bottom:10px}
.tabs button{flex:1;background:var(--card);color:var(--tx);border:1px solid var(--bd);padding:10px 4px;font-size:13px}
.tabs button.on{background:linear-gradient(135deg,var(--ac),var(--ac2));color:#fff;border-color:transparent}
.grid{display:grid;grid-template-columns:repeat(8,1fr);gap:2px;background:var(--bd);padding:3px;border-radius:12px}
.grid div{aspect-ratio:1;display:flex;align-items:center;justify-content:center;font-size:clamp(14px,5vw,22px);background:var(--card)}
.bgrid{display:grid;grid-template-columns:repeat(4,1fr);gap:6px;margin-bottom:8px}
.bgrid button{background:var(--card);color:var(--tx);border:1px solid var(--bd);border-radius:12px;padding:8px 2px;font-size:11px;min-height:60px}
.bgrid button.on{background:linear-gradient(135deg,var(--ac),var(--ac2));color:#fff;border:0}
.en{display:flex;align-items:center;gap:10px;padding:10px 0;border-top:1px solid var(--bd)}.en:first-child{border-top:0}
.bar{height:7px;background:var(--bd);border-radius:4px;margin:4px 0;overflow:hidden}
.bar span{display:block;height:100%;background:linear-gradient(90deg,#fa5252,#fcc419,#51cf66)}
.rank{display:inline-block;background:#ffd43b;color:#5c3d00;border-radius:8px;padding:2px 8px;font-size:12px;font-weight:700}
.srv{display:flex;justify-content:space-between;align-items:center;padding:10px 0;border-top:1px solid var(--bd)}.srv:first-child{border-top:0}
.badge{display:inline-block;padding:2px 8px;border-radius:12px;font-size:11px;font-weight:700}
.ok{background:#2f9e44;color:#fff}.no{background:#e03131;color:#fff}.warn{background:#f59f00;color:#212529}.blue{background:#1971c2;color:#fff}
#toast{position:fixed;left:50%;bottom:16px;transform:translate(-50%,30px);background:#212529;color:#fff;padding:11px 18px;border-radius:22px;font-size:14px;opacity:0;transition:.3s;max-width:90%;text-align:center;z-index:20}
#toast.s{opacity:1;transform:translate(-50%,0)}
</style>
</head>
<body>
<div id="app"></div><div id="toast"></div>
<script>
const API_STATS="https://data-base-fazxy.lovable.app/api/public/v1/player_stats";
const KEY_STATS="dk_7a757b64d9584e6bb1e005e536854a3b";
const API_META="https://data-base-fazxy.lovable.app/api/public/v1/player_meta";
const KEY_META="dk_9b7f76500c7e4b5db41c34636ebce111";
const SRV_PREFIX="SERVER|";

const CS=[
{n:"Indonesia",f:"🇮🇩",m:600,a:30,p:40},{n:"Jepang",f:"🇯🇵",m:900,a:25,p:30},
{n:"Amerika",f:"🇺🇸",m:800,a:60,p:40},{n:"Rusia",f:"🇷🇺",m:500,a:70,p:30},
{n:"Brasil",f:"🇧🇷",m:600,a:30,p:45},{n:"Jerman",f:"🇩🇪",m:850,a:35,p:30},
{n:"Tiongkok",f:"🇨🇳",m:700,a:55,p:50},{n:"India",f:"🇮🇳",m:550,a:40,p:55},
{n:"Korea Selatan",f:"🇰🇷",m:750,a:35,p:28},{n:"Prancis",f:"🇫🇷",m:720,a:40,p:32},
{n:"Inggris",f:"🇬🇧",m:780,a:45,p:30},{n:"Turki",f:"🇹🇷",m:580,a:42,p:38}
];
const B={h:{e:"🏠",n:"Rumah",c:100},f:{e:"🌾",n:"Ladang",c:80},p:{e:"🏭",n:"Pabrik",c:150},b:{e:"🏰",n:"Barak",c:200},r:{e:"🛣️",n:"Jalan",c:15},x:{e:"💣",n:"Bongkar",c:0}};

let S=null,tab="b",timer=null,uid=null,ACC=null,metaRow=null,statsRow=null,currentServer=null;

const $=id=>document.getElementById(id);
function toast(t){const e=$("toast");e.textContent=t;e.className="s";clearTimeout(window._tt);window._tt=setTimeout(()=>e.className="",2600)}
function fmt(n){n=Math.floor(n);if(n>=1e9)return(n/1e9).toFixed(1)+" M";if(n>=1e6)return(n/1e6).toFixed(1)+" Jt";if(n>=1e3)return(n/1e3).toFixed(1)+" Rb";return""+n}
function ls(k,v){try{if(v===undefined)return localStorage.getItem(k);if(v===null)localStorage.removeItem(k);else localStorage.setItem(k,v)}catch(e){}}
function getRank(exp){exp=+exp||0;if(exp>=91)return"Super Pro";if(exp>=88)return"Pro";if(exp>=55)return"Jagoan";if(exp>=25)return"Jago";if(exp>=12)return"Lumayan";return"Pemula"}

async function api(method,url,key,body){
  const opt={method,headers:{"x-api-key":key,"Content-Type":"application/json"}};
  if(body)opt.body=JSON.stringify(body);
  const r=await fetch(url,opt);const t=await r.text();
  if(!r.ok)throw new Error(r.status+" "+t.slice(0,100));
  try{return JSON.parse(t)}catch(e){return null}
}
function arr(d){return Array.isArray(d)?d:(d?.data||d?.rows||d?.items||[])}

async function loadMeta(){try{const list=arr(await api("GET",API_META+"?player_id="+encodeURIComponent(uid),KEY_META));metaRow=list.find(x=>x.player_id===uid)||list[0]||null;return metaRow}catch(e){metaRow=null;return null}}
async function loadStats(){try{const list=arr(await api("GET",API_STATS+"?player_id="+encodeURIComponent(uid),KEY_STATS));statsRow=list.find(x=>x.player_id===uid)||list[0]||null;return statsRow}catch(e){statsRow=null;return null}}
async function ensureMeta(){await loadMeta();if(!metaRow){try{metaRow=await api("POST",API_META,KEY_META,{player_id:uid,is_admin:false,is_banned:false,is_whitelisted:false,extra:{}})}catch(e){}}}
async function ensureStats(name){await loadStats();if(!statsRow){try{statsRow=await api("POST",API_STATS,KEY_STATS,{player_id:uid,level:1,exp:0,money:500,army:20,game_stats:{name:name||"Pemain",rank:"Pemula",win_streak:0}})}catch(e){}}}
function isBanned(){return !!(metaRow&&metaRow.is_banned)}

async function listServers(){
  try{
    const list=arr(await api("GET",API_META,KEY_META));
    return list.filter(x=>String(x.player_id).startsWith(SRV_PREFIX)||(x.extra&&x.extra.is_server)).map(s=>{
      const ex=s.extra||{};
      return{id:s.id||s._id,code:ex.server_code||String(s.player_id).replace(SRV_PREFIX,""),type:ex.server_type||"free",active:ex.server_is_active!==false,expires:ex.server_expires_at?new Date(ex.server_expires_at):null,minLevel:ex.server_min_level||1};
    }).filter(s=>s.active&&(!s.expires||s.expires>new Date()));
  }catch(e){return[]}
}

function pick(i,pub){
  const c=CS[i];const ter=[];
  for(let k=0;k<64;k++){const r=Math.random();ter.push(r<.1?1:r<.28?2:0)}
  S={c:i,m:c.m,food:100,pop:c.p,army:c.a,t:Array(64).fill(""),lv:Array(64).fill(1),ter,day:1,land:1,sel:"h",xp:0,lvl:1,en:rndEn(i),win_streak:0,mode:pub?"pub":"self",sid:pub||null};
  if(statsRow){S.m=statsRow.money||S.m;S.army=statsRow.army||S.army;S.lvl=statsRow.level||1;S.xp=statsRow.exp||0}
  tab="b";start();
}
function rndEn(i){const ix=CS.map((_,k)=>k).filter(k=>k!==i);for(let k=ix.length-1;k>0;k--){const j=Math.floor(Math.random()*(k+1));[ix[k],ix[j]]=[ix[j],ix[k]]}return ix.slice(0,5).map((c,j)=>({n:CS[c].n,f:CS[c].f,pw:20+Math.floor(Math.random()*20)+j*12}))}
function sum(k){let s=0;for(let i=0;i<S.t.length;i++)if(S.t[i]===k)s+=(1+0.5*(S.lv[i]-1));return s}
function cap(){return 20+Math.floor(sum("h")*10)}
function tick(){if(!S)return;const f=sum("f"),p=sum("p"),b=sum("b");S.day++;S.m+=p*8+S.pop*0.3+(S.land-1)*6-Math.min(S.army*0.2,50);S.food+=f*6-S.pop*0.2;if(S.food<0){S.food=0;S.pop=Math.max(5,S.pop-2)}else if(S.pop<cap())S.pop=Math.min(cap(),S.pop+2);if(b>0&&S.m>=b*3){S.army+=b;S.m-=b*3}S.en.forEach(e=>e.pw+=0.12);if(S.day%10===0)cloudSave();renderStats()}
async function cloudSave(){if(!S||!uid)return;try{const body={level:S.lvl,exp:S.xp,money:Math.floor(S.m),army:Math.floor(S.army),game_stats:{name:ACC?.name,rank:getRank(S.xp),win_streak:S.win_streak||0,day:S.day,country:CS[S.c].n,server:S.sid||null}};if(statsRow&&(statsRow.id||statsRow._id))await api("PATCH",API_STATS+"/"+(statsRow.id||statsRow._id),KEY_STATS,body);else{body.player_id=uid;statsRow=await api("POST",API_STATS,KEY_STATS,body)}}catch(e){}}

function build(i){if(!S)return;const k=S.sel,t=S.t[i];if(S.ter[i]===1){toast("Air tidak bisa dibangun");return}if(k==="x"){if(t){S.t[i]="";S.lv[i]=1;S.m+=30;toast("Dibongkar");render()}return}if(t){toast("Petak terisi");return}const cost=B[k].c+(S.ter[i]===2?20:0);if(S.m<cost){toast("Uang kurang");return}S.m-=cost;S.t[i]=k;S.lv[i]=1;S.ter[i]=0;toast(B[k].e+" dibangun");render()}
function attack(i){const e=S.en[i];if(S.army<5){toast("Pasukan kurang");return}if(Math.random()<S.army/(S.army+e.pw)){const gain=Math.floor(e.pw*10);S.army=Math.max(0,S.army-Math.floor(e.pw*0.3));S.m+=gain;S.land++;e.pw=Math.max(15,e.pw*0.7);S.win_streak=(S.win_streak||0)+1;if(S.win_streak>=3){S.win_streak=0;S.xp=Math.min(100,(S.xp||0)+1);S.lvl=Math.max(S.lvl,Math.floor(S.xp/10)+1);toast("Menang! +"+fmt(gain)+" · +1 Exp")}else toast("Menang! +"+fmt(gain));cloudSave()}else{S.army=Math.floor(S.army*0.5);S.win_streak=0;toast("Kalah")}render()}

function renderStats(){const el=$("st");if(!el||!S)return;el.innerHTML=[["💰",fmt(S.m)],["🌾",fmt(S.food)],["👥",Math.floor(S.pop)+"/"+cap()],["⚔️",fmt(S.army)],["🗺️",S.land],["📅","Hari "+S.day]].map(x=>`<div>${x[0]}<b>${x[1]}</b></div>`).join("");const rk=$("rank");if(rk)rk.innerHTML=`<span class="rank">Lv ${S.lvl} · ${getRank(S.xp)} (${S.xp})</span>`}

function render(){
  if(!S){lobby();return}
  const c=CS[S.c];
  let h=`<div class="card" style="background:linear-gradient(135deg,#1b5e20,#0277bd);color:#fff;border:0">
    <div style="display:flex;justify-content:space-between;align-items:center">
      <b style="font-size:17px">${c.f} ${c.n}${S.sid?" · "+S.sid:""}</b>
      <button onclick="menu()" style="background:rgba(255,255,255,.2);color:#fff;padding:4px 10px;font-size:13px">🌍</button>
    </div>
    <div id="rank" style="margin-top:6px"></div>
    <div class="stats" id="st"></div>
  </div>
  <div class="tabs">
    <button class="${tab==='b'?'on':''}" onclick="tab='b';render()">🏗️ Bangun</button>
    <button class="${tab==='w'?'on':''}" onclick="tab='w';render()">⚔️ Perang</button>
    <button class="${tab==='c'?'on':''}" onclick="tab='c';render()">⚙️</button>
  </div>`;
  if(tab==="b"){
    h+=`<div class="bgrid">${Object.keys(B).map(k=>`<button class="${S.sel===k?'on':''}" onclick="S.sel='${k}';render()"><span style="font-size:20px">${B[k].e}</span><br>${B[k].n}</button>`).join("")}</div>`;
    h+=`<div class="grid" id="grid">${S.t.map((x,i)=>`<div data-i="${i}" style="background:${S.ter[i]===1?'#6ab7e8':S.ter[i]===2&&!x?'#6fae52':((i%8+Math.floor(i/8))%2?'#a6d27a':'#9bc970')}">${x?B[x].e:(S.ter[i]===1?'🌊':S.ter[i]===2?'🌲':'')}</div>`).join("")}</div>`;
  }else if(tab==="w"){
    h+=`<div class="card">${S.en.map((e,i)=>{const ch=Math.round(S.army/(S.army+e.pw)*100);return`<div class="en"><span style="font-size:28px">${e.f}</span><div style="flex:1"><b>${e.n}</b><div class="bar"><span style="width:${ch}%"></span></div><span class="mu">${ch}%</span></div><button class="btn-red" style="padding:8px 12px" onclick="attack(${i})">⚔️</button></div>`}).join("")}</div>`;
  }else{
    h+=`<div class="card"><b>Config</b><p class="mu">Mode: ${S.mode==="pub"?"Public "+S.sid:"Self"}</p>
      <button class="btn" onclick="cloudSave();toast('Tersimpan')">💾 Simpan</button>
      <button class="btn-gray" style="width:100%;margin-top:8px" onclick="menu()">🚪 Lobby</button></div>`;
  }
  $("app").innerHTML=h;renderStats();
  const g=$("grid");if(g)g.onclick=e=>{const el=e.target.closest("[data-i]");if(el)build(+el.dataset.i)};
}
function start(){clearInterval(timer);render();timer=setInterval(tick,1500)}
function menu(){clearInterval(timer);if(S)cloudSave();S=null;currentServer=null;lobby()}
function showBan(){$("app").innerHTML=`<div class="hero"><h1>🚫 AKUN DIBANNED</h1></div><div class="card" style="text-align:center"><h2 style="color:var(--bad)">Akun Diblokir</h2><p class="mu">Hubungi admin.</p></div>`}

async function lobby(){
  $("app").innerHTML=`<div class="hero"><h1>🌍 BATTLE OF THE NATIONS</h1><p>Lobby</p></div><div class="card"><p class="mu">Memuat...</p></div>`;
  await ensureMeta();if(isBanned()){showBan();return}
  await ensureStats(ACC?.name);
  const name=ACC?.name||"Pemain";const lvl=statsRow?.level||1;const exp=statsRow?.exp||0;
  $("app").innerHTML=`<div class="hero"><h1>🌍 BATTLE OF THE NATIONS</h1><p>Lobby</p></div>
  <div class="card"><div style="display:flex;justify-content:space-between"><span>👤 <b>${name}</b></span><span class="rank">Lv ${lvl} · ${getRank(exp)}</span></div>
  <p class="mu" style="margin-top:4px">ID: ${uid}</p></div>
  <button class="btn-blue" onclick="serverScreen()">🌐 Server Public</button>
  <button class="btn" onclick="countryScreen(false)">🤖 Main Self</button>
  <div class="card" style="margin-top:10px"><b>📊 Stat</b>
  <p class="mu">Exp ${exp}/100 · ${getRank(exp)} · 💰 ${fmt(statsRow?.money||0)} · ⚔️ ${fmt(statsRow?.army||0)}</p></div>`;
}

async function serverScreen(){
  $("app").innerHTML=`<div class="card"><div style="display:flex;justify-content:space-between"><b>🌐 Server Public</b><button class="btn-gray" style="padding:4px 10px" onclick="lobby()">←</button></div>
  <p class="mu">Pilih server atau masukkan kode.</p></div>
  <div class="card"><b>Gabung dengan Kode</b>
  <input id="sid" placeholder="S-XXXX" style="text-transform:uppercase">
  <button class="btn" onclick="joinByCode()">Gabung</button></div>
  <div class="card"><div style="display:flex;justify-content:space-between"><b>Server Aktif</b><button class="btn-gray" style="padding:4px 10px" onclick="serverScreen()">⟳</button></div>
  <div id="sl"><p class="mu">Memuat...</p></div></div>`;
  const servers=await listServers();
  const el=$("sl");
  if(!servers.length){el.innerHTML="<p class='mu'>Belum ada server aktif. Minta admin membuatkan.</p>";return}
  el.innerHTML=servers.map(s=>{
    const typeBadge=s.type==="permanent"?"<span class='badge blue'>PERMANENT</span>":s.type==="timed"?"<span class='badge warn'>TIMED</span>":"<span class='badge'>FREE 24j</span>";
    const exp=s.expires?(" · sisa "+Math.max(0,Math.round((s.expires-Date.now())/3600000))+"j"):"";
    return`<div class="srv"><div><b>${s.code}</b> ${typeBadge}<br><span class="mu">Min Lv ${s.minLevel}${exp}</span></div>
    <button class="btn" style="width:auto;padding:8px 14px;margin:0" onclick="joinServer('${s.code}',${s.minLevel})">Masuk</button></div>`;
  }).join("");
}
function joinByCode(){const v=($("sid").value||"").trim().toUpperCase();if(!v)return toast("Isi kode");joinServer(v,1)}
async function joinServer(code,minLv){
  const lvl=statsRow?.level||1;
  if(lvl<minLv)return toast("Butuh Level "+minLv);
  const servers=await listServers();
  const s=servers.find(x=>x.code===code);
  if(!s)return toast("Server tidak ditemukan / sudah mati");
  currentServer=s;countryScreen(code);
}
function countryScreen(pub){
  let h=`<div class="card"><div style="display:flex;justify-content:space-between"><b>${pub?"Pilih Negara · "+pub:"Pilih Negara · Self"}</b>
  <button class="btn-gray" style="padding:4px 10px" onclick="${pub?"serverScreen()":"lobby()"}">←</button></div></div>
  <div style="display:grid;grid-template-columns:1fr 1fr;gap:8px">`;
  CS.forEach((c,i)=>h+=`<button class="card" style="text-align:center" onclick="pick(${i},${pub?`'${pub}'`:false})"><span style="font-size:30px">${c.f}</span><br><b>${c.n}</b></button>`);
  h+=`</div>`;$("app").innerHTML=h;
}
function nameScreen(){$("app").innerHTML=`<div class="hero"><h1>🌍 BATTLE OF THE NATIONS</h1><p>Masuk / Daftar</p></div>
  <div class="card"><b>Nama</b><input id="nm" maxlength="14" placeholder="3-14 karakter">
  <button class="btn" onclick="saveName()">Mulai</button></div>`}
async function saveName(){
  const u=$("nm").value.trim();
  if(!/^[A-Za-z0-9_ ]{3,14}$/.test(u))return toast("Nama 3-14 karakter");
  uid=ls("negara_uid");if(!uid){uid="u"+Math.random().toString(36).slice(2,10)+Date.now().toString(36);ls("negara_uid",uid)}
  ls("negara_name",u);ACC={name:u,id:uid};
  await ensureMeta();if(isBanned()){showBan();return}
  await ensureStats(u);toast("Halo, "+u+"!");lobby();
}
(async function boot(){
  uid=ls("negara_uid");const name=ls("negara_name");
  if(uid&&name){ACC={name,id:uid};await ensureMeta();if(isBanned()){showBan();return}await ensureStats(name);lobby()}
  else nameScreen();
})();
</script>
</body>
</html>

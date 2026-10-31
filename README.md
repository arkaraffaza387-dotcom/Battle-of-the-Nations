<!DOCTYPE html>
<html lang="id"><head><meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Game Negara Public</title>
<style>
:root{--bg:#e6efe0;--card:rgba(255,255,255,.88);--tx:#1d2a1a;--mu:#5b6b55;--ac:#2f9e44;--ac2:#0288d1;--bd:#c5d4bd;--g1:#a6d27a;--g2:#9bc970;--bad:#d32f2f;--w:#6ab7e8;--fo:#6fae52;color-scheme:light;box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]){--bg:#0c130a;--card:rgba(28,40,24,.9);--tx:#e8f0e3;--mu:#9aab93;--ac:#51cf66;--ac2:#4dabf7;--bd:#33432f;--g1:#3d6b2a;--g2:#386227;--bad:#ef5350;--w:#2b5f86;--fo:#2f5a22;color-scheme:dark}}
:root[data-theme="dark"]{--bg:#0c130a;--card:rgba(28,40,24,.9);--tx:#e8f0e3;--mu:#9aab93;--ac:#51cf66;--ac2:#4dabf7;--bd:#33432f;--g1:#3d6b2a;--g2:#386227;--bad:#ef5350;--w:#2b5f86;--fo:#2f5a22;color-scheme:dark}
*{box-sizing:border-box;-webkit-tap-highlight-color:transparent}
body{margin:0;background:var(--bg);color:var(--tx);font-family:system-ui,-apple-system,"Segoe UI",sans-serif;max-width:520px;margin:0 auto;padding:12px 12px 80px;min-height:100vh}
button,input{font:inherit}
button{cursor:pointer;transition:transform .12s,box-shadow .2s}
button:active{transform:scale(.94)}
.hero{text-align:center;padding:22px 10px;border-radius:18px;color:#fff;margin-bottom:12px;background:linear-gradient(135deg,#1b5e20,#0288d1,#6a1b9a);background-size:300% 300%;animation:bg 8s ease infinite;box-shadow:0 8px 24px rgba(2,136,209,.35)}
.hero h1{margin:0;font-size:28px;letter-spacing:1px;text-shadow:0 2px 8px rgba(0,0,0,.4)}
.hero p{margin:6px 0 0;opacity:.9;font-size:13px}
@keyframes bg{50%{background-position:100% 50%}}
.globe{display:inline-block;animation:spin 6s linear infinite}
@keyframes spin{to{transform:rotate(360deg)}}
.card{background:var(--card);border:1px solid var(--bd);border-radius:16px;padding:12px;margin-bottom:10px;backdrop-filter:blur(6px);box-shadow:0 4px 14px rgba(0,0,0,.08)}
.mu{color:var(--mu);font-size:13px}
.cl{display:grid;grid-template-columns:1fr 1fr;gap:10px}
.cl button{background:var(--card);color:var(--tx);border:1px solid var(--bd);border-radius:16px;padding:14px 8px;font-size:15px;box-shadow:0 4px 12px rgba(0,0,0,.08)}
.cl button:hover{box-shadow:0 0 0 2px var(--ac),0 6px 18px rgba(47,158,68,.35)}
.cl .f{font-size:40px;display:block;filter:drop-shadow(0 3px 4px rgba(0,0,0,.3))}
.head{border:0;color:#fff;background:linear-gradient(135deg,#1b5e20,#0277bd)}
.head .mu{color:#d6efff}
.top{display:flex;justify-content:space-between;align-items:center;gap:6px}
.top button{background:rgba(255,255,255,.18);border:1px solid rgba(255,255,255,.35);color:#fff;border-radius:8px;padding:3px 9px;font-size:13px;margin-left:3px}
.top button.on{background:#fff;color:#1b5e20}
.lv{display:flex;align-items:center;gap:8px;margin-top:8px;font-size:12px}
.lv b{background:#ffd43b;color:#5c3d00;border-radius:10px;padding:2px 9px}
.xp{flex:1;height:8px;background:rgba(255,255,255,.25);border-radius:4px;overflow:hidden}
.xp span{display:block;height:100%;background:linear-gradient(90deg,#ffd43b,#ff922b);transition:width .4s}
.stats{display:grid;grid-template-columns:repeat(3,1fr);gap:6px;text-align:center;font-size:13px;margin-top:10px}
.stats div{background:rgba(255,255,255,.14);border-radius:10px;padding:5px 2px}
.stats b{display:block;font-size:15px}
.tabs,.tool{display:flex;gap:5px;margin-bottom:8px}
.tabs button,.tool button{flex:1;background:var(--card);color:var(--tx);border:1px solid var(--bd);border-radius:12px;padding:8px 2px;font-size:12px;line-height:1.3}
.tabs button{font-size:14px;padding:10px 2px}
.tabs button.on,.tool button.on{background:linear-gradient(135deg,var(--ac),var(--ac2));color:#fff;border-color:transparent;box-shadow:0 4px 12px rgba(2,136,209,.35)}
.grid{display:grid;grid-template-columns:repeat(8,1fr);gap:1px;background:var(--bd);padding:3px;border-radius:14px;touch-action:none;box-shadow:0 6px 20px rgba(0,0,0,.18)}
.grid div{position:relative;aspect-ratio:1;display:flex;align-items:center;justify-content:center;font-size:clamp(16px,6vw,28px);user-select:none;box-shadow:inset 0 0 6px rgba(0,0,0,.12)}
.grid div.a{background:var(--g1)}.grid div.b{background:var(--g2)}
.grid div.w{background:var(--w);animation:wv 3s ease-in-out infinite}
.grid div.fo{background:var(--fo)}
@keyframes wv{50%{filter:brightness(1.15)}}
.grid i{position:absolute;bottom:0;font-size:8px;font-style:normal;color:#ffd43b;text-shadow:0 0 3px #000}
.pop{animation:pop .35s ease-out}
@keyframes pop{0%{transform:scale(.2) rotate(-12deg)}60%{transform:scale(1.35)}100%{transform:scale(1)}}
.fx{position:absolute;pointer-events:none;font-size:16px;animation:fl .8s ease-out forwards}
@keyframes fl{from{transform:translateY(0);opacity:1}to{transform:translateY(-34px);opacity:0}}
.en{display:flex;align-items:center;gap:10px;padding:10px 0;border-top:1px solid var(--bd)}
.en:first-child{border-top:0}
.en .f{font-size:32px;filter:drop-shadow(0 2px 3px rgba(0,0,0,.3))}
.en>div{flex:1}
.bar{height:7px;background:var(--bd);border-radius:4px;margin:4px 0;overflow:hidden}
.bar span{display:block;height:100%;background:linear-gradient(90deg,#fa5252,#fcc419,#51cf66)}
.en button{background:linear-gradient(135deg,#e03131,#c2255c);color:#fff;border:0;border-radius:12px;padding:10px 14px;box-shadow:0 4px 10px rgba(224,49,49,.4)}
.shake{animation:sh .4s}
@keyframes sh{20%{transform:translateX(-6px)}40%{transform:translateX(6px)}60%{transform:translateX(-4px)}80%{transform:translateX(4px)}}
.cfg{display:flex;gap:6px;flex-wrap:wrap;margin:8px 0}
.cfg button{flex:1;min-width:30%;background:var(--card);color:var(--tx);border:1px solid var(--bd);border-radius:10px;padding:9px 6px;font-size:13px}
.cfg button.on{background:var(--ac);color:#fff;border-color:var(--ac)}
.cfg .dn{background:var(--bad);color:#fff;border-color:var(--bad)}
.code{display:flex;gap:6px;margin-top:8px}
.code input{flex:1;min-width:0;padding:10px;border-radius:10px;border:1px solid var(--bd);background:var(--bg);color:var(--tx)}
.code button{background:linear-gradient(135deg,#f59f00,#e8590c);color:#fff;border:0;border-radius:10px;padding:10px 16px;font-weight:600}
.cont{background:linear-gradient(135deg,var(--ac),var(--ac2));color:#fff;border:0;border-radius:14px;padding:13px 18px;width:100%;margin-top:12px;font-weight:600}
#toast{position:fixed;left:50%;bottom:calc(16px + env(safe-area-inset-bottom,0px));transform:translate(-50%,30px);background:#212529;color:#fff;padding:11px 18px;border-radius:22px;font-size:14px;opacity:0;transition:.3s;max-width:90%;text-align:center;pointer-events:none;box-shadow:0 6px 20px rgba(0,0,0,.4);z-index:9}
#toast.s{opacity:1;transform:translate(-50%,0)}
.big{display:block;width:100%;text-align:left;border:0;border-radius:18px;padding:18px;margin-bottom:12px;color:#fff;font-size:17px;box-shadow:0 8px 22px rgba(0,0,0,.25)}
.big small{display:block;opacity:.9;font-size:13px;margin-top:4px;font-weight:400}
.big.pu{background:linear-gradient(135deg,#1971c2,#7048e8)}.big.se{background:linear-gradient(135deg,#2f9e44,#0b7285)}
.search,.nm{width:100%;padding:11px;border-radius:12px;border:1px solid var(--bd);background:var(--bg);color:var(--tx);margin-top:8px}
.bk{background:none;border:1px solid var(--bd);color:var(--tx);border-radius:8px;padding:3px 10px}
.sv{margin-top:8px;font-size:12px;background:rgba(255,255,255,.18);border-radius:8px;padding:5px 8px}
.srv{display:flex;align-items:center;justify-content:space-between;padding:9px 0;border-top:1px solid var(--bd)}
.srv:first-child{border-top:0}
.srv button{background:var(--ac);color:#fff;border:0;border-radius:10px;padding:8px 14px}
.srv button:disabled{background:var(--bd)}
.btns{display:flex;flex-direction:column;gap:5px}
.en button.al{background:linear-gradient(135deg,#2f9e44,#0b7285);box-shadow:0 4px 10px rgba(11,114,133,.4)}
.cl button:disabled{opacity:.45}
</style></head><body>
<div id="app"></div><div id="toast"></div>
<script>
var CS=[
{n:"Indonesia",f:"🇮🇩",m:600,a:30,p:40,d:"Seimbang, penduduk banyak"},
{n:"Jepang",f:"🇯🇵",m:900,a:25,p:30,d:"Kaya, ekonomi kuat"},
{n:"Amerika",f:"🇺🇸",m:800,a:60,p:40,d:"Militer terkuat"},
{n:"Rusia",f:"🇷🇺",m:500,a:70,p:30,d:"Tentara besar, kas tipis"},
{n:"Brasil",f:"🇧🇷",m:600,a:30,p:45,d:"Lahan subur"},
{n:"Mesir",f:"🇪🇬",m:450,a:35,p:35,d:"Negara berkembang"},
{n:"Jerman",f:"🇩🇪",m:850,a:35,p:30,d:"Industri maju"},
{n:"Tiongkok",f:"🇨🇳",m:700,a:55,p:50,d:"Populasi raksasa"}];
var CL="AF:Afganistan,AL:Albania,DZ:Aljazair,AD:Andorra,AO:Angola,AG:Antigua dan Barbuda,AR:Argentina,AM:Armenia,AU:Australia,AT:Austria,AZ:Azerbaijan,BS:Bahama,BH:Bahrain,BD:Bangladesh,BB:Barbados,BY:Belarus,BE:Belgia,BZ:Belize,BJ:Benin,BT:Bhutan,BO:Bolivia,BA:Bosnia dan Herzegovina,BW:Botswana,BN:Brunei,BG:Bulgaria,BF:Burkina Faso,BI:Burundi,KH:Kamboja,CM:Kamerun,CA:Kanada,CV:Tanjung Verde,CF:Afrika Tengah,TD:Chad,CL:Cile,CO:Kolombia,KM:Komoro,CG:Kongo,CD:RD Kongo,CR:Kosta Rika,CI:Pantai Gading,HR:Kroasia,CU:Kuba,CY:Siprus,CZ:Ceko,DK:Denmark,DJ:Djibouti,DM:Dominika,DO:Republik Dominika,EC:Ekuador,SV:El Salvador,GQ:Guinea Ekuatorial,ER:Eritrea,EE:Estonia,SZ:Eswatini,ET:Etiopia,FJ:Fiji,FI:Finlandia,FR:Prancis,GA:Gabon,GM:Gambia,GE:Georgia,GH:Ghana,GR:Yunani,GD:Grenada,GT:Guatemala,GN:Guinea,GW:Guinea-Bissau,GY:Guyana,HT:Haiti,HN:Honduras,HU:Hungaria,IS:Islandia,IN:India,IR:Iran,IQ:Irak,IE:Irlandia,IL:Israel,IT:Italia,JM:Jamaika,JO:Yordania,KZ:Kazakhstan,KE:Kenya,KI:Kiribati,KP:Korea Utara,KR:Korea Selatan,KW:Kuwait,KG:Kirgistan,LA:Laos,LV:Latvia,LB:Lebanon,LS:Lesotho,LR:Liberia,LY:Libya,LI:Liechtenstein,LT:Lituania,LU:Luksemburg,MG:Madagaskar,MW:Malawi,MY:Malaysia,MV:Maladewa,ML:Mali,MT:Malta,MH:Kepulauan Marshall,MR:Mauritania,MU:Mauritius,MX:Meksiko,FM:Mikronesia,MD:Moldova,MC:Monako,MN:Mongolia,ME:Montenegro,MA:Maroko,MZ:Mozambik,MM:Myanmar,NA:Namibia,NR:Nauru,NP:Nepal,NL:Belanda,NZ:Selandia Baru,NI:Nikaragua,NE:Niger,NG:Nigeria,MK:Makedonia Utara,NO:Norwegia,OM:Oman,PK:Pakistan,PW:Palau,PS:Palestina,PA:Panama,PG:Papua Nugini,PY:Paraguay,PE:Peru,PH:Filipina,PL:Polandia,PT:Portugal,QA:Qatar,RO:Rumania,RW:Rwanda,KN:Saint Kitts dan Nevis,LC:Saint Lucia,VC:Saint Vincent,WS:Samoa,SM:San Marino,ST:Sao Tome dan Principe,SA:Arab Saudi,SN:Senegal,RS:Serbia,SC:Seychelles,SL:Sierra Leone,SG:Singapura,SK:Slovakia,SI:Slovenia,SB:Kepulauan Solomon,SO:Somalia,ZA:Afrika Selatan,SS:Sudan Selatan,ES:Spanyol,LK:Sri Lanka,SD:Sudan,SR:Suriname,SE:Swedia,CH:Swiss,SY:Suriah,TJ:Tajikistan,TZ:Tanzania,TH:Thailand,TL:Timor Leste,TG:Togo,TO:Tonga,TT:Trinidad dan Tobago,TN:Tunisia,TR:Turki,TM:Turkmenistan,TV:Tuvalu,UG:Uganda,UA:Ukraina,AE:Uni Emirat Arab,GB:Inggris,UY:Uruguay,UZ:Uzbekistan,VU:Vanuatu,VA:Vatikan,VE:Venezuela,VN:Vietnam,YE:Yemen,ZM:Zambia,ZW:Zimbabwe";
function flag(c){return String.fromCodePoint.apply(null,c.split("").map(function(x){return 127397+x.charCodeAt(0)}))}
function hs(t){var h=7;for(var i=0;i<t.length;i++)h=(h*31+t.charCodeAt(i))>>>0;return h}
(function(){var skip="ID JP US RU BR EG DE CN",x=[];
CL.split(",").forEach(function(e){var c=e.slice(0,2),n=e.slice(3);if(skip.indexOf(c)>=0)return;
var m=400+hs(c+"m")%600,a=20+hs(c+"a")%50,p=25+hs(c+"p")%25;
x.push({n:n,f:flag(c),m:m,a:a,p:p,d:a>=55?"Militer kuat":m>=850?"Kaya, ekonomi kuat":p>=42?"Penduduk banyak":"Seimbang"})});
x.sort(function(a,b){return a.n.localeCompare(b.n,"id")});CS=CS.concat(x)})();
var B={h:{e:"🏠",n:"Rumah",c:100},f:{e:"🌾",n:"Ladang",c:80},p:{e:"🏭",n:"Pabrik",c:150},b:{e:"🏰",n:"Barak",c:200},r:{e:"🛣️",n:"Jalan",c:15},x:{e:"💣",n:"Bongkar",c:0}};
var S=null,tab="b",timer=null,painting=false,tt=null,mem={},CFG={auto:true,theme:"auto"};
var $=function(i){return document.getElementById(i)};
function ls(k,v){try{if(v===undefined)return localStorage.getItem(k);if(v===null)localStorage.removeItem(k);else localStorage.setItem(k,v);return 1}catch(e){if(v===undefined)return mem[k]||null;if(v===null)delete mem[k];else mem[k]=v;return 0}}
function toast(t){var e=$("toast");e.textContent=t;e.className="s";clearTimeout(tt);tt=setTimeout(function(){e.className=""},2600)}
function fmt(n){n=Math.floor(n);var u=[[1e12," T"],[1e9," M"],[1e6," Jt"],[1e3," Rb"]];for(var i=0;i<4;i++)if(n>=u[i][0])return(n/u[i][0]).toFixed(1).replace(".0","")+u[i][1];return""+n}
function save(){if(S&&S.mode=="pub")cloudSave()}
function saveCfg(){ls("negara_cfg",JSON.stringify(CFG))}
function load(){
  try{var c=JSON.parse(ls("negara_cfg"));if(c)CFG=c}catch(e){}
  try{var s=JSON.parse(ls("negara3")||ls("negara2"));if(s&&s.lv&&s.ter){s.xp=s.xp||0;s.lvl=s.lvl||1;return s}}catch(e){}
  return null;
}
function applyTheme(){var r=document.documentElement;if(CFG.theme=="auto")r.removeAttribute("data-theme");else r.setAttribute("data-theme",CFG.theme)}
function pick(i,pub){
  var c=CS[i],ter=[];
  for(var k=0;k<64;k++){var r=Math.random();ter.push(r<.1?1:r<.28?2:0)}
  S={c:i,m:c.m,food:100,pop:c.p,army:c.a,t:Array(64).fill(""),lv:Array(64).fill(1),ter:ter,day:1,land:1,sel:"h",spd:1,xp:0,lvl:1,
   mode:"self",en:rndEn(i)};
  if(pub)return S;tab="b";start();
}
function rndEn(i){var ix=[],k;for(k=0;k<CS.length;k++)if(k!=i)ix.push(k);for(k=ix.length-1;k>0;k--){var j=Math.floor(Math.random()*(k+1)),t=ix[k];ix[k]=ix[j];ix[j]=t}return ix.slice(0,5).map(function(c,j){return{n:CS[c].n,f:CS[c].f,pw:20+Math.floor(Math.random()*20)+j*12}})}
function nb(i){var r=[],x=i%8;if(i>7)r.push(i-8);if(i+8<S.t.length)r.push(i+8);if(x>0)r.push(i-1);if(x<7)r.push(i+1);return r}
function mult(i){var m=1+0.5*(S.lv[i]-1);if(nb(i).some(function(j){return S.t[j]=="r"}))m*=1.25;return m}
function sum(k){var s=0;for(var i=0;i<S.t.length;i++)if(S.t[i]==k)s+=mult(i);return s}
function cap(){return 20+Math.floor(sum("h")*10)}
function addXp(n){
  S.xp+=n;
  while(S.xp>=S.lvl*100){S.xp-=S.lvl*100;S.lvl++;S.m+=100*S.lvl;toast("🏆 LEVEL UP! Level "+S.lvl+" (bonus "+100*S.lvl+" uang)")}
}
function tick(){
  var f=sum("f"),p=sum("p"),b=sum("b");
  S.day++;
  var gross=p*8+S.pop*0.3+(S.land-1)*6;
  S.m+=gross-Math.min(S.army*0.2,gross*0.5);
  S.food+=f*6-S.pop*0.2;
  if(S.food<0){S.food=0;S.pop=Math.max(5,S.pop-2)}
  else if(S.pop<cap())S.pop=Math.min(cap(),S.pop+2);
  if(b>0&&S.m>=b*3){S.army+=b;S.m-=b*3}
  S.en.forEach(function(e){e.pw+=0.15});
  if(S.day%12==0)event();
  if(S.day%10==0)addXp(5);
  if(CFG.auto&&S.day%10==0)save();
  stats();
}
function event(){
  var r=Math.floor(Math.random()*5);if(r==4&&!S.en.length)r=0;
  if(r==0){S.food+=80;toast("🌾 Panen raya! +80 makanan")}
  else if(r==1){var l=Math.floor(S.m*0.15);S.m-=l;toast("🌊 Banjir melanda! -"+fmt(l)+" uang")}
  else if(r==2){S.m+=200;toast("💼 Investor asing datang! +200 uang")}
  else if(r==3){var d=Math.floor(S.pop*0.1);S.pop-=d;toast("🦠 Wabah menyebar! -"+d+" penduduk")}
  else{
    var e=S.en[Math.floor(Math.random()*S.en.length)];
    if(S.army*1.2>=e.pw){var g=Math.floor(e.pw*4);S.m+=g;toast("🛡️ Serangan "+e.n+" berhasil ditahan! +"+g+" uang")}
    else{var l2=Math.floor(S.m*0.2);S.m-=l2;S.pop=Math.max(5,S.pop-5);S.army=Math.floor(S.army*0.8);toast("🔥 "+e.n+" menyerangmu! -"+fmt(l2)+" uang, pasukan berkurang")}
  }
}
function stats(){
  var el=$("st");if(!el)return;
  el.innerHTML=[["💰",fmt(S.m)],["🌾",fmt(S.food)],["👥",Math.floor(S.pop)+"/"+cap()],["⚔️",fmt(S.army)],["🗺️",S.land+" wilayah"],["📅","Hari "+S.day]]
   .map(function(x){return"<div>"+x[0]+"<b>"+x[1]+"</b></div>"}).join("");
  svUpd();var lv=$("lv");if(lv)lv.innerHTML="<b>Lv "+S.lvl+"</b><div class=xp><span style='width:"+Math.min(100,S.xp/(S.lvl*100)*100)+"%'></span></div><span>"+S.xp+"/"+S.lvl*100+" XP</span>";
}
function cell(i){var x=S.t[i];return x?B[x].e+(S.lv[i]>1?"<i>"+"★".repeat(S.lv[i]-1)+"</i>":""):(S.ter[i]==1?"🌊":S.ter[i]==2?"🌲":"")}
function cls(i){return(S.ter[i]==1?"w":S.ter[i]==2&&!S.t[i]?"fo":((i%8+Math.floor(i/8))%2?"a":"b"))}
function upd(i,anim,fx){
  var el=document.querySelector('[data-i="'+i+'"]');if(!el)return;
  el.innerHTML=cell(i);el.className=cls(i);
  if(anim){void el.offsetWidth;el.classList.add("pop")}
  if(fx){var s=document.createElement("b");s.className="fx";s.textContent=fx;el.appendChild(s);setTimeout(function(){s.remove()},800)}
  stats();
}
function build(i,drag){
  var k=S.sel,t=S.t[i];
  if(S.ter[i]==1){if(!drag)toast("Air tidak bisa dibangun");return}
  if(k=="x"){if(t){S.t[i]="";S.lv[i]=1;S.m+=30;upd(i,false,"💥")}return}
  if(t){
    if(drag)return;
    if(t==k&&k!="r"){
      var c=Math.floor(B[k].c*S.lv[i]*1.5);
      if(S.lv[i]>=3)toast("Sudah level maksimal");
      else if(S.m<c)toast("Upgrade butuh "+fmt(c)+" uang");
      else{S.m-=c;S.lv[i]++;upd(i,true,"⬆️");addXp(15);toast("⬆️ "+B[k].n+" naik level "+S.lv[i])}
    }else toast("Petak terisi (pilih bangunan sama untuk upgrade)");
    return;
  }
  var cost=B[k].c+(S.ter[i]==2?20:0);
  if(S.m<cost){if(!drag)toast("Uang tidak cukup ("+cost+")");return}
  S.m-=cost;S.t[i]=k;S.lv[i]=1;S.ter[i]=0;upd(i,true,"✨");addXp(5);
}
function hit(e,drag){
  var el=document.elementFromPoint(e.clientX,e.clientY);
  if(el&&(el.tagName=="I"||el.tagName=="B"))el=el.parentNode;
  if(el&&el.dataset&&el.dataset.i!==undefined)build(+el.dataset.i,drag);
}
function attack(i,btn){
  var e=S.en[i];
  if(S.army<5){toast("Pasukan terlalu sedikit. Bangun Barak dulu.");return}
  btn.closest(".en").classList.add("shake");
  setTimeout(function(){
    if(Math.random()<S.army/(S.army+e.pw)){
      var loss=Math.floor(e.pw*0.3),gain=Math.floor(e.pw*10);
      S.army=Math.max(0,S.army-loss);S.m+=gain;S.land++;e.pw=Math.max(15,e.pw*0.7);addXp(40);
      toast("🎉 Menang lawan "+e.n+"! +"+fmt(gain)+" uang, +1 wilayah");
    }else{
      var l=Math.floor(S.army*0.5);S.army-=l;
      toast("💥 Kalah dari "+e.n+"! Pasukan hilang "+fmt(l));
    }
    render();
  },400);
}
function redeem(){
  var v=$("code").value.trim().toLowerCase();
  if(!v){toast("Masukkan kode dulu");return}
  if(v!="azfermodz"){toast("❌ Kode tidak valid");return}
  var R={};try{R=JSON.parse(ls("negara_redeem"))||{}}catch(e){}
  if(R.azfermodz||S.rd){toast("⚠️ Kode ini sudah pernah diklaim");return}
  R.azfermodz=1;S.rd=1;ls("negara_redeem",JSON.stringify(R));
  S.m+=1e11;S.army+=5e11;save();stats();$("code").value="";
  toast("🎁 Berhasil! +100 Miliar uang, +500 Miliar pasukan");
}
function setSpd(n){if(S.mode=="pub"&&n==0)n=1;S.spd=n;clearInterval(timer);if(n)timer=setInterval(tick,n==2?600:1500);render()}
function doSave(){cloudSave();toast("💾 Progres disimpan (Level "+S.lvl+", Hari "+S.day+")")}
function doLoad(){if(S.mode=="pub"){toast("Muat data tidak tersedia di server public");return}var s=load();if(!s){toast("Belum ada data tersimpan");return}S=s;toast("📂 Data dimuat (Level "+S.lvl+")");start()}
function doDel(){ls("negara3",null);ls("negara2",null);toast("🗑️ Data simpanan dihapus");render()}
function setTheme(t){CFG.theme=t;saveCfg();applyTheme();render()}
function toggleAuto(){CFG.auto=!CFG.auto;saveCfg();render()}
function render(){
  var c=CS[S.c],h="";
  h+="<div class='card head'><div class=top><b style='font-size:19px'>"+c.f+" "+c.n+"</b><span>"+
   [["⏸",0],["▶",1],["⏩",2]].map(function(x){return"<button class='"+(S.spd==x[1]?"on":"")+"' onclick=setSpd("+x[1]+")>"+x[0]+"</button>"}).join("")+
   "<button onclick=menu()>🌍</button></span></div>"+(S.mode=="pub"?"<div class=sv id=sv></div>":"")+"<div class=lv id=lv></div><div class=stats id=st></div></div>";
  h+="<div class=tabs>"+[["b","🏗️ Bangun"],["w","⚔️ Perang"],["c","⚙️ Config"]].map(function(x){return"<button class='"+(tab==x[0]?"on":"")+"' onclick=\"tab='"+x[0]+"';render()\">"+x[1]+"</button>"}).join("")+"</div>";
  if(tab=="b"){
    h+="<div class=tool>"+Object.keys(B).map(function(k){return"<button class='"+(S.sel==k?"on":"")+"' onclick=\"S.sel='"+k+"';render()\">"+B[k].e+"<br>"+B[k].n+"<br>"+(B[k].c||"+30")+"</button>"}).join("")+"</div>";
    h+="<div class=grid id=grid>"+S.t.map(function(x,i){return"<div data-i="+i+" class="+cls(i)+">"+cell(i)+"</div>"}).join("")+"</div>";
    h+="<p class=mu>Geser jari untuk membangun banyak petak. Tap bangunan yang sama untuk upgrade (maks ★★). Jalan di samping bangunan memberi bonus +25%.</p>";
  }else if(tab=="w"&&S.mode=="pub"){h+=pubWar();}else if(tab=="w"){
    h+="<div class=card>"+S.en.map(function(e,i){var ch=Math.round(S.army/(S.army+e.pw)*100);return"<div class=en><span class=f>"+e.f+"</span><div><b>"+e.n+"</b> <span class=mu>kekuatan "+fmt(e.pw)+"</span><div class=bar><span style='width:"+ch+"%'></span></div><span class=mu>Peluang menang "+ch+"%</span></div><button onclick=attack("+i+",this)>⚔️ Serang</button></div>"}).join("")+"</div>";
  }else{
    h+="<div class=card><b>💾 Local Config</b><p class=mu>Progres, level, dan pengaturan disimpan di perangkat ini.</p><div class=cfg>"+
     "<button onclick=doSave()>💾 Simpan ke akun</button><button onclick=changeScreen()>🏳️ Ganti negara</button><button class=dn onclick=logout()>🚪 Keluar akun</button></div>"+
     (S.mode=="pub"?"<div class=cfg><button class=dn onclick=menu()>🚪 Keluar dari server</button></div>":"")+"<div class=cfg><button class='"+(CFG.auto?"on":"")+"' onclick=toggleAuto()>Auto-simpan: "+(CFG.auto?"ON":"OFF")+"</button></div>"+
     "<div class=cfg>"+[["auto","🌓 Otomatis"],["light","☀️ Terang"],["dark","🌙 Gelap"]].map(function(x){return"<button class='"+(CFG.theme==x[0]?"on":"")+"' onclick=setTheme('"+x[0]+"')>"+x[1]+"</button>"}).join("")+"</div></div>"+
     "<div class=card><b>🎁 Redeem Code</b><p class=mu>Masukkan kode hadiah. Setiap kode hanya bisa diklaim 1 kali.</p><div class=code><input id=code placeholder='Masukkan kode' autocomplete=off autocapitalize=off><button onclick=redeem()>Klaim</button></div></div>";
  }
  $("app").innerHTML=h;stats();
  var g=$("grid");
  if(g){
    g.onpointerdown=function(e){painting=true;hit(e,false)};
    g.onpointermove=function(e){if(painting)hit(e,true)};
    g.onpointerup=g.onpointercancel=function(){painting=false};
  }
}
function start(){clearInterval(timer);render();if(S.spd)timer=setInterval(tick,S.spd==2?600:1500)}
var CH="join",PEND=null,TAKEN={},ACC=null,DB=true,uid=null,PL=[],hb=null,sig="",ACT=25000,errShown=false,tick5=0,seenReq={};
var API="https://data-base-fazxy.lovable.app/api/public/v1",KEY="dk_e160867ebfcd422ab19e9cf7942d7d7c";
function esc(t){return String(t).replace(/[&<>"']/g,function(c){return{"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"}[c]})}
async function api(method,path,body){
  var h={"x-api-key":KEY};if(body)h["Content-Type"]="application/json";
  var r=await fetch(API+path,{method:method,headers:h,body:body?JSON.stringify(body):undefined});
  var t=await r.text();
  if(!r.ok){var er=new Error("HTTP "+r.status+" "+t.slice(0,100));er.status=r.status;throw er}
  try{return JSON.parse(t)}catch(e){return null}
}
function nrm(r){
  var g=r.game_stats;if(typeof g=="string"){try{g=JSON.parse(g)}catch(e){g=null}}g=g||{};
  return{rid:r.id!==undefined?r.id:r._id,uid:r.player_id,sid:r.server_code,name:r.name||"Pemain",cname:r.country,lvl:+r.level||1,m:+r.money||0,
   seen:+g.seen||Date.parse(r.last_active)||0,army:+g.army||0,land:+g.land||1,joinedAt:+g.joinedAt||0,lastHit:g.lastHit||null,
   allies:Array.isArray(g.allies)?g.allies:[],tag:g.tag||"",ph:g.ph,save:g.save,gs:g}
}
async function rows(sc){
  var j=await api("GET","/players"+(sc?"?server_code="+encodeURIComponent(sc):"")),l=Array.isArray(j)?j:(j&&(j.data||j.rows||j.items))||[];
  var o=l.map(nrm);return sc?o.filter(function(x){return x.sid==sc}):o;
}
async function sha(t){try{var b=await crypto.subtle.digest("SHA-256",new TextEncoder().encode(t));return Array.from(new Uint8Array(b)).map(function(x){return("0"+x.toString(16)).slice(-2)}).join("")}catch(e){return"w"+hs(t)+hs(t+"x")}}
function dn(){return ACC.name+"#"+ACC.tag}
function setAcc(x){ACC={id:x.uid,name:x.name,tag:x.tag,ph:x.ph,rid:x.rid};CFG.name=dn();uid=ACC.id;ls("negara_acc",JSON.stringify({id:ACC.id,ph:ACC.ph}))}
function loading(t){$("app").innerHTML="<div class=hero><h1>"+t+"</h1><p>Mohon tunggu</p></div>"}
async function boot(){
  loading("🌍 Memuat...");
  var sv=null;try{sv=JSON.parse(ls("negara_acc"))}catch(e){}
  if(sv){try{var x=(await rows("ACC")).filter(function(r){return r.uid==sv.id&&r.ph==sv.ph})[0];if(x){setAcc(x);return lobby()}}catch(e){toast("Tidak bisa terhubung: "+e.message)}}
  authScreen("login");
}
function authScreen(m){
  var r=m=="reg";
  $("app").innerHTML="<div class=hero><h1><span class=globe>🌍</span> GAME NEGARA</h1><p>Server Public · lawan pemain online</p></div><div class=card><b>"+(r?"Buat akun baru":"Masuk akun")+"</b>"+
   "<input id=au class=nm "+(r?"maxlength=14 placeholder='Username (3-14 huruf/angka)'":"placeholder='Username#1234'")+" autocomplete=off autocapitalize=off>"+
   "<input id=ap class=nm type=password placeholder='Password (min. 6 karakter)'>"+
   "<button class=cont onclick="+(r?"register()":"login()")+">"+(r?"Daftar":"Masuk")+"</button>"+
   "<p class=mu style='text-align:center'>"+(r?"Sudah punya akun? <a href=# onclick=\"authScreen('login');return false\">Masuk</a>":"Belum punya akun? <a href=# onclick=\"authScreen('reg');return false\">Daftar</a>")+"</p>"+
   (r?"<p class=mu>Username boleh sama dengan orang lain. Setiap akun otomatis dapat kode unik (contoh Budi#4821) dan dikunci password, jadi tidak bisa diambil orang lain. Catat kodenya.</p>":"")+"</div>";
}
async function register(){
  var u=$("au").value.trim(),p=$("ap").value;
  if(!/^[A-Za-z0-9_ ]{3,14}$/.test(u)){toast("Username 3-14 karakter: huruf, angka, spasi, _");return}
  if(p.length<6){toast("Password minimal 6 karakter");return}
  try{
    var ex=await rows("ACC"),tag,k=0;
    do{tag=""+(1000+Math.floor(Math.random()*9000));k++}while(k<8&&ex.some(function(x){return x.name.toLowerCase()==u.toLowerCase()&&x.tag==tag}));
    var id="AC"+Math.random().toString(36).slice(2,12),ph=await sha(id+":"+p);
    await api("POST","/players",{server_code:"ACC",player_id:id,name:u,country:"-",level:1,money:0,last_active:new Date().toISOString(),game_stats:{ph:ph,tag:tag,save:null}});
    var x=(await rows("ACC")).filter(function(r){return r.uid==id})[0];
    if(!x)throw new Error("akun tidak tersimpan");
    setAcc(x);toast("✅ Akun dibuat: "+dn()+" (catat kode ini!)");lobby();
  }catch(e){toast("Gagal daftar: "+e.message)}
}
async function login(){
  var v=$("au").value.trim(),p=$("ap").value,i=v.lastIndexOf("#");
  if(i<1){toast("Format: Username#1234");return}
  try{
    var n=v.slice(0,i).toLowerCase(),t=v.slice(i+1).trim();
    var x=(await rows("ACC")).filter(function(r){return r.name.toLowerCase()==n&&r.tag==t})[0];
    if(!x){toast("Akun tidak ditemukan");return}
    if(await sha(x.uid+":"+p)!=x.ph){toast("Password salah");return}
    setAcc(x);toast("Selamat datang, "+dn());lobby();
  }catch(e){toast("Gagal masuk: "+e.message)}
}
function logout(){
  clearInterval(timer);
  if(S&&S.mode=="pub"){cloudSave();leavePub()}
  S=null;ACC=null;ls("negara_acc",null);authScreen("login");
}
function menu(){clearInterval(timer);if(S&&S.mode=="pub"){cloudSave();leavePub()}S=null;lobby()}
function lobby(){
  $("app").innerHTML="<div class=hero><h1><span class=globe>🌍</span> GAME NEGARA</h1><p>Server Public · maks 10 pemain</p></div>"+
   "<div class=card><div class=top><span>👤 <b>"+esc(dn())+"</b></span><button class=bk onclick=logout()>Keluar</button></div></div>"+
   "<button class='big pu' onclick=\"goServer('auto')\">⚡ Cari Otomatis<small>Masuk server yang sedang ada pemainnya</small></button>"+
   "<div class=card><b>Gabung dengan ID Server</b><div class=code><input id=sid placeholder='S-XXXX' autocapitalize=characters autocomplete=off><button onclick=joinById()>Gabung</button></div><div class=cfg><button onclick=\"goServer('new')\">➕ Buat server baru</button></div></div>"+
   "<div class=card><div class=top><b>Daftar server</b><button class=bk onclick=refreshServers()>⟳</button></div><div id=sl class=mu>Memuat...</div></div>"+
   "<p><button class=bk onclick=testApi()>🔧 Tes koneksi</button> <span id=tr class=mu></span></p>";
  refreshServers();
}
async function testApi(){
  var el=$("tr");if(el)el.textContent="menguji...";
  try{var l=await rows();toast("✅ Terhubung ke Datakit ("+l.length+" baris)");if($("tr"))$("tr").textContent="OK · "+l.length+" baris"}
  catch(e){toast("❌ "+e.message);if($("tr"))$("tr").textContent=e.message}
}
function joinById(){var v=$("sid").value.trim().toUpperCase();if(!v){toast("Masukkan ID server");return}goServer(v)}
function pickSrv(id){goServer(id)}
function isAct(x){return x&&Date.now()-x.seen<ACT}
async function listServers(){
  var all=(await rows()).filter(function(x){return x.sid!="ACC"}),g={};
  all.forEach(function(x){if(isAct(x))g[x.sid]=(g[x.sid]||0)+1});
  all.filter(function(x){return Date.now()-x.seen>120000}).slice(0,5).forEach(function(x){api("DELETE","/players/"+x.rid).catch(function(){})});
  return Object.keys(g).map(function(k){return{id:k,n:g[k]}}).sort(function(a,b){return b.n-a.n});
}
async function refreshServers(){
  var el=$("sl");if(!el)return;
  try{
    var l=await listServers();el=$("sl");if(!el)return;
    el.innerHTML=l.length?l.map(function(x){return"<div class=srv><span>🖥️ <b>"+esc(x.id)+"</b> · "+x.n+"/10 pemain</span><button "+(x.n>=10?"disabled":"")+" onclick=pickSrv('"+esc(x.id)+"')>"+(x.n>=10?"Penuh":"Gabung")+"</button></div>"}).join(""):"Belum ada server aktif. Pakai Cari Otomatis untuk membuat yang baru.";
  }catch(e){if($("sl"))$("sl").textContent="Gagal memuat: "+e.message}
}
function takenMap(l){var t={};l.forEach(function(x){if(x.uid!=uid&&isAct(x)){var ci=CS.findIndex(function(c){return c.n==x.cname});if(ci>=0)t[ci]=x.name}});return t}
async function goServer(t){
  loading("🔎 Mencari server...");
  try{
    var all=(await rows()).filter(function(x){return x.sid!="ACC"}),act=all.filter(isAct),cnt={};
    act.forEach(function(x){cnt[x.sid]=(cnt[x.sid]||0)+1});
    var sid=t;
    if(sid=="auto"){var ks=Object.keys(cnt).filter(function(k){return cnt[k]<10}).sort(function(a,b){return cnt[b]-cnt[a]});sid=ks.length?ks[0]:"new"}
    if(sid=="new")sid="S-"+Math.random().toString(36).slice(2,6).toUpperCase();
    else if(!cnt[sid]){toast("Server "+sid+" tidak ditemukan atau kosong");return lobby()}
    else if(cnt[sid]>=10&&!act.some(function(x){return x.sid==sid&&x.uid==uid})){toast("Server penuh (10/10)");return lobby()}
    PEND={sid:sid};TAKEN=takenMap(act.filter(function(x){return x.sid==sid}));CH="join";countryScreen();
  }catch(e){toast("Gagal: "+e.message);lobby()}
}
function countryScreen(){
  var sid=CH=="join"?PEND.sid:S.sid;
  $("app").innerHTML="<div class=card><div class=top><b>"+(CH=="join"?"Pilih negara":"Ganti negara")+" · "+esc(sid)+"</b><button class=bk onclick="+(CH=="join"?"lobby()":"render()")+">←</button></div><p class=mu>Negara yang dipakai pemain lain dikunci 🔒 sampai pemainnya keluar atau ganti negara.</p><input id=q class=search placeholder='🔎 Cari negara (mis. jepang)' oninput=showList() autocomplete=off><p class=mu id=qc></p></div><div class=cl id=cl></div>";
  showList();
}
function showList(){
  var q=$("q").value.toLowerCase().trim(),h="",n=0;
  CS.forEach(function(c,i){if(c.n.toLowerCase().indexOf(q)<0)return;n++;var tk=TAKEN[i];h+="<button "+(tk?"disabled":"")+" onclick=chooseC("+i+")><span class=f>"+c.f+"</span><b>"+c.n+"</b><br><span class=mu>"+(tk?"🔒 "+esc(tk):c.d)+"</span></button>"});
  $("cl").innerHTML=h||"<p class=mu>Negara tidak ditemukan</p>";$("qc").textContent=n+" negara";
}
function chooseC(i){if(CH=="change")doChange(i);else joinPub(i)}
async function changeScreen(){
  try{TAKEN=takenMap(await rows(S.sid));CH="change";countryScreen()}catch(e){toast("Gagal: "+e.message)}
}
async function doChange(i){
  try{
    var tk=takenMap(await rows(S.sid))[i];
    if(tk){toast("Negara itu dipakai "+tk);TAKEN=takenMap(await rows(S.sid));return countryScreen()}
    S.c=i;tab="b";await pollNet();render();toast("🏳️ Sekarang kamu memakai "+CS[i].n);
  }catch(e){toast("Gagal: "+e.message)}
}
function pack(){return{c:S.c,m:S.m,food:S.food,pop:S.pop,army:S.army,day:S.day,land:S.land,xp:S.xp,lvl:S.lvl,
  t:S.t.map(function(x){return x||"."}).join(""),lv:S.lv.join(""),ter:S.ter.join(""),al:S.allies||[],rd:S.rd?1:0}}
function unpack(v){
  try{
    if(!v||typeof v.t!="string"||v.t.length%8||v.lv.length!=v.t.length||v.ter.length!=v.t.length)return null;
    return{c:v.c,m:+v.m,food:+v.food,pop:+v.pop,army:+v.army,day:+v.day,land:+v.land,xp:+v.xp,lvl:+v.lvl,
     t:v.t.split("").map(function(x){return x=="."?"":x}),lv:v.lv.split("").map(Number),ter:v.ter.split("").map(Number),
     sel:"h",spd:1,allies:v.al||[],rd:v.rd,mode:"pub",en:[]}
  }catch(e){return null}
}
function ensureMap(){
  var need=(8+(S.land-1))*8;
  while(S.t.length<need){for(var k=0;k<8;k++){var r=Math.random();S.t.push("");S.lv.push(1);S.ter.push(r<.1?1:r<.28?2:0)}}
}
async function cloudSave(){
  if(!ACC||!ACC.rid||!S||S.mode!="pub")return;
  try{await api("PATCH","/players/"+ACC.rid,{level:S.lvl,money:Math.floor(S.m),last_active:new Date().toISOString(),game_stats:{ph:ACC.ph,tag:ACC.tag,save:pack()}})}catch(e){}
}
function myRow(now){return{server_code:S.sid,player_id:uid,name:ACC.name,country:CS[S.c].n,level:S.lvl,money:Math.floor(S.m),last_active:new Date(now).toISOString(),
  game_stats:{army:Math.floor(S.army),land:S.land,joinedAt:S.joinedAt,seen:now,lastHit:S.myHit||null,allies:S.allies||[],tag:ACC.tag}}}
async function joinPub(ci){
  var sid=PEND.sid;loading("🔎 Masuk server...");
  try{
    var all=await rows(sid),act=all.filter(isAct),mine=all.filter(function(x){return x.uid==uid});
    var tk=takenMap(act)[ci];
    if(tk){toast("Negara itu baru dipakai "+tk);TAKEN=takenMap(act);return countryScreen()}
    if(act.length>=10&&!mine.some(isAct)){toast("Server penuh (10/10)");return lobby()}
    var ax=(await rows("ACC")).filter(function(r){return r.uid==uid})[0];
    S=unpack(ax&&ax.save)||pick(ci,true);
    S.c=ci;S.mode="pub";S.en=[];S.sid=sid;S.hitSeen=Date.now();S.spd=1;S.joinedAt=Date.now();S.rid=null;S.myHit=null;S.allies=S.allies||[];ensureMap();
    if(mine[0])await api("PATCH","/players/"+mine[0].rid,myRow(Date.now()));else await api("POST","/players",myRow(Date.now()));
    var l=(await rows(sid)).filter(isAct).sort(function(a,b){return a.joinedAt-b.joinedAt}),me=l.filter(function(x){return x.uid==uid})[0];
    var clash=l.filter(function(x){return x.uid!=uid&&x.cname==CS[ci].n&&(x.joinedAt<S.joinedAt||(x.joinedAt==S.joinedAt&&x.uid<uid))})[0];
    if(clash||l.indexOf(me)>=10){
      if(me)api("DELETE","/players/"+me.rid).catch(function(){});
      S=null;toast(clash?"Negara itu baru diambil "+clash.name:"Server penuh (10/10)");
      if(clash){TAKEN=takenMap(l);return countryScreen()}return lobby();
    }
    tab="b";errShown=false;tick5=0;startNet();start();
    toast("🌐 Masuk server "+sid);
  }catch(e){S=null;toast("Gagal terhubung: "+e.message);lobby()}
}
function relOf(x){
  var a=S.allies.indexOf(x.uid)>=0,b=x.allies.indexOf(uid)>=0;
  return a&&b?"ally":b?"in":a?"out":"none";
}
async function pollNet(){
  if(!S||S.mode!="pub")return;
  try{
    var now=Date.now();
    if(S.rid)await api("PATCH","/players/"+S.rid,myRow(now));
    var all=await rows(S.sid);PL=[];
    all.forEach(function(x){
      if(x.uid==uid){S.rid=x.rid;var h=x.lastHit;if(h&&h.t>(S.hitSeen||0)){S.hitSeen=h.t;S.myHit=h;S.army=Math.max(0,S.army-h.la);S.m=Math.max(0,S.m-h.loot);S.land=Math.max(1,S.land-(h.land||0));toast("🔥 "+h.by+" menyerangmu! -"+fmt(h.loot)+" uang, -"+fmt(h.la)+" pasukan")}}
      else if(isAct(x)){PL.push(x);if(relOf(x)=="in"&&!seenReq[x.uid]){seenReq[x.uid]=1;toast("🤝 "+x.name+" mengajak bersekutu (buka tab Perang)")}}
    });
    if(!S.rid)await api("POST","/players",myRow(now));
    if(++tick5%5==0)cloudSave();
    errShown=false;netChanged();
  }catch(e){if(!errShown){errShown=true;toast("Koneksi server bermasalah: "+e.message)}}
}
function startNet(){PL=[];sig="";clearInterval(hb);pollNet();hb=setInterval(pollNet,6000)}
function netChanged(){
  var g=PL.map(function(x){return x.uid+x.army+x.land+relOf(x)}).join("|");
  svUpd();
  if(g!=sig){sig=g;if(S&&S.mode=="pub"&&tab=="w"&&$("app"))render()}
}
function leavePub(){
  clearInterval(hb);hb=null;
  if(S&&S.rid)api("DELETE","/players/"+S.rid).catch(function(){});
  PL=[];
}
function svUpd(){var el=$("sv");if(el&&S&&S.mode=="pub")el.innerHTML="🌐 Server <b>"+esc(S.sid)+"</b> · "+(PL.length+1)+"/10 pemain · 🤝 "+PL.filter(function(x){return relOf(x)=="ally"}).length+" sekutu · 🗺️ "+S.t.length/8+" baris"}
function pubWar(){
  var me={uid:uid,name:ACC.name,tag:ACC.tag,c:CS.findIndex(function(c){return c.n==CS[S.c].n}),army:S.army,land:S.land,lvl:S.lvl,me:1};
  var all=PL.concat([me]).sort(function(a,b){return b.army-a.army});
  return"<div class=card><b>🏆 Peringkat · "+esc(S.sid)+"</b>"+all.map(function(p,i){
    var c=CS.filter(function(z){return z.n==p.cname})[0]||CS[p.c]||CS[0],bt="",rl=p.me?"":relOf(p),ix=PL.indexOf(p);
    if(!p.me){
      if(rl=="ally")bt="<button class=al onclick=ally("+ix+",'cut')>🤝 Putus</button>";
      else if(rl=="in")bt="<button class=al onclick=ally("+ix+",'acc')>✅ Terima</button><button onclick=attackP("+ix+",this)>⚔️ Serang</button>";
      else if(rl=="out")bt="<button class=al onclick=ally("+ix+",'cut')>⏳ Batal</button><button onclick=attackP("+ix+",this)>⚔️ Serang</button>";
      else bt="<button onclick=attackP("+ix+",this)>⚔️ Serang</button><button class=al onclick=ally("+ix+",'ask')>🤝 Ajak</button>";
    }
    return"<div class=en><span class=f>"+(p.me?CS[S.c].f:c.f)+"</span><div><b>"+(i+1)+". "+esc(p.name)+(p.tag?"#"+esc(p.tag):"")+(rl=="ally"?" 🤝":"")+"</b><br><span class=mu>"+(p.me?CS[S.c].n:esc(p.cname||""))+" · ⚔️ "+fmt(p.army)+" · 🗺️ "+p.land+" · Lv "+p.lvl+"</span></div><div class=btns>"+bt+"</div></div>"}).join("")+"</div>"+
    (PL.length?"":"<p class=mu>Menunggu pemain lain bergabung. Bagikan ID server <b>"+esc(S.sid)+"</b> ke temanmu.</p>");
}
function ally(i,act){
  var t=PL[i];if(!t)return;
  if(act=="cut"){S.allies=S.allies.filter(function(u){return u!=t.uid});toast("Aliansi dengan "+t.name+" dibatalkan")}
  else{if(S.allies.indexOf(t.uid)<0)S.allies.push(t.uid);toast(act=="ask"?"🤝 Ajakan dikirim ke "+t.name:"✅ Kamu bersekutu dengan "+t.name)}
  pollNet().then(render);
}
async function attackP(i,btn){
  var t=PL[i];if(!t)return;
  if(relOf(t)=="ally"){toast("Tidak bisa menyerang sekutu. Putus aliansi dulu.");return}
  if(S.army<5){toast("Pasukan terlalu sedikit. Bangun Barak dulu.");return}
  btn.closest(".en").classList.add("shake");
  try{
    var x=(await rows(S.sid)).filter(function(r){return r.uid==t.uid})[0];
    if(!isAct(x)){toast("Pemain sudah offline");return}
    if(Math.random()<S.army/(S.army+x.army+1)){
      var loot=Math.floor(x.m*0.1),la=Math.floor(x.army*0.4);
      S.army=Math.max(0,S.army-Math.floor(x.army*0.3));S.m+=loot;S.land++;ensureMap();addXp(60);
      await api("PATCH","/players/"+x.rid,{game_stats:Object.assign({},x.gs,{lastHit:{t:Date.now(),by:dn(),la:la,loot:loot,land:1}})});
      toast("🎉 Menang lawan "+x.name+"! +"+fmt(loot)+" uang, peta bertambah 1 baris");
    }else{
      var l=Math.floor(S.army*0.4);S.army-=l;toast("💥 Kalah dari "+x.name+"! Pasukan hilang "+fmt(l));
    }
  }catch(e){toast("Serangan gagal: "+e.message)}
  render();
}
document.addEventListener("visibilitychange",function(){if(document.hidden&&S&&CFG.auto)save()});
load();S=null;applyTheme();boot();
</script></body></html>

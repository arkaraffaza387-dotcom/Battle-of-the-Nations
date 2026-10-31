
<html lang="id"><head><meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Battle of the Nations</title>
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
.hero h1{margin:0;font-size:24px;letter-spacing:1px;text-shadow:0 2px 8px rgba(0,0,0,.4)}
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
.tabs,.tool{display:flex;gap:5px;margin-bottom:8px;flex-wrap:wrap}
.tabs button,.tool button{flex:1;min-width:70px;background:var(--card);color:var(--tx);border:1px solid var(--bd);border-radius:12px;padding:8px 2px;font-size:12px;line-height:1.3}
.tabs button{font-size:14px;padding:10px 2px}
.tabs button.on,.tool button.on{background:linear-gradient(135deg,var(--ac),var(--ac2));color:#fff;border-color:transparent;box-shadow:0 4px 12px rgba(2,136,209,.35)}
.grid{display:grid;grid-template-columns:repeat(8,1fr);gap:1px;background:var(--bd);padding:3px;border-radius:14px;touch-action:none;box-shadow:0 6px 20px rgba(0,0,0,.18)}
.grid div{position:relative;aspect-ratio:1;display:flex;align-items:center;justify-content:center;font-size:clamp(14px,5.5vw,24px);user-select:none;box-shadow:inset 0 0 6px rgba(0,0,0,.12)}
.grid div.a{background:var(--g1)}.grid div.b{background:var(--g2)}
.grid div.w{background:var(--w);animation:wv 3s ease-in-out infinite}
.grid div.fo{background:var(--fo)}
.grid div.sel{outline:3px solid #ffd43b;outline-offset:-2px;z-index:1}
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
.wwrap{position:relative;width:min(300px,86vw);aspect-ratio:1;margin:18px auto}
.wheel{width:100%;height:100%;border-radius:50%;border:6px solid #fff;box-shadow:0 8px 24px rgba(0,0,0,.35),inset 0 0 20px rgba(0,0,0,.3);position:relative;transition:transform 4.2s cubic-bezier(.12,.7,.1,1)}
.wheel span{position:absolute;left:50%;top:50%;width:34px;height:34px;margin:-17px 0 0 -17px;font-size:26px;text-align:center;line-height:34px}
.ptr{position:absolute;top:-16px;left:50%;transform:translateX(-50%);font-size:32px;z-index:2;color:#ffd43b;text-shadow:0 2px 4px #000}
.big.wh{background:linear-gradient(135deg,#f59f00,#e8590c)}
.badge{background:#ffd43b;color:#5c3d00;border-radius:10px;padding:2px 9px;font-size:12px;font-weight:700}
/* Baru: konfirmasi & kategori bangunan */
.modal{position:fixed;inset:0;background:rgba(0,0,0,.55);display:flex;align-items:center;justify-content:center;z-index:20;padding:16px}
.modal .box{background:var(--card);border:1px solid var(--bd);border-radius:18px;padding:18px;max-width:360px;width:100%;box-shadow:0 12px 40px rgba(0,0,0,.35)}
.modal h3{margin:0 0 8px;font-size:18px}
.modal .acts{display:flex;gap:8px;margin-top:14px}
.modal .acts button{flex:1;padding:12px;border-radius:12px;border:0;font-weight:600}
.modal .acts .ok{background:linear-gradient(135deg,var(--ac),var(--ac2));color:#fff}
.modal .acts .no{background:var(--bd);color:var(--tx)}
.catbar{display:flex;gap:4px;overflow-x:auto;padding-bottom:6px;margin-bottom:6px;-webkit-overflow-scrolling:touch}
.catbar button{flex:0 0 auto;background:var(--card);color:var(--tx);border:1px solid var(--bd);border-radius:20px;padding:6px 12px;font-size:12px;white-space:nowrap}
.catbar button.on{background:linear-gradient(135deg,var(--ac),var(--ac2));color:#fff;border-color:transparent}
.bgrid{display:grid;grid-template-columns:repeat(4,1fr);gap:6px;margin-bottom:8px}
.bgrid button{background:var(--card);color:var(--tx);border:1px solid var(--bd);border-radius:12px;padding:8px 2px;font-size:11px;line-height:1.25;min-height:64px}
.bgrid button.on{background:linear-gradient(135deg,var(--ac),var(--ac2));color:#fff;border-color:transparent;box-shadow:0 4px 12px rgba(2,136,209,.35)}
.bgrid .ic{font-size:22px;display:block}
.satbar{height:10px;background:rgba(255,255,255,.25);border-radius:5px;overflow:hidden;margin-top:6px}
.satbar span{display:block;height:100%;transition:width .5s,background .5s}
.sat-label{font-size:12px;margin-top:4px;display:flex;justify-content:space-between}
.undo-btn{position:fixed;right:16px;bottom:calc(70px + env(safe-area-inset-bottom,0px));background:linear-gradient(135deg,#7048e8,#1971c2);color:#fff;border:0;border-radius:50%;width:52px;height:52px;font-size:22px;box-shadow:0 6px 18px rgba(25,113,194,.45);z-index:8;display:none}
.undo-btn.show{display:flex;align-items:center;justify-content:center}
.gameover{position:fixed;inset:0;background:rgba(0,0,0,.75);display:flex;align-items:center;justify-content:center;z-index:30;padding:20px}
.gameover .box{background:var(--card);border-radius:20px;padding:24px;max-width:360px;text-align:center}
.gameover h2{margin:0 0 10px;color:var(--bad)}
.detail{font-size:12px;color:var(--mu);margin-top:4px;line-height:1.4}
</style></head><body>
<div id="app"></div><div id="toast"></div>
<script>
/* ========== DATA NEGARA ========== */
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

/* ========== BANGUNAN LENGKAP ========== */
var B={
  /* Infrastruktur */
  h:{e:"🏠",n:"Rumah",c:100,cat:"infra",d:"Tempat tinggal dasar. +kapasitas penduduk, naik kepuasan."},
  ap:{e:"🏢",n:"Apartemen",c:280,cat:"infra",d:"Hunian padat. +banyak kapasitas penduduk."},
  r:{e:"🛣️",n:"Jalan",c:15,cat:"infra",d:"Bonus +25% ke bangunan di sampingnya."},
  jbr:{e:"🌉",n:"Jembatan",c:120,cat:"infra",d:"Menghubungkan wilayah. Bonus infrastruktur."},
  st:{e:"🚉",n:"Stasiun",c:220,cat:"infra",d:"Transportasi. Naik mobilitas & ekonomi."},
  bd:{e:"✈️",n:"Bandara",c:450,cat:"infra",d:"Pintu gerbang internasional. +uang besar."},
  pl:{e:"⚓",n:"Pelabuhan",c:380,cat:"infra",d:"Perdagangan laut. +uang & lapangan kerja."},
  tm:{e:"🚌",n:"Terminal",c:160,cat:"infra",d:"Transportasi darat. Naik kepuasan."},
  /* Industri & Ekonomi */
  f:{e:"🌾",n:"Ladang",c:80,cat:"eko",d:"Produksi makanan."},
  p:{e:"🏭",n:"Pabrik",c:150,cat:"eko",d:"Produksi uang & lapangan kerja."},
  gd:{e:"📦",n:"Gudang",c:130,cat:"eko",d:"Menyimpan hasil. Bonus efisiensi pabrik."},
  ps:{e:"🛒",n:"Pasar",c:140,cat:"eko",d:"Perdagangan lokal. +uang & kepuasan."},
  ml:{e:"🏬",n:"Mall",c:320,cat:"eko",d:"Pusat belanja. +uang & kepuasan tinggi."},
  bk:{e:"🏦",n:"Bank",c:300,cat:"eko",d:"Stabilisasi ekonomi. +uang pasif."},
  tb:{e:"⛏️",n:"Pertambangan",c:250,cat:"eko",d:"Sumber daya alam. +uang besar."},
  pt:{e:"🏢",n:"Pusat Dagang",c:350,cat:"eko",d:"Perdagangan internasional. +uang."},
  pr:{e:"🏗️",n:"Perusahaan",c:400,cat:"eko",d:"Korporasi besar. +uang & pekerjaan banyak."},
  /* Pendidikan & Kesehatan */
  sk:{e:"🏫",n:"Sekolah",c:180,cat:"edu",d:"Pendidikan dasar. +pendidikan & kepuasan."},
  un:{e:"🎓",n:"Universitas",c:420,cat:"edu",d:"Pendidikan tinggi. +pendidikan besar."},
  rs:{e:"🏥",n:"Rumah Sakit",c:300,cat:"edu",d:"Kesehatan utama. +kesehatan & kepuasan."},
  pk:{e:"🩺",n:"Puskesmas",c:160,cat:"edu",d:"Kesehatan dasar. +kesehatan."},
  lb:{e:"🔬",n:"Laboratorium",c:280,cat:"edu",d:"Penelitian. +pendidikan & inovasi."},
  /* Militer & Keamanan */
  b:{e:"🏰",n:"Barak",c:200,cat:"mil",d:"Melatih tentara. +pasukan."},
  mk:{e:"🎖️",n:"Markas Militer",c:450,cat:"mil",d:"Pusat komando. +pasukan & keamanan."},
  kp:{e:"👮",n:"Kantor Polisi",c:180,cat:"mil",d:"Keamanan dalam negeri. +keamanan."},
  pp:{e:"🛡️",n:"Pos Penjagaan",c:90,cat:"mil",d:"Pengamanan wilayah. +keamanan kecil."},
  pd:{e:"🏰",n:"Pusat Pertahanan",c:500,cat:"mil",d:"Pertahanan nasional. +keamanan & pasukan."},
  /* Pemerintahan */
  is:{e:"🏛️",n:"Istana Negara",c:600,cat:"gov",d:"Simbol kekuasaan. +kepuasan & prestise."},
  bc:{e:"🏢",n:"Balai Kota",c:250,cat:"gov",d:"Administrasi lokal. +kepuasan."},
  gp:{e:"🏛️",n:"Gedung Parlemen",c:480,cat:"gov",d:"Legislatif. Stabilitas politik."},
  kg:{e:"🏢",n:"Kantor Pemerintah",c:200,cat:"gov",d:"Birokrasi. Efisiensi negara."},
  gj:{e:"⚖️",n:"Gedung Pengadilan",c:280,cat:"gov",d:"Keadilan. +keamanan & kepuasan."},
  /* Hiburan & Fasilitas Umum */
  tk:{e:"🌳",n:"Taman Kota",c:100,cat:"fun",d:"Ruang hijau. +kepuasan tinggi."},
  sd:{e:"🏟️",n:"Stadion",c:350,cat:"fun",d:"Olahraga & hiburan. +kepuasan."},
  bi:{e:"🎬",n:"Bioskop",c:180,cat:"fun",d:"Hiburan. +kepuasan."},
  ms:{e:"🖼️",n:"Museum",c:220,cat:"fun",d:"Budaya. +kepuasan & pendidikan."},
  pb:{e:"📚",n:"Perpustakaan",c:150,cat:"fun",d:"Pengetahuan. +pendidikan & kepuasan."},
  tw:{e:"🏞️",n:"Tempat Wisata",c:280,cat:"fun",d:"Pariwisata. +uang & kepuasan."},
  /* Utility */
  x:{e:"💣",n:"Bongkar",c:0,cat:"util",d:"Hancurkan bangunan, dapat refund sebagian."}
};
var CATS=[
  {id:"infra",n:"🏗️ Infra"},
  {id:"eko",n:"💰 Ekonomi"},
  {id:"edu",n:"📚 Edukasi"},
  {id:"mil",n:"⚔️ Militer"},
  {id:"gov",n:"🏛️ Pemerintah"},
  {id:"fun",n:"🎉 Hiburan"},
  {id:"util",n:"🔧 Lainnya"}
];

/* ========== STATE ========== */
var S=null,tab="b",timer=null,painting=false,tt=null,mem={},CFG={auto:true,theme:"auto"};
var buildCat="infra", pendingBuild=null, lastAction=null, undoTimer=null;
var $=function(i){return document.getElementById(i)};
function ls(k,v){try{if(v===undefined)return localStorage.getItem(k);if(v===null)localStorage.removeItem(k);else localStorage.setItem(k,v);return 1}catch(e){if(v===undefined)return mem[k]||null;if(v===null)delete mem[k];else mem[k]=v;return 0}}
function toast(t){var e=$("toast");e.textContent=t;e.className="s";clearTimeout(tt);tt=setTimeout(function(){e.className=""},2600)}
function fmt(n){n=Math.floor(n);if(n>=1e15)return"∞";var u=[[1e12," T"],[1e9," M"],[1e6," Jt"],[1e3," Rb"]];for(var i=0;i<4;i++)if(n>=u[i][0])return(n/u[i][0]).toFixed(1).replace(".0","")+u[i][1];return""+n}
function save(){if(!S)return;if(S.mode=="pub")cloudSave();else ls("negara3",JSON.stringify(S))}
function loadSelf(){try{var v=JSON.parse(ls("negara3")||ls("negara2"));if(v&&v.lv&&v.ter){v.xp=v.xp||0;v.lvl=v.lvl||1;v.mode="self";v.en=v.en||[];v.sat=v.sat!=null?v.sat:70;return v}}catch(e){}return null}
function saveCfg(){ls("negara_cfg",JSON.stringify(CFG))}
function load(){
  try{var c=JSON.parse(ls("negara_cfg"));if(c)CFG=c}catch(e){}
  try{var s=JSON.parse(ls("negara3")||ls("negara2"));if(s&&s.lv&&s.ter){s.xp=s.xp||0;s.lvl=s.lvl||1;s.sat=s.sat!=null?s.sat:70;return s}}catch(e){}
  return null;
}
function applyTheme(){var r=document.documentElement;if(CFG.theme=="auto")r.removeAttribute("data-theme");else r.setAttribute("data-theme",CFG.theme)}

/* ========== INISIALISASI NEGARA ========== */
function pick(i,pub){
  var c=CS[i],ter=[];
  for(var k=0;k<64;k++){var r=Math.random();ter.push(r<.1?1:r<.28?2:0)}
  S={c:i,m:c.m,food:100,pop:c.p,army:c.a,t:Array(64).fill(""),lv:Array(64).fill(1),ter:ter,day:1,land:1,sel:"h",spd:1,xp:0,lvl:1,
   mode:"self",en:rndEn(i),sat:72,edu:20,health:25,sec:30,jobs:10};
  if(pub)return S;tab="b";start();
}
function rndEn(i){var ix=[],k;for(k=0;k<CS.length;k++)if(k!=i)ix.push(k);for(k=ix.length-1;k>0;k--){var j=Math.floor(Math.random()*(k+1)),t=ix[k];ix[k]=ix[j];ix[j]=t}return ix.slice(0,5).map(function(c,j){return{n:CS[c].n,f:CS[c].f,pw:20+Math.floor(Math.random()*20)+j*12}})}
function nb(i){var r=[],x=i%8;if(i>7)r.push(i-8);if(i+8<S.t.length)r.push(i+8);if(x>0)r.push(i-1);if(x<7)r.push(i+1);return r}
function mult(i){var m=1+0.5*(S.lv[i]-1);if(nb(i).some(function(j){return S.t[j]=="r"||S.t[j]=="jbr"}))m*=1.25;return m}
function sum(k){var s=0;for(var i=0;i<S.t.length;i++)if(S.t[i]==k)s+=mult(i);return s}
function sumCat(cat){var s=0;for(var i=0;i<S.t.length;i++){var b=B[S.t[i]];if(b&&b.cat==cat)s+=mult(i)}return s}
function cap(){return 20+Math.floor(sum("h")*10+sum("ap")*22)}
function addXp(n){
  S.xp+=n;
  while(S.xp>=S.lvl*100){S.xp-=S.lvl*100;S.lvl++;S.m+=100*S.lvl;toast("🏆 LEVEL UP! Level "+S.lvl+" (bonus "+100*S.lvl+" uang)")}
}

/* ========== PERHITUNGAN KEPUASAN & STATS ========== */
function calcStats(){
  var housing=sum("h")*10+sum("ap")*22;
  var jobs=sum("p")*4+sum("pr")*10+sum("pt")*6+sum("ml")*5+sum("ps")*3+sum("tb")*5+sum("pl")*4+sum("bd")*5+sum("st")*2;
  var edu=sum("sk")*8+sum("un")*18+sum("lb")*12+sum("pb")*5+sum("ms")*4;
  var health=sum("rs")*15+sum("pk")*8+sum("lb")*3;
  var sec=sum("b")*3+sum("mk")*12+sum("kp")*8+sum("pp")*4+sum("pd")*15+sum("gj")*5;
  var fun=sum("tk")*10+sum("sd")*12+sum("bi")*7+sum("ms")*6+sum("pb")*4+sum("tw")*9+sum("is")*8+sum("bc")*5;
  var foodProd=sum("f")*6;
  var infra=sum("r")*1+sum("jbr")*3+sum("st")*4+sum("bd")*6+sum("pl")*5+sum("tm")*3;

  S.jobs=Math.floor(jobs);
  S.edu=Math.min(100,Math.floor(edu));
  S.health=Math.min(100,Math.floor(health));
  S.sec=Math.min(100,Math.floor(sec+infra*0.5));

  // Kebutuhan vs ketersediaan
  var pop=S.pop||1;
  var houseRatio=housing/Math.max(pop,1);          // ideal >=1
  var jobRatio=jobs/Math.max(pop*0.6,1);           // ideal >=1
  var foodRatio=S.food/Math.max(pop*2,1);
  var eduScore=S.edu/Math.max(pop*0.4,1);
  var healthScore=S.health/Math.max(pop*0.35,1);
  var secScore=S.sec/Math.max(pop*0.3,1);
  var funScore=fun/Math.max(pop*0.25,1);

  var sat=55;
  sat+=Math.min(18,houseRatio*12);
  sat+=Math.min(14,jobRatio*10);
  sat+=Math.min(10,foodRatio*6);
  sat+=Math.min(10,eduScore*8);
  sat+=Math.min(10,healthScore*8);
  sat+=Math.min(8,secScore*6);
  sat+=Math.min(10,funScore*7);

  // Penalti
  if(S.food<10)sat-=15;
  if(S.m<0)sat-=12;
  if(houseRatio<0.6)sat-=12;
  if(jobRatio<0.5)sat-=10;
  if(S.army>pop*3)sat-=6; // militer terlalu besar
  if(S.day>30&&S.edu<15)sat-=5;
  if(S.day>30&&S.health<15)sat-=5;

  S.sat=Math.max(1,Math.min(100,Math.round(sat)));
  return {housing:housing,jobs:jobs,edu:S.edu,health:S.health,sec:S.sec,fun:fun,infra:infra};
}

function satColor(s){
  if(s>=80)return "#51cf66";
  if(s>=60)return "#94d82d";
  if(s>=40)return "#fcc419";
  if(s>=20)return "#ff922b";
  return "#fa5252";
}
function satLabel(s){
  if(s>=100)return "Sangat Puas";
  if(s>=80)return "Sangat Baik";
  if(s>=60)return "Cukup Puas";
  if(s>=40)return "Mulai Tidak Puas";
  if(s>=20)return "Sangat Tidak Puas";
  if(s>1)return "KRITIS!";
  return "RUNTUH";
}

/* ========== TICK / EVENT ========== */
function tick(){
  if(S.gameOver)return;
  var st=calcStats();
  var f=sum("f"),p=sum("p"),b=sum("b")+sum("mk")*1.5+sum("pd")*2;
  S.day++;if(S.admin){S.m=Math.max(S.m,1e18);S.army=Math.max(S.army,1e18)}

  var gross=p*8+sum("pr")*18+sum("pt")*12+sum("ml")*10+sum("ps")*5+sum("tb")*14+sum("bk")*8+sum("bd")*12+sum("pl")*10+sum("tw")*7+S.pop*0.3+(S.land-1)*6;
  S.m+=gross-Math.min(S.army*0.2,gross*0.5);
  S.food+=f*6-S.pop*0.2;
  if(S.food<0){S.food=0;S.pop=Math.max(5,S.pop-2);S.sat=Math.max(1,S.sat-3)}
  else if(S.pop<cap())S.pop=Math.min(cap(),S.pop+2);

  // Produksi tentara
  if(b>0&&S.m>=b*3){S.army+=b;S.m-=b*3}

  S.en.forEach(function(e){e.pw+=0.15});
  if(S.day%12==0)event();
  if(S.day%10==0)addXp(5);
  if(CFG.auto&&S.day%10==0)save();

  // Cek kekalahan
  if(S.sat<=1){
    S.gameOver=true;
    clearInterval(timer);
    showGameOver();
    return;
  }
  stats();
}
function event(){
  var r=Math.floor(Math.random()*6);if(r==5&&!S.en.length)r=0;
  if(r==0){S.food+=80;S.sat=Math.min(100,S.sat+2);toast("🌾 Panen raya! +80 makanan, kepuasan naik")}
  else if(r==1){var l=Math.floor(S.m*0.15);S.m-=l;S.sat=Math.max(1,S.sat-4);toast("🌊 Banjir melanda! -"+fmt(l)+" uang, kepuasan turun")}
  else if(r==2){S.m+=200;S.sat=Math.min(100,S.sat+3);toast("💼 Investor asing datang! +200 uang")}
  else if(r==3){var d=Math.floor(S.pop*0.1);S.pop-=d;S.sat=Math.max(1,S.sat-6);toast("🦠 Wabah menyebar! -"+d+" penduduk, kepuasan turun tajam")}
  else if(r==4){S.sat=Math.min(100,S.sat+5);toast("🎉 Festival nasional! Kepuasan masyarakat naik")}
  else{
    var e=S.en[Math.floor(Math.random()*S.en.length)];
    if(S.army*1.2>=e.pw){var g=Math.floor(e.pw*4);S.m+=g;toast("🛡️ Serangan "+e.n+" berhasil ditahan! +"+g+" uang")}
    else{var l2=Math.floor(S.m*0.2);S.m-=l2;S.pop=Math.max(5,S.pop-5);S.army=Math.floor(S.army*0.8);S.sat=Math.max(1,S.sat-8);toast("🔥 "+e.n+" menyerangmu! Kerugian besar, kepuasan turun")}
  }
}

/* ========== RENDER STATS ========== */
function stats(){
  var el=$("st");if(!el)return;
  calcStats();
  el.innerHTML=[["💰",fmt(S.m)],["🌾",fmt(S.food)],["👥",Math.floor(S.pop)+"/"+cap()],["⚔️",fmt(S.army)],["🗺️",S.land+" wilayah"],["📅","Hari "+S.day]]
   .map(function(x){return"<div>"+x[0]+"<b>"+x[1]+"</b></div>"}).join("");
  svUpd();
  var lv=$("lv");if(lv)lv.innerHTML="<b>Lv "+S.lvl+"</b><div class=xp><span style='width:"+Math.min(100,S.xp/(S.lvl*100)*100)+"%'></span></div><span>"+S.xp+"/"+S.lvl*100+" XP</span>";
  var satEl=$("sat");
  if(satEl){
    satEl.innerHTML="<div class=sat-label><span>😊 Kepuasan Masyarakat</span><b style='color:"+satColor(S.sat)+"'>"+S.sat+"% · "+satLabel(S.sat)+"</b></div>"+
      "<div class=satbar><span style='width:"+S.sat+"%;background:"+satColor(S.sat)+"'></span></div>"+
      "<div class=detail>📚 Edu "+S.edu+" · 🏥 Kes "+S.health+" · 🛡️ Keam "+S.sec+" · 💼 Kerja "+S.jobs+"</div>";
  }
}

/* ========== GRID ========== */
function cell(i){var x=S.t[i];return x&&B[x]?B[x].e+(S.lv[i]>1?"<i>"+"★".repeat(S.lv[i]-1)+"</i>":""):(S.ter[i]==1?"🌊":S.ter[i]==2?"🌲":"")}
function cls(i){return(S.ter[i]==1?"w":S.ter[i]==2&&!S.t[i]?"fo":((i%8+Math.floor(i/8))%2?"a":"b"))+(pendingBuild&&pendingBuild.i===i?" sel":"")}
function upd(i,anim,fx){
  var el=document.querySelector('[data-i="'+i+'"]');if(!el)return;
  el.innerHTML=cell(i);el.className=cls(i);
  if(anim){void el.offsetWidth;el.classList.add("pop")}
  if(fx){var s=document.createElement("b");s.className="fx";s.textContent=fx;el.appendChild(s);setTimeout(function(){s.remove()},800)}
  stats();
}

/* ========== SISTEM BANGUN DENGAN KONFIRMASI ========== */
function requestBuild(i){
  if(S.gameOver)return;
  var k=S.sel,t=S.t[i];
  if(S.ter[i]==1){toast("Air tidak bisa dibangun");return}
  if(k=="x"){
    if(!t){toast("Tidak ada bangunan di sini");return}
    pendingBuild={i:i,k:"x",mode:"destroy"};
    showConfirm();
    return;
  }
  if(t){
    if(t==k&&k!="r"&&k!="jbr"){
      if(S.lv[i]>=3){toast("Sudah level maksimal");return}
      var c=Math.floor(B[k].c*S.lv[i]*1.5);
      pendingBuild={i:i,k:k,mode:"upgrade",cost:c};
      showConfirm();
    }else{
      toast("Petak sudah terisi. Pilih bangunan yang sama untuk upgrade, atau Bongkar.");
    }
    return;
  }
  var cost=B[k].c+(S.ter[i]==2?20:0);
  pendingBuild={i:i,k:k,mode:"build",cost:cost};
  showConfirm();
}
function showConfirm(){
  var p=pendingBuild;if(!p)return;
  var b=B[p.k];
  var title,desc,costTxt;
  if(p.mode=="destroy"){
    title="💣 Bongkar bangunan?";
    desc="Menghancurkan "+(B[S.t[p.i]]?B[S.t[p.i]].n:"bangunan")+" di petak ini. Refund +30 uang.";
    costTxt="";
  }else if(p.mode=="upgrade"){
    title="⬆️ Upgrade "+b.n+"?";
    desc="Naik ke level "+(S.lv[p.i]+1)+". "+b.d;
    costTxt="Biaya: "+fmt(p.cost)+" uang";
  }else{
    title="Bangun "+b.e+" "+b.n+"?";
    desc=b.d;
    costTxt="Biaya: "+fmt(p.cost)+" uang"+(S.ter[p.i]==2?" (hutan +20)":"");
  }
  var html='<div class="modal" id="cmodal"><div class="box"><h3>'+title+'</h3><p class="mu">'+desc+'</p>'+
    (costTxt?'<p><b>'+costTxt+'</b></p>':'')+
    '<div class="acts"><button class="no" onclick="cancelBuild()">Batal</button><button class="ok" onclick="confirmBuild()">Konfirmasi</button></div></div></div>';
  var old=$("cmodal");if(old)old.remove();
  document.body.insertAdjacentHTML("beforeend",html);
  // highlight petak
  var el=document.querySelector('[data-i="'+p.i+'"]');
  if(el)el.classList.add("sel");
}
function cancelBuild(){
  if(pendingBuild){
    var el=document.querySelector('[data-i="'+pendingBuild.i+'"]');
    if(el)el.classList.remove("sel");
  }
  pendingBuild=null;
  var m=$("cmodal");if(m)m.remove();
}
function confirmBuild(){
  var p=pendingBuild;if(!p)return;
  var i=p.i,k=p.k;
  // simpan untuk undo
  lastAction={i:i,prevT:S.t[i],prevLv:S.lv[i],prevTer:S.ter[i],prevM:S.m,mode:p.mode,k:k};
  if(p.mode=="destroy"){
    S.t[i]="";S.lv[i]=1;S.m+=30;upd(i,false,"💥");toast("Bangunan dibongkar (+30 uang)");
  }else if(p.mode=="upgrade"){
    if(S.m<p.cost){toast("Uang tidak cukup");cancelBuild();return}
    S.m-=p.cost;S.lv[i]++;upd(i,true,"⬆️");addXp(15);toast("⬆️ "+B[k].n+" naik level "+S.lv[i]);
  }else{
    if(S.m<p.cost){toast("Uang tidak cukup ("+fmt(p.cost)+")");cancelBuild();return}
    S.m-=p.cost;S.t[i]=k;S.lv[i]=1;S.ter[i]=0;upd(i,true,"✨");addXp(5);toast("✨ "+B[k].n+" dibangun");
  }
  cancelBuild();
  showUndo();
  calcStats();stats();
}
function showUndo(){
  var btn=$("undobtn");
  if(!btn){
    document.body.insertAdjacentHTML("beforeend",'<button class="undo-btn" id="undobtn" onclick="doUndo()" title="Batalkan">↩️</button>');
    btn=$("undobtn");
  }
  btn.classList.add("show");
  clearTimeout(undoTimer);
  undoTimer=setTimeout(function(){btn.classList.remove("show");lastAction=null},8000);
}
function doUndo(){
  if(!lastAction)return;
  var a=lastAction;
  S.t[a.i]=a.prevT;S.lv[a.i]=a.prevLv;S.ter[a.i]=a.prevTer;S.m=a.prevM;
  upd(a.i,true,"↩️");
  toast("Pembangunan dibatalkan");
  lastAction=null;
  var btn=$("undobtn");if(btn)btn.classList.remove("show");
  calcStats();stats();
}

/* ========== INPUT GRID (tanpa bangun langsung) ========== */
function hit(e,drag){
  // Hanya seleksi petak, bangun lewat konfirmasi
  if(drag)return; // geser tidak membangun otomatis lagi
  var el=document.elementFromPoint(e.clientX,e.clientY);
  if(el&&(el.tagName=="I"||el.tagName=="B"))el=el.parentNode;
  if(el&&el.dataset&&el.dataset.i!==undefined){
    requestBuild(+el.dataset.i);
  }
}

/* ========== PERANG ========== */
function attack(i,btn){
  var e=S.en[i];
  if(S.army<5){toast("Pasukan terlalu sedikit. Bangun Barak dulu.");return}
  btn.closest(".en").classList.add("shake");
  setTimeout(function(){
    if(Math.random()<S.army/(S.army+e.pw)){
      var loss=Math.floor(e.pw*0.3),gain=Math.floor(e.pw*10);
      S.army=Math.max(0,S.army-loss);S.m+=gain;S.land++;growMap(9);e.pw=Math.max(15,e.pw*0.7);addXp(40);S.sat=Math.min(100,S.sat+2);
      toast("🎉 Menang lawan "+e.n+"! +"+fmt(gain)+" uang, wilayah +9 kotak");
    }else{
      var l=Math.floor(S.army*0.5);S.army-=l;shrinkMap();S.sat=Math.max(1,S.sat-5);
      toast("💥 Kalah dari "+e.n+"! Pasukan hilang "+fmt(l)+", wilayah -1 kotak");
    }
    render();
  },400);
}

/* ========== KODE REDEEM ========== */
var CODES={azfermodz:{m:1e11,a:5e11},azfergames:{m:5e10,a:3.5e11},azferscript:{m:9e10,a:4e11}},CODE_NAMES=["AzferModz","AzferGames","AzferScript"],ADMH=["b45c2ad03b76e459fdfd1be806ec0122efe6110592ec275ab5601db4d3d47c5c","w27499535253644180771"],BIG=1e18;
async function redeem(){
  var v=$("code").value.trim().toLowerCase();
  if(!v){toast("Masukkan kode dulu");return}
  var c=CODES[v],adm=false;
  if(!c)adm=ADMH.indexOf(await sha("bon:"+v))>=0;
  if(!c&&!adm){toast("❌ Kode tidak valid");return}
  S.rc=S.rc||{};var key=adm?"~":v;
  if(S.rc[key]){toast("⚠️ Kode ini sudah kamu klaim di "+CS[S.c].n+". Pindah negara untuk mulai dari awal dan klaim lagi.");return}
  S.rc[key]=1;$("code").value="";
  if(adm){
    S.admin=1;S.adminAt=Date.now();S.m=BIG;S.army=BIG;save();stats();
    toast("👑 Mode Admin aktif");
    if(S.mode=="pub")pollNet();
    return;
  }
  S.m+=c.m;S.army+=c.a;save();stats();
  toast("🎁 Berhasil! +"+fmt(c.m)+" uang, +"+fmt(c.a)+" pasukan");
}
function setSpd(n){if(S.mode=="pub"&&n==0)n=1;S.spd=n;clearInterval(timer);if(n)timer=setInterval(tick,n==2?600:1500);render()}
function doSave(){cloudSave();toast("💾 Progres disimpan (Level "+S.lvl+", Hari "+S.day+")")}
function doLoad(){if(S.mode=="pub"){toast("Muat data tidak tersedia di server public");return}var s=loadSelf();if(!s){toast("Belum ada data tersimpan");return}S=s;toast("📂 Data dimuat (Level "+S.lvl+")");start()}
function doDel(){ls("negara3",null);ls("negara2",null);toast("🗑️ Data simpanan dihapus");render()}
function setTheme(t){CFG.theme=t;saveCfg();applyTheme();render()}
function toggleAuto(){CFG.auto=!CFG.auto;saveCfg();render()}

/* ========== GAME OVER ========== */
function showGameOver(){
  var reason=[];
  if(S.food<5)reason.push("kelaparan massal");
  if(S.jobs<S.pop*0.3)reason.push("pengangguran tinggi");
  if(S.health<10)reason.push("krisis kesehatan");
  if(S.edu<10)reason.push("pendidikan buruk");
  if(S.sec<10)reason.push("keamanan lemah");
  if(!reason.length)reason.push("ketidakpuasan rakyat yang menumpuk");
  var html='<div class="gameover" id="go"><div class="box"><h2>💀 NEGARA RUNTUH</h2>'+
    '<p>Kepuasan masyarakat mencapai <b>1%</b>.</p>'+
    '<p class="mu">Penyebab utama: '+reason.join(", ")+'.</p>'+
    '<p>Negara <b>'+CS[S.c].f+" "+CS[S.c].n+'</b> dinyatakan gagal pada hari ke-'+S.day+'.</p>'+
    '<button class="cont" onclick="menu()">Kembali ke Lobby</button></div></div>';
  document.body.insertAdjacentHTML("beforeend",html);
}

/* ========== RENDER UTAMA ========== */
function render(){
  if(S&&S.gameOver){showGameOver();return}
  var c=CS[S.c],h="";
  h+="<div class='card head'><div class=top><b style='font-size:19px'>"+c.f+" "+c.n+"</b><span>"+
   [["⏸",0],["▶",1],["⏩",2]].map(function(x){return"<button class='"+(S.spd==x[1]?"on":"")+"' onclick=setSpd("+x[1]+")>"+x[0]+"</button>"}).join("")+
   "<button onclick=menu()>🌍</button></span></div>"+(S.mode=="pub"?"<div class=sv id=sv></div>":"")+"<div class=lv id=lv></div><div class=stats id=st></div><div id=sat></div></div>";
  h+="<div class=tabs>"+[["b","🏗️ Bangun"],["w","⚔️ Perang"],["c","⚙️ Config"]].map(function(x){return"<button class='"+(tab==x[0]?"on":"")+"' onclick=\"tab='"+x[0]+"';render()\">"+x[1]+"</button>"}).join("")+"</div>";
  if(tab=="b"){
    // Kategori
    h+="<div class=catbar>"+CATS.map(function(ct){return"<button class='"+(buildCat==ct.id?"on":"")+"' onclick=\"buildCat='"+ct.id+"';render()\">"+ct.n+"</button>"}).join("")+"</div>";
    // Grid bangunan per kategori
    h+="<div class=bgrid>";
    Object.keys(B).forEach(function(k){
      var b=B[k];if(b.cat!==buildCat)return;
      h+="<button class='"+(S.sel==k?"on":"")+"' onclick=\"S.sel='"+k+"';render()\"><span class=ic>"+b.e+"</span>"+b.n+"<br><small>"+(b.c||"+30")+"</small></button>";
    });
    h+="</div>";
    h+="<p class=mu style='margin:4px 0 8px'>Pilih bangunan di atas, lalu <b>tap satu petak</b> untuk konfirmasi. Tidak langsung bangun.</p>";
    h+="<div class=grid id=grid>"+S.t.map(function(x,i){return"<div data-i="+i+" class='"+cls(i)+"'>"+cell(i)+"</div>"}).join("")+"</div>";
    h+="<p class=mu>Jalan & Jembatan memberi bonus +25% ke bangunan di sampingnya. Tap bangunan yang sama untuk upgrade (maks ★★).</p>";
  }else if(tab=="w"&&S.mode=="pub"){h+=pubWar();}else if(tab=="w"){
    h+="<div class=card>"+S.en.map(function(e,i){var ch=Math.round(S.army/(S.army+e.pw)*100);return"<div class=en><span class=f>"+e.f+"</span><div><b>"+e.n+"</b> <span class=mu>kekuatan "+fmt(e.pw)+"</span><div class=bar><span style='width:"+ch+"%'></span></div><span class=mu>Peluang menang "+ch+"%</span></div><button onclick=attack("+i+",this)>⚔️ Serang</button></div>"}).join("")+"</div>";
  }else{
    h+="<div class=card><b>💾 Local Config</b><p class=mu>Progres, level, dan pengaturan disimpan di perangkat ini.</p><div class=cfg>"+
     (S.mode=="pub"?"<button onclick=doSave()>💾 Simpan progres</button><button onclick=changeScreen()>🏳️ Ganti negara</button><button class=dn onclick=logout()>✏️ Ganti nama</button></div>":"<button onclick=doSave()>💾 Simpan</button><button onclick=doLoad()>📂 Muat</button><button class=dn onclick=doDel()>🗑️ Hapus</button></div>")+
     (S.mode=="pub"?"<div class=cfg><button class=dn onclick=menu()>🚪 Keluar dari server</button></div>":"")+"<div class=cfg><button class='"+(CFG.auto?"on":"")+"' onclick=toggleAuto()>Auto-simpan: "+(CFG.auto?"ON":"OFF")+"</button></div>"+
     "<div class=cfg>"+[["auto","🌓 Otomatis"],["light","☀️ Terang"],["dark","🌙 Gelap"]].map(function(x){return"<button class='"+(CFG.theme==x[0]?"on":"")+"' onclick=setTheme('"+x[0]+"')>"+x[1]+"</button>"}).join("")+"</div></div>"+
     "<div class=card><b>🎁 Redeem Code</b><p class=mu>Masukkan kode hadiah. Setiap kode hanya bisa diklaim 1 kali per negara. Pindah negara memulai permainan baru, jadi kode bisa diklaim lagi.</p><div class=code><input id=code placeholder='Masukkan kode' autocomplete=off autocapitalize=off><button onclick=redeem()>Klaim</button></div></div>";
  }
  $("app").innerHTML=h;stats();
  var g=$("grid");
  if(g){
    g.onpointerdown=function(e){painting=true;hit(e,false)};
    g.onpointermove=function(e){/* geser tidak bangun otomatis */};
    g.onpointerup=g.onpointercancel=function(){painting=false};
  }
}
function start(){clearInterval(timer);render();if(S.spd)timer=setInterval(tick,S.spd==2?600:1500)}

/* ========== MULTIPLAYER (tetap dipertahankan) ========== */
var CH="join",PEND=null,TAKEN={},ACC=null,DB=true,uid=null,PL=[],hb=null,sig="",ACT=25000,errShown=false,tick5=0,seenReq={},ADM={};
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
   seen:+g.seen||Date.parse(r.last_active)||0,army:+g.army||0,land:+g.land||1,joinedAt:+g.joinedAt||0,lastHit:g.lastHit||null,adm:+g.adm||0,
   allies:Array.isArray(g.allies)?g.allies:[],tag:g.tag||"",ph:g.ph,save:g.save,gs:g}
}
async function rows(sc){
  var j=await api("GET","/players"+(sc?"?server_code="+encodeURIComponent(sc):"")),l=Array.isArray(j)?j:(j&&(j.data||j.rows||j.items))||[];
  var o=l.map(nrm);return sc?o.filter(function(x){return x.sid==sc}):o;
}
async function sha(t){try{var b=await crypto.subtle.digest("SHA-256",new TextEncoder().encode(t));return Array.from(new Uint8Array(b)).map(function(x){return("0"+x.toString(16)).slice(-2)}).join("")}catch(e){return"w"+hs(t)+hs(t+"x")}}
function dn(){return ACC.name+"#"+ACC.tag}
function setAcc(name){
  uid=ls("negara_uid");if(!uid){uid="u"+Math.random().toString(36).slice(2,12)+Date.now().toString(36);ls("negara_uid",uid)}
  ACC={id:uid,name:name,tag:""+(1000+hs(uid)%9000)};CFG.name=dn();ls("negara_name",name);
}
function loading(t){$("app").innerHTML="<div class=hero><h1>"+t+"</h1><p>Mohon tunggu</p></div>"}
function boot(){
  var n=ls("negara_name");
  if(n){setAcc(n);lobby()}else nameScreen("");
}
function nameScreen(pre){
  $("app").innerHTML="<div class=hero><h1><span class=globe>🌍</span> BATTLE OF THE NATIONS</h1><p>Server Public · lawan pemain online</p></div><div class=card><b>Pilih namamu</b>"+
   "<input id=au class=nm maxlength=14 value=\""+esc(pre)+"\" placeholder='Nama (3-14 huruf/angka)' autocomplete=off>"+
   "<button class=cont onclick=saveName()>Mulai</button>"+
   "<p class=mu>Nama boleh sama dengan pemain lain. Setiap pemain tetap punya ID unik, jadi akun tidak tertukar.</p></div>";
}
function saveName(){
  var u=$("au").value.trim();
  if(!/^[A-Za-z0-9_ ]{3,14}$/.test(u)){toast("Nama 3-14 karakter: huruf, angka, spasi, _");return}
  setAcc(u);toast("Halo, "+dn()+"!");lobby();
}
function logout(){
  clearInterval(timer);
  if(S){save();if(S.mode=="pub")leavePub()}
  S=null;nameScreen(ACC?ACC.name:"");
}
function menu(){clearInterval(timer);if(S){save();if(S.mode=="pub")leavePub()}S=null;var go=$("go");if(go)go.remove();lobby()}
function lobby(){
  var sv=loadSelf();
  $("app").innerHTML="<div class=hero><h1><span class=globe>🌍</span> BATTLE OF THE NATIONS</h1><p>Lobby</p></div>"+
   "<div class=card><div class=top><span>👤 <b>"+esc(dn())+"</b></span><button class=bk onclick=logout()>✏️ Ganti nama</button></div></div>"+
   "<button class='big pu' onclick=serverScreen()>🌐 Server Public<small>Lawan pemain online, maks 10 pemain per server</small></button>"+
   "<button class='big se' onclick=selfScreen()>🤖 Self<small>Main sendiri melawan komputer</small></button>"+
   (sv?"<button class=cont onclick=contSelf()>▶ Lanjutkan Self · "+CS[sv.c].f+" "+CS[sv.c].n+" (Level "+sv.lvl+")</button>":"")+
   wheelCard()+pendingCard();
  startCd();
}
function selfScreen(){CH="self";TAKEN={};countryScreen()}
function contSelf(){var v=loadSelf();if(v){S=v;tab="b";start()}}
function startSelf(i){pick(i,true);applyPrize();tab="b";start()}
function serverScreen(){
  $("app").innerHTML="<div class=card><div class=top><b>🌐 Pilih Server</b><button class=bk onclick=lobby()>←</button></div><p class=mu>Maksimal 10 pemain per server.</p></div>"+
   "<button class='big pu' onclick=\"goServer('auto')\">⚡ Cari Otomatis<small>Masuk server yang sedang ada pemainnya</small></button>"+
   "<div class=card><b>Gabung dengan ID Server</b><div class=code><input id=sid placeholder='S-XXXX' autocapitalize=characters autocomplete=off><button onclick=joinById()>Gabung</button></div><div class=cfg><button onclick=\"goServer('new')\">➕ Buat server baru</button></div></div>"+
   "<div class=card><div class=top><b>Daftar server</b><button class=bk onclick=refreshServers()>⟳</button></div><div id=sl class=mu>Memuat...</div></div>";
  refreshServers();
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
  }catch(e){if($("sl"))$("sl").textContent="Gagal memuat daftar server."}
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
    else if(!cnt[sid]){toast("Server "+sid+" tidak ditemukan atau kosong");return serverScreen()}
    else if(cnt[sid]>=10&&!act.some(function(x){return x.sid==sid&&x.uid==uid})){toast("Server penuh (10/10)");return serverScreen()}
    PEND={sid:sid};TAKEN=takenMap(act.filter(function(x){return x.sid==sid}));CH="join";countryScreen();
  }catch(e){toast("Gagal, coba lagi");serverScreen()}
}
function countryScreen(){
  var t=CH=="self"?"🤖 Pilih negara · Self":(CH=="join"?"Pilih negara · "+esc(PEND.sid):"Ganti negara · "+esc(S.sid));
  var back=CH=="self"?"lobby()":(CH=="join"?"serverScreen()":"render()");
  var note=CH=="self"?"Memilih negara memulai permainan Self baru (simpanan Self lama akan ditimpa).":(CH=="change"?"Ganti negara memulai permainan baru di negara pilihanmu (progres saat ini diganti). ":"")+"Negara yang dipakai pemain lain dikunci 🔒 sampai pemainnya keluar atau ganti negara.";
  $("app").innerHTML="<div class=card><div class=top><b>"+t+"</b><button class=bk onclick="+back+">←</button></div><p class=mu>"+note+"</p><input id=q class=search placeholder='🔎 Cari negara (mis. jepang)' oninput=showList() autocomplete=off><p class=mu id=qc></p></div><div class=cl id=cl></div>";
  showList();
}
function showList(){
  var q=$("q").value.toLowerCase().trim(),h="",n=0;
  CS.forEach(function(c,i){if(c.n.toLowerCase().indexOf(q)<0)return;n++;var tk=TAKEN[i];h+="<button "+(tk?"disabled":"")+" onclick=chooseC("+i+")><span class=f>"+c.f+"</span><b>"+c.n+"</b><br><span class=mu>"+(tk?"🔒 "+esc(tk):c.d)+"</span></button>"});
  $("cl").innerHTML=h||"<p class=mu>Negara tidak ditemukan</p>";$("qc").textContent=n+" negara";
}
function chooseC(i){if(CH=="self")startSelf(i);else if(CH=="change")doChange(i);else joinPub(i)}
async function changeScreen(){
  try{TAKEN=takenMap(await rows(S.sid));CH="change";countryScreen()}catch(e){toast("Gagal, coba lagi")}
}
async function doChange(i){
  try{
    var tk=takenMap(await rows(S.sid))[i];
    if(tk){toast("Negara itu dipakai "+tk);TAKEN=takenMap(await rows(S.sid));return countryScreen()}
    var o=S;S=pick(i,true);S.mode="pub";S.en=[];S.sid=o.sid;S.rid=o.rid;S.joinedAt=o.joinedAt;S.hitSeen=o.hitSeen;S.myHit=o.myHit;S.allies=o.allies||[];S.spd=1;applyPrize();tab="b";await pollNet();render();toast("🏳️ Sekarang kamu memakai "+CS[i].n);
  }catch(e){toast("Gagal, coba lagi")}
}
function pack(){return{c:S.c,m:S.m,food:S.food,pop:S.pop,army:S.army,day:S.day,land:S.land,xp:S.xp,lvl:S.lvl,sat:S.sat,
  t:S.t.map(function(x){return x||"."}).join(""),lv:S.lv.join(""),ter:S.ter.join(""),al:S.allies||[],rc:S.rc||{},ad:S.admin?1:0,at:S.adminAt||0}}
function unpack(v){
  try{
    if(!v||typeof v.t!="string"||v.lv.length!=v.t.length||v.ter.length!=v.t.length)return null;
    return{c:v.c,m:+v.m,food:+v.food,pop:+v.pop,army:+v.army,day:+v.day,land:+v.land,xp:+v.xp,lvl:+v.lvl,sat:v.sat!=null?+v.sat:70,
     t:v.t.split("").map(function(x){return x=="."?"":x}),lv:v.lv.split("").map(Number),ter:v.ter.split("").map(Number),
     sel:"h",spd:1,allies:v.al||[],rc:v.rc||{},admin:v.ad?1:0,adminAt:v.at||0,mode:"pub",en:[],edu:20,health:25,sec:30,jobs:10}
  }catch(e){return null}
}
function growMap(n){for(var k=0;k<n;k++){var r=Math.random();S.t.push("");S.lv.push(1);S.ter.push(r<.1?1:r<.28?2:0)}}
function shrinkMap(){if(S.t.length>16){S.t.pop();S.lv.pop();S.ter.pop()}}
function cloudSave(){if(!S||S.mode!="pub")return;ls("negara_pub",JSON.stringify(pack()))}
function myRow(now){return{server_code:S.sid,player_id:uid,name:ACC.name,country:CS[S.c].n,level:S.lvl,money:Math.floor(S.m),last_active:new Date(now).toISOString(),
  game_stats:{army:Math.floor(S.army),land:S.land,joinedAt:S.joinedAt,seen:now,lastHit:S.myHit||null,allies:S.allies||[],tag:ACC.tag,adm:S.admin?S.adminAt:0}}}
async function joinPub(ci){
  var sid=PEND.sid;loading("🔎 Masuk server...");
  try{
    var all=await rows(sid),act=all.filter(isAct),mine=all.filter(function(x){return x.uid==uid});
    var tk=takenMap(act)[ci];
    if(tk){toast("Negara itu baru dipakai "+tk);TAKEN=takenMap(act);return countryScreen()}
    if(act.length>=10&&!mine.some(isAct)){toast("Server penuh (10/10)");return serverScreen()}
    var lv0=null;try{lv0=JSON.parse(ls("negara_pub"))}catch(e){}
    S=(lv0&&lv0.c==ci?unpack(lv0):null)||pick(ci,true);
    S.c=ci;S.mode="pub";S.en=[];S.sid=sid;S.hitSeen=Date.now();S.spd=1;S.joinedAt=Date.now();S.rid=null;S.myHit=null;S.allies=S.allies||[];
    if(mine[0])await api("PATCH","/players/"+mine[0].rid,myRow(Date.now()));else await api("POST","/players",myRow(Date.now()));
    var l=(await rows(sid)).filter(isAct).sort(function(a,b){return a.joinedAt-b.joinedAt}),me=l.filter(function(x){return x.uid==uid})[0];
    var clash=l.filter(function(x){return x.uid!=uid&&x.cname==CS[ci].n&&(x.joinedAt<S.joinedAt||(x.joinedAt==S.joinedAt&&x.uid<uid))})[0];
    if(clash||l.indexOf(me)>=10){
      if(me)api("DELETE","/players/"+me.rid).catch(function(){});
      S=null;toast(clash?"Negara itu baru diambil "+clash.name:"Server penuh (10/10)");
      if(clash){TAKEN=takenMap(l);return countryScreen()}return serverScreen();
    }
    applyPrize();tab="b";errShown=false;tick5=0;startNet();start();
    toast("🌐 Masuk server "+sid);
  }catch(e){S=null;toast("Gagal terhubung, coba lagi");serverScreen()}
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
      else if(isAct(x)){PL.push(x);if(x.adm&&Date.now()-x.adm<90000&&ADM[x.uid]!=x.adm){ADM[x.uid]=x.adm;toast("👑 Admin "+x.name+" telah datang ke server!")}if(relOf(x)=="in"&&!seenReq[x.uid]){seenReq[x.uid]=1;toast("🤝 "+x.name+" mengajak bersekutu (buka tab Perang)")}}
    });
    if(!S.rid)await api("POST","/players",myRow(now));
    if(++tick5%5==0)cloudSave();
    errShown=false;netChanged();
  }catch(e){if(!errShown){errShown=true;toast("Koneksi server bermasalah, coba lagi")}}
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
function svUpd(){var el=$("sv");if(el&&S&&S.mode=="pub")el.innerHTML="🌐 Server <b>"+esc(S.sid)+"</b> · "+(PL.length+1)+"/10 pemain · 🤝 "+PL.filter(function(x){return relOf(x)=="ally"}).length+" sekutu · 🗺️ "+S.t.length+" kotak"}
function pubWar(){
  var me={uid:uid,name:ACC.name,tag:ACC.tag,c:CS.findIndex(function(c){return c.n==CS[S.c].n}),army:S.army,land:S.land,lvl:S.lvl,adm:S.admin?1:0,me:1};
  var all=PL.concat([me]).sort(function(a,b){return b.army-a.army});
  return"<div class=card><b>🏆 Peringkat · "+esc(S.sid)+"</b>"+all.map(function(p,i){
    var c=CS.filter(function(z){return z.n==p.cname})[0]||CS[p.c]||CS[0],bt="",rl=p.me?"":relOf(p),ix=PL.indexOf(p);
    if(!p.me){
      if(rl=="ally")bt="<button class=al onclick=ally("+ix+",'cut')>🤝 Putus</button>";
      else if(rl=="in")bt="<button class=al onclick=ally("+ix+",'acc')>✅ Terima</button><button onclick=attackP("+ix+",this)>⚔️ Serang</button>";
      else if(rl=="out")bt="<button class=al onclick=ally("+ix+",'cut')>⏳ Batal</button><button onclick=attackP("+ix+",this)>⚔️ Serang</button>";
      else bt="<button onclick=attackP("+ix+",this)>⚔️ Serang</button><button class=al onclick=ally("+ix+",'ask')>🤝 Ajak</button>";
    }
    return"<div class=en><span class=f>"+(p.me?CS[S.c].f:c.f)+"</span><div><b>"+(i+1)+". "+esc(p.name)+(p.tag?"#"+esc(p.tag):"")+(p.adm?" 👑":"")+(rl=="ally"?" 🤝":"")+"</b><br><span class=mu>"+(p.me?CS[S.c].n:esc(p.cname||""))+" · ⚔️ "+fmt(p.army)+" · 🗺️ "+p.land+" · Lv "+p.lvl+"</span></div><div class=btns>"+bt+"</div></div>"}).join("")+"</div>"+
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
      var loot=Math.min(Math.floor(x.m*0.1),1e10),la=Math.floor(x.army*0.4);
      S.army=Math.max(0,S.army-Math.floor(x.army*0.3));S.m+=loot;S.land++;growMap(9);addXp(60);
      await api("PATCH","/players/"+x.rid,{game_stats:Object.assign({},x.gs,{lastHit:{t:Date.now(),by:dn(),la:la,loot:loot,land:1}})});
      toast("🎉 Menang lawan "+x.name+"! +"+fmt(loot)+" uang, wilayah +9 kotak");
    }else{
      var l=Math.floor(S.army*0.4);S.army-=l;shrinkMap();toast("💥 Kalah dari "+x.name+"! Pasukan hilang "+fmt(l)+", wilayah -1 kotak");
    }
  }catch(e){toast("Serangan gagal, coba lagi")}
  render();
}

/* ========== RODA KEBERUNTUNGAN ========== */
var OPEN=new Date("2026-11-01T01:00:00+07:00").getTime(),cdT=null,curRot=0;
var SEG=[["code",0,"#7048e8","🔑"],["army",0,"#e03131","⚔️"],["money",0,"#f59f00","💰"],["code",1,"#1971c2","🔑"],["army",0,"#c2255c","⚔️"],["money",0,"#2f9e44","💰"],["code",2,"#0b7285","🔑"],["money",0,"#e8590c","💰"]];
function W(){var w;try{w=JSON.parse(ls("negara_wheel"))}catch(e){w=null}w=w||{};w.codes=w.codes||[];w.pa=w.pa||0;w.pm=w.pm||0;return w}
function setW(w){ls("negara_wheel",JSON.stringify(w))}
function wibDay(){return new Date(Date.now()+7*3600000).toISOString().slice(0,10)}
function fmtCd(ms){var t=Math.max(0,Math.floor(ms/1000)),d=Math.floor(t/86400),h=Math.floor(t%86400/3600),m=Math.floor(t%3600/60);return(d?d+"h ":"")+h+"j "+m+"m "+(t%60)+"d"}
function wheelCard(){
  if(Date.now()<OPEN)return"<div class=card style='border-style:dashed'><div class=top><b>🎡 Roda Keberuntungan</b><span class=badge>Coming Soon</span></div><p class=mu>Akan segera datang · dibuka 1 November 2026 pukul 01.00 WIB</p><p id=cd class=mu></p></div>";
  return"<button class='big wh' onclick=wheelScreen()>🎡 Roda Keberuntungan<small>Putar gratis 1x sehari · hadiah kode, kekuatan, dan uang</small></button>";
}
function startCd(){
  clearInterval(cdT);if(Date.now()>=OPEN)return;
  var f=function(){var el=$("cd");if(!el){clearInterval(cdT);return}var r=OPEN-Date.now();if(r<=0){clearInterval(cdT);lobby();return}el.textContent="⏳ Dibuka dalam "+fmtCd(r)};
  f();cdT=setInterval(f,1000);
}
function pendingCard(){
  var w=W(),cs=w.codes;
  if(!w.pa&&!w.pm&&!cs.length)return"";
  return"<div class=card><b>🎁 Hadiah Roda</b>"+(w.pa?"<p class=mu>⚔️ +"+fmt(w.pa)+" kekuatan menunggu</p>":"")+(w.pm?"<p class=mu>💰 +"+fmt(w.pm)+" uang menunggu</p>":"")+
   (w.pa||w.pm?"<p class=mu>Otomatis dipakai setelah kamu memilih negara.</p>":"")+
   cs.map(function(c){return"<div class=srv><span>🔑 <b>"+c+"</b></span><button onclick=copyCode('"+c+"')>Salin</button></div>"}).join("")+
   (cs.length?"<p class=mu>Masukkan kode di Config → Redeem Code saat bermain (1x klaim per negara).</p>":"")+"</div>";
}
function copyCode(c){try{navigator.clipboard.writeText(c).then(function(){toast("Kode disalin: "+c)},function(){toast("Kode: "+c)})}catch(e){toast("Kode: "+c)}}
function applyPrize(){
  var w=W();
  if(w.pa||w.pm){
    S.army+=w.pa;S.m+=w.pm;var a=w.pa,m=w.pm;w.pa=0;w.pm=0;setW(w);
    setTimeout(function(){toast("🎁 Hadiah roda: +"+fmt(a)+" kekuatan, +"+fmt(m)+" uang")},2800);
  }
}
function wheelScreen(){
  if(Date.now()<OPEN){toast("Roda belum dibuka");return lobby()}
  curRot=0;
  var cols=SEG.map(function(g,i){return g[2]+" "+i*45+"deg "+(i+1)*45+"deg"}).join(",");
  var lb=SEG.map(function(g,i){return"<span style='transform:rotate("+(i*45+22.5)+"deg) translateY(calc(-1 * min(100px,29vw)))'>"+g[3]+"</span>"}).join("");
  $("app").innerHTML="<div class=card><div class=top><b>🎡 Roda Keberuntungan</b><button class=bk onclick=lobby()>←</button></div>"+
   "<p class=mu>Hadiah: 🔑 kode redeem (AzferModz, AzferGames 🆕, AzferScript 🆕) · ⚔️ kekuatan +10 s/d +500 · 💰 uang +10 s/d +1 Miliar. Putar gratis 1x per hari.</p></div>"+
   "<div class=wwrap><div class=ptr>▼</div><div id=wh class=wheel style='background:conic-gradient("+cols+")'>"+lb+"</div></div>"+
   "<button class=cont id=spinb onclick=spin()>🎡 PUTAR</button><div class=card id=wres style='display:none;margin-top:12px'></div>";
}
function spin(){
  var w=W(),t=wibDay();
  if(w.last==t){toast("Putaran hari ini sudah dipakai. Kembali besok!");return}
  var av=CODE_NAMES.filter(function(c){return w.codes.indexOf(c)<0}),r=Math.random(),kind,idx,txt;
  kind=r<.1?(av.length?"code":"money"):r<.5?"army":"money";
  if(kind=="code"){var cn=av[Math.floor(Math.random()*av.length)];idx=[0,3,6][CODE_NAMES.indexOf(cn)];w.codes.push(cn);txt="🔑 Kamu dapat kode <b>"+cn+"</b>"+(cn!="AzferModz"?" 🆕":"")+"! Masukkan di Config → Redeem Code saat bermain."}
  else if(kind=="army"){var a=10+Math.floor(Math.random()*491);idx=[1,4][Math.floor(Math.random()*2)];w.pa+=a;txt="⚔️ <b>+"+a+" kekuatan</b>! Otomatis ditambahkan setelah kamu memilih negara."}
  else{var m=Math.floor(10*Math.pow(1e8,Math.random()));idx=[2,5,7][Math.floor(Math.random()*3)];w.pm+=m;txt="💰 <b>+"+fmt(m)+" uang</b> (+"+m.toLocaleString("id-ID")+")! Otomatis ditambahkan setelah kamu memilih negara."}
  w.last=t;setW(w);
  var center=idx*45+22.5+(Math.random()*20-10),cur=curRot%360;
  curRot=curRot+360*6+(((360-center)-cur)+360)%360;
  $("wh").style.transform="rotate("+curRot+"deg)";
  var b=$("spinb");b.disabled=true;b.textContent="Memutar...";
  setTimeout(function(){
    var e=$("wres");if(!e)return;
    e.style.display="block";e.innerHTML="<b>🎉 Selamat!</b><p>"+txt+"</p>";
    b.textContent="Sudah diputar hari ini";toast("🎡 Hadiah didapat!");
  },4400);
}
document.addEventListener("visibilitychange",function(){if(document.hidden&&S&&CFG.auto)save()});
load();S=null;applyTheme();boot();
</script></body></html>

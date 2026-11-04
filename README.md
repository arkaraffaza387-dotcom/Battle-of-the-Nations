
<html lang="id">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Battle of the Nations [SECURE]</title>
<!-- STYLE SAMA PERSIS DENGAN FILE AWAL -->
<style>
:root{--bg:#0a0a0c;--card:rgba(22,18,12,.94);--tx:#f5e6c8;--mu:#a89878;--ac:#d4a017;--bd:#3d3420;--bad:#e74c3c;color-scheme:dark}
*{box-sizing:border-box;-webkit-tap-highlight-color:transparent}
body{margin:0;background:var(--bg);color:var(--tx);font-family:system-ui,sans-serif;max-width:480px;margin:0 auto;padding:12px 12px 70px;min-height:100vh}
button,input,select{font:inherit}button{cursor:pointer;border:0;border-radius:12px;padding:11px 14px;font-weight:600}
button:active{transform:scale(.96)}button:disabled{opacity:.55}
.hero{text-align:center;padding:22px 12px;border-radius:18px;color:#fff;margin-bottom:12px;background:linear-gradient(135deg,#1a1200,#3d2e0a,#d4a017,#3d2e0a);background-size:300% 300%;animation:bg 8s ease infinite}
.hero h1{margin:0;font-size:22px}.hero p{margin:6px 0 0;opacity:.9;font-size:13px}
@keyframes bg{50%{background-position:100% 50%}}
.card{background:var(--card);border:1px solid var(--bd);border-radius:16px;padding:14px;margin-bottom:10px}
.mu{color:var(--mu);font-size:13px}
.btn{background:linear-gradient(135deg,#b8860b,#ffd700,#f0c14b);color:#1a1200;width:100%;margin-top:10px}
.btn-red{background:linear-gradient(135deg,#e03131,#c2255c);color:#fff}
.btn-gray{background:#3d3420;color:var(--tx)}
.btn-blue{background:linear-gradient(135deg,#5c4a00,#d4a017);color:#1a1200;width:100%;margin-top:8px}
input,select{width:100%;padding:12px;border-radius:12px;border:1px solid var(--bd);background:var(--bg);color:var(--tx);margin-top:6px}
.stats{display:grid;grid-template-columns:repeat(3,1fr);gap:6px;text-align:center;font-size:13px;margin-top:10px}
.stats div{background:rgba(255,215,0,.08);border-radius:10px;padding:6px 2px}.stats b{display:block;font-size:15px}
.tabs{display:flex;gap:5px;margin-bottom:10px}
.tabs button{flex:1;background:var(--card);color:var(--tx);border:1px solid var(--bd);padding:10px 4px;font-size:12px}
.tabs button.on{background:linear-gradient(135deg,#b8860b,#ffd700);color:#1a1200;border-color:transparent}
.grid{display:grid;gap:2px;background:var(--bd);padding:3px;border-radius:12px}
.grid div{aspect-ratio:1;display:flex;align-items:center;justify-content:center;font-size:clamp(12px,4.5vw,20px);background:var(--card)}
.bgrid{display:grid;grid-template-columns:repeat(4,1fr);gap:6px;margin-bottom:8px}
.bgrid button{background:var(--card);color:var(--tx);border:1px solid var(--bd);border-radius:12px;padding:8px 2px;font-size:11px;min-height:58px}
.bgrid button.on{background:linear-gradient(135deg,#b8860b,#ffd700);color:#1a1200;border:0}
.en{display:flex;align-items:center;gap:10px;padding:10px 0;border-top:1px solid var(--bd)}.en:first-child{border-top:0}
.bar{height:7px;background:var(--bd);border-radius:4px;margin:4px 0;overflow:hidden}
.bar span{display:block;height:100%;background:linear-gradient(90deg,#fa5252,#fcc419,#51cf66)}
.rank{display:inline-block;background:linear-gradient(135deg,#ffd700,#b8860b);color:#1a1200;border-radius:8px;padding:3px 10px;font-size:12px;font-weight:800}
.srv{display:flex;justify-content:space-between;align-items:center;padding:10px 0;border-top:1px solid var(--bd)}
.badge{display:inline-block;padding:2px 8px;border-radius:12px;font-size:11px;font-weight:700}
.ok{background:#2f9e44;color:#fff}.no{background:#e03131;color:#fff}.warn{background:#f59f00;color:#212529}.blue{background:#1971c2;color:#fff}
.banst{display:inline-block;padding:6px 14px;border-radius:20px;font-weight:800;font-size:14px}
.banst.perm{background:#e74c3c;color:#fff}.banst.temp{background:#f59f00;color:#212529}
.wa{display:block;text-align:center;text-decoration:none;background:linear-gradient(135deg,#2f9e44,#37b24d);color:#fff;border-radius:12px;padding:11px 14px;font-weight:700;margin-top:10px}
#toast{position:fixed;left:50%;bottom:16px;transform:translate(-50%,30px);background:#1a1200;color:#ffd700;border:1px solid #d4a017;padding:11px 18px;border-radius:22px;font-size:14px;opacity:0;transition:.3s;max-width:90%;text-align:center;z-index:20}
#toast.s{opacity:1;transform:translate(-50%,0)}
.card{transform:translateZ(0);box-shadow:0 8px 24px rgba(0,0,0,.45),0 0 0 1px rgba(212,160,23,.12);transition:transform .2s,box-shadow .2s}
.card:active{transform:scale(.99)}
.hero{box-shadow:0 12px 40px rgba(212,160,23,.25),inset 0 1px 0 rgba(255,215,0,.3);position:relative;overflow:hidden}
.hero::after{content:"";position:absolute;inset:0;background:linear-gradient(120deg,transparent 40%,rgba(255,215,0,.12) 50%,transparent 60%);animation:shine 4s infinite}
@keyframes shine{0%{transform:translateX(-100%)}100%{transform:translateX(100%)}}
.grid{perspective:600px;transform-style:preserve-3d;box-shadow:inset 0 0 30px rgba(0,0,0,.35),0 10px 28px rgba(0,0,0,.4)}
.grid div{box-shadow:inset 0 -2px 4px rgba(0,0,0,.25),inset 0 1px 0 rgba(255,255,255,.08);transition:transform .15s}
.grid div:active{transform:translateY(2px) scale(.96)}
.btn,.btn-blue,.btn-red{box-shadow:0 4px 14px rgba(0,0,0,.35),0 1px 0 rgba(255,255,255,.15) inset;text-shadow:0 1px 0 rgba(0,0,0,.2)}
.btn:active,.btn-blue:active{box-shadow:0 1px 4px rgba(0,0,0,.4) inset}
.rank{box-shadow:0 0 16px rgba(255,215,0,.5),0 2px 6px rgba(0,0,0,.4)}
.stats div{box-shadow:inset 0 2px 6px rgba(0,0,0,.3),0 1px 0 rgba(255,215,0,.1);transform:translateZ(4px)}
.bgrid button{box-shadow:0 3px 10px rgba(0,0,0,.3);transition:transform .12s,box-shadow .12s}
.bgrid button:active{transform:translateY(2px);box-shadow:0 1px 4px rgba(0,0,0,.4)}
.acc-item{display:flex;justify-content:space-between;align-items:center;padding:12px 0;border-top:1px solid var(--bd)}
.acc-item:first-child{border-top:0}
.chatbox{height:52vh;overflow-y:auto;background:rgba(0,0,0,.25);border:1px solid var(--bd);border-radius:14px;padding:10px;display:flex;flex-direction:column;gap:8px}
.msg{max-width:85%;padding:8px 10px;border-radius:12px;background:#2a2314;font-size:14px;line-height:1.35;word-break:break-word;align-self:flex-start}
.msg.me{align-self:flex-end;background:linear-gradient(135deg,#b8860b,#ffd700);color:#1a1200}
.msg .nm{display:block;font-size:11px;font-weight:800;color:var(--ac);margin-bottom:2px;cursor:pointer}
.msg.me .nm{color:#5c4a00;cursor:default}
.msg .tm{font-size:10px;font-weight:400;opacity:.6;margin-left:6px}
.msg.sys{align-self:center;background:transparent;color:var(--mu);font-size:12px;text-align:center;padding:2px 6px}
</style>
</head>
<body>
<div id="app"></div><div id="toast"></div>
<script>
// KONFIGURASI API (SAMA)
const API_STATS="https://data-base-fazxy.lovable.app/api/public/v1/player_stats";
const KEY_STATS="dk_74b1821ecf174d93ac2b432d1709b858";
const API_META="https://data-base-fazxy.lovable.app/api/public/v1/player_meta";
const KEY_META="dk_9b7f76500c7e4b5db41c34636ebce111";
const API_CHAT="https://data-base-fazxy.lovable.app/api/public/v1/server_chat";
const KEY_CHAT="dk_fa72a2910ae64758862bc32b6e73e43d";
const CHAT_KEEP_MS=24*3600*1000,CHAT_MAX=200,CHAT_SHOW=60;
const SRV_PREFIX="SERVER|",QUEST_PREFIX="QUEST|";
const DAY_MS=24*3600*1000;
const ADMIN_PHONE="0858-8238-2854",ADMIN_WA="6285882382854";
const REVIEW_MAX_DAYS=14,REVIEW_MS=3*60*1000;

// DATA NEGARA & BANGUNAN (SAMA)
const CORE=[
["Indonesia","🇮🇩",600,30,40],["Jepang","🇯🇵",900,25,30],["Amerika Serikat","🇺🇸",800,60,40],["Rusia","🇷🇺",500,70,30],
["Brasil","🇧🇷",600,30,45],["Jerman","🇩🇪",850,35,30],["Tiongkok","🇨🇳",700,55,50],["India","🇮🇳",550,40,55],
["Korea Selatan","🇰🇷",750,35,28],["Prancis","🇫🇷",720,40,32],["Inggris","🇬🇧",780,45,30],["Turki","🇹🇷",580,42,38],
["Kanada","🇨🇦",700,40,35],["Australia","🇦🇺",720,38,32],["Meksiko","🇲🇽",580,35,45],["Italia","🇮🇹",680,40,35],
["Spanyol","🇪🇸",650,38,36],["Arab Saudi","🇸🇦",900,50,30],["Mesir","🇪🇬",500,40,45],["Afrika Selatan","🇿🇦",550,35,40],
["Argentina","🇦🇷",580,35,40],["Thailand","🇹🇭",520,30,42],["Vietnam","🇻🇳",500,35,48],["Filipina","🇵🇭",480,30,50],
["Malaysia","🇲🇾",600,32,35],["Singapura","🇸🇬",950,25,25],["Polandia","🇵🇱",620,40,34],["Ukraina","🇺🇦",450,55,38],
["Belanda","🇳🇱",800,30,30],["Swedia","🇸🇪",780,28,28],["Swiss","🇨🇭",920,25,25],["Norwegia","🇳🇴",880,28,26],
["Belgia","🇧🇪",750,32,30],["Portugal","🇵🇹",600,35,32],["Yunani","🇬🇷",520,35,33],["Iran","🇮🇷",550,50,40],
["Irak","🇮🇶",480,45,38],["Pakistan","🇵🇰",450,50,55],["Bangladesh","🇧🇩",400,30,60],["Nigeria","🇳🇬",420,35,55],
["Kenya","🇰🇪",400,30,40],["Etiopia","🇪🇹",380,28,50],["Kolombia","🇨🇴",520,35,42],["Chili","🇨🇱",580,32,35],
["Peru","🇵🇪",500,30,38],["Venezuela","🇻🇪",450,40,36],["Taiwan","🇹🇼",800,40,30],["Hong Kong","🇭🇰",900,20,28],
["Uni Emirat Arab","🇦🇪",950,40,25],["Israel","🇮🇱",850,55,28],["Korea Utara","🇰🇵",300,80,35],["Kuba","🇨🇺",400,40,32],
["Selandia Baru","🇳🇿",700,30,28],["Irlandia","🇮🇪",720,30,28],["Austria","🇦🇹",780,32,30],["Ceko","🇨🇿",680,35,30],
["Hungaria","🇭🇺",600,35,30],["Rumania","🇷🇴",520,38,35],["Finlandia","🇫🇮",700,28,28],["Denmark","🇩🇰",820,30,28],
["Maroko","🇲🇦",480,35,40],["Aljazair","🇩🇿",500,40,42],["Tunisia","🇹🇳",450,30,35],["Ghana","🇬🇭",420,28,38],
["Tanzania","🇹🇿",400,28,45],["Uganda","🇺🇬",380,25,40],["Sudan","🇸🇩",350,35,42],["Angola","🇦🇴",450,30,38],
["Nepal","🇳🇵",380,25,40],["Sri Lanka","🇱🇰",420,28,36],["Myanmar","🇲🇲",400,40,45],["Kamboja","🇰🇭",380,25,38],
["Laos","🇱🇦",360,22,32],["Kazakhstan","🇰🇿",500,35,35],["Uzbekistan","🇺🇿",420,30,38],["Afghanistan","🇦🇫",300,45,40],
["Yaman","🇾🇪",320,35,38],["Suriah","🇸🇾",300,40,35],["Yordania","🇯🇴",450,35,32],["Lebanon","🇱🇧",400,30,30],
["Kuwait","🇰🇼",900,30,25],["Qatar","🇶🇦",980,25,22],["Bahrain","🇧🇭",850,22,22],["Oman","🇴🇲",700,30,28],
["Belarus","🇧🇾",450,40,32],["Bulgaria","🇧🇬",480,32,30],["Serbia","🇷🇸",450,35,30],["Kroasia","🇭🇷",520,30,28],
["Slovakia","🇸🇰",550,28,28],["Slovenia","🇸🇮",580,25,26],["Lituania","🇱🇹",500,25,28],["Latvia","🇱🇻",480,25,26],
["Estonia","🇪🇪",520,25,25],["Islandia","🇮🇸",750,15,20],["Georgia","🇬🇪",400,30,28],["Armenia","🇦🇲",380,28,26],
["Azerbaijan","🇦🇿",500,35,30],["Mongolia","🇲🇳",350,25,28],["Brunei","🇧🇳",800,18,18],["Timor Leste","🇹🇱",300,15,25],
["Papua Nugini","🇵🇬",350,20,30],["Fiji","🇫🇯",400,15,22],["Jamaika","🇯🇲",420,18,25],["Panama","🇵🇦",550,20,28],
["Kosta Rika","🇨🇷",520,18,28],["Guatemala","🇬🇹",400,25,35],["Bolivia","🇧🇴",380,25,35],["Paraguay","🇵🇾",400,25,32],
["Uruguay","🇺🇾",520,22,28],["Ekuador","🇪🇨",420,28,35],["Libya","🇱🇾",450,35,30],["Palestina","🇵🇸",300,25,30],
["Somalia","🇸🇴",250,30,35],["RD Kongo","🇨🇩",300,30,50],["Rwanda","🇷🇼",380,22,32],["Botswana","🇧🇼",480,18,25],
["Namibia","🇳🇦",450,18,25],["Mauritius","🇲🇺",600,12,20],["Maladewa","🇲🇻",500,10,18],["Bhutan","🇧🇹",350,12,20],
["Albania","🇦🇱",380,25,26],["Moldova","🇲🇩",350,22,28],["Vatikan","🇻🇦",1000,5,5],["Monako","🇲🇨",990,5,10],
["Andorra","🇦🇩",800,8,12],["Luksemburg","🇱🇺",950,15,18],["Malta","🇲🇹",600,15,20],["Siprus","🇨🇾",550,25,25],
["Senegal","🇸🇳",400,28,35],["Kamerun","🇨🇲",400,30,40],["Madagaskar","🇲🇬",350,22,38],["Zimbabwe","🇿🇼",340,28,35],
["Zambia","🇿🇲",360,25,36],["Mozambik","🇲🇿",360,25,40],["Mali","🇲🇱",300,20,32],["Niger","🇳🇪",280,18,35],
["Chad","🇹🇩",280,22,32],["Burkina Faso","🇧🇫",300,18,35],["Guinea","🇬🇳",320,18,30],["Benin","🇧🇯",320,15,28],
["Togo","🇹🇬",300,14,26],["Sierra Leone","🇸🇱",280,12,28],["Liberia","🇱🇷",280,12,26],["Mauritania","🇲🇷",320,15,25],
["Gabon","🇬🇦",480,15,22],["Kongo","🇨🇬",320,25,35],["Eritrea","🇪🇷",280,20,25],["Djibouti","🇩🇯",350,12,18],
["Turkmenistan","🇹🇲",420,25,28],["Tajikistan","🇹🇯",320,22,30],["Kirgizstan","🇰🇬",340,20,28],["Honduras","🇭🇳",360,22,32],
["El Salvador","🇸🇻",380,22,30],["Nikaragua","🇳🇮",340,22,30],["Haiti","🇭🇹",280,15,35],["Republik Dominika","🇩🇴",450,25,32],
["Trinidad dan Tobago","🇹🇹",500,18,22],["Bahama","🇧🇸",550,10,16],["Barbados","🇧🇧",500,8,14],["Belize","🇧🇿",360,10,16],
["Suriname","🇸🇷",380,12,18],["Guyana","🇬🇾",400,12,20],["Samoa","🇼🇸",340,8,14],["Tonga","🇹🇴",320,8,12],
["Vanuatu","🇻🇺",300,8,14],["Solomon","🇸🇧",280,10,16],["Palau","🇵🇼",400,5,10],["Nauru","🇳🇷",350,5,8],
["Tuvalu","🇹🇻",300,5,8],["Kiribati","🇰🇮",280,5,12],["Cabo Verde","🇨🇻",380,8,14],["Komoro","🇰🇲",280,8,16],
["Sao Tome","🇸🇹",300,6,12],["Eswatini","🇸🇿",320,10,18],["Lesotho","🇱🇸",300,10,18],["Afrika Tengah","🇨🇫",250,15,25],
["Sudan Selatan","🇸🇸",260,25,30],["Burundi","🇧🇮",280,18,30],["Malawi","🇲🇼",300,15,35],["Gambia","🇬🇲",300,10,20],
["Guinea-Bissau","🇬🇼",260,10,22],["Grenada","🇬🇩",380,6,12],["Saint Lucia","🇱🇨",400,6,12],["Dominika","🇩🇲",350,6,12],
["Antigua dan Barbuda","🇦🇬",420,6,12],["Saint Kitts","🇰🇳",450,5,10],["Saint Vincent","🇻🇨",360,6,12],
["Liechtenstein","🇱🇮",950,5,10],["San Marino","🇸🇲",700,8,12],["Montenegro","🇲🇪",380,18,22],["Bosnia","🇧🇦",360,25,26],
["Kosovo","🇽🇰",320,20,24],["Makedonia Utara","🇲🇰",360,22,25],["Pantai Gading","🇨🇮",420,30,38]
];
const CS=CORE.map(x=>({n:x[0],f:x[1],m:x[2],a:x[3],p:x[4]}));
CS.sort((a,b)=>a.n.localeCompare(b.n,"id"));

const B={
h:{e:"🏠",n:"Rumah",c:100,cat:"infra"},ap:{e:"🏢",n:"Apartemen",c:280,cat:"infra"},
r:{e:"🛣️",n:"Jalan",c:15,cat:"infra"},jbr:{e:"🌉",n:"Jembatan",c:120,cat:"infra"},
st:{e:"🚉",n:"Stasiun",c:220,cat:"infra"},bd:{e:"✈️",n:"Bandara",c:450,cat:"infra"},
pl:{e:"⚓",n:"Pelabuhan",c:380,cat:"infra"},f:{e:"🌾",n:"Ladang",c:80,cat:"eko"},
p:{e:"🏭",n:"Pabrik",c:150,cat:"eko"},ps:{e:"🛒",n:"Pasar",c:140,cat:"eko"},
ml:{e:"🏬",n:"Mall",c:320,cat:"eko"},bk:{e:"🏦",n:"Bank",c:300,cat:"eko"},
tb:{e:"⛏️",n:"Tambang",c:250,cat:"eko"},sk:{e:"🏫",n:"Sekolah",c:180,cat:"edu"},
un:{e:"🎓",n:"Universitas",c:420,cat:"edu"},rs:{e:"🏥",n:"RS",c:300,cat:"edu"},
pk:{e:"🩺",n:"Puskesmas",c:160,cat:"edu"},b:{e:"🏰",n:"Barak",c:200,cat:"mil"},
mk:{e:"🎖️",n:"Markas",c:450,cat:"mil"},kp:{e:"👮",n:"Polisi",c:180,cat:"mil"},
pd:{e:"🛡️",n:"Pertahanan",c:500,cat:"mil"},is:{e:"🏛️",n:"Istana",c:600,cat:"gov"},
bc:{e:"🏢",n:"Balai Kota",c:250,cat:"gov"},tk:{e:"🌳",n:"Taman",c:100,cat:"fun"},
sd:{e:"🏟️",n:"Stadion",c:350,cat:"fun"},bi:{e:"🎬",n:"Bioskop",c:180,cat:"fun"},
tw:{e:"🏞️",n:"Wisata",c:280,cat:"fun"},x:{e:"💣",n:"Bongkar",c:0,cat:"util"}
};
const CATS=[{id:"infra",n:"🏗️ Infra"},{id:"eko",n:"💰 Ekonomi"},{id:"edu",n:"📚 Edu"},{id:"mil",n:"⚔️ Militer"},{id:"gov",n:"🏛️ Gov"},{id:"fun",n:"🎉 Hiburan"},{id:"util",n:"🔧 Lain"}];
let buildCat="infra";
const CODES={azfermodz:{m:1e11,a:5e11},azfergames:{m:5e10,a:3.5e11},azferscript:{m:9e10,a:4e11},azferadmin:{admin:true}};
const PACK_AMOUNTS=[1e6,5e6,1e7,5e7,1e8,5e8,1e9,5e9,1e10,5e10,1e11,5e11,1e12,1e14];
function packLabel(n){if(n>=1e12)return(n/1e12).toFixed(n%1e12===0?0:1)+" T";if(n>=1e9)return(n/1e9).toFixed(n%1e9===0?0:1)+" M";if(n>=1e6)return(n/1e6).toFixed(n%1e6===0?0:1)+" Jt";return fmt(n)}
function costMoney(a){return Math.round(a/1e6*100000)}
function costArmy(a){return Math.round(a/1e6*500000)}
function getCart(){try{return JSON.parse(ls("negara_cart")||"{}")}catch(e){return{}}}
function setCart(c){ls("negara_cart",JSON.stringify(c))}
const TRADE_PREFIX="TRADE|";
function genTradeId(){return "T"+Math.random().toString(36).slice(2,9).toUpperCase()}

/* ===== CHAT PUBLIC ===== */
const CHAT_ROOM="PUBLIK";
let chatTab="chat",chatTimer=null,chatSig="",chatCleaned=false,chatShape="extra",chatLastSend=0,chatLastText="",tradeCtx="lobby",plMode="players",plOnly=false;
async function chatApi(method,body,qs){
  try{return await api(method,API_CHAT+(qs||""),KEY_CHAT,body)}
  catch(e){throw new Error("[chat] "+method+" gagal: "+e.message)}
}
function cd(m){return(m.extra&&typeof m.extra==="object"&&m.extra.text!==undefined)?m.extra:m}
async function chatSend(payload){
  const withExtra={player_id:uid,extra:payload};
  const flat={player_id:uid,...payload};
  if(chatShape==="extra"){
    try{return await chatApi("POST",withExtra)}
    catch(e){if(!/\b(400|422)\b/.test(e.message))throw e;chatShape="flat"}
  }
  return await chatApi("POST",flat);
}
function sysChat(text){
  chatSend({kind:"sys",server:CHAT_ROOM,name:"Sistem",text,at:new Date().toISOString()}).catch(()=>{});
}
function chatTabsHtml(){
  return `<div class="card"><div style="display:flex;justify-content:space-between;align-items:center"><b>💬 Chat Public</b><button class="btn-gray" style="padding:4px 10px" onclick="leaveChat()">←</button></div>
  <div class="tabs" style="margin:10px 0 0"><button class="${chatTab==="chat"?"on":""}" onclick="openChat('chat')">💬 Chat</button><button class="${chatTab==="players"?"on":""}" onclick="openChat('players')">👥 Pemain</button><button class="${chatTab==="trade"?"on":""}" onclick="openChat('trade')">🤝 Trade</button></div></div>`;
}
function openChat(t){
  if(!uid)return;
  chatTab=t||"chat";
  clearInterval(chatTimer);chatTimer=null;
  if(chatTab==="trade"){tradeCtx="chat";openTrade()}
  else if(chatTab==="players")renderPlayers();
  else renderChat();
}
function leaveChat(){clearInterval(chatTimer);chatTimer=null;lobby()}
function renderChat(){
  $("app").innerHTML=chatTabsHtml()+`<div class="chatbox" id="chatBox"><p class="mu" style="text-align:center;margin:auto">Memuat chat...</p></div>
  <div style="display:flex;gap:6px;margin-top:8px"><input id="chatIn" maxlength="${CHAT_MAX}" placeholder="Ngobrol di sini..." autocomplete="off" style="margin:0" onkeydown="if(event.key==='Enter')sendChat()"><button class="btn" style="width:auto;margin:0;padding:10px 16px" onclick="sendChat()">Kirim</button></div>
  <p class="mu" style="margin-top:6px">Ruang santai untuk ngobrol. Ketuk nama pemain untuk memilihnya sebagai tujuan Trade. Pesan terhapus otomatis setelah 24 jam.</p>`;
  chatSig="";chatCleaned=false;
  loadChat(true);
  chatTimer=setInterval(loadChat,4000);
}
async function loadChat(force){
  const box=$("chatBox");
  if(!box){clearInterval(chatTimer);chatTimer=null;return}
  try{
    const list=arr(await chatApi("GET"));
    const now=Date.now();
    const tOf=m=>new Date(cd(m).at||m.created_at||0).getTime();
    if(!chatCleaned){
      chatCleaned=true;
      list.filter(m=>m.id&&tOf(m)>0&&now-tOf(m)>CHAT_KEEP_MS).slice(0,10).forEach(m=>{chatApi("DELETE",null,"?id="+m.id).catch(()=>{})});
    }
    const msgs=list.filter(m=>cd(m).server===CHAT_ROOM&&tOf(m)>0&&now-tOf(m)<=CHAT_KEEP_MS)
      .sort((a,b)=>tOf(a)-tOf(b)).slice(-CHAT_SHOW);
    const last=msgs[msgs.length-1];
    const sig=msgs.length+"|"+(last?(last.id||tOf(last)):"");
    if(sig===chatSig&&!force)return;
    chatSig=sig;
    const near=box.scrollHeight-box.scrollTop-box.clientHeight<90;
    box.innerHTML=msgs.length?msgs.map(m=>{
      const d=cd(m);
      if(d.kind==="sys")return `<div class="msg sys">${esc(d.text)}</div>`;
      const me=m.player_id===uid;
      const tm=new Date(tOf(m)).toLocaleTimeString("id-ID",{hour:"2-digit",minute:"2-digit"});
      const nm=esc(d.name||m.player_id);
      return `<div class="msg${me?" me":""}"><span class="nm"${me?"":` onclick="pickChatTarget('${esc(m.player_id)}','${esc(d.name||"")}')"`}>${esc(d.flag||"")} ${nm}<span class="tm">${tm}</span></span>${esc(d.text)}</div>`;
    }).join(""):`<p class="mu" style="text-align:center;margin:auto">Belum ada pesan. Mulai ngobrol!</p>`;
    if(near||force)box.scrollTop=box.scrollHeight;
  }catch(e){
    box.innerHTML=`<p class="mu" style="color:var(--bad);margin:auto;text-align:center">${esc(e.message)}</p>`;
  }
}
async function sendChat(){
  const inp=$("chatIn");if(!inp)return;
  const text=inp.value.trim().slice(0,CHAT_MAX);
  if(!text)return;
  const now=Date.now();
  if(now-chatLastSend<1500)return toast("Pelan-pelan, jangan spam");
  if(text===chatLastText&&now-chatLastSend<15000)return toast("Pesan yang sama baru saja dikirim");
  chatLastSend=now;chatLastText=text;inp.value="";
  try{
    await chatSend({kind:"msg",server:CHAT_ROOM,uid,name:ACC?.name||"Pemain",flag:"",text,at:new Date().toISOString()});
    loadChat(true);
  }catch(e){toast(e.message);inp.value=text}
}
function pickChatTarget(id,name){
  if(id===uid)return;
  window._tradeTo={id,name};
  toast("🤝 Tujuan trade: "+name+" · buka tab Trade");
}

/* ===== DAFTAR PEMAIN ===== */
let _playerCache=[];
async function loadAllPlayers(){
  const list=arr(await api("GET",API_STATS,KEY_STATS));
  const lastChat={};
  try{arr(await chatApi("GET")).forEach(m=>{const d=cd(m);if(d.server!==CHAT_ROOM||d.kind==="sys")return;const t=new Date(d.at||m.created_at||0).getTime();if(t>(lastChat[m.player_id]||0))lastChat[m.player_id]=t})}catch(e){}
  const map={};
  list.forEach(p=>{
    const id=String(p.player_id||"");
    if(!id||id.startsWith(SRV_PREFIX)||id.startsWith(TRADE_PREFIX)||id.startsWith(QUEST_PREFIX)||id.startsWith("BOTTRADE|"))return;
    if(!map[id]||new Date(p.created_at||0)>new Date(map[id].created_at||0))map[id]=p;
  });
  const now=Date.now();
  return Object.values(map).map(p=>{
    const gs=p.game_stats||{};
    const la=Math.max(gs.last_active?new Date(gs.last_active).getTime():0,lastChat[p.player_id]||0);
    return{id:p.player_id,name:gs.name||p.name||p.player_id,level:p.level||1,exp:p.exp||0,
      country:gs.country||"",server:gs.server||"",online:la>0&&now-la<5*60000,last:la,me:p.player_id===uid};
  });
}
async function refreshPlayers(){
  const el=$("plList");if(!el)return;
  el.innerHTML="<p class='mu'>Memuat...</p>";
  try{_playerCache=await loadAllPlayers();filterPlayerList()}
  catch(e){el.innerHTML=`<p class="mu" style="color:var(--bad)">${esc(e.message)}</p>`}
}
function playerRowHtml(p){
  const rk=getRank(p.level*100+p.exp);
  const fl=p.country?flagOf(p.country):"";
  const acts=plMode==="players"
    ?(p.me?`<span class="badge blue">Kamu</span>`
      :`<button class="btn-gray" style="padding:8px 10px" onclick="copyId('${esc(p.id)}')">📋</button><button class="btn" style="width:auto;margin:0;padding:8px 12px" onclick="tradeWith('${esc(p.id)}','${esc(p.name)}')">🤝</button>`)
    :`<button class="btn" style="width:auto;margin:0;padding:8px 12px" onclick="selectTradePlayer('${esc(p.id)}','${esc(p.name)}')">Pilih</button>`;
  return `<div class="acc-item"><div style="min-width:0"><b>${p.online?"🟢":"⚪"} ${esc(p.name)}</b> ${fl}<br>
    <span class="rank" style="font-size:10px;padding:1px 7px">${esc(rk)}</span> <span class="mu">Lv ${p.level}${p.server?" · "+esc(p.server):""}</span><br>
    <span class="mu" style="font-size:11px">${esc(p.id)}</span></div><div style="display:flex;gap:6px;align-items:center">${acts}</div></div>`;
}
function filterPlayerList(){
  const el=$("plList");if(!el)return;
  const q=($("plSearch")?.value||"").toLowerCase().trim();
  let rows=_playerCache.filter(p=>plMode==="players"||!p.me);
  if(plMode==="players"&&plOnly)rows=rows.filter(p=>p.online);
  if(q)rows=rows.filter(p=>(p.name||"").toLowerCase().includes(q)||(p.id||"").toLowerCase().includes(q)||(p.country||"").toLowerCase().includes(q));
  rows.sort((a,b)=>(b.online-a.online)||(a.name||"").localeCompare(b.name||""));
  const online=_playerCache.filter(p=>p.online).length;
  const cnt=$("plCount");if(cnt)cnt.textContent=rows.length+" pemain ditampilkan · 🟢 "+online+" online dari "+_playerCache.length;
  if(!rows.length){el.innerHTML="<p class='mu'>Pemain tidak ditemukan</p>";return}
  el.innerHTML=rows.slice(0,50).map(playerRowHtml).join("")+(rows.length>50?`<p class="mu">+${rows.length-50} lainnya, gunakan pencarian</p>`:"");
}
function setPlOnly(v){
  plOnly=v;
  const a=$("plAll"),o=$("plOn");if(a)a.className=v?"":"on";if(o)o.className=v?"on":"";
  filterPlayerList();
}
function copyId(id){try{navigator.clipboard.writeText(id).then(()=>toast("ID disalin"),()=>toast(id))}catch(e){toast(id)}}
function tradeWith(id,name){window._tradeTo={id,name};openChat("trade")}
function renderPlayers(){
  plMode="players";plOnly=false;
  $("app").innerHTML=chatTabsHtml()+`<div class="card"><div style="display:flex;justify-content:space-between;align-items:center"><b>👥 Daftar Pemain</b>
    <button class="btn-gray" style="padding:4px 10px" onclick="refreshPlayers()">⟳</button></div>
    <input id="plSearch" placeholder="🔎 Cari nama, ID, atau negara" oninput="filterPlayerList()">
    <div class="tabs" style="margin:8px 0 0"><button id="plAll" class="on" onclick="setPlOnly(false)">Semua</button><button id="plOn" onclick="setPlOnly(true)">🟢 Online</button></div>
    <p class="mu" id="plCount" style="margin-top:8px"></p>
    <div id="plList"><p class="mu">Memuat...</p></div></div>`;
  refreshPlayers();
}

/* ===== TRADE ===== */
async function openTrade(ctx){
  if(ctx)tradeCtx=ctx;
  if(S)return toast("Trade hanya di Lobby & Chat Public");
  plMode="trade";plOnly=false;
  clearInterval(chatTimer);chatTimer=null;
  const head=tradeCtx==="chat"?chatTabsHtml():`<div class="card"><div style="display:flex;justify-content:space-between;align-items:center"><b>🤝 Trade</b><button class="btn-gray" style="padding:4px 10px" onclick="lobby()">←</button></div></div>`;
  $("app").innerHTML=head+`<div class="card"><p class="mu">Tukar Koin / Uang / Kekuatan dengan pemain lain. Hanya di Lobby & Chat Public.</p>
  <p class="mu">Koin: 🪙 <b>${fmt(coins)}</b> · Uang: 💰 <b>${fmt(statsRow?.money||0)}</b> · Pasukan: ⚔️ <b>${fmt(statsRow?.army||0)}</b></p></div>

  <div class="card"><div style="display:flex;justify-content:space-between"><b>🤖 Bot Trade (Gratis)</b>
  <button class="btn-gray" style="padding:4px 10px" onclick="loadBots()">⟳</button></div>
  <p class="mu">Minta resource gratis dari bot admin (ada batas harian).</p>
  <div id="botList"><p class="mu">Memuat bot...</p></div></div>

  <div class="card"><div style="display:flex;justify-content:space-between"><b>👥 Cari Pemain</b>
  <button class="btn-gray" style="padding:4px 10px" onclick="refreshPlayers()">⟳</button></div>
  <input id="plSearch" placeholder="🔎 Cari nama / ID / negara" oninput="filterPlayerList()" style="margin-bottom:6px">
  <p class="mu" id="plCount"></p>
  <div id="plList" class="mu">Memuat...</div></div>

  <div class="card"><b>Buat Penawaran</b>
    <label class="mu">Player ID lawan</label>
    <input id="trTo" placeholder="Pilih pemain di daftar


<html lang="id">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Battle of the Nations</title>
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
.banst.perm{background:#e03131;color:#fff}.banst.temp{background:#f59f00;color:#212529}
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
.badge{display:inline-block;padding:2px 8px;border-radius:12px;font-size:11px;font-weight:700}
.ok{background:#2f9e44;color:#fff}.no{background:#e03131;color:#fff}.warn{background:#f59f00;color:#212529}.blue{background:#1971c2;color:#fff}
</style>
</head>
<body>
<div id="app"></div><div id="toast"></div>
<script>
const API_STATS="https://data-base-fazxy.lovable.app/api/public/v1/player_stats";
const KEY_STATS="dk_74b1821ecf174d93ac2b432d1709b858";
const API_META="https://data-base-fazxy.lovable.app/api/public/v1/player_meta";
const KEY_META="dk_9b7f76500c7e4b5db41c34636ebce111";
const API_CHAT="https://data-base-fazxy.lovable.app/api/public/v1/server_chat";
const KEY_CHAT="dk_fa72a2910ae64758862bc32b6e73e43d";
const CHAT_MAX=200,CHAT_SHOW=80,CHAT_ROOM="PUBLIK";
const SRV_PREFIX="SERVER|",QUEST_PREFIX="QUEST|";
const DAY_MS=24*3600*1000;
/* ===== ANTI-CHEAT ===== */
const MAX_COINS=5e8;      // 500 juta koin maks (non-admin)
const MAX_MONEY=1e18;     // uang sangat besar masih sah (admin gift)
const MAX_ARMY=1e18;
const CHEAT_COIN_FLAG=1e12; // koin >= 1T = pasti cheat
function isAdminAcc(){return!!(metaRow&&metaRow.is_admin)}
function clampNum(n,max){n=+n||0;if(!isFinite(n)||n<0)return 0;return Math.min(Math.floor(n),max)}
function isCheatCoins(v){return(+v||0)>=CHEAT_COIN_FLAG}
function sanitizeCoins(v){if(isAdminAcc())return Math.max(0,Math.floor(+v||0));return clampNum(v,MAX_COINS)}
function sanitizeMoney(v){if(isAdminAcc())return Math.max(0,Math.floor(+v||0));return clampNum(v,MAX_MONEY)}
function sanitizeArmy(v){if(isAdminAcc())return Math.max(0,Math.floor(+v||0));return clampNum(v,MAX_ARMY)}
function maxTradeAmt(type){
  if(isAdminAcc())return 1e18;
  if(type==="coins")return MAX_COINS;
  if(type==="money")return MAX_MONEY;
  if(type==="army")return MAX_ARMY;
  return MAX_COINS;
}
async function flagCheater(reason){
  if(isAdminAcc())return; // admin tidak di-flag
  try{
    if(!uid||!metaRow||!metaRow.id)return;
    const ex={...(metaRow.extra||{}),cheat_flag:true,cheat_reason:reason,cheat_at:new Date().toISOString()};
    await api("PATCH",API_META+"?id="+metaRow.id,KEY_META,{extra:ex});
    metaRow.extra=ex;
  }catch(e){}
}
async function enforceAntiCheat(src){
  if(isAdminAcc())return false; // admin bypass total
  let dirty=false,reason="";
  const rawCoins=statsRow?(statsRow.coins!=null?+statsRow.coins:((statsRow.game_stats||{}).coins||0)):coins;
  if(isCheatCoins(rawCoins)||(+rawCoins)>MAX_COINS*2||isCheatCoins(coins)){
    reason="coins="+rawCoins;
    coins=sanitizeCoins(Math.min(rawCoins,MAX_COINS));
    dirty=true;
  }else{
    coins=sanitizeCoins(coins);
  }
  if(statsRow){
    // JANGAN pakai isCheatCoins untuk money/army
    if((+statsRow.money||0)>MAX_MONEY){statsRow.money=sanitizeMoney(statsRow.money);dirty=true;reason+=(reason?",":"")+"money"}
    if((+statsRow.army||0)>MAX_ARMY){statsRow.army=sanitizeArmy(statsRow.army);dirty=true;reason+=(reason?",":"")+"army"}
  }
  if(S){
    if((+S.m||0)>MAX_MONEY){S.m=sanitizeMoney(S.m);dirty=true}
    if((+S.army||0)>MAX_ARMY){S.army=sanitizeArmy(S.army);dirty=true}
  }
  if(dirty){
    try{
      if(statsRow&&statsRow.id){
        const gs={...(statsRow.game_stats||{}),coins,anti_cheat_reset:new Date().toISOString()};
        await api("PATCH",API_STATS+"?id="+statsRow.id,KEY_STATS,{coins,money:sanitizeMoney(statsRow.money),army:sanitizeArmy(statsRow.army),game_stats:gs});
        statsRow.coins=coins;statsRow.game_stats=gs;
      }
    }catch(e){}
    await flagCheater(reason||src||"anomaly");
    toast("🛡️ Anti-cheat: nilai tidak wajar dinormalisasi");
  }
  return dirty;
}

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

/* ===== CHAT PUBLIC (permanen, hanya admin reset) ===== */
let chatTab="chat",chatTimer=null,chatSig="",chatShape="extra",chatLastSend=0,chatLastText="",tradeCtx="lobby",plMode="players",plOnly=false,_playerCache=[];
async function chatApi(method,body,qs){
  try{return await api(method,API_CHAT+(qs||""),KEY_CHAT,body)}
  catch(e){throw new Error("[chat] "+e.message)}
}
function cd(m){return(m.extra&&typeof m.extra==="object"&&(m.extra.text!==undefined||m.extra.kind))?m.extra:m}
async function chatSend(payload){
  const withExtra={player_id:uid,extra:payload};
  const flat={player_id:uid,...payload};
  if(chatShape==="extra"){
    try{return await chatApi("POST",withExtra)}
    catch(e){if(!/\b(400|422)\b/.test(e.message))throw e;chatShape="flat"}
  }
  return await chatApi("POST",flat);
}
function chatTabsHtml(){
  return `<div class="card"><div style="display:flex;justify-content:space-between;align-items:center"><b>💬 Chat Public</b><button class="btn-gray" style="padding:4px 10px" onclick="leaveChat()">←</button></div>
  <div class="tabs" style="margin:10px 0 0"><button class="${chatTab==="chat"?"on":""}" onclick="openChat('chat')">💬 Chat</button><button class="${chatTab==="players"?"on":""}" onclick="openChat('players')">👥 Pemain</button><button class="${chatTab==="trade"?"on":""}" onclick="openChat('trade')">🤝 Trade</button></div></div>`;
}
function openChat(t){
  if(!uid)return;
  chatTab=t||"chat";
  clearInterval(chatTimer);chatTimer=null;
  if(chatTab==="trade"){tradeCtx="chat";openTrade("chat")}
  else if(chatTab==="players")renderPlayers();
  else renderChat();
}
function leaveChat(){clearInterval(chatTimer);chatTimer=null;lobby()}
function renderChat(){
  $("app").innerHTML=chatTabsHtml()+`<div class="chatbox" id="chatBox"><p class="mu" style="text-align:center;margin:auto">Memuat chat...</p></div>
  <div style="display:flex;gap:6px;margin-top:8px"><input id="chatIn" maxlength="${CHAT_MAX}" placeholder="Ngobrol..." autocomplete="off" style="margin:0" onkeydown="if(event.key==='Enter')sendChat()"><button class="btn" style="width:auto;margin:0;padding:10px 16px" onclick="sendChat()">Kirim</button></div>
  <p class="mu" style="margin-top:6px">Chat permanen — hanya admin yang bisa reset. Ketuk nama untuk trade.</p>`;
  chatSig="";
  loadChat(true);
  chatTimer=setInterval(loadChat,4000);
}
async function loadChat(force){
  const box=$("chatBox");
  if(!box){clearInterval(chatTimer);chatTimer=null;return}
  try{
    const list=arr(await chatApi("GET"));
    const tOf=m=>new Date(cd(m).at||m.created_at||0).getTime();
    const msgs=list.filter(m=>cd(m).server===CHAT_ROOM).sort((a,b)=>tOf(a)-tOf(b)).slice(-CHAT_SHOW);
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
      const inv=!!d.investigation;
      const invWarn=inv?`<div style="font-size:10px;color:#f59f00;margin-top:4px">⚠️ Jangan percaya orang ini — pernah di-ban / sedang investigasi. Akunmu bisa ikut terpengaruh.</div>`:"";
      const rl=d.role||"biasa";
      const rb=rl==="admin"?`<span class="title-admin">👑 ADMIN</span>`:rl==="premium"?`<span class="title-prem">⭐ PREMIUM</span>`:`<span class="title-biasa">👤 BIASA</span>`;
      return `<div class="msg${me?" me":""}"><span class="nm"${me?"":` onclick="pickChatTarget('${esc(m.player_id)}','${esc(d.name||"")}')"`}>${esc(d.flag||"")} ${nm} ${rb}${inv?` <span class="badge warn" style="font-size:9px">INV</span>`:""}<span class="tm">${tm}</span></span>${esc(d.text)}${invWarn}</div>`;
    }).join(""):`<p class="mu" style="text-align:center;margin:auto">Belum ada pesan.</p>`;
    if(near||force)box.scrollTop=box.scrollHeight;
  }catch(e){box.innerHTML=`<p class="mu" style="color:var(--bad);margin:auto;text-align:center">${esc(e.message)}</p>`}
}
async function sendChat(){
  const inp=$("chatIn");if(!inp)return;
  const text=inp.value.trim().slice(0,CHAT_MAX);
  if(!text)return;
  const now=Date.now();
  if(now-chatLastSend<1500)return toast("Jangan spam");
  if(text===chatLastText&&now-chatLastSend<15000)return toast("Pesan sama baru dikirim");
  chatLastSend=now;chatLastText=text;inp.value="";
  try{
    await chatSend({kind:"msg",server:CHAT_ROOM,uid,name:ACC?.name||"Pemain",flag:"",text,at:new Date().toISOString(),investigation:isInvestigation(),role:getRole()});
    loadChat(true);
  }catch(e){toast(e.message);inp.value=text}
}
function pickChatTarget(id,name){
  if(id===uid)return;
  window._tradeTo={id,name};
  toast("🤝 Tujuan trade: "+name);
}

/* ===== CEK PROFIL ===== */
async function loadAllPlayers(){
  const list=arr(await api("GET",API_STATS,KEY_STATS));
  const metaAll=arr(await api("GET",API_META,KEY_META));
  const metaMap={};
  metaAll.forEach(m=>{
    if(!m.player_id)return;
    if(!metaMap[m.player_id]||(m.is_banned&&!metaMap[m.player_id].is_banned))metaMap[m.player_id]=m;
  });
  const map={};
  list.forEach(p=>{
    const id=String(p.player_id||"");
    if(!id||id.startsWith(SRV_PREFIX)||id.startsWith(TRADE_PREFIX)||id.startsWith(QUEST_PREFIX)||id.startsWith("BOTTRADE|"))return;
    if(!map[id]||new Date(p.created_at||0)>new Date(map[id].created_at||0))map[id]=p;
  });
  const now=Date.now();
  return Object.values(map).map(p=>{
    const gs=p.game_stats||{};
    const la=gs.last_active?new Date(gs.last_active).getTime():0;
    const meta=metaMap[p.player_id];
    return{id:p.player_id,name:gs.name||p.name||p.player_id,level:p.level||1,exp:p.exp||0,
      country:gs.country||"",server:gs.server||"",online:la>0&&now-la<5*60000,me:p.player_id===uid,
      banned:!!(meta&&meta.is_banned),investigation:!!(meta&&meta.extra&&meta.extra.investigation&&!meta.is_banned),
      ban_reason:(meta&&meta.extra&&(meta.extra.ban_reason||meta.extra.investigation_reason))||""};
  });
}
async function openProfileCheck(){
  $("app").innerHTML=`<div class="card"><div style="display:flex;justify-content:space-between"><b>🔍 Cek Profil</b>
  <button class="btn-gray" style="padding:4px 10px" onclick="lobby()">←</button></div>
  <p class="mu">Cek online, ban, atau status investigasi pemain lain.</p>
  <input id="profQ" placeholder="Player ID atau nama" onkeydown="if(event.key==='Enter')doProfileCheck()">
  <button class="btn" onclick="doProfileCheck()">Cek</button></div>
  <div class="card"><b>Daftar pemain</b>
  <input id="plSearch" placeholder="🔎 Cari..." oninput="filterProfList()">
  <div id="plList"><p class="mu">Memuat...</p></div></div>
  <div id="profResult"></div>`;
  try{_playerCache=await loadAllPlayers();filterProfList()}catch(e){$("plList").innerHTML="<p class='mu'>Gagal</p>"}
}
function filterProfList(){
  const el=$("plList");if(!el)return;
  const q=($("plSearch")?.value||"").toLowerCase().trim();
  let rows=(_playerCache||[]).filter(p=>!p.me);
  if(q)rows=rows.filter(p=>(p.name||"").toLowerCase().includes(q)||(p.id||"").toLowerCase().includes(q));
  rows.sort((a,b)=>(b.online-a.online)||(a.name||"").localeCompare(b.name||""));
  el.innerHTML=rows.slice(0,40).map(p=>{
    let st=p.banned?"🚫":p.investigation?"⚠️":p.online?"🟢":"⚪";
    return `<div class="acc-item"><div><b>${st} ${esc(p.name)}</b><br><span class="mu">${esc(p.id)}</span></div>
    <button class="btn" style="width:auto;margin:0;padding:8px 12px" onclick="showProfile('${esc(p.id)}')">Cek</button></div>`;
  }).join("")||"<p class='mu'>Tidak ada</p>";
}
async function doProfileCheck(){
  const q=($("profQ").value||"").trim();
  if(!q)return toast("Isi ID/nama");
  if(!_playerCache.length)try{_playerCache=await loadAllPlayers()}catch(e){}
  const hit=_playerCache.find(p=>p.id===q||(p.name||"").toLowerCase()===q.toLowerCase());
  showProfile(hit?hit.id:q);
}
async function showProfile(pid){
  const host=$("profResult");
  const put=(h)=>{if(host)host.innerHTML=h;else toast("Buka Cek Profil dulu")};
  put(`<div class="card"><p class="mu">Memuat...</p></div>`);
  try{
    if(!_playerCache.length)_playerCache=await loadAllPlayers();
    let p=_playerCache.find(x=>x.id===pid);
    if(!p){
      const statsList=arr(await api("GET",API_STATS,KEY_STATS)).filter(x=>x.player_id===pid);
      const metaList=arr(await api("GET",API_META,KEY_META)).filter(x=>x.player_id===pid);
      const st=statsList.sort((a,b)=>new Date(b.created_at||0)-new Date(a.created_at||0))[0];
      const meta=metaList[0];
      const gs=(st&&st.game_stats)||{};
      p={id:pid,name:gs.name||pid,level:st?(st.level||1):1,exp:st?(st.exp||0):0,country:gs.country||"",server:gs.server||"",
        online:false,banned:!!(meta&&meta.is_banned),investigation:!!(meta&&meta.extra&&meta.extra.investigation&&!(meta&&meta.is_banned)),
        ban_reason:(meta&&meta.extra&&(meta.extra.ban_reason||meta.extra.investigation_reason))||""};
    }
    let statusBadge=p.banned?`<span class="badge no">🚫 DIBANNED</span>`:p.investigation?`<span class="badge warn">⚠️ INVESTIGASI</span>`:`<span class="badge ok">✅ AKTIF</span>`;
    let onlineBadge=p.online?`<span class="badge ok">🟢 Online</span>`:`<span class="badge">⚪ Offline / tidak aktif</span>`;
    put(`<div class="card">
      <div style="display:flex;justify-content:space-between;align-items:center"><b>👤 ${esc(p.name)}</b>${statusBadge}</div>
      <p class="mu" style="margin-top:6px">ID: ${esc(p.id)}</p>
      <p style="margin-top:8px">${onlineBadge} · <span class="rank">Lv ${p.level} · ${getRank(p.level*100+p.exp)}</span></p>
      <p class="mu" style="margin-top:8px">Negara: ${esc(p.country||"-")} · Server: ${esc(p.server||"-")}</p>
      ${p.banned||p.investigation?`<p style="margin-top:10px;color:var(--bad)"><b>Catatan:</b> ${esc(p.ban_reason||"-")}</p>`:""}
      ${p.investigation?`<p class="mu" style="margin-top:8px">⚠️ Dalam investigasi: bisa main, <b>tidak bisa trade</b>, chat bertanda peringatan.</p>`:""}
      <button class="btn-blue" style="margin-top:10px" onclick="window._tradeTo={id:'${esc(p.id)}',name:'${esc(p.name)}'};openTrade('lobby')" ${p.banned||p.investigation?"disabled style='opacity:.45'":""}>🤝 Trade</button>
    </div>`);
  }catch(e){put(`<div class="card"><p class="mu" style="color:var(--bad)">${esc(e.message)}</p></div>`)}
}
function renderPlayers(){
  plMode="players";
  $("app").innerHTML=chatTabsHtml()+`<div class="card"><div style="display:flex;justify-content:space-between"><b>👥 Pemain</b>
  <button class="btn-gray" style="padding:4px 10px" onclick="refreshChatPlayers()">⟳</button></div>
  <input id="plSearch" placeholder="🔎 Cari..." oninput="filterChatPlayers()">
  <div id="plList"><p class="mu">Memuat...</p></div></div>`;
  refreshChatPlayers();
}
async function refreshChatPlayers(){
  const el=$("plList");if(!el)return;
  try{_playerCache=await loadAllPlayers();filterChatPlayers()}catch(e){el.innerHTML="<p class='mu'>Gagal</p>"}
}
function filterChatPlayers(){
  const el=$("plList");if(!el)return;
  const q=($("plSearch")?.value||"").toLowerCase().trim();
  let rows=(_playerCache||[]);
  if(q)rows=rows.filter(p=>(p.name||"").toLowerCase().includes(q)||(p.id||"").toLowerCase().includes(q));
  rows.sort((a,b)=>(b.online-a.online)||(a.name||"").localeCompare(b.name||""));
  el.innerHTML=rows.slice(0,50).map(p=>{
    const st=p.banned?"🚫":p.investigation?"⚠️":p.online?"🟢":"⚪";
    return `<div class="acc-item"><div><b>${st} ${esc(p.name)}</b>${p.me?" <span class='badge blue'>Kamu</span>":""}<br>
    <span class="mu">${esc(p.id)} · Lv ${p.level}</span></div>
    ${p.me?"":`<button class="btn" style="width:auto;margin:0;padding:8px 12px" onclick="showProfile('${esc(p.id)}')">Profil</button>`}
    </div>`;
  }).join("")||"<p class='mu'>Kosong</p>";
}


async function openTrade(){
  if(S){toast("Uang & kekuatan reset tiap pilih negara · Trade di Lobby");return}
  $("app").innerHTML=`<div class="card"><div style="display:flex;justify-content:space-between"><b>🤝 Trade</b>
  <button class="btn-gray" style="padding:4px 10px" onclick="lobby()">←</button></div>
  <p class="mu">Tukar Koin / Uang / Kekuatan. Hanya di Lobby.</p>
  <p class="mu">Koin: 🪙 <b>${fmt(coins)}</b> · Uang: 💰 <b>${fmt(statsRow?.money||0)}</b> · Pasukan: ⚔️ <b>${fmt(statsRow?.army||0)}</b></p></div>

  <div class="card"><div style="display:flex;justify-content:space-between"><b>🤖 Bot Trade (Gratis)</b>
  <button class="btn-gray" style="padding:4px 10px" onclick="loadBots()">⟳</button></div>
  <p class="mu">Minta resource gratis dari bot admin (ada batas harian).</p>
  <div id="botList"><p class="mu">Memuat bot...</p></div></div>

  <div class="card"><div style="display:flex;justify-content:space-between"><b>👥 Daftar Pemain</b>
  <button class="btn-gray" style="padding:4px 10px" onclick="loadPlayerList()">⟳</button></div>
  <input id="plSearch" placeholder="🔎 Cari nama / ID" oninput="filterPlayerList()" style="margin-bottom:8px">
  <div id="plList" class="mu">Memuat...</div></div>

  <div class="card"><b>Buat Penawaran</b>
    <label class="mu">Player ID lawan</label>
    <input id="trTo" placeholder="Klik pemain di daftar atau isi manual">
    <label class="mu">Kamu beri</label>
    <select id="trGiveType"><option value="coins">🪙 Koin</option><option value="money">💰 Uang</option><option value="army">⚔️ Kekuatan</option></select>
    <input id="trGiveAmt" type="number" min="1" placeholder="Jumlah yang kamu beri">
    <label class="mu">Kamu minta</label>
    <select id="trWantType"><option value="coins">🪙 Koin</option><option value="money">💰 Uang</option><option value="army">⚔️ Kekuatan</option></select>
    <input id="trWantAmt" type="number" min="1" placeholder="Jumlah yang kamu minta">
    <button class="btn" onclick="createTrade()">Kirim Penawaran</button>
  </div>
  <div class="card"><div style="display:flex;justify-content:space-between"><b>Penawaran masuk</b>
  <button class="btn-gray" style="padding:4px 10px" onclick="openTrade()">⟳</button></div>
  <div id="trIn"><p class="mu">Memuat...</p></div></div>
  <div class="card"><b>Penawaran keluar</b><div id="trOut"><p class="mu">Memuat...</p></div></div>`;
  loadTrades();loadPlayerList();loadBots();
}
async function loadPlayerList(){
  const el=$("plList");if(!el)return;
  el.innerHTML="Memuat...";
  try{
    const list=arr(await api("GET",API_STATS,KEY_STATS));
    const map={};
    list.forEach(p=>{
      if(!p.player_id||String(p.player_id).startsWith(SRV_PREFIX)||String(p.player_id).startsWith(TRADE_PREFIX)||String(p.player_id).startsWith(QUEST_PREFIX))return;
      if(p.player_id===uid)return;
      if(!map[p.player_id]||new Date(p.created_at||0)>new Date(map[p.player_id].created_at||0))map[p.player_id]=p;
    });
    _playerCache=Object.values(map).map(p=>({
      id:p.player_id,
      name:(p.game_stats&&p.game_stats.name)||p.name||p.player_id,
      level:p.level||1,coins:p.coins!=null?p.coins:((p.game_stats||{}).coins||0),
      money:p.money||0,army:p.army||0
    })).sort((a,b)=>(a.name||"").localeCompare(b.name||""));
    filterPlayerList();
  }catch(e){el.innerHTML="Gagal memuat pemain"}
}
function filterPlayerList(){
  const el=$("plList");if(!el)return;
  const q=($("plSearch")?.value||"").toLowerCase().trim();
  const rows=_playerCache.filter(p=>!q||(p.name||"").toLowerCase().includes(q)||(p.id||"").toLowerCase().includes(q));
  if(!rows.length){el.innerHTML="<p class='mu'>Tidak ada pemain</p>";return}
  el.innerHTML=rows.slice(0,40).map(p=>`<div class="acc-item">
    <div><b>${esc(p.name)}</b><br><span class="mu">${esc(p.id)} · Lv ${p.level}</span></div>
    <button class="btn" style="width:auto;margin:0;padding:8px 12px" onclick="selectTradePlayer('${esc(p.id)}','${esc(p.name)}')">Pilih</button>
  </div>`).join("")+(rows.length>40?`<p class="mu">+${rows.length-40} lainnya, gunakan pencarian</p>`:"");
}
function selectTradePlayer(id,name){
  const inp=$("trTo");if(inp)inp.value=id;
  toast("Dipilih: "+name);
}
const BOT_PREFIX="BOTTRADE|";
async function loadBots(){
  const el=$("botList");if(!el)return;
  try{
    const list=arr(await api("GET",API_META,KEY_META)).filter(x=>String(x.player_id).startsWith(BOT_PREFIX)||(x.extra&&x.extra.is_bot_trade));
    const active=list.filter(x=>{const e=x.extra||{};return e.active!==false});
    if(!active.length){el.innerHTML="<p class='mu'>Belum ada bot. Tunggu admin.</p>";return}
    el.innerHTML=active.map(b=>{
      const e=b.extra||{};
      const label=e.res_type==="coins"?"🪙 Koin":e.res_type==="money"?"💰 Uang":"⚔️ Kekuatan";
      return `<div class="acc-item">
        <div><b>${esc(e.name||"Bot")}</b><br>
        <span class="mu">${label} maks ${fmt(e.max_per_claim||0)}/klaim · ${fmt(e.daily_limit||0)}/hari</span></div>
        <button class="btn" style="width:auto;margin:0;padding:8px 12px" onclick="claimBot('${b.id}')">Ambil</button>
      </div>`;
    }).join("");
  }catch(e){el.innerHTML="<p class='mu'>Gagal memuat bot</p>"}
}
function botClaimKey(botId){return "botclaim_"+botId+"_"+wibDay()}
async function claimBot(rowId){
  if(S)return toast("Hanya di Lobby");
  try{
    const list=arr(await api("GET",API_META,KEY_META));
    const row=list.find(x=>x.id===rowId);
    if(!row)return toast("Bot tidak ada");
    const e=row.extra||{};
    if(e.active===false)return toast("Bot nonaktif");
    const maxC=+e.max_per_claim||0;
    const daily=+e.daily_limit||0;
    if(maxC<=0)return toast("Bot belum dikonfigurasi");
    // track local daily claims
    let used=0;try{used=+ls(botClaimKey(rowId))||0}catch(err){}
    if(daily>0&&used>=daily)return toast("Batas harian bot ini habis");
    const give=Math.min(maxC, daily>0?Math.max(0,daily-used):maxC);
    if(give<=0)return toast("Batas habis");
    await applyResDelta(uid,+give,e.res_type||"coins");
    try{ls(botClaimKey(rowId),String(used+give))}catch(err){}
    toast("🤖 Bot +"+fmt(give)+" "+(e.res_type||"coins"));
    await loadStats();
    openTrade();
  }catch(e){toast("Gagal: "+e.message)}
}

async function loadTrades(){
  const elIn=$("trIn"),elOut=$("trOut");
  try{
    const list=arr(await api("GET",API_META,KEY_META)).filter(x=>String(x.player_id).startsWith(TRADE_PREFIX)||(x.extra&&x.extra.is_trade));
    const open=list.filter(x=>{const e=x.extra||{};return e.status==="open"});
    const incoming=open.filter(x=>(x.extra||{}).to===uid);
    const outgoing=open.filter(x=>(x.extra||{}).from===uid);
    if(elIn)elIn.innerHTML=incoming.length?incoming.map(trHtml).join(""):"<p class='mu'>Tidak ada</p>";
    if(elOut)elOut.innerHTML=outgoing.length?outgoing.map(trHtml).join(""):"<p class='mu'>Tidak ada</p>";
  }catch(e){
    if(elIn)elIn.innerHTML="<p class='mu'>Gagal memuat</p>";
    if(elOut)elOut.innerHTML="";
  }
}
function trHtml(row){
  const e=row.extra||{};
  const mine=e.from===uid;
  const label=(t)=>t==="coins"?"🪙 Koin":t==="money"?"💰 Uang":"⚔️ Kekuatan";
  return `<div class="acc-item" style="flex-direction:column;align-items:stretch;gap:6px">
    <div><span class="mu">${mine?"Ke":"Dari"}:</span> <b>${esc(mine?e.to_name||e.to:e.from_name||e.from)}</b></div>
    <div class="mu">Beri: ${label(e.give_type)} <b>${fmt(e.give_amt)}</b> → Minta: ${label(e.want_type)} <b>${fmt(e.want_amt)}</b></div>
    <div style="display:flex;gap:6px">
      ${!mine?`<button class="btn" style="flex:1;margin:0;padding:8px" onclick="acceptTrade('${row.id}')">✅ Terima</button>
      <button class="btn-red" style="flex:1;margin:0;padding:8px" onclick="rejectTrade('${row.id}')">❌ Tolak</button>`:
      `<button class="btn-gray" style="flex:1;margin:0;padding:8px" onclick="rejectTrade('${row.id}')">Batalkan</button>`}
    </div>
  </div>`;
}
function myRes(type){
  if(type==="coins")return coins||0;
  if(type==="money")return statsRow?.money||0;
  if(type==="army")return statsRow?.army||0;
  return 0;
}
async function createTrade(){if(isInvestigation())return toast("⚠️ Akun investigasi: tidak bisa trade");
  if(S)return toast("Uang & kekuatan reset tiap pilih negara · Trade di Lobby");
  const to=($("trTo").value||"").trim();
  const giveType=$("trGiveType").value;
  const wantType=$("trWantType").value;
  const giveAmt=Math.floor(+$("trGiveAmt").value||0);
  const wantAmt=Math.floor(+$("trWantAmt").value||0);
  if(!to||to===uid)return toast("Isi Player ID lawan yang valid");
  if(giveAmt<1||wantAmt<1)return toast("Jumlah minimal 1");
  if(giveAmt>maxTradeAmt(giveType)||wantAmt>maxTradeAmt(wantType))return toast("🛡️ Jumlah terlalu besar (anti-cheat)");
  if(myRes(giveType)<giveAmt)return toast("Saldo tidak cukup");
  // lock resources: deduct immediately so tidak double spend
  try{
    await applyResDelta(uid,-giveAmt,giveType);
    const id=genTradeId();
    await api("POST",API_META,KEY_META,{
      player_id:TRADE_PREFIX+id,
      is_admin:false,is_banned:false,is_whitelisted:false,
      extra:{
        is_trade:true,trade_id:id,status:"open",
        from:uid,from_name:ACC?.name||uid,
        to:to,to_name:to,
        give_type:giveType,give_amt:giveAmt,
        want_type:wantType,want_amt:wantAmt,
        created_at:new Date().toISOString()
      }
    });
    toast("🤝 Penawaran dikirim");
    openTrade();
  }catch(e){toast("Gagal: "+e.message)}
}
async function applyResDelta(pid,delta,type){
  // update stats for player (self uses local statsRow)
  if(pid===uid){
    if(type==="coins"){coins=Math.max(0,(coins||0)+delta);if(!isAdminAcc()){if(isCheatCoins(coins)||coins>MAX_COINS){coins=sanitizeCoins(coins);await flagCheater("trade coins")}}else{coins=Math.floor(coins)}await saveCoins();return}
    if(!statsRow||!statsRow.id)throw new Error("Stats tidak ada");
    const body={};
    if(type==="money")body.money=Math.max(0,(statsRow.money||0)+delta);
    if(type==="army")body.army=Math.max(0,(statsRow.army||0)+delta);
    await api("PATCH",API_STATS+"?id="+statsRow.id,KEY_STATS,body);
    if(type==="money")statsRow.money=body.money;
    if(type==="army")statsRow.army=body.army;
    return;
  }
  // other player
  const list=arr(await api("GET",API_STATS,KEY_STATS)).filter(x=>x.player_id===pid).sort((a,b)=>new Date(b.created_at||0)-new Date(a.created_at||0));
  const row=list[0];
  if(!row||!row.id)throw new Error("Lawan tidak ditemukan di database");
  if(type==="coins"){
    const cur=row.coins!=null?+row.coins:((row.game_stats||{}).coins||0);
    const nc=Math.max(0,cur+delta);
    const gs={...(row.game_stats||{}),coins:nc};
    await api("PATCH",API_STATS+"?id="+row.id,KEY_STATS,{coins:nc,game_stats:gs});
  }else{
    const body={};
    if(type==="money")body.money=Math.max(0,(row.money||0)+delta);
    if(type==="army")body.army=Math.max(0,(row.army||0)+delta);
    await api("PATCH",API_STATS+"?id="+row.id,KEY_STATS,body);
  }
}
async function acceptTrade(rowId){if(isInvestigation())return toast("⚠️ Akun investigasi: tidak bisa trade");
  if(S)return toast("Uang & kekuatan reset tiap pilih negara · Trade di Lobby");
  try{
    const list=arr(await api("GET",API_META,KEY_META));
    const row=list.find(x=>x.id===rowId);
    if(!row)return toast("Tidak ditemukan");
    const e=row.extra||{};
    if(e.status!=="open"||e.to!==uid)return toast("Penawaran tidak valid");
    // cek saldo penerima cukup untuk want
    if(myRes(e.want_type)<e.want_amt)return toast("Saldomu kurang untuk menukar");
    // penerima bayar want, terima give
    await applyResDelta(uid,-e.want_amt,e.want_type);
    await applyResDelta(uid,+e.give_amt,e.give_type);
    // pengirim sudah potong give saat create; terima want
    await applyResDelta(e.from,+e.want_amt,e.want_type);
    await api("PATCH",API_META+"?id="+rowId,KEY_META,{extra:{...e,status:"done",done_at:new Date().toISOString()}});
    toast("✅ Trade berhasil");
    await loadStats();
    openTrade();
  }catch(e){toast("Gagal: "+e.message)}
}
async function rejectTrade(rowId){
  try{
    const list=arr(await api("GET",API_META,KEY_META));
    const row=list.find(x=>x.id===rowId);
    if(!row)return toast("Tidak ditemukan");
    const e=row.extra||{};
    // refund give ke pengirim jika masih open
    if(e.status==="open"&&e.from){
      try{await applyResDelta(e.from,+e.give_amt,e.give_type)}catch(err){}
    }
    await api("PATCH",API_META+"?id="+rowId,KEY_META,{extra:{...e,status:"cancelled",cancelled_at:new Date().toISOString()}});
    toast("Penawaran dibatalkan");
    if(e.from===uid||e.to===uid)await loadStats();
    openTrade();
  }catch(e){toast("Gagal: "+e.message)}
}

const NORMAL_QUESTS=[
{q:"5 + 7 = ?",a:"12",reward:15},{q:"12 × 3 = ?",a:"36",reward:20},{q:"Ibukota Indonesia?",a:"jakarta",reward:25},
{q:"Tahun proklamasi RI?",a:"1945",reward:25},{q:"100 - 37 = ?",a:"63",reward:15},{q:"Benua terbesar?",a:"asia",reward:20},
{q:"8 × 8 = ?",a:"64",reward:15},{q:"Presiden pertama RI?",a:"soekarno",reward:25},{q:"50% dari 200?",a:"100",reward:15}
];

let S=null,tab="b",timer=null,pollTimer=null,banTimer=null,uid=null,ACC=null;
let metaRow=null,metaRows=[],statsRow=null,currentServer=null,onlinePlayers=[];
let coins=0,claimedQuests={};

const $=id=>document.getElementById(id);
function toast(t){const e=$("toast");e.textContent=t;e.className="s";clearTimeout(window._tt);window._tt=setTimeout(()=>e.className="",2800)}
function fmt(n){n=Math.floor(+n||0);if(n>=1e12)return(n/1e12).toFixed(1)+" T";if(n>=1e9)return(n/1e9).toFixed(1)+" M";if(n>=1e6)return(n/1e6).toFixed(1)+" Jt";if(n>=1e3)return(n/1e3).toFixed(1)+" Rb";return""+n}
function esc(s){return String(s==null?"":s).replace(/[&<>"']/g,c=>({"&":"&amp;","<":"&lt;",">":"&gt;","\"":"&quot;","'":"&#39;"}[c]))}
function ls(k,v){try{if(v===undefined)return localStorage.getItem(k);if(v===null)localStorage.removeItem(k);else localStorage.setItem(k,v)}catch(e){}}

/* ===== MULTI AKUN (maks 5) ===== */
const MAX_ACC=5;
function loadAccounts(){try{return JSON.parse(ls("negara_accounts")||"[]")}catch(e){return[]}}
function saveAccounts(list){ls("negara_accounts",JSON.stringify(list.slice(0,MAX_ACC)))}
function currentAccSlot(){return ls("negara_uid")}
function upsertAccount(uid,name){
  let list=loadAccounts().filter(a=>a.uid!==uid);
  list.unshift({uid,name,last:Date.now()});
  // keep max 5 unique
  const seen=new Set();const out=[];
  for(const a of list){if(seen.has(a.uid))continue;seen.add(a.uid);out.push(a);if(out.length>=MAX_ACC)break}
  saveAccounts(out);
}
function removeAccount(uid){
  saveAccounts(loadAccounts().filter(a=>a.uid!==uid));
}
function logoutAccount(){
  clearInterval(timer);clearInterval(pollTimer);clearInterval(banTimer);
  if(S)try{cloudSave()}catch(e){}
  S=null;onlinePlayers=[];metaRow=null;statsRow=null;ACC=null;uid=null;
  ls("negara_uid",null);ls("negara_name",null);
  accountScreen();
}

function getRank(score){score=+score||0;if(score>=100000)return"The Anomali";if(score>=80000)return"Celestial";if(score>=60000)return"Mythic Emperor";if(score>=45000)return"Grandmaster";if(score>=35000)return"Legend";if(score>=25000)return"Champion";if(score>=18000)return"Elite";if(score>=12000)return"Master";if(score>=8000)return"Expert";if(score>=5000)return"Veteran";if(score>=3000)return"Warrior";if(score>=1500)return"Fighter";if(score>=800)return"Skilled";if(score>=400)return"Trained";if(score>=200)return"Adept";if(score>=100)return"Super Pro";if(score>=88)return"Pro";if(score>=55)return"Jagoan";if(score>=25)return"Jago";if(score>=12)return"Lumayan";return"Pemula"}
function rankScore(){if(!S)return(statsRow?(statsRow.level||1)*100+(statsRow.exp||0):0);return(S.lvl||1)*100+(S.xp||0)+Math.floor((S.land||1)*2)+(S.win_streak||0)*5}
function getWheel(){try{return JSON.parse(ls("negara_wheel")||"{}")}catch(e){return{}}}
function setWheel(w){ls("negara_wheel",JSON.stringify(w))}
function wibDay(){return new Date(Date.now()+7*3600000).toISOString().slice(0,10)}
function applyWheelPrize(){const w=getWheel();if(!S)return;if(w.pa||w.pm){S.army+=(w.pa||0);S.m+=(w.pm||0);const a=w.pa||0,m=w.pm||0;w.pa=0;w.pm=0;setWheel(w);setTimeout(()=>toast("🎁 Gacha: +"+fmt(a)+" pasukan, +"+fmt(m)+" uang"),1500)}}
function applyCartOnce(){const c=getCart();if(!S)return;const m=c.money||0,a=c.army||0;if(!m&&!a)return;S.m+=m;S.army+=a;setCart({});setTimeout(()=>toast("🛒 Keranjang: +"+fmt(m)+" uang, +"+fmt(a)+" kekuatan"),1200)}

async function api(method,url,key,body){const o={method,headers:{"x-api-key":key,"Content-Type":"application/json"}};if(body)o.body=JSON.stringify(body);const r=await fetch(url,o);const t=await r.text();if(!r.ok)throw new Error(r.status+" "+t.slice(0,100));try{return JSON.parse(t)}catch(e){return null}}
function arr(d){if(!d)return[];if(Array.isArray(d))return d;if(Array.isArray(d.records))return d.records;if(Array.isArray(d.data))return d.data;return[]}
function flagOf(c){const x=CS.find(z=>z.n===c);return x?x.f:"🏳️"}

function banKey(ex){return ex.banned_at||ex.ban_until||"x"}
function isPermBan(m){return!((m&&m.extra)&&m.extra.ban_until)}
function banExpired(m){const ex=(m&&m.extra)||{};return!!m.is_banned&&!!ex.ban_until&&new Date(ex.ban_until)<=new Date()}
function reviewInfo(m){const ex=(m&&m.extra)||{};if(ex.review_for&&ex.review_for===banKey(ex)&&ex.review_until)return{until:new Date(ex.review_until)};return null}
function reviewDone(m){const rv=reviewInfo(m);return!!m.is_banned&&!!rv&&rv.until<=new Date()}
function banDaysOf(ex){if(ex.ban_days)return+ex.ban_days;if(ex.ban_until&&ex.banned_at)return Math.round((new Date(ex.ban_until)-new Date(ex.banned_at))/DAY_MS);if(ex.ban_until)return Math.ceil((new Date(ex.ban_until)-Date.now())/DAY_MS);return null}
function canReview(m){const ex=(m&&m.extra)||{};if(isPermBan(m)||reviewInfo(m))return false;const d=banDaysOf(ex);return d!==null&&d<REVIEW_MAX_DAYS}
function clearedExtra(ex,by){return{...(ex||{}),ban_reason:"",ban_until:null,ban_type:"",ban_days:null,review_for:null,review_until:null,unbanned_at:new Date().toISOString(),unbanned_by:by}}
function fmtLeft(ms){if(ms<=0)return"0 detik";const s=Math.floor(ms/1000);const d=Math.floor(s/86400),h=Math.floor((s%86400)/3600),m=Math.floor((s%3600)/60),c=s%60;if(d>0)return d+" hari "+h+" jam "+m+" menit";if(h>0)return h+" jam "+m+" menit "+c+" dtk";return m+" mnt "+c+" dtk"}

async function loadMeta(){
  try{const list=arr(await api("GET",API_META,KEY_META));const rows=list.filter(x=>x.player_id===uid);
    for(const r of rows){if(!r.id)continue;if(banExpired(r)||reviewDone(r)){const by=reviewDone(r)&&!banExpired(r)?"auto-review":"auto";const ne=clearedExtra(r.extra,by);try{await api("PATCH",API_META+"?id="+r.id,KEY_META,{is_banned:false,extra:ne});r.is_banned=false;r.extra=ne}catch(e){}}}
    rows.sort((a,b)=>{if(!!a.is_banned!==!!b.is_banned)return(b.is_banned?1:0)-(a.is_banned?1:0);return new Date(b.created_at||0)-new Date(a.created_at||0)});
    metaRows=rows;metaRow=rows[0]||null;return metaRow}catch(e){metaRow=null;metaRows=[];return null}
}
async function loadStats(){try{const list=arr(await api("GET",API_STATS,KEY_STATS));const m=list.filter(x=>x.player_id===uid).sort((a,b)=>new Date(b.created_at||0)-new Date(a.created_at||0));statsRow=m[0]||null;if(statsRow){let c=statsRow.coins!=null?+statsRow.coins:((statsRow.game_stats||{}).coins||0);if(isAdminAcc()){coins=Math.max(0,Math.floor(c))}else{coins=sanitizeCoins(c);if(isCheatCoins(c)||c>MAX_COINS*2){coins=sanitizeCoins(c);try{const gs={...(statsRow.game_stats||{}),coins};await api("PATCH",API_STATS+"?id="+statsRow.id,KEY_STATS,{coins,game_stats:gs});statsRow.coins=coins;statsRow.game_stats=gs;await flagCheater("load coins="+c)}catch(e){}}}try{claimedQuests=JSON.parse(ls("negara_qclaim")||"{}")}catch(e){claimedQuests={}}}return statsRow}catch(e){statsRow=null;return null}}
async function ensureMeta(){await loadMeta();if(!metaRow){try{metaRow=await api("POST",API_META,KEY_META,{player_id:uid,is_admin:false,is_banned:false,is_whitelisted:false,extra:{}});if(metaRow)metaRows=[metaRow]}catch(e){}}}
async function ensureStats(name){await loadStats();if(!statsRow){try{statsRow=await api("POST",API_STATS,KEY_STATS,{player_id:uid,level:1,exp:0,money:500,army:20,coins:50,game_stats:{name:name||"Pemain",rank:"Pemula",win_streak:0,coins:50}});coins=50}catch(e){}}}
function isBanned(){return!!(metaRow&&metaRow.is_banned)}

function getRole(){
  if(metaRow&&(metaRow.is_admin||(metaRow.extra&&(metaRow.extra.admin_on||metaRow.extra.role==='admin'))))return 'admin';
  if(typeof metaRows!=='undefined'&&metaRows){
    for(const r of metaRows){if(r&&(r.is_admin||(r.extra&&(r.extra.admin_on||r.extra.role==='admin'))))return 'admin'}
  }
  let role=(metaRow&&metaRow.extra&&metaRow.extra.role)||'biasa';
  if(role==='premium'||role==='admin')return role;
  if(typeof metaRows!=='undefined'&&metaRows){
    for(const r of metaRows){
      const rr=(r&&r.extra&&r.extra.role)||'';
      if(rr==='admin')return 'admin';
      if(rr==='premium')return 'premium';
    }
  }
  return 'biasa';
}
function isAdminAcc(){return getRole()==='admin'}
function isPremiumAcc(){const r=getRole();return r==='premium'||r==='admin'}
function roleBadge(role){
  role=role||'biasa';
  if(role==='admin')return '<span class="title-admin">👑 ADMIN</span>';
  if(role==='premium')return '<span class="title-prem">⭐ PREMIUM</span>';
  return '<span class="title-biasa">👤 BIASA</span>';
}
function roleTitle(role){role=role||getRole();return role==='admin'?'Admin':role==='premium'?'Premium':'Biasa'}
function roleOfMeta(meta){
  if(!meta)return 'biasa';
  if(meta.is_admin||(meta.extra&&(meta.extra.admin_on||meta.extra.role==='admin')))return 'admin';
  const r=(meta.extra&&meta.extra.role)||'biasa';
  return r==='premium'?'premium':'biasa';
}

function isInvestigation(m){const row=m||metaRow;const ex=(row&&row.extra)||{};return!!ex.investigation&&!row.is_banned}
function investigationOf(m){const ex=(m&&m.extra)||{};return!!ex.investigation}

async function saveCoins(){if(!statsRow||!statsRow.id)return;coins=sanitizeCoins(coins);try{const gs={...(statsRow.game_stats||{}),coins};await api("PATCH",API_STATS+"?id="+statsRow.id,KEY_STATS,{coins,game_stats:gs});statsRow.coins=coins;statsRow.game_stats=gs}catch(e){}}

async function listServers(){try{const list=arr(await api("GET",API_META,KEY_META));return list.filter(x=>String(x.player_id).startsWith(SRV_PREFIX)||(x.extra&&x.extra.is_server)).map(s=>{const ex=s.extra||{};return{id:s.id,code:ex.server_code||String(s.player_id).replace(SRV_PREFIX,""),type:ex.server_type||"free",active:ex.server_is_active!==false,expires:ex.server_expires_at?new Date(ex.server_expires_at):null,minLevel:ex.server_min_level||1}}).filter(s=>s.active&&(!s.expires||s.expires>new Date()))}catch(e){return[]}}

async function loadOnlinePlayers(){
  if(!S||S.mode!=="pub"||!S.sid){onlinePlayers=[];return}
  const prev=onlinePlayers.length;
  try{const list=arr(await api("GET",API_STATS,KEY_STATS));const map={};
    list.forEach(p=>{if(p.player_id===uid||String(p.player_id).startsWith(SRV_PREFIX))return;const gs=p.game_stats||{};if(gs.server!==S.sid)return;
      if(!map[p.player_id]||new Date(p.updated_at||p.created_at||0)>new Date(map[p.player_id].updated_at||map[p.player_id].created_at||0))map[p.player_id]=p});
    onlinePlayers=Object.values(map)}catch(e){onlinePlayers=[]}
  if(prev===0&&onlinePlayers.length>0&&S&&S.aiFarm)resetAiProgress();
  if(S&&onlinePlayers.length===0)S.aiFarm=true;
}
function resetAiProgress(){
  if(!S)return;const c=CS[S.c];
  S.m=c.m;S.army=c.a;S.food=100;S.pop=c.p;S.land=1;S.day=1;
  S.t=Array(64).fill("");S.lv=Array(64).fill(1);
  const ter=[];for(let k=0;k<64;k++){const r=Math.random();ter.push(r<.1?1:r<.28?2:0)}S.ter=ter;
  S.en=rndEn(S.c);S.win_streak=0;S.aiFarm=false;cloudSave();
  toast("⚖️ Musuh online masuk! Progres AI direset demi keadilan.");render();
}

function pick(i,pub){
  if(pub&&window._taken&&window._taken[CS[i].n]){toast("Negara dipakai "+window._taken[CS[i].n]);return}
  const c=CS[i];const ter=[];for(let k=0;k<64;k++){const r=Math.random();ter.push(r<.1?1:r<.28?2:0)}
  // Uang & Kekuatan SELALU mulai dari statistik negara (reset tiap pilih/ganti negara)
  // Level & Exp tetap dari akun; hadiah (gacha/keranjang) masuk setelah ini
  S={c:i,m:c.m,food:100,pop:c.p,army:c.a,t:Array(64).fill(""),lv:Array(64).fill(1),ter,day:1,land:1,sel:"h",xp:0,lvl:1,en:rndEn(i),win_streak:0,mode:pub?"pub":"self",sid:pub||null,rc:{},aiFarm:!!pub};
  if(statsRow){S.lvl=statsRow.level||1;S.xp=statsRow.exp||0}
  // JANGAN ambil money/army dari cloud — selalu fresh per negara
  tab="b";
  applyWheelPrize();
  applyCartOnce();
  applyPendingGifts();
  start();
  if(S.mode==="pub"){cloudSave();loadOnlinePlayers()}
  toast(c.f+" "+c.n+" · mulai dari awal (uang & kekuatan negara)");
}
async function applyPendingGifts(){
  // Hadiah admin: pending_money / pending_army di game_stats — masuk 1x lalu dikosongkan
  if(!S||!statsRow)return;
  const gs=statsRow.game_stats||{};
  const pm=+gs.pending_money||0;
  const pa=+gs.pending_army||0;
  if(!pm&&!pa)return;
  S.m+=(pm||0);
  S.army+=(pa||0);
  const ngs={...gs,pending_money:0,pending_army:0};
  try{
    if(statsRow.id){
      await api("PATCH",API_STATS+"?id="+statsRow.id,KEY_STATS,{game_stats:ngs});
      statsRow.game_stats=ngs;
    }
  }catch(e){}
  setTimeout(()=>toast("🎁 Hadiah admin: +"+fmt(pm)+" uang, +"+fmt(pa)+" kekuatan"),1000);
}

function rndEn(i){const ix=CS.map((_,k)=>k).filter(k=>k!==i);for(let k=ix.length-1;k>0;k--){const j=Math.floor(Math.random()*(k+1));[ix[k],ix[j]]=[ix[j],ix[k]]}return ix.slice(0,5).map((c,j)=>({n:CS[c].n,f:CS[c].f,pw:20+Math.floor(Math.random()*20)+j*12}))}
function growMap(n){if(!S)return;for(let k=0;k<n;k++){const r=Math.random();S.t.push("");S.lv.push(1);S.ter.push(r<.1?1:r<.28?2:0)}}
function shrinkMap(n){if(!S)return;n=n||1;for(let k=0;k<n;k++){if(S.t.length>16){S.t.pop();S.lv.pop();S.ter.pop()}}}
function sum(k){let s=0;for(let i=0;i<S.t.length;i++)if(S.t[i]===k)s+=(1+0.5*(S.lv[i]-1));return s}
function cap(){return 20+Math.floor(sum("h")*10+sum("ap")*22)}
function tick(){if(!S)return;if(S.admin){S.m=Math.max(S.m,1e18);S.army=Math.max(S.army,1e18)}
  const f=sum("f"),p=sum("p"),b=sum("b")+sum("mk")*1.5+sum("pd")*2;
  const eco=p*8+sum("ml")*10+sum("ps")*5+sum("bk")*8+sum("tb")*12+sum("bd")*10+sum("pl")*9+sum("tw")*6;
  S.day++;S.m+=eco+S.pop*0.3+(S.land-1)*6-Math.min(S.army*0.2,50);S.food+=f*6-S.pop*0.2;
  if(S.food<0){S.food=0;S.pop=Math.max(5,S.pop-2)}else if(S.pop<cap())S.pop=Math.min(cap(),S.pop+2);
  if(b>0&&S.m>=b*3){S.army+=b;S.m-=b*3}if(S.mode==="self")S.en.forEach(e=>e.pw+=0.12);
  if(S.day%8===0)cloudSave();renderStats()}
async function cloudSave(){if(!S||!uid)return;try{coins=sanitizeCoins(coins);const money=sanitizeMoney(S.m);const army=sanitizeArmy(S.army);S.m=money;S.army=army;const body={level:S.lvl,exp:S.xp,money,army,coins,game_stats:{name:ACC?.name,rank:getRank(rankScore()),role:getRole(),win_streak:S.win_streak||0,day:S.day,country:CS[S.c].n,server:S.sid||null,land:S.land,last_active:new Date().toISOString(),rc:S.rc||{},coins}};
  if(statsRow&&statsRow.id)await api("PATCH",API_STATS+"?id="+statsRow.id,KEY_STATS,body);else{body.player_id=uid;statsRow=await api("POST",API_STATS,KEY_STATS,body)}}catch(e){}}

function build(i){
  if(!S)return;const k=S.sel,t=S.t[i];
  if(S.ter[i]===1){toast("Air tidak bisa dibangun");return}
  if(k==="x"){if(!t){toast("Tidak ada bangunan");return}const cost=B[t]?B[t].c:0;const refund=Math.floor(cost*0.85);
    if(!confirm("💣 Bongkar "+(B[t]?B[t].n:"bangunan")+"?\nRefund 85%: +"+refund+" uang"))return;
    S.t[i]="";S.lv[i]=1;S.m+=refund;toast("💣 Refund +"+refund+" (85%)");render();return}
  if(t){toast("Petak terisi. Pakai Bongkar untuk refund 85%.");return}
  const cost=B[k].c+(S.ter[i]===2?20:0);if(S.m<cost){toast("Uang kurang");return}
  if(!confirm("Bangun "+(B[k]?B[k].e+" "+B[k].n:"")+"?\nBiaya: "+cost+(S.ter[i]===2?" (hutan +20)":"")))return;
  S.m-=cost;S.t[i]=k;S.lv[i]=1;S.ter[i]=0;toast(B[k].e+" dibangun");render();
}
function attackAI(i){const e=S.en[i];if(S.army<5){toast("Pasukan kurang");return}
  if(Math.random()<S.army/(S.army+e.pw)){const gain=Math.floor(e.pw*10);S.army=Math.max(0,S.army-Math.floor(e.pw*0.3));S.m+=gain;S.land=(S.land||1)+1;growMap(5);e.pw=Math.max(15,e.pw*0.7);S.win_streak=(S.win_streak||0)+1;
    if(S.win_streak>=3){S.win_streak=0;S.xp=(S.xp||0)+1;S.lvl=Math.max(S.lvl||1,Math.floor((S.xp||0)/100)+1);toast("🎉 Menang AI +5 kotak ⭐")}else toast("🎉 Menang AI +5 kotak");cloudSave()}
  else{S.army=Math.floor(S.army*0.5);S.land=Math.max(1,(S.land||1)-1);shrinkMap(5);S.win_streak=0;toast("💥 Kalah -5 kotak")}render()}
async function attackPlayer(pid){
  if(S.army<5){toast("Pasukan kurang");return}const target=onlinePlayers.find(p=>p.player_id===pid);if(!target){toast("Tidak ditemukan");return}
  const tArmy=Math.max(1,target.army||1),tMoney=Math.max(0,target.money||0),tName=(target.game_stats&&target.game_stats.name)||pid;
  const chance=S.army/(S.army+tArmy);toast("⚔️ Menyerang "+tName+"...");await new Promise(r=>setTimeout(r,400));if(!S)return;
  if(Math.random()<chance){const loot=Math.floor(tMoney*0.12),dmg=Math.floor(tArmy*0.35),myLoss=Math.floor(tArmy*0.2);
    S.army=Math.max(0,S.army-myLoss);S.m+=loot;S.land=(S.land||1)+1;growMap(5);S.win_streak=(S.win_streak||0)+1;
    if(S.win_streak>=3){S.win_streak=0;S.xp=(S.xp||0)+1;S.lvl=Math.max(S.lvl||1,Math.floor((S.xp||0)/100)+1)}
    toast("🎉 Menang vs "+tName+" +5 kotak");
    try{const tLand=Math.max(1,((target.game_stats||{}).land||1)-1);await api("PATCH",API_STATS+"?id="+target.id,KEY_STATS,{army:Math.max(0,(target.army||0)-dmg),money:Math.max(0,(target.money||0)-loot),game_stats:{...(target.game_stats||{}),land:tLand}})}catch(e){}
    await cloudSave()}else{const loss=Math.floor(S.army*0.4);S.army=Math.max(0,S.army-loss);S.land=Math.max(1,(S.land||1)-1);shrinkMap(5);S.win_streak=0;toast("💥 Kalah -5 kotak");await cloudSave()}
  await loadOnlinePlayers();if(S)render()}

function renderStats(){const el=$("st");if(!el||!S)return;el.innerHTML=[["💰",fmt(S.m)],["🌾",fmt(S.food)],["👥",Math.floor(S.pop)+"/"+cap()],["⚔️",fmt(S.army)],["🗺️",S.land],["🪙",coins]].map(x=>`<div>${x[0]}<b>${x[1]}</b></div>`).join("");const rk=$("rank");if(rk)rk.innerHTML=`${roleBadge(getRole())} <span class="rank">Lv ${S.lvl} · ${getRank(rankScore())}</span>`}
function render(){
  if(!S){lobby();return}const c=CS[S.c];
  let h=`<div class="card" style="background:linear-gradient(135deg,#2a1f00,#d4a017 40%,#8a6d0b);color:#fff;border:0">
    <div style="display:flex;justify-content:space-between"><b style="font-size:16px">${c.f} ${c.n}${S.sid?" · "+S.sid:""}</b>
    <button onclick="menu()" style="background:rgba(255,255,255,.2);color:#fff;padding:4px 10px">🌍</button></div>
    <div id="rank" style="margin-top:6px"></div><div class="stats" id="st"></div></div>
  <div class="tabs">
    <button class="${tab==='b'?'on':''}" onclick="tab='b';render()">🏗️ Bangun</button>
    <button class="${tab==='w'?'on':''}" onclick="tab='w';render()">⚔️ Perang</button>
    <button class="${tab==='s'?'on':''}" onclick="tab='s';render()">🛒 Toko</button>
    <button class="${tab==='c'?'on':''}" onclick="tab='c';render()">⚙️</button></div>`;
  if(tab==="b"){
    h+=`<div style="display:flex;gap:4px;overflow-x:auto;margin-bottom:6px">${CATS.map(ct=>`<button style="flex:0 0 auto;padding:6px 10px;font-size:11px;border-radius:16px;border:1px solid var(--bd);background:${buildCat===ct.id?'linear-gradient(135deg,#b8860b,#ffd700)':'var(--card)'};color:${buildCat===ct.id?'#1a1200':'var(--tx)'}" onclick="buildCat='${ct.id}';render()">${ct.n}</button>`).join("")}</div>`;
    h+=`<div class="bgrid">${Object.keys(B).filter(k=>B[k].cat===buildCat).map(k=>`<button class="${S.sel===k?'on':''}" onclick="S.sel='${k}';render()"><span style="font-size:18px">${B[k].e}</span><br>${B[k].n}<br><small>${B[k].c||'85%'}</small></button>`).join("")}</div>`;
    const cols=8;h+=`<div class="grid" id="grid" style="grid-template-columns:repeat(8,1fr)">${S.t.map((x,i)=>`<div data-i="${i}" style="background:${S.ter[i]===1?'#6ab7e8':S.ter[i]===2&&!x?'#6fae52':((i%8+Math.floor(i/8))%2?'#a6d27a':'#9bc970')}">${x?B[x].e:(S.ter[i]===1?'🌊':S.ter[i]===2?'🌲':'')}</div>`).join("")}</div>
    <p class="mu">Konfirmasi sebelum bangun. Bongkar = refund 85%. Wilayah ${S.land||1} · Kotak ${S.t.length}</p>`;
  }else if(tab==="w"){
    if(S.mode==="pub"){
      h+=`<div class="card"><b>🌐 Online · ${S.sid}</b><p class="mu">${onlinePlayers.length} pemain lain</p>`;
      if(!onlinePlayers.length)h+=`<p class="mu">Belum ada musuh — lawan AI dulu. Saat pemain lain masuk, progres AI direset demi keadilan. Bagikan <b>${S.sid}</b></p>`;
      else h+=onlinePlayers.map(p=>{const name=(p.game_stats&&p.game_stats.name)||p.player_id;const country=(p.game_stats&&p.game_stats.country)||"?";const rl=(p.game_stats&&p.game_stats.role)||"biasa";const rb=rl==="admin"?`<span class="title-admin">👑 ADMIN</span>`:rl==="premium"?`<span class="title-prem">⭐ PREMIUM</span>`:`<span class="title-biasa">👤 BIASA</span>`;const ch=Math.round(S.army/(S.army+Math.max(1,p.army||1))*100);
        return`<div class="en"><span style="font-size:26px">${flagOf(country)}</span><div style="flex:1"><b>${esc(name)}</b> ${rb} <span class="mu">${esc(country)}</span><br><span class="mu">⚔️ ${fmt(p.army)} · 💰 ${fmt(p.money)}</span><div class="bar"><span style="width:${ch}%"></span></div></div><button class="btn-red" style="padding:8px 12px" onclick="attackPlayer('${esc(p.player_id)}')">⚔️</button></div>`}).join("");
      h+=`<button class="btn-gray" style="width:100%;margin-top:8px" onclick="loadOnlinePlayers().then(render)">⟳ Refresh</button></div>`;
      h+=`<div class="card"><b>🤖 AI</b>${S.en.slice(0,3).map((e,i)=>{const ch=Math.round(S.army/(S.army+e.pw)*100);return`<div class="en"><span style="font-size:22px">${e.f}</span><div style="flex:1"><b>${e.n}</b><div class="bar"><span style="width:${ch}%"></span></div></div><button class="btn-gray" style="padding:6px 10px;font-size:12px" onclick="attackAI(${i})">⚔️</button></div>`}).join("")}</div>`;
    }else h+=`<div class="card">${S.en.map((e,i)=>{const ch=Math.round(S.army/(S.army+e.pw)*100);return`<div class="en"><span style="font-size:26px">${e.f}</span><div style="flex:1"><b>${e.n}</b><div class="bar"><span style="width:${ch}%"></span></div><span class="mu">${ch}%</span></div><button class="btn-red" style="padding:8px 12px" onclick="attackAI(${i})">⚔️</button></div>`}).join("")}</div>`;
  }else if(tab==="s"){
    const c=getCart();
    h+=`<div class="card"><b>🛒 Toko / Keranjang</b><p class="mu">Koin: <b>🪙 ${fmt(coins)}</b></p>
      <button class="btn" onclick="openCoinShop()">Buka Toko Koin</button></div>
      <div class="card"><b>🧺 Keranjang</b><p>💰 ${fmt(c.money||0)} · ⚔️ ${fmt(c.army||0)}</p>
      <p class="mu">Masuk 1x saat pilih negara.</p></div>`;
  }else{
    h+=`<div class="card"><b>⚙️ Config</b><p class="mu">Mode: ${S.mode==="pub"?"🌐 "+S.sid:"🤖 Self"}</p>
      <button class="btn" onclick="cloudSave();toast('💾 Tersimpan')">💾 Simpan</button>
      <button class="btn-blue" style="margin-top:8px" onclick="openRedeem()">🎁 Redeem</button>
      <button class="btn" style="margin-top:8px;background:linear-gradient(135deg,#f59f00,#e8590c)" onclick="openGacha()">🎡 Gacha</button>
      <button class="btn-gray" style="width:100%;margin-top:8px" onclick="menu()">🚪 Lobby</button></div>`;
  }
  $("app").innerHTML=h;renderStats();
  const g=$("grid");if(g)g.onclick=e=>{const el=e.target.closest("[data-i]");if(el)build(+el.dataset.i)};
}
function start(){clearInterval(timer);clearInterval(pollTimer);render();timer=setInterval(tick,1500);if(S&&S.mode==="pub")pollTimer=setInterval(async()=>{await loadOnlinePlayers();if(tab==="w")render()},8000)}
function menu(){clearInterval(timer);clearInterval(pollTimer);if(S)cloudSave();S=null;currentServer=null;onlinePlayers=[];lobby()}

async function addToCart(type,amount){amount=+amount||0;if(amount<1e6||amount>1e14)return toast("1 Jt – 100 T");const cost=type==="money"?costMoney(amount):costArmy(amount);if(coins<cost)return toast("Koin kurang");coins-=cost;const c=getCart();if(type==="money")c.money=(c.money||0)+amount;else c.army=(c.army||0)+amount;setCart(c);await saveCoins();toast("🛒 +"+packLabel(amount));openCoinShop()}
function clearCart(){setCart({});toast("Keranjang kosong");openCoinShop()}
function openCoinShop(){
  const c=getCart();const packs=PACK_AMOUNTS.filter(n=>n<=1e14);
  const moneyOpts=packs.map(n=>`<option value="${n}">${packLabel(n)} uang — 🪙 ${fmt(costMoney(n))}</option>`).join("");
  const armyOpts=packs.map(n=>`<option value="${n}">${packLabel(n)} kekuatan — 🪙 ${fmt(costArmy(n))}</option>`).join("");
  $("app").innerHTML=`<div class="card"><div style="display:flex;justify-content:space-between"><b>🛒 Toko Koin</b><button class="btn-gray" style="padding:4px 10px" onclick="S?render():lobby()">←</button></div>
  <p class="mu">Koin: <b>🪙 ${fmt(coins)}</b> · Masuk <b>1x</b> saat pilih negara</p></div>
  <div class="card"><b>💰 Uang</b><p class="mu">1 Jt = 100.000 koin</p><select id="buyMoneyAmt">${moneyOpts}</select><button class="btn" onclick="addToCart('money',$('buyMoneyAmt').value)">+ Keranjang</button></div>
  <div class="card"><b>⚔️ Kekuatan</b><p class="mu">1 Jt = 500.000 koin</p><select id="buyArmyAmt">${armyOpts}</select><button class="btn" onclick="addToCart('army',$('buyArmyAmt').value)">+ Keranjang</button></div>
  <div class="card"><b>🧺 Keranjang</b><p>💰 ${fmt(c.money||0)} · ⚔️ ${fmt(c.army||0)}</p>
  ${(c.money||c.army)?'<button class="btn-red" style="width:100%;margin-top:8px" onclick="clearCart()">Kosongkan</button>':""}</div>`;
}

function showBan(){
  clearInterval(timer);clearInterval(pollTimer);clearInterval(banTimer);
  const m=metaRow||{is_banned:true,extra:{}};const ex=m.extra||{};const perm=isPermBan(m);
  const reason=ex.ban_reason||"Pelanggaran";const by=ex.banned_by||"";const at=ex.banned_at||"";const days=banDaysOf(ex);
  const rv=perm?null:reviewInfo(m);const can=!perm&&!rv&&canReview(m);
  const wa="https://wa.me/"+ADMIN_WA+"?text="+encodeURIComponent("Tinjau ban.\nNama: "+(ACC?ACC.name:"-")+"\nID: "+(uid||"-")+"\nAlasan: "+reason);
  const status=perm?`<div class="banst perm">🔴 PERMANEN</div>`:`<div class="banst temp">🟡 SEMENTARA${days?" · "+days+" hari":""}</div><p>Sisa: <b id="banLeft">-</b></p>`;
  const review=perm?`<p class="mu">Tidak bisa tinjau otomatis</p>`:rv?`<p>🔍 <b id="revLeft">-</b></p>`:can?`<button id="revBtn" class="btn" onclick="requestReview()">🔍 Tinjau Otomatis</button>`:`<p class="mu">Hubungi admin</p>`;
  $("app").innerHTML=`<div class="hero"><h1>🚫 DIBANNED</h1></div><div class="card" style="text-align:center">${status}<p style="margin-top:12px"><b>Alasan:</b> ${esc(reason)}</p>
  ${by?`<p class="mu">Oleh: ${esc(by)}</p>`:""}<p class="mu">ID: ${esc(uid||"-")}</p></div>
  <div class="card" style="text-align:center"><b>Tinjau</b><div style="margin-top:8px">${review}</div></div>
  <div class="card" style="text-align:center"><b>Admin</b><p style="font-size:20px;font-weight:800">${ADMIN_PHONE}</p><a class="wa" href="${wa}" target="_blank">💬 WhatsApp</a></div>`;
  banTimer=setInterval(banTick,1000);banTick();
}
async function banTick(){if(!metaRow||!metaRow.is_banned){clearInterval(banTimer);return}const ex=metaRow.extra||{};const now=Date.now();const rv=reviewInfo(metaRow);
  const bl=$("banLeft");if(bl&&ex.ban_until)bl.textContent=fmtLeft(new Date(ex.ban_until)-now);const rl=$("revLeft");if(rl&&rv)rl.textContent=fmtLeft(rv.until-now);
  if((ex.ban_until&&new Date(ex.ban_until)<=now)||(rv&&rv.until<=now)){clearInterval(banTimer);await loadMeta();if(!isBanned()){toast("✅ Dibuka");lobby()}else banTimer=setInterval(banTick,5000)}}
async function requestReview(){if(!metaRow||!canReview(metaRow))return toast("Tidak tersedia");const until=new Date(Date.now()+REVIEW_MS).toISOString();const nowIso=new Date().toISOString();
  try{for(const r of metaRows){if(!r.is_banned||!r.id)continue;const ex=r.extra||{};const ne={...ex,review_for:banKey(ex),review_until:until,review_requested_at:nowIso};await api("PATCH",API_META+"?id="+r.id,KEY_META,{extra:ne});r.extra=ne}toast("🔍 Tunggu 3 menit")}catch(e){toast("Gagal")}showBan()}

async function lobby(){
  $("app").innerHTML=`<div class="hero"><h1>🌍 BATTLE OF THE NATIONS</h1><p>Lobby</p></div><div class="card"><p class="mu">Memuat...</p></div>`;
  await ensureMeta();if(isBanned()){showBan();return}await ensureStats(ACC?.name);await enforceAntiCheat("lobby");
  const name=ACC?.name||"Pemain";const lvl=statsRow?.level||1;const exp=statsRow?.exp||0;
  $("app").innerHTML=`<div class="hero"><h1>🌍 BATTLE OF THE NATIONS</h1><p>Lobby</p></div>
  <div class="card"><div style="display:flex;justify-content:space-between;align-items:center;gap:8px;flex-wrap:wrap"><span>👤 <b>${esc(name)}</b> ${roleBadge(getRole())}</span><span class="rank">Lv ${lvl} · ${getRank((lvl||1)*100+exp)}</span></div>
  <p class="mu" style="margin-top:6px">ID: ${uid}</p>
  <p style="margin-top:10px;font-size:22px;font-weight:800">🪙 ${coins} <span class="mu" style="font-size:13px">Koin</span></p>
  <button class="btn-gray" style="width:100%;margin-top:10px" onclick="logoutAccount()">🚪 Logout / Ganti Akun</button>
  ${isInvestigation()?`<p style="margin-top:10px;padding:8px;background:rgba(245,159,0,.15);border-radius:10px;color:#f59f00;font-size:13px">⚠️ <b>Status Investigasi</b> — Bisa main, <b>tidak bisa Trade</b>. Chat bertanda peringatan sampai Unban penuh.</p>`:""}
  </div>
  <button class="btn-blue" onclick="serverScreen()">🌐 Server Public (PvP)</button>
  <button class="btn" onclick="countryScreen(false)">🤖 Main Self</button>
  <div style="display:flex;gap:8px;margin-top:8px">
    <button class="btn" style="flex:1;margin:0;background:linear-gradient(135deg,#f59f00,#e8590c)" onclick="openGacha()">🎡 Gacha</button>
    <button class="btn-blue" style="flex:1;margin:0" onclick="openQuest()">❓ Quest</button></div>
  <button class="btn" style="margin-top:8px" onclick="openCoinShop()">🛒 Toko Koin / Keranjang</button>
  <button class="btn-blue" style="margin-top:8px" onclick="openTrade()">🤝 Trade (Lobby)</button>
  <p class="mu" style="margin-top:12px;text-align:center">${CS.length} negara · Uang & kekuatan reset tiap pilih negara · Trade di Lobby</p>`;
}
async function serverScreen(){
  $("app").innerHTML=`<div class="card"><div style="display:flex;justify-content:space-between"><b>🌐 Server</b><button class="btn-gray" style="padding:4px 10px" onclick="lobby()">←</button></div>
  <p class="mu">Negara eksklusif · maks ${CS.length}</p></div>
  <div class="card"><b>Gabung Kode</b><input id="sid" placeholder="S-XXXX" style="text-transform:uppercase"><button class="btn" onclick="joinByCode()">Gabung</button></div>
  <div class="card"><div style="display:flex;justify-content:space-between"><b>Aktif</b><button class="btn-gray" style="padding:4px 10px" onclick="serverScreen()">⟳</button></div><div id="sl"><p class="mu">Memuat...</p></div></div>`;
  const servers=await listServers();const el=$("sl");
  if(!servers.length){el.innerHTML="<p class='mu'>Belum ada server.</p>";return}
  el.innerHTML=servers.map(s=>{const tb=s.type==="permanent"?"<span class='badge blue'>PERMANENT</span>":s.type==="timed"?"<span class='badge warn'>TIMED</span>":"<span class='badge'>FREE</span>";
    const exp=s.expires?(" · "+Math.max(0,Math.round((s.expires-Date.now())/3600000))+"j"):"";
    return`<div class="srv"><div><b>${s.code}</b> ${tb}<br><span class="mu">Min Lv ${s.minLevel}${exp}</span></div>
    <button class="btn" style="width:auto;padding:8px 14px;margin:0" onclick="joinServer('${s.code}',${s.minLevel})">Masuk</button></div>`}).join("");
}
function joinByCode(){const v=($("sid").value||"").trim().toUpperCase();if(!v)return toast("Isi kode");joinServer(v,1)}
async function joinServer(code,minLv){if((statsRow?.level||1)<minLv)return toast("Butuh Lv "+minLv);const servers=await listServers();const s=servers.find(x=>x.code===code);if(!s)return toast("Tidak ditemukan");
  try{const list=arr(await api("GET",API_STATS,KEY_STATS));const online=new Set();list.forEach(p=>{const gs=p.game_stats||{};if(gs.server===code&&p.player_id!==uid)online.add(p.player_id)});if(online.size>=CS.length)return toast("Penuh")}catch(e){}
  currentServer=s;countryScreen(code)}
async function countryScreen(pub){
  window._pubCountry=pub;window._taken={};
  $("app").innerHTML=`<div class="card"><div style="display:flex;justify-content:space-between"><b>${pub?"Negara · "+pub:"Self"}</b>
  <button class="btn-gray" style="padding:4px 10px" onclick="${pub?"serverScreen()":"lobby()"}">←</button></div>
  <p class="mu">${pub?"🔒 terpakai dikunci":"Latihan AI"} · ${CS.length} negara</p>
  <input id="qNegara" placeholder="🔎 Cari..." oninput="filterNegara()"></div>
  <div id="listNegara" style="display:grid;grid-template-columns:1fr 1fr;gap:8px"><p class="mu">Memuat...</p></div>`;
  if(pub){try{const list=arr(await api("GET",API_STATS,KEY_STATS));const map={};list.forEach(p=>{if(p.player_id===uid)return;const gs=p.game_stats||{};if(gs.server===pub&&gs.country)map[gs.country]=gs.name||p.player_id});window._taken=map}catch(e){window._taken={}}}
  filterNegara()}
function filterNegara(){const q=($("qNegara")?.value||"").toLowerCase().trim();const pub=window._pubCountry;const taken=window._taken||{};const el=$("listNegara");if(!el)return;let h="";
  CS.forEach((c,i)=>{if(q&&c.n.toLowerCase().indexOf(q)<0)return;const who=taken[c.n];
    if(who)h+=`<button class="card" disabled style="text-align:center;opacity:.45"><span style="font-size:26px">${c.f}</span><br><b style="font-size:12px">${c.n}</b><br><span class="mu">🔒 ${esc(who)}</span></button>`;
    else h+=`<button class="card" style="text-align:center" onclick="pick(${i},${pub?`'${pub}'`:false})"><span style="font-size:26px">${c.f}</span><br><b style="font-size:12px">${c.n}</b></button>`});
  el.innerHTML=h||`<p class="mu">Tidak ketemu</p>`}

function openRedeem(){if(!S){toast("Pilih negara dulu");return}
  $("app").innerHTML=`<div class="card"><div style="display:flex;justify-content:space-between"><b>🎁 Redeem</b><button class="btn-gray" style="padding:4px 10px" onclick="render()">←</button></div>
  <p class="mu">1x per negara</p><input id="codeIn" placeholder="Kode"><button class="btn" onclick="doRedeem()">Klaim</button></div>`}
async function doRedeem(){const v=($("codeIn").value||"").trim().toLowerCase();if(!v)return toast("Isi kode");if(!S)return;const c=CODES[v];if(!c)return toast("❌ Invalid");S.rc=S.rc||{};if(S.rc[v])return toast("⚠️ Sudah diklaim");S.rc[v]=1;
  if(c.admin){S.admin=1;S.m=1e18;S.army=1e18;S.land=Math.max(S.land||1,50);growMap(Math.max(0,200-S.t.length));S.food=1e18;S.lvl=Math.max(S.lvl||1,500);S.xp=Math.max(S.xp||0,50000);await cloudSave();toast("👑 Admin")}
  else{S.m+=c.m;S.army+=c.a;await cloudSave();toast("🎁 +"+fmt(c.m))}setTimeout(render,800)}
function openGacha(){const w=getWheel();const today=wibDay();if(w.last!==today){w.spins=0;w.last=today;setWheel(w)}const spins=w.spins||0;const sisa=Math.max(0,14-spins);const habis=sisa<=0;
  $("app").innerHTML=`<div class="card"><div style="display:flex;justify-content:space-between"><b>🎡 Gacha</b><button class="btn-gray" style="padding:4px 10px" onclick="S?render():lobby()">←</button></div>
  <p class="mu">14x/hari · Sisa <b>${sisa}/14</b></p><div style="text-align:center;padding:20px;font-size:64px" id="gachaIcon">🎡</div>
  <button class="btn" id="spinBtn" ${habis?"disabled style='opacity:.5'":""} onclick="spinGacha()">${habis?"Habis":"🎡 PUTAR ("+sisa+")"}</button>
  <div id="gachaRes" class="mu" style="margin-top:12px;text-align:center"></div></div>`}
function spinGacha(){const w=getWheel();const today=wibDay();if(w.last!==today){w.spins=0;w.last=today}if((w.spins||0)>=14)return toast("Habis");
  const btn=$("spinBtn");if(btn){btn.disabled=true;btn.textContent="..."}const icon=$("gachaIcon");let n=0;const spin=setInterval(()=>{icon.textContent=["💰","⚔️","🎁","💎","🏆","🎡"][n++%6]},80);
  setTimeout(()=>{clearInterval(spin);const r=Math.random();let txt="";
    if(r<0.08){const keys=Object.keys(CODES).filter(k=>!CODES[k].admin);const k=keys[Math.floor(Math.random()*keys.length)];txt="🔑 "+k;icon.textContent="🔑"}
    else if(r<0.4){const a=10+Math.floor(Math.random()*490);if(S)S.army+=a;else w.pa=(w.pa||0)+a;txt="⚔️ +"+a;icon.textContent="⚔️"}
    else if(r<0.7){const m=Math.floor(50*Math.pow(1e6,Math.random()));if(S)S.m+=m;else w.pm=(w.pm||0)+m;txt="💰 +"+fmt(m);icon.textContent="💰"}
    else{const c=5+Math.floor(Math.random()*30);coins+=c;saveCoins();txt="🪙 +"+c;icon.textContent="🪙"}
    w.spins=(w.spins||0)+1;w.last=today;setWheel(w);if(S)cloudSave();const sisa=Math.max(0,14-w.spins);
    const res=$("gachaRes");if(res)res.innerHTML="<b>🎉</b> "+txt+" · sisa "+sisa;
    if(btn){if(sisa<=0){btn.disabled=true;btn.textContent="Habis"}else{btn.disabled=false;btn.textContent="🎡 PUTAR ("+sisa+")"}}
    toast("🎡 "+txt)},2200)}

async function openQuest(){$("app").innerHTML=`<div class="card"><div style="display:flex;justify-content:space-between"><b>❓ Quest</b><button class="btn-gray" style="padding:4px 10px" onclick="lobby()">←</button></div>
  <p class="mu">Benar = koin</p></div><div class="card"><b>Quest Biasa</b><button class="btn" onclick="startNormalQuest()">Soal acak</button></div>
  <div class="card"><b>Event</b><div id="eq"><p class="mu">Memuat...</p></div></div>`;
  try{const list=arr(await api("GET",API_META,KEY_META)).filter(x=>String(x.player_id).startsWith(QUEST_PREFIX)||(x.extra&&x.extra.is_quest));
    const active=list.filter(s=>{const ex=s.extra||{};return ex.active!==false&&(!ex.expires_at||new Date(ex.expires_at)>new Date())});
    const el=$("eq");if(!active.length){el.innerHTML="<p class='mu'>Belum ada event</p>";return}
    el.innerHTML=active.map(s=>{const ex=s.extra||{};const id=ex.quest_id||s.player_id;const done=claimedQuests[id];
      return`<div class="srv"><div><b>${esc((ex.question||"").slice(0,40))}...</b><br><span class="mu">🪙 ${ex.reward_coins||0}</span></div>
      <button class="btn" style="width:auto;margin:0;padding:8px 12px" ${done?"disabled":""} onclick="startEventQuest('${esc(id)}')">${done?"Selesai":"Jawab"}</button></div>`}).join("")}catch(e){$("eq").innerHTML="<p class='mu'>Gagal</p>"}}
function startNormalQuest(){const q=NORMAL_QUESTS[Math.floor(Math.random()*NORMAL_QUESTS.length)];window._cq={...q,id:"N"+Date.now()};
  $("app").innerHTML=`<div class="card"><div style="display:flex;justify-content:space-between"><b>❓ Quest</b><button class="btn-gray" style="padding:4px 10px" onclick="openQuest()">←</button></div>
  <p style="margin-top:12px;font-size:16px">${esc(q.q)}</p><input id="qans" placeholder="Jawaban"><button class="btn" onclick="submitQuest()">Kirim</button><p class="mu">🪙 ${q.reward}</p></div>`}
async function startEventQuest(qid){if(claimedQuests[qid])return toast("Sudah");try{const list=arr(await api("GET",API_META,KEY_META));const row=list.find(x=>(x.extra&&x.extra.quest_id===qid)||x.player_id===QUEST_PREFIX+qid);if(!row)return toast("Tidak ada");const ex=row.extra||{};
  window._cq={q:ex.question,a:String(ex.answer||"").toLowerCase(),reward:+ex.reward_coins||50,id:qid};
  $("app").innerHTML=`<div class="card"><div style="display:flex;justify-content:space-between"><b>📢 Event</b><button class="btn-gray" style="padding:4px 10px" onclick="openQuest()">←</button></div>
  <p style="margin-top:12px;font-size:16px">${esc(ex.question)}</p><input id="qans"><button class="btn" onclick="submitQuest()">Kirim</button><p class="mu">🪙 ${ex.reward_coins||0}</p></div>`}catch(e){toast("Gagal")}}
async function submitQuest(){const cq=window._cq;if(!cq)return;const ans=($("qans").value||"").trim().toLowerCase();if(!ans)return toast("Isi");
  if(ans===String(cq.a).toLowerCase()){coins+=(cq.reward||10);await saveCoins();claimedQuests[cq.id]=1;ls("negara_qclaim",JSON.stringify(claimedQuests));toast("🎉 +"+cq.reward+" koin")}else toast("❌ Salah");
  setTimeout(openQuest,900)}

function nameScreen(){accountScreen()}
async function saveName(){
  const u=$("nm").value.trim();
  if(!/^[A-Za-z0-9_ ]{3,14}$/.test(u))return toast("Nama 3-14 karakter");
  // akun baru?
  let isNew=!ls("negara_uid");
  if(isNew){
    const list=loadAccounts();
    if(list.length>=MAX_ACC)return toast("Maksimal "+MAX_ACC+" akun. Hapus salah satu dulu.");
    uid="u"+Math.random().toString(36).slice(2,10)+Date.now().toString(36);
    ls("negara_uid",uid);
  }else{
    uid=ls("negara_uid");
  }
  ls("negara_name",u);ACC={name:u,id:uid};
  upsertAccount(uid,u);
  await ensureMeta();if(isBanned()){showBan();return}
  await ensureStats(u);toast("Halo, "+u+"!");lobby();
}
function switchToAccount(targetUid,name){
  clearInterval(timer);clearInterval(pollTimer);clearInterval(banTimer);
  S=null;onlinePlayers=[];metaRow=null;statsRow=null;
  uid=targetUid;ls("negara_uid",targetUid);ls("negara_name",name);
  ACC={name,id:targetUid};upsertAccount(targetUid,name);
  (async()=>{await ensureMeta();if(isBanned()){showBan();return}await ensureStats(name);toast("Masuk: "+name);lobby()})();
}
function accountScreen(){
  const list=loadAccounts();
  let h=`<div class="hero"><h1>🌍 BATTLE OF THE NATIONS</h1><p>Pilih Akun · Maks ${MAX_ACC}</p></div>
  <div class="card"><b>Akun tersimpan (${list.length}/${MAX_ACC})</b>`;
  if(!list.length)h+=`<p class="mu" style="margin-top:8px">Belum ada akun.</p>`;
  else h+=list.map(a=>`<div class="acc-item">
      <div><b>${esc(a.name)}</b><br><span class="mu">${esc(a.uid)}</span></div>
      <div style="display:flex;gap:6px">
        <button class="btn" style="width:auto;margin:0;padding:8px 12px" onclick="switchToAccount('${esc(a.uid)}','${esc(a.name)}')">Masuk</button>
        <button class="btn-red" style="width:auto;margin:0;padding:8px 10px" onclick="deleteAccPrompt('${esc(a.uid)}','${esc(a.name)}')">Hapus</button>
      </div></div>`).join("");
  h+=`</div>`;
  if(list.length<MAX_ACC){
    h+=`<div class="card"><b>Buat Akun Baru</b>
      <input id="nm" maxlength="14" placeholder="Nama 3-14 karakter">
      <button class="btn" onclick="createNewAccount()">➕ Buat Akun</button>
      <p class="mu">Sisa slot: ${MAX_ACC-list.length}</p></div>`;
  }else{
    h+=`<div class="card"><p class="mu">Slot penuh (${MAX_ACC}/${MAX_ACC}). Hapus akun lama untuk membuat baru.</p></div>`;
  }
  $("app").innerHTML=h;
}
function createNewAccount(){
  // clear current session keys so saveName creates new uid
  ls("negara_uid",null);ls("negara_name",null);uid=null;ACC=null;
  saveName();
}
function deleteAccPrompt(id,name){
  if(!confirm("Hapus akun \""+name+"\" dari perangkat ini?\nData cloud tidak otomatis terhapus."))return;
  removeAccount(id);
  if(ls("negara_uid")===id){ls("negara_uid",null);ls("negara_name",null)}
  toast("Akun dihapus dari daftar");accountScreen();
}

(async function boot(){
  uid=ls("negara_uid");const name=ls("negara_name");
  if(uid&&name){
    ACC={name,id:uid};upsertAccount(uid,name);
    await ensureMeta();if(isBanned()){showBan();return}
    await ensureStats(name);lobby();
  }else accountScreen();
})();
</script>
</body>
</html>

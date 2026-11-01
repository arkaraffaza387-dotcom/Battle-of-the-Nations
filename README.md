
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
{n:"Afghanistan",f:"🇦🇫",m:508,a:27,p:33},
{n:"Afrika Selatan",f:"🇿🇦",m:922,a:63,p:36},
{n:"Afrika Tengah",f:"🇨🇫",m:415,a:53,p:51},
{n:"Albania",f:"🇦🇱",m:419,a:69,p:28},
{n:"Aljazair",f:"🇩🇿",m:803,a:22,p:49},
{n:"Amerika Serikat",f:"🇺🇸",m:439,a:64,p:54},
{n:"Andorra",f:"🇦🇩",m:790,a:67,p:28},
{n:"Angola",f:"🇦🇴",m:932,a:41,p:50},
{n:"Antigua dan Barbuda",f:"🇦🇬",m:449,a:34,p:30},
{n:"Arab Saudi",f:"🇸🇦",m:412,a:45,p:59},
{n:"Argentina",f:"🇦🇷",m:719,a:42,p:55},
{n:"Armenia",f:"🇦🇲",m:839,a:35,p:61},
{n:"Australia",f:"🇦🇺",m:807,a:38,p:31},
{n:"Austria",f:"🇦🇹",m:886,a:34,p:47},
{n:"Azerbaijan",f:"🇦🇿",m:689,a:53,p:29},
{n:"Bahama",f:"🇧🇸",m:428,a:47,p:31},
{n:"Bahrain",f:"🇧🇭",m:706,a:40,p:46},
{n:"Bangladesh",f:"🇧🇩",m:730,a:27,p:58},
{n:"Barbados",f:"🇧🇧",m:614,a:74,p:40},
{n:"Belanda",f:"🇳🇱",m:688,a:53,p:50},
{n:"Belarus",f:"🇧🇾",m:897,a:51,p:58},
{n:"Belgia",f:"🇧🇪",m:772,a:57,p:60},
{n:"Belize",f:"🇧🇿",m:846,a:52,p:54},
{n:"Benin",f:"🇧🇯",m:635,a:22,p:37},
{n:"Bhutan",f:"🇧🇹",m:762,a:40,p:52},
{n:"Bolivia",f:"🇧🇴",m:705,a:32,p:55},
{n:"Bosnia dan Herzegovina",f:"🇧🇦",m:439,a:57,p:30},
{n:"Botswana",f:"🇧🇼",m:815,a:71,p:61},
{n:"Brasil",f:"🇧🇷",m:529,a:30,p:25},
{n:"Brunei",f:"🇧🇳",m:919,a:47,p:46},
{n:"Bulgaria",f:"🇧🇬",m:570,a:52,p:27},
{n:"Burkina Faso",f:"🇧🇫",m:590,a:23,p:29},
{n:"Burundi",f:"🇧🇮",m:892,a:66,p:32},
{n:"Chad",f:"🇹🇩",m:948,a:27,p:37},
{n:"Chili",f:"🇨🇱",m:628,a:68,p:40},
{n:"Denmark",f:"🇩🇰",m:850,a:52,p:23},
{n:"Djibouti",f:"🇩🇯",m:864,a:54,p:60},
{n:"Dominika",f:"🇩🇲",m:677,a:36,p:60},
{n:"Ekuador",f:"🇪🇨",m:418,a:22,p:27},
{n:"El Salvador",f:"🇸🇻",m:907,a:61,p:52},
{n:"Eritrea",f:"🇪🇷",m:670,a:35,p:27},
{n:"Estonia",f:"🇪🇪",m:494,a:41,p:27},
{n:"Eswatini",f:"🇸🇿",m:728,a:59,p:23},
{n:"Etiopia",f:"🇪🇹",m:434,a:64,p:58},
{n:"Fiji",f:"🇫🇯",m:734,a:67,p:56},
{n:"Filipina",f:"🇵🇭",m:608,a:26,p:25},
{n:"Finlandia",f:"🇫🇮",m:436,a:33,p:53},
{n:"Gabon",f:"🇬🇦",m:626,a:44,p:61},
{n:"Gambia",f:"🇬🇲",m:517,a:52,p:44},
{n:"Georgia",f:"🇬🇪",m:516,a:20,p:50},
{n:"Ghana",f:"🇬🇭",m:874,a:72,p:53},
{n:"Grenada",f:"🇬🇩",m:648,a:55,p:29},
{n:"Guatemala",f:"🇬🇹",m:549,a:49,p:55},
{n:"Guinea",f:"🇬🇳",m:480,a:23,p:27},
{n:"Guinea Khatulistiwa",f:"🇬🇶",m:560,a:50,p:61},
{n:"Guinea-Bissau",f:"🇬🇼",m:511,a:67,p:32},
{n:"Guyana",f:"🇬🇾",m:721,a:73,p:59},
{n:"Haiti",f:"🇭🇹",m:713,a:33,p:53},
{n:"Honduras",f:"🇭🇳",m:507,a:35,p:42},
{n:"Hungaria",f:"🇭🇺",m:547,a:64,p:34},
{n:"India",f:"🇮🇳",m:926,a:48,p:54},
{n:"Indonesia",f:"🇮🇩",m:936,a:25,p:61},
{n:"Inggris",f:"🇬🇧",m:570,a:52,p:36},
{n:"Irak",f:"🇮🇶",m:615,a:74,p:47},
{n:"Iran",f:"🇮🇷",m:418,a:69,p:28},
{n:"Irlandia",f:"🇮🇪",m:829,a:57,p:22},
{n:"Islandia",f:"🇮🇸",m:658,a:41,p:25},
{n:"Israel",f:"🇮🇱",m:401,a:51,p:42},
{n:"Italia",f:"🇮🇹",m:594,a:39,p:56},
{n:"Jamaika",f:"🇯🇲",m:813,a:47,p:31},
{n:"Jepang",f:"🇯🇵",m:796,a:37,p:47},
{n:"Jerman",f:"🇩🇪",m:923,a:47,p:41},
{n:"Kamboja",f:"🇰🇭",m:668,a:34,p:52},
{n:"Kamerun",f:"🇨🇲",m:794,a:37,p:60},
{n:"Kanada",f:"🇨🇦",m:640,a:38,p:53},
{n:"Kazakhstan",f:"🇰🇿",m:767,a:33,p:42},
{n:"Kenya",f:"🇰🇪",m:824,a:64,p:28},
{n:"Kirgizstan",f:"🇰🇬",m:842,a:43,p:29},
{n:"Kiribati",f:"🇰🇮",m:775,a:42,p:54},
{n:"Kolombia",f:"🇨🇴",m:775,a:73,p:53},
{n:"Komoro",f:"🇰🇲",m:642,a:46,p:49},
{n:"Kongo",f:"🇨🇬",m:721,a:58,p:41},
{n:"Korea Selatan",f:"🇰🇷",m:698,a:70,p:24},
{n:"Korea Utara",f:"🇰🇵",m:700,a:62,p:33},
{n:"Kosovo",f:"🇽🇰",m:704,a:55,p:46},
{n:"Kosta Rika",f:"🇨🇷",m:439,a:41,p:41},
{n:"Kroasia",f:"🇭🇷",m:616,a:74,p:48},
{n:"Kuba",f:"🇨🇺",m:713,a:72,p:59},
{n:"Kuwait",f:"🇰🇼",m:468,a:21,p:51},
{n:"Laos",f:"🇱🇦",m:776,a:42,p:27},
{n:"Latvia",f:"🇱🇻",m:676,a:20,p:30},
{n:"Lebanon",f:"🇱🇧",m:438,a:25,p:39},
{n:"Lesotho",f:"🇱🇸",m:435,a:25,p:23},
{n:"Liberia",f:"🇱🇷",m:713,a:33,p:39},
{n:"Libya",f:"🇱🇾",m:772,a:33,p:36},
{n:"Liechtenstein",f:"🇱🇮",m:593,a:47,p:56},
{n:"Lituania",f:"🇱🇹",m:520,a:21,p:33},
{n:"Luksemburg",f:"🇱🇺",m:850,a:29,p:48},
{n:"Madagaskar",f:"🇲🇬",m:599,a:48,p:47},
{n:"Makedonia Utara",f:"🇲🇰",m:795,a:45,p:43},
{n:"Maladewa",f:"🇲🇻",m:427,a:63,p:37},
{n:"Malawi",f:"🇲🇼",m:597,a:71,p:24},
{n:"Malaysia",f:"🇲🇾",m:596,a:63,p:61},
{n:"Mali",f:"🇲🇱",m:648,a:71,p:40},
{n:"Malta",f:"🇲🇹",m:696,a:38,p:36},
{n:"Maroko",f:"🇲🇦",m:564,a:74,p:46},
{n:"Marshall",f:"🇲🇭",m:866,a:63,p:36},
{n:"Mauritania",f:"🇲🇷",m:856,a:38,p:34},
{n:"Mauritius",f:"🇲🇺",m:557,a:73,p:27},
{n:"Meksiko",f:"🇲🇽",m:619,a:35,p:60},
{n:"Mesir",f:"🇪🇬",m:805,a:54,p:23},
{n:"Mikronesia",f:"🇫🇲",m:606,a:41,p:27},
{n:"Moldova",f:"🇲🇩",m:583,a:38,p:55},
{n:"Monako",f:"🇲🇨",m:836,a:35,p:60},
{n:"Mongolia",f:"🇲🇳",m:624,a:44,p:50},
{n:"Montenegro",f:"🇲🇪",m:608,a:26,p:57},
{n:"Mozambik",f:"🇲🇿",m:574,a:37,p:54},
{n:"Myanmar",f:"🇲🇲",m:816,a:40,p:30},
{n:"Namibia",f:"🇳🇦",m:422,a:62,p:42},
{n:"Nauru",f:"🇳🇷",m:753,a:39,p:56},
{n:"Nepal",f:"🇳🇵",m:878,a:72,p:38},
{n:"Niger",f:"🇳🇪",m:463,a:21,p:43},
{n:"Nigeria",f:"🇳🇬",m:845,a:20,p:26},
{n:"Nikaragua",f:"🇳🇮",m:897,a:59,p:61},
{n:"Norwegia",f:"🇳🇴",m:603,a:56,p:55},
{n:"Oman",f:"🇴🇲",m:807,a:23,p:42},
{n:"Pakistan",f:"🇵🇰",m:807,a:38,p:27},
{n:"Palau",f:"🇵🇼",m:721,a:50,p:49},
{n:"Palestina",f:"🇵🇸",m:817,a:56,p:56},
{n:"Panama",f:"🇵🇦",m:647,a:39,p:59},
{n:"Pantai Gading",f:"🇨🇮",m:723,a:74,p:49},
{n:"Papua Nugini",f:"🇵🇬",m:904,a:29,p:36},
{n:"Paraguay",f:"🇵🇾",m:760,a:32,p:52},
{n:"Perancis",f:"🇫🇷",m:814,a:47,p:30},
{n:"Peru",f:"🇵🇪",m:697,a:38,p:24},
{n:"Polandia",f:"🇵🇱",m:933,a:56,p:52},
{n:"Portugal",f:"🇵🇹",m:934,a:57,p:61},
{n:"Qatar",f:"🇶🇦",m:405,a:36,p:44},
{n:"RD Kongo",f:"🇨🇩",m:737,a:21,p:36},
{n:"Republik Ceko",f:"🇨🇿",m:404,a:59,p:47},
{n:"Republik Dominika",f:"🇩🇴",m:749,a:30,p:41},
{n:"Rumania",f:"🇷🇴",m:580,a:30,p:58},
{n:"Rusia",f:"🇷🇺",m:545,a:25,p:50},
{n:"Rwanda",f:"🇷🇼",m:841,a:35,p:55},
{n:"Saint Kitts dan Nevis",f:"🇰🇳",m:839,a:27,p:27},
{n:"Saint Lucia",f:"🇱🇨",m:856,a:38,p:60},
{n:"Saint Vincent",f:"🇻🇨",m:651,a:71,p:35},
{n:"Samoa",f:"🇼🇸",m:601,a:72,p:41},
{n:"San Marino",f:"🇸🇲",m:520,a:45,p:57},
{n:"Sao Tome dan Principe",f:"🇸🇹",m:547,a:41,p:29},
{n:"Selandia Baru",f:"🇳🇿",m:533,a:54,p:23},
{n:"Senegal",f:"🇸🇳",m:439,a:41,p:29},
{n:"Serbia",f:"🇷🇸",m:685,a:21,p:47},
{n:"Seychelles",f:"🇸🇨",m:781,a:35,p:59},
{n:"Sierra Leone",f:"🇸🇱",m:854,a:69,p:59},
{n:"Singapura",f:"🇸🇬",m:424,a:70,p:38},
{n:"Siprus",f:"🇨🇾",m:460,a:52,p:49},
{n:"Slovakia",f:"🇸🇰",m:801,a:22,p:42},
{n:"Slovenia",f:"🇸🇮",m:931,a:33,p:42},
{n:"Solomon",f:"🇸🇧",m:610,a:57,p:35},
{n:"Somalia",f:"🇸🇴",m:407,a:44,p:25},
{n:"Spanyol",f:"🇪🇸",m:892,a:74,p:34},
{n:"Sri Lanka",f:"🇱🇰",m:849,a:60,p:33},
{n:"Sudan",f:"🇸🇩",m:679,a:59,p:58},
{n:"Sudan Selatan",f:"🇸🇸",m:406,a:52,p:42},
{n:"Suriah",f:"🇸🇾",m:515,a:52,p:42},
{n:"Suriname",f:"🇸🇷",m:526,a:53,p:35},
{n:"Swedia",f:"🇸🇪",m:811,a:70,p:22},
{n:"Swiss",f:"🇨🇭",m:460,a:67,p:25},
{n:"Taiwan",f:"🇹🇼",m:568,a:51,p:43},
{n:"Tajikistan",f:"🇹🇯",m:848,a:21,p:26},
{n:"Tanjung Verde",f:"🇨🇻",m:891,a:74,p:39},
{n:"Tanzania",f:"🇹🇿",m:833,a:74,p:46},
{n:"Thailand",f:"🇹🇭",m:591,a:63,p:56},
{n:"Timor Leste",f:"🇹🇱",m:451,a:74,p:43},
{n:"Tiongkok",f:"🇨🇳",m:688,a:37,p:27},
{n:"Togo",f:"🇹🇬",m:646,a:47,p:30},
{n:"Tonga",f:"🇹🇴",m:883,a:41,p:43},
{n:"Trinidad dan Tobago",f:"🇹🇹",m:909,a:37,p:43},
{n:"Tunisia",f:"🇹🇳",m:452,a:51,p:46},
{n:"Turki",f:"🇹🇷",m:915,a:38,p:28},
{n:"Turkmenistan",f:"🇹🇲",m:880,a:72,p:34},
{n:"Tuvalu",f:"🇹🇻",m:550,a:57,p:45},
{n:"Uganda",f:"🇺🇬",m:814,a:55,p:23},
{n:"Ukraina",f:"🇺🇦",m:888,a:42,p:55},
{n:"Uni Emirat Arab",f:"🇦🇪",m:790,a:44,p:37},
{n:"Uruguay",f:"🇺🇾",m:766,a:25,p:60},
{n:"Uzbekistan",f:"🇺🇿",m:599,a:48,p:53},
{n:"Vanuatu",f:"🇻🇺",m:870,a:40,p:40},
{n:"Vatikan",f:"🇻🇦",m:626,a:36,p:57},
{n:"Venezuela",f:"🇻🇪",m:851,a:29,p:24},
{n:"Vietnam",f:"🇻🇳",m:826,a:73,p:30},
{n:"Yaman",f:"🇾🇪",m:483,a:63,p:23},
{n:"Yordania",f:"🇯🇴",m:765,a:40,p:50},
{n:"Yunani",f:"🇬🇷",m:682,a:21,p:36},
{n:"Zambia",f:"🇿🇲",m:638,a:61,p:42},
{n:"Zimbabwe",f:"🇿🇼",m:822,a:25,p:34}
];
const B={h:{e:"🏠",n:"Rumah",c:100},f:{e:"🌾",n:"Ladang",c:80},p:{e:"🏭",n:"Pabrik",c:150},b:{e:"🏰",n:"Barak",c:200},r:{e:"🛣️",n:"Jalan",c:15},x:{e:"💣",n:"Bongkar",c:0}};

let S=null,tab="b",timer=null,pollTimer=null,uid=null,ACC=null,metaRow=null,statsRow=null,currentServer=null,onlinePlayers=[];

const $=id=>document.getElementById(id);
function toast(t){const e=$("toast");e.textContent=t;e.className="s";clearTimeout(window._tt);window._tt=setTimeout(()=>e.className="",2800)}
function fmt(n){n=Math.floor(+n||0);if(n>=1e9)return(n/1e9).toFixed(1)+" M";if(n>=1e6)return(n/1e6).toFixed(1)+" Jt";if(n>=1e3)return(n/1e3).toFixed(1)+" Rb";return""+n}
function ls(k,v){try{if(v===undefined)return localStorage.getItem(k);if(v===null)localStorage.removeItem(k);else localStorage.setItem(k,v)}catch(e){}}
function getRank(exp){exp=+exp||0;if(exp>=91)return"Super Pro";if(exp>=88)return"Pro";if(exp>=55)return"Jagoan";if(exp>=25)return"Jago";if(exp>=12)return"Lumayan";return"Pemula"}
function flagOf(country){const c=CS.find(x=>x.n===country);return c?c.f:"🏳️"}

async function api(method,url,key,body){
  const opt={method,headers:{"x-api-key":key,"Content-Type":"application/json"}};
  if(body)opt.body=JSON.stringify(body);
  const r=await fetch(url,opt);const t=await r.text();
  if(!r.ok)throw new Error(r.status+" "+t.slice(0,100));
  try{return JSON.parse(t)}catch(e){return null}
}
function arr(d){if(!d)return[];if(Array.isArray(d))return d;if(Array.isArray(d.records))return d.records;if(Array.isArray(d.data))return d.data;return[]}

async function loadMeta(){try{const list=arr(await api("GET",API_META,KEY_META));const m=list.filter(x=>x.player_id===uid).sort((a,b)=>new Date(b.created_at||0)-new Date(a.created_at||0));metaRow=m[0]||null;return metaRow}catch(e){metaRow=null;return null}}
async function loadStats(){try{const list=arr(await api("GET",API_STATS,KEY_STATS));const m=list.filter(x=>x.player_id===uid).sort((a,b)=>new Date(b.created_at||0)-new Date(a.created_at||0));statsRow=m[0]||null;return statsRow}catch(e){statsRow=null;return null}}
async function ensureMeta(){await loadMeta();if(!metaRow){try{metaRow=await api("POST",API_META,KEY_META,{player_id:uid,is_admin:false,is_banned:false,is_whitelisted:false,extra:{}})}catch(e){}}}
async function ensureStats(name){await loadStats();if(!statsRow){try{statsRow=await api("POST",API_STATS,KEY_STATS,{player_id:uid,level:1,exp:0,money:500,army:20,game_stats:{name:name||"Pemain",rank:"Pemula",win_streak:0}})}catch(e){}}}
function isBanned(){return !!(metaRow&&metaRow.is_banned)}

/* ===== SERVERS ===== */
async function listServers(){
  try{
    const list=arr(await api("GET",API_META,KEY_META));
    return list.filter(x=>String(x.player_id).startsWith(SRV_PREFIX)||(x.extra&&x.extra.is_server)).map(s=>{
      const ex=s.extra||{};
      return{id:s.id,code:ex.server_code||String(s.player_id).replace(SRV_PREFIX,""),type:ex.server_type||"free",active:ex.server_is_active!==false,expires:ex.server_expires_at?new Date(ex.server_expires_at):null,minLevel:ex.server_min_level||1};
    }).filter(s=>s.active&&(!s.expires||s.expires>new Date()));
  }catch(e){return[]}
}

/* ===== ONLINE PLAYERS (PvP) ===== */
async function loadOnlinePlayers(){
  if(!S||S.mode!=="pub"||!S.sid){onlinePlayers=[];return}
  try{
    const list=arr(await api("GET",API_STATS,KEY_STATS));
    // unique by player_id, latest only, same server, not me
    const map={};
    list.forEach(p=>{
      if(p.player_id===uid)return;
      if(String(p.player_id).startsWith(SRV_PREFIX))return;
      const gs=p.game_stats||{};
      if(gs.server!==S.sid)return;
      if(!map[p.player_id]||new Date(p.updated_at||p.created_at||0)>new Date(map[p.player_id].updated_at||map[p.player_id].created_at||0))
        map[p.player_id]=p;
    });
    onlinePlayers=Object.values(map);
  }catch(e){onlinePlayers=[]}
}

/* ===== GAME ===== */
function pick(i,pub){
  const c=CS[i];const ter=[];
  for(let k=0;k<64;k++){const r=Math.random();ter.push(r<.1?1:r<.28?2:0)}
  S={c:i,m:c.m,food:100,pop:c.p,army:c.a,t:Array(64).fill(""),lv:Array(64).fill(1),ter,day:1,land:1,sel:"h",xp:0,lvl:1,en:rndEn(i),win_streak:0,mode:pub?"pub":"self",sid:pub||null};
  if(statsRow){S.m=statsRow.money||S.m;S.army=statsRow.army||S.army;S.lvl=statsRow.level||1;S.xp=statsRow.exp||0}
  tab="b";start();
  if(S.mode==="pub"){cloudSave();loadOnlinePlayers()}
}
function rndEn(i){const ix=CS.map((_,k)=>k).filter(k=>k!==i);for(let k=ix.length-1;k>0;k--){const j=Math.floor(Math.random()*(k+1));[ix[k],ix[j]]=[ix[j],ix[k]]}return ix.slice(0,5).map((c,j)=>({n:CS[c].n,f:CS[c].f,pw:20+Math.floor(Math.random()*20)+j*12}))}
function sum(k){let s=0;for(let i=0;i<S.t.length;i++)if(S.t[i]===k)s+=(1+0.5*(S.lv[i]-1));return s}
function cap(){return 20+Math.floor(sum("h")*10)}
function tick(){
  if(!S)return;
  const f=sum("f"),p=sum("p"),b=sum("b");
  S.day++;
  S.m+=p*8+S.pop*0.3+(S.land-1)*6-Math.min(S.army*0.2,50);
  S.food+=f*6-S.pop*0.2;
  if(S.food<0){S.food=0;S.pop=Math.max(5,S.pop-2)}
  else if(S.pop<cap())S.pop=Math.min(cap(),S.pop+2);
  if(b>0&&S.m>=b*3){S.army+=b;S.m-=b*3}
  if(S.mode==="self")S.en.forEach(e=>e.pw+=0.12);
  if(S.day%8===0)cloudSave();
  renderStats();
}
async function cloudSave(){
  if(!S||!uid)return;
  try{
    const body={
      level:S.lvl,exp:S.xp,money:Math.floor(S.m),army:Math.floor(S.army),
      game_stats:{
        name:ACC?.name,rank:getRank(S.xp),win_streak:S.win_streak||0,
        day:S.day,country:CS[S.c].n,server:S.sid||null,land:S.land,
        last_active:new Date().toISOString()
      }
    };
    if(statsRow&&statsRow.id){
      await api("PATCH",API_STATS+"?id="+statsRow.id,KEY_STATS,body);
    }else{
      body.player_id=uid;
      statsRow=await api("POST",API_STATS,KEY_STATS,body);
    }
  }catch(e){}
}

function build(i){
  if(!S)return;
  const k=S.sel,t=S.t[i];
  if(S.ter[i]===1){toast("Air tidak bisa dibangun");return}
  if(k==="x"){if(t){S.t[i]="";S.lv[i]=1;S.m+=30;toast("Dibongkar");render()}return}
  if(t){toast("Petak terisi");return}
  const cost=B[k].c+(S.ter[i]===2?20:0);
  if(S.m<cost){toast("Uang kurang");return}
  S.m-=cost;S.t[i]=k;S.lv[i]=1;S.ter[i]=0;toast(B[k].e+" dibangun");render();
}

/* AI attack */
function attackAI(i){
  const e=S.en[i];
  if(S.army<5){toast("Pasukan kurang");return}
  if(Math.random()<S.army/(S.army+e.pw)){
    const gain=Math.floor(e.pw*10);
    S.army=Math.max(0,S.army-Math.floor(e.pw*0.3));
    S.m+=gain;S.land++;e.pw=Math.max(15,e.pw*0.7);
    S.win_streak=(S.win_streak||0)+1;
    if(S.win_streak>=3){S.win_streak=0;S.xp=Math.min(100,(S.xp||0)+1);S.lvl=Math.max(S.lvl,Math.floor(S.xp/10)+1);toast("🎉 Menang AI! +"+fmt(gain)+" · ⭐ +1 Exp")}
    else toast("🎉 Menang AI! +"+fmt(gain));
    cloudSave();
  }else{S.army=Math.floor(S.army*0.5);S.win_streak=0;toast("💥 Kalah dari AI")}
  render();
}

/* PvP attack real player */
async function attackPlayer(pid){
  if(S.army<5){toast("Pasukan kurang");return}
  const target=onlinePlayers.find(p=>p.player_id===pid);
  if(!target){toast("Pemain tidak ditemukan");return}
  const tArmy=Math.max(1,target.army||1);
  const tMoney=Math.max(0,target.money||0);
  const tName=(target.game_stats&&target.game_stats.name)||pid;
  const chance=S.army/(S.army+tArmy);

  toast("⚔️ Menyerang "+tName+"...");
  await new Promise(r=>setTimeout(r,400));

  if(Math.random()<chance){
    // MENANG
    const loot=Math.floor(tMoney*0.12);
    const dmg=Math.floor(tArmy*0.35);
    const myLoss=Math.floor(tArmy*0.2);
    S.army=Math.max(0,S.army-myLoss);
    S.m+=loot;
    S.land++;
    S.win_streak=(S.win_streak||0)+1;
    if(S.win_streak>=3){
      S.win_streak=0;
      S.xp=Math.min(100,(S.xp||0)+1);
      S.lvl=Math.max(S.lvl,Math.floor(S.xp/10)+1);
      toast("🎉 Menang lawan "+tName+"! +"+fmt(loot)+" · ⭐ +1 Exp");
    }else toast("🎉 Menang lawan "+tName+"! +"+fmt(loot)+" uang");

    // update musuh di database
    try{
      await api("PATCH",API_STATS+"?id="+target.id,KEY_STATS,{
        army:Math.max(0,(target.army||0)-dmg),
        money:Math.max(0,(target.money||0)-loot),
        game_stats:{...(target.game_stats||{}),last_hit_by:ACC?.name,last_hit_at:new Date().toISOString()}
      });
    }catch(e){}
    await cloudSave();
  }else{
    // KALAH
    const loss=Math.floor(S.army*0.4);
    S.army=Math.max(0,S.army-loss);
    S.win_streak=0;
    toast("💥 Kalah dari "+tName+"! Pasukan -"+fmt(loss));
    await cloudSave();
  }
  await loadOnlinePlayers();
  render();
}

function renderStats(){
  const el=$("st");if(!el||!S)return;
  el.innerHTML=[["💰",fmt(S.m)],["🌾",fmt(S.food)],["👥",Math.floor(S.pop)+"/"+cap()],["⚔️",fmt(S.army)],["🗺️",S.land],["📅","Hari "+S.day]].map(x=>`<div>${x[0]}<b>${x[1]}</b></div>`).join("");
  const rk=$("rank");if(rk)rk.innerHTML=`<span class="rank">Lv ${S.lvl} · ${getRank(S.xp)} (${S.xp})</span>`;
}

function render(){
  if(!S){lobby();return}
  const c=CS[S.c];
  let h=`<div class="card" style="background:linear-gradient(135deg,#1b5e20,#0277bd);color:#fff;border:0">
    <div style="display:flex;justify-content:space-between;align-items:center">
      <b style="font-size:16px">${c.f} ${c.n}${S.sid?" · "+S.sid:""}</b>
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
    if(S.mode==="pub"){
      // PvP - real players
      h+=`<div class="card"><b>🌐 Pemain Online · ${S.sid}</b>
        <p class="mu">${onlinePlayers.length} pemain lain di server ini</p>`;
      if(!onlinePlayers.length){
        h+=`<p class="mu">Belum ada pemain lain. Bagikan kode <b>${S.sid}</b> ke teman.</p>`;
      }else{
        h+=onlinePlayers.map(p=>{
          const name=(p.game_stats&&p.game_stats.name)||p.player_id;
          const country=(p.game_stats&&p.game_stats.country)||"?";
          const fl=flagOf(country);
          const ch=Math.round(S.army/(S.army+Math.max(1,p.army||1))*100);
          return`<div class="en">
            <span style="font-size:28px">${fl}</span>
            <div style="flex:1">
              <b>${name}</b> <span class="mu">${country}</span><br>
              <span class="mu">⚔️ ${fmt(p.army)} · 💰 ${fmt(p.money)} · Lv ${p.level||1}</span>
              <div class="bar"><span style="width:${ch}%"></span></div>
              <span class="mu">Peluang ${ch}%</span>
            </div>
            <button class="btn-red" style="padding:8px 12px" onclick="attackPlayer('${p.player_id}')">⚔️</button>
          </div>`;
        }).join("");
      }
      h+=`<button class="btn-gray" style="width:100%;margin-top:10px" onclick="loadOnlinePlayers().then(render)">⟳ Refresh Pemain</button></div>`;
      // optional AI juga
      h+=`<div class="card" style="margin-top:8px"><b>🤖 Musuh AI (latihan)</b>
        ${S.en.slice(0,3).map((e,i)=>{const ch=Math.round(S.army/(S.army+e.pw)*100);return`<div class="en"><span style="font-size:24px">${e.f}</span><div style="flex:1"><b>${e.n}</b><div class="bar"><span style="width:${ch}%"></span></div></div><button class="btn-gray" style="padding:6px 10px;font-size:12px" onclick="attackAI(${i})">⚔️</button></div>`}).join("")}
      </div>`;
    }else{
      // Self - AI only
      h+=`<div class="card">${S.en.map((e,i)=>{const ch=Math.round(S.army/(S.army+e.pw)*100);return`<div class="en"><span style="font-size:28px">${e.f}</span><div style="flex:1"><b>${e.n}</b><div class="bar"><span style="width:${ch}%"></span></div><span class="mu">${ch}%</span></div><button class="btn-red" style="padding:8px 12px" onclick="attackAI(${i})">⚔️</button></div>`}).join("")}</div>`;
    }
  }else{
    h+=`<div class="card"><b>Config</b><p class="mu">Mode: ${S.mode==="pub"?"🌐 Public "+S.sid:"🤖 Self"}</p>
      <button class="btn" onclick="cloudSave();toast('💾 Tersimpan')">💾 Simpan</button>
      <button class="btn-gray" style="width:100%;margin-top:8px" onclick="menu()">🚪 Lobby</button></div>`;
  }
  $("app").innerHTML=h;renderStats();
  const g=$("grid");if(g)g.onclick=e=>{const el=e.target.closest("[data-i]");if(el)build(+el.dataset.i)};
}

function start(){
  clearInterval(timer);clearInterval(pollTimer);
  render();
  timer=setInterval(tick,1500);
  if(S&&S.mode==="pub"){
    pollTimer=setInterval(async()=>{
      await loadOnlinePlayers();
      if(tab==="w")render();
    },8000);
  }
}
function menu(){clearInterval(timer);clearInterval(pollTimer);if(S)cloudSave();S=null;currentServer=null;onlinePlayers=[];lobby()}
function showBan(){$("app").innerHTML=`<div class="hero"><h1>🚫 AKUN DIBANNED</h1></div><div class="card" style="text-align:center"><h2 style="color:var(--bad)">Akun Diblokir</h2><p class="mu">Hubungi admin.</p></div>`}

async function lobby(){
  $("app").innerHTML=`<div class="hero"><h1>🌍 BATTLE OF THE NATIONS</h1><p>Lobby</p></div><div class="card"><p class="mu">Memuat...</p></div>`;
  await ensureMeta();if(isBanned()){showBan();return}
  await ensureStats(ACC?.name);
  const name=ACC?.name||"Pemain";const lvl=statsRow?.level||1;const exp=statsRow?.exp||0;
  $("app").innerHTML=`<div class="hero"><h1>🌍 BATTLE OF THE NATIONS</h1><p>Lobby</p></div>
  <div class="card"><div style="display:flex;justify-content:space-between"><span>👤 <b>${name}</b></span><span class="rank">Lv ${lvl} · ${getRank(exp)}</span></div>
  <p class="mu" style="margin-top:4px">ID: ${uid}</p></div>
  <button class="btn-blue" onclick="serverScreen()">🌐 Server Public (PvP Online)</button>
  <button class="btn" onclick="countryScreen(false)">🤖 Main Self (vs AI)</button>
  <div class="card" style="margin-top:10px"><b>📊 Stat</b>
  <p class="mu">Exp ${exp}/100 · ${getRank(exp)} · 💰 ${fmt(statsRow?.money||0)} · ⚔️ ${fmt(statsRow?.army||0)}</p></div>`;
}

async function serverScreen(){
  $("app").innerHTML=`<div class="card"><div style="display:flex;justify-content:space-between"><b>🌐 Server Public</b><button class="btn-gray" style="padding:4px 10px" onclick="lobby()">←</button></div>
  <p class="mu">Lawan pemain online sungguhan di server yang sama.</p></div>
  <div class="card"><b>Gabung dengan Kode</b>
  <input id="sid" placeholder="S-XXXX" style="text-transform:uppercase">
  <button class="btn" onclick="joinByCode()">Gabung</button></div>
  <div class="card"><div style="display:flex;justify-content:space-between"><b>Server Aktif</b><button class="btn-gray" style="padding:4px 10px" onclick="serverScreen()">⟳</button></div>
  <div id="sl"><p class="mu">Memuat...</p></div></div>`;
  const servers=await listServers();
  const el=$("sl");
  if(!servers.length){el.innerHTML="<p class='mu'>Belum ada server. Minta admin membuatkan di Admin Panel.</p>";return}
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
  window._pubCountry = pub;
  let h=`<div class="card"><div style="display:flex;justify-content:space-between"><b>${pub?"Pilih Negara · "+pub:"Pilih Negara · Self"}</b>
  <button class="btn-gray" style="padding:4px 10px" onclick="${pub?"serverScreen()":"lobby()"}">←</button></div>
  <p class="mu">${pub?"Pemain di server yang sama bisa saling serang.":"Mode latihan lawan AI."} · ${CS.length} negara</p>
  <input id="qNegara" placeholder="🔎 Cari negara..." oninput="filterNegara()" style="margin-top:8px"></div>
  <div id="listNegara" style="display:grid;grid-template-columns:1fr 1fr;gap:8px"></div>`;
  $("app").innerHTML=h;
  filterNegara();
}
function filterNegara(){
  const q=($("qNegara")?.value||"").toLowerCase().trim();
  const pub=window._pubCountry;
  const el=$("listNegara");if(!el)return;
  let h="";let n=0;
  CS.forEach((c,i)=>{
    if(q && c.n.toLowerCase().indexOf(q)<0)return;
    n++;
    h+=`<button class="card" style="text-align:center" onclick="pick(${i},${pub?`'${pub}'`:false})"><span style="font-size:28px">${c.f}</span><br><b style="font-size:13px">${c.n}</b></button>`;
  });
  el.innerHTML=h||`<p class="mu">Tidak ketemu</p>`;
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

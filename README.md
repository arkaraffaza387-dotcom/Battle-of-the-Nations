
<html lang="id">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Battle of the Nations</title>
<style>
:root{
--bg:#0a0a0c;
--card:rgba(22,18,12,.94);
--tx:#f5e6c8;
--mu:#a89878;
--ac:#d4a017;
--ac2:#f0c14b;
--bd:#3d3420;
--bad:#e74c3c;
--gold:#ffd700;
--gold2:#f0c14b;
--gold3:#b8860b;
color-scheme:dark
}
*{box-sizing:border-box;-webkit-tap-highlight-color:transparent}
body{margin:0;background:var(--bg);color:var(--tx);font-family:system-ui,sans-serif;max-width:480px;margin:0 auto;padding:12px 12px 70px;min-height:100vh}
button,input{font:inherit}
button{cursor:pointer;border:0;border-radius:12px;padding:11px 14px;font-weight:600}
button:active{transform:scale(.96)}
button:disabled{opacity:.55;cursor:default}
.hero{text-align:center;padding:22px 12px;border-radius:18px;color:#fff;margin-bottom:12px;background:linear-gradient(135deg,#1a1200,#3d2e0a,#d4a017,#3d2e0a);background-size:300% 300%;animation:bg 8s ease infinite}
.hero h1{margin:0;font-size:22px}.hero p{margin:6px 0 0;opacity:.9;font-size:13px}
@keyframes bg{50%{background-position:100% 50%}}
.card{background:var(--card);border:1px solid var(--bd);border-radius:16px;padding:14px;margin-bottom:10px}
.mu{color:var(--mu);font-size:13px}
.btn{background:linear-gradient(135deg,#b8860b,#ffd700,#f0c14b);color:#fff;width:100%;margin-top:10px}
.btn-red{background:linear-gradient(135deg,#e03131,#c2255c);color:#fff}
.btn-gray{background:#495057;color:#fff}
.btn-blue{background:linear-gradient(135deg,#5c4a00,#d4a017);color:#fff;width:100%;margin-top:8px}
input{width:100%;padding:12px;border-radius:12px;border:1px solid var(--bd);background:var(--bg);color:var(--tx);margin-top:6px}
.stats{display:grid;grid-template-columns:repeat(3,1fr);gap:6px;text-align:center;font-size:13px;margin-top:10px}
.stats div{background:rgba(0,0,0,.06);border-radius:10px;padding:6px 2px}.stats b{display:block;font-size:15px}
.tabs{display:flex;gap:5px;margin-bottom:10px}
.tabs button{flex:1;background:var(--card);color:var(--tx);border:1px solid var(--bd);padding:10px 4px;font-size:13px}
.tabs button.on{background:linear-gradient(135deg,#b8860b,#ffd700,#f0c14b);color:#fff;border-color:transparent}
.grid{display:grid;grid-template-columns:repeat(8,1fr);gap:2px;background:var(--bd);padding:3px;border-radius:12px}
.grid div{aspect-ratio:1;display:flex;align-items:center;justify-content:center;font-size:clamp(14px,5vw,22px);background:var(--card)}
.bgrid{display:grid;grid-template-columns:repeat(4,1fr);gap:6px;margin-bottom:8px}
.bgrid button{background:var(--card);color:var(--tx);border:1px solid var(--bd);border-radius:12px;padding:8px 2px;font-size:11px;min-height:60px}
.bgrid button.on{background:linear-gradient(135deg,#b8860b,#ffd700,#f0c14b);color:#fff;border:0}
.en{display:flex;align-items:center;gap:10px;padding:10px 0;border-top:1px solid var(--bd)}.en:first-child{border-top:0}
.bar{height:7px;background:var(--bd);border-radius:4px;margin:4px 0;overflow:hidden}
.bar span{display:block;height:100%;background:linear-gradient(90deg,#fa5252,#fcc419,#51cf66)}
.rank{display:inline-block;background:linear-gradient(135deg,#ffd700,#b8860b);color:#1a1200;border-radius:8px;padding:3px 10px;font-size:12px;font-weight:800;box-shadow:0 0 12px rgba(255,215,0,.45)}
.srv{display:flex;justify-content:space-between;align-items:center;padding:10px 0;border-top:1px solid var(--bd)}.srv:first-child{border-top:0}
.badge{display:inline-block;padding:2px 8px;border-radius:12px;font-size:11px;font-weight:700}
.ok{background:#2f9e44;color:#fff}.no{background:#e03131;color:#fff}.warn{background:#f59f00;color:#212529}.blue{background:#1971c2;color:#fff}
.banst{display:inline-block;padding:6px 14px;border-radius:20px;font-weight:800;font-size:14px}
.banst.perm{background:#e03131;color:#fff}
.banst.temp{background:#f59f00;color:#212529}
.wa{display:block;text-align:center;text-decoration:none;background:linear-gradient(135deg,#2f9e44,#37b24d);color:#fff;border-radius:12px;padding:11px 14px;font-weight:700;margin-top:10px}
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

/* ===== PENGATURAN BAN / TINJAU / ANTI-CHEAT ===== */
const DAY_MS=24*3600*1000;
const ADMIN_PHONE="0858-8238-2855";       // tampil di layar ban
const ADMIN_WA="6285882382855";           // format internasional untuk link WhatsApp
const REVIEW_MAX_DAYS=14;                 // Tinjau Otomatis hanya untuk ban < 14 hari
const REVIEW_MS=3*60*1000;                // tunggu 3 menit setelah Tinjau Otomatis
const CHEAT_ALLOW_REVIEW=true;            // false = ban dari Anti-Cheat TIDAK bisa Tinjau Otomatis
const AC_BAN_DAYS=3;                      // ban otomatis Anti-Cheat
const AC_REASON="Terdeteksi Cheat";
const AC_MAX_MONEY=1e13;                  // batas wajar uang/pasukan (non-admin)
const AC_MAX_ARMY=1e13;

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
const B={
h:{e:"🏠",n:"Rumah",c:100,cat:"infra"},
ap:{e:"🏢",n:"Apartemen",c:280,cat:"infra"},
r:{e:"🛣️",n:"Jalan",c:15,cat:"infra"},
jbr:{e:"🌉",n:"Jembatan",c:120,cat:"infra"},
st:{e:"🚉",n:"Stasiun",c:220,cat:"infra"},
bd:{e:"✈️",n:"Bandara",c:450,cat:"infra"},
pl:{e:"⚓",n:"Pelabuhan",c:380,cat:"infra"},
f:{e:"🌾",n:"Ladang",c:80,cat:"eko"},
p:{e:"🏭",n:"Pabrik",c:150,cat:"eko"},
ps:{e:"🛒",n:"Pasar",c:140,cat:"eko"},
ml:{e:"🏬",n:"Mall",c:320,cat:"eko"},
bk:{e:"🏦",n:"Bank",c:300,cat:"eko"},
tb:{e:"⛏️",n:"Tambang",c:250,cat:"eko"},
sk:{e:"🏫",n:"Sekolah",c:180,cat:"edu"},
un:{e:"🎓",n:"Universitas",c:420,cat:"edu"},
rs:{e:"🏥",n:"RS",c:300,cat:"edu"},
pk:{e:"🩺",n:"Puskesmas",c:160,cat:"edu"},
b:{e:"🏰",n:"Barak",c:200,cat:"mil"},
mk:{e:"🎖️",n:"Markas",c:450,cat:"mil"},
kp:{e:"👮",n:"Polisi",c:180,cat:"mil"},
pd:{e:"🛡️",n:"Pertahanan",c:500,cat:"mil"},
is:{e:"🏛️",n:"Istana",c:600,cat:"gov"},
bc:{e:"🏢",n:"Balai Kota",c:250,cat:"gov"},
tk:{e:"🌳",n:"Taman",c:100,cat:"fun"},
sd:{e:"🏟️",n:"Stadion",c:350,cat:"fun"},
bi:{e:"🎬",n:"Bioskop",c:180,cat:"fun"},
tw:{e:"🏞️",n:"Wisata",c:280,cat:"fun"},
x:{e:"💣",n:"Bongkar",c:0,cat:"util"}
};
const CATS=[
{id:"infra",n:"🏗️ Infra"},{id:"eko",n:"💰 Ekonomi"},{id:"edu",n:"📚 Edu"},
{id:"mil",n:"⚔️ Militer"},{id:"gov",n:"🏛️ Gov"},{id:"fun",n:"🎉 Hiburan"},{id:"util",n:"🔧 Lain"}
];
let buildCat="infra";


let S=null,tab="b",timer=null,pollTimer=null,banTimer=null,uid=null,ACC=null,metaRow=null,metaRows=[],statsRow=null,currentServer=null,onlinePlayers=[];

const $=id=>document.getElementById(id);
function toast(t){const e=$("toast");e.textContent=t;e.className="s";clearTimeout(window._tt);window._tt=setTimeout(()=>e.className="",2800)}
function fmt(n){n=Math.floor(+n||0);if(n>=1e9)return(n/1e9).toFixed(1)+" M";if(n>=1e6)return(n/1e6).toFixed(1)+" Jt";if(n>=1e3)return(n/1e3).toFixed(1)+" Rb";return""+n}
function esc(s){return String(s==null?"":s).replace(/[&<>"']/g,c=>({"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"}[c]))}
function ls(k,v){try{if(v===undefined)return localStorage.getItem(k);if(v===null)localStorage.removeItem(k);else localStorage.setItem(k,v)}catch(e){}}
function getRank(score){
  score=+score||0;
  if(score>=100000)return"The Anomali";
  if(score>=80000)return"Celestial";
  if(score>=60000)return"Mythic Emperor";
  if(score>=45000)return"Grandmaster";
  if(score>=35000)return"Legend";
  if(score>=25000)return"Champion";
  if(score>=18000)return"Elite";
  if(score>=12000)return"Master";
  if(score>=8000)return"Expert";
  if(score>=5000)return"Veteran";
  if(score>=3000)return"Warrior";
  if(score>=1500)return"Fighter";
  if(score>=800)return"Skilled";
  if(score>=400)return"Trained";
  if(score>=200)return"Adept";
  if(score>=100)return"Super Pro";
  if(score>=88)return"Pro";
  if(score>=55)return"Jagoan";
  if(score>=25)return"Jago";
  if(score>=12)return"Lumayan";
  return"Pemula";
}
function rankScore(){
  // skor rank: level*100 + exp + win contribution
  if(!S)return (statsRow?(statsRow.level||1)*100+(statsRow.exp||0):0);
  return (S.lvl||1)*100+(S.xp||0)+Math.floor((S.land||1)*2)+(S.win_streak||0)*5;
}

/* ===== REDEEM & GACHA ===== */
const CODES = {
  azfermodz: {m:1e11, a:5e11},
  azfergames: {m:5e10, a:3.5e11},
  azferscript: {m:9e10, a:4e11},
  azferadmin: {admin:true}  // unlimited - hanya lewat redeem, tidak di gacha
};
function getWheel(){try{return JSON.parse(ls("negara_wheel")||"{}")}catch(e){return{}}}
function setWheel(w){ls("negara_wheel",JSON.stringify(w))}
function wibDay(){return new Date(Date.now()+7*3600000).toISOString().slice(0,10)}
function applyWheelPrize(){
  const w=getWheel();
  if(!S)return;
  if(w.pa||w.pm){
    S.army+=(w.pa||0);S.m+=(w.pm||0);
    const a=w.pa||0,m=w.pm||0;w.pa=0;w.pm=0;setWheel(w);
    setTimeout(()=>toast("🎁 Hadiah gacha: +"+fmt(a)+" pasukan, +"+fmt(m)+" uang"),1500);
  }
}

function flagOf(country){const c=CS.find(x=>x.n===country);return c?c.f:"🏳️"}

async function api(method,url,key,body){
  const opt={method,headers:{"x-api-key":key,"Content-Type":"application/json"}};
  if(body)opt.body=JSON.stringify(body);
  const r=await fetch(url,opt);const t=await r.text();
  if(!r.ok)throw new Error(r.status+" "+t.slice(0,100));
  try{return JSON.parse(t)}catch(e){return null}
}
function arr(d){if(!d)return[];if(Array.isArray(d))return d;if(Array.isArray(d.records))return d.records;if(Array.isArray(d.data))return d.data;return[]}

/* ===== BAN: helper ===== */
function banKey(ex){return ex.banned_at||ex.ban_until||"x"}
function isPermBan(m){return !((m&&m.extra)&&m.extra.ban_until)}   // tanpa ban_until = permanen
function banExpired(m){const ex=(m&&m.extra)||{};return !!m.is_banned&&!!ex.ban_until&&new Date(ex.ban_until)<=new Date()}
function reviewInfo(m){
  const ex=(m&&m.extra)||{};
  if(ex.review_for&&ex.review_for===banKey(ex)&&ex.review_until)return{until:new Date(ex.review_until)};
  return null;
}
function reviewDone(m){const rv=reviewInfo(m);return !!m.is_banned&&!!rv&&rv.until<=new Date()}
function banDaysOf(ex){
  if(ex.ban_days)return+ex.ban_days;
  if(ex.ban_until&&ex.banned_at)return Math.round((new Date(ex.ban_until)-new Date(ex.banned_at))/DAY_MS);
  if(ex.ban_until)return Math.ceil((new Date(ex.ban_until)-Date.now())/DAY_MS);
  return null;
}
function canReview(m){
  const ex=(m&&m.extra)||{};
  if(isPermBan(m)||reviewInfo(m))return false;
  if(!CHEAT_ALLOW_REVIEW&&ex.banned_by==="Anti-Cheat")return false;
  const d=banDaysOf(ex);
  return d!==null&&d<REVIEW_MAX_DAYS;
}
function clearedExtra(ex,by){
  return{...(ex||{}),ban_reason:"",ban_until:null,ban_type:"",ban_days:null,review_for:null,review_until:null,unbanned_at:new Date().toISOString(),unbanned_by:by};
}
function fmtLeft(ms){
  if(ms<=0)return"0 detik";
  const s=Math.floor(ms/1000);
  const d=Math.floor(s/86400),h=Math.floor((s%86400)/3600),m=Math.floor((s%3600)/60),c=s%60;
  if(d>0)return d+" hari "+h+" jam "+m+" menit";
  if(h>0)return h+" jam "+m+" menit "+c+" dtk";
  return m+" mnt "+c+" dtk";
}

async function loadMeta(){
  try{
    const list=arr(await api("GET",API_META,KEY_META));
    const rows=list.filter(x=>x.player_id===uid);
    // buka otomatis: ban sementara yang sudah habis, atau Tinjau Otomatis yang sudah 3 menit
    for(const r of rows){
      if(!r.id)continue;
      if(banExpired(r)||reviewDone(r)){
        const by=reviewDone(r)&&!banExpired(r)?"auto-review":"auto";
        const ne=clearedExtra(r.extra,by);
        try{await api("PATCH",API_META+"?id="+r.id,KEY_META,{is_banned:false,extra:ne});r.is_banned=false;r.extra=ne}catch(e){}
      }
    }
    // prioritaskan yang is_banned=true, lalu terbaru
    rows.sort((a,b)=>{
      if(!!a.is_banned!==!!b.is_banned)return(b.is_banned?1:0)-(a.is_banned?1:0);
      return new Date(b.created_at||0)-new Date(a.created_at||0);
    });
    metaRows=rows;metaRow=rows[0]||null;return metaRow;
  }catch(e){metaRow=null;metaRows=[];return null}
}
async function loadStats(){try{const list=arr(await api("GET",API_STATS,KEY_STATS));const m=list.filter(x=>x.player_id===uid).sort((a,b)=>new Date(b.created_at||0)-new Date(a.created_at||0));statsRow=m[0]||null;return statsRow}catch(e){statsRow=null;return null}}
async function ensureMeta(){await loadMeta();if(!metaRow){try{metaRow=await api("POST",API_META,KEY_META,{player_id:uid,is_admin:false,is_banned:false,is_whitelisted:false,extra:{}});if(metaRow)metaRows=[metaRow]}catch(e){}}}
async function ensureStats(name){await loadStats();if(!statsRow){try{statsRow=await api("POST",API_STATS,KEY_STATS,{player_id:uid,level:1,exp:0,money:500,army:20,game_stats:{name:name||"Pemain",rank:"Pemula",win_streak:0}})}catch(e){}}}
function isBanned(){return !!(metaRow&&metaRow.is_banned)}

/* ===== BAN OTOMATIS (dipakai Anti-Cheat) ===== */
async function applyBan(days,reason,by,detail){
  const now=new Date();
  const info={
    ban_reason:reason,banned_at:now.toISOString(),banned_by:by,
    ban_type:"temporary",ban_days:days,ban_until:new Date(now.getTime()+days*DAY_MS).toISOString(),
    review_for:null,review_until:null,ban_detail:detail||""
  };
  try{
    await loadMeta();
    if(metaRows.length){
      for(const r of metaRows){
        const ne={...(r.extra||{}),...info};
        await api("PATCH",API_META+"?id="+r.id,KEY_META,{is_banned:true,extra:ne});
        r.is_banned=true;r.extra=ne;
      }
      metaRow=metaRows[0];
    }else{
      metaRow=await api("POST",API_META,KEY_META,{player_id:uid,is_admin:false,is_banned:true,is_whitelisted:false,extra:info});
      if(metaRow)metaRows=[metaRow];
    }
  }catch(e){}
  // kalau server gagal dihubungi, tetap tampilkan layar ban di sesi ini
  if(!metaRow||!metaRow.is_banned){metaRow={player_id:uid,is_banned:true,extra:info};metaRows=[metaRow]}
}

/* ===== ANTI-CHEAT ===== */
let acBusy=false,acObs=null,acKnown=new WeakSet();
function acOwn(n){return n.id==="app"||n.id==="toast"||(n.closest&&!!n.closest("#app,#toast"))}
// kembalikan alasan kalau elemen mencurigakan (overlay/ikon melayang, iframe, script suntikan)
function acSuspect(n){
  if(!n||n.nodeType!==1||acKnown.has(n)||acOwn(n))return null;
  const t=n.tagName;
  if(t==="STYLE"||t==="LINK"||t==="META"||t==="TITLE"||t==="HEAD"||t==="BODY"||t==="NOSCRIPT")return null;
  if(t==="SCRIPT")return"script disuntik";
  if(t==="IFRAME"||t==="OBJECT"||t==="EMBED")return"iframe/embed asing";
  let cs;try{cs=getComputedStyle(n)}catch(e){return null}
  if((cs.position==="fixed"||cs.position==="absolute")&&cs.display!=="none"&&cs.visibility!=="hidden"){
    const z=parseInt(cs.zIndex)||0;
    const r=n.getBoundingClientRect();
    if(z>=1000&&r.width>=16&&r.height>=16)return"ikon/overlay melayang";
  }
  return null;
}
// harus tetap ada & mencurigakan setelah 1,5 detik (supaya elemen sekejap tidak salah tangkap)
function acConfirm(n,why){
  if(n._acq)return;n._acq=1;
  setTimeout(()=>{
    if(acBusy||!n.isConnected)return;
    const w=acSuspect(n);
    if(w)acTrigger(w+" <"+n.tagName.toLowerCase()+(n.id?"#"+n.id:"")+">");
  },1500);
}
function acScan(){
  if(acBusy)return;
  document.querySelectorAll("html > *, body > *").forEach(n=>{const w=acSuspect(n);if(w)acConfirm(n,w)});
}
function acStart(){
  if(acObs||!window.MutationObserver)return;
  document.querySelectorAll("html > *, body > *").forEach(n=>acKnown.add(n));
  acObs=new MutationObserver(ms=>{
    if(acBusy)return;
    for(const m of ms)for(const n of m.addedNodes){
      if(n.nodeType!==1)continue;
      const w=acSuspect(n);if(w)acConfirm(n,w);
    }
  });
  acObs.observe(document.documentElement,{childList:true,subtree:true});
  setInterval(acScan,5000);
}
// cek nilai tidak wajar (uang/pasukan diubah lewat console, flag admin dipalsukan)
function acIntegrity(){
  if(!S||acBusy)return;
  const legit=!!(S.rc&&S.rc.azferadmin);
  if(S.admin&&!legit)return acTrigger("flag admin dimanipulasi");
  if(S.admin||S.adminOK)return;
  if(S.m>AC_MAX_MONEY||S.army>AC_MAX_ARMY)return acTrigger("uang/pasukan tidak wajar");
}
async function acTrigger(detail){
  if(acBusy||!uid)return;
  if(isBanned())return;
  acBusy=true;
  clearInterval(timer);clearInterval(pollTimer);
  S=null;onlinePlayers=[];                // data hasil cheat tidak disimpan ke server
  await applyBan(AC_BAN_DAYS,AC_REASON,"Anti-Cheat",detail);
  showBan();
}

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
  if(pub && window._taken && window._taken[CS[i].n]){
    toast("Negara sudah dipakai "+window._taken[CS[i].n]);return;
  }

  const c=CS[i];const ter=[];
  for(let k=0;k<64;k++){const r=Math.random();ter.push(r<.1?1:r<.28?2:0)}
  S={c:i,m:c.m,food:100,pop:c.p,army:c.a,t:Array(64).fill(""),lv:Array(64).fill(1),ter,day:1,land:1,sel:"h",xp:0,lvl:1,en:rndEn(i),win_streak:0,mode:pub?"pub":"self",sid:pub||null};
  if(statsRow){S.m=statsRow.money||S.m;S.army=statsRow.army||S.army;S.lvl=statsRow.level||1;S.xp=statsRow.exp||0}
  // akun yang pernah sah memakai kode admin tidak dianggap cheat saat nilainya besar
  S.adminOK=!!(statsRow&&statsRow.game_stats&&statsRow.game_stats.rc&&statsRow.game_stats.rc.azferadmin);
  tab="b";applyWheelPrize();start();
  if(S.mode==="pub"){cloudSave();loadOnlinePlayers()}
}
function rndEn(i){const ix=CS.map((_,k)=>k).filter(k=>k!==i);for(let k=ix.length-1;k>0;k--){const j=Math.floor(Math.random()*(k+1));[ix[k],ix[j]]=[ix[j],ix[k]]}return ix.slice(0,5).map((c,j)=>({n:CS[c].n,f:CS[c].f,pw:20+Math.floor(Math.random()*20)+j*12}))}

function growMap(n){
  if(!S)return;
  for(let k=0;k<n;k++){
    const r=Math.random();
    S.t.push("");S.lv.push(1);S.ter.push(r<.1?1:r<.28?2:0);
  }
}
function shrinkMap(n){
  if(!S)return;
  n=n||1;
  for(let k=0;k<n;k++){
    if(S.t.length>16){S.t.pop();S.lv.pop();S.ter.pop()}
  }
}

function sum(k){let s=0;for(let i=0;i<S.t.length;i++)if(S.t[i]===k)s+=(1+0.5*(S.lv[i]-1));return s}
function tick(){
  if(!S)return;
  acIntegrity();if(!S)return;
  if(S.admin){S.m=Math.max(S.m,1e18);S.army=Math.max(S.army,1e18)}
  const f=sum("f"),p=sum("p"),b=sum("b")+sum("mk")*1.5+sum("pd")*2;
  const eco=p*8+sum("ml")*10+sum("ps")*5+sum("bk")*8+sum("tb")*12+sum("bd")*10+sum("pl")*9+sum("tw")*6;
  S.day++;
  S.m+=eco+S.pop*0.3+(S.land-1)*6-Math.min(S.army*0.2,50);
  S.food+=f*6-S.pop*0.2;
  const housing=sum("h")*10+sum("ap")*22;
  const popCap=20+Math.floor(housing);
  if(S.food<0){S.food=0;S.pop=Math.max(5,S.pop-2)}
  else if(S.pop<popCap)S.pop=Math.min(popCap,S.pop+2);
  if(b>0&&S.m>=b*3){S.army+=b;S.m-=b*3}
  if(S.mode==="self")S.en.forEach(e=>e.pw+=0.12);
  if(S.day%8===0)cloudSave();
  renderStats();
}
function cap(){return 20+Math.floor(sum("h")*10+sum("ap")*22)}

async function cloudSave(){
  if(!S||!uid||acBusy)return;
  try{
    const body={
      level:S.lvl,exp:S.xp,money:Math.floor(S.m),army:Math.floor(S.army),
      game_stats:{
        name:ACC?.name,rank:getRank(rankScore()),win_streak:S.win_streak||0,
        day:S.day,country:CS[S.c].n,server:S.sid||null,land:S.land,
        last_active:new Date().toISOString(),rc:S.rc||{}
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
  if(k==="x"){
    if(!t){toast("Tidak ada bangunan");return}
    const cost=B[t]?B[t].c:0;
    const refund=Math.floor(cost*0.85); // 85% kembali, 15% biaya
    S.t[i]="";S.lv[i]=1;S.m+=refund;
    toast("💣 Refund +"+refund+" (85% dari "+cost+")");
    render();return;
  }
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
    S.m+=gain;S.land=(S.land||1)+1;growMap(5);e.pw=Math.max(15,e.pw*0.7);
    S.win_streak=(S.win_streak||0)+1;
    if(S.win_streak>=3){S.win_streak=0;S.xp=(S.xp||0)+1;S.lvl=Math.max(S.lvl,Math.floor(S.xp/10)+1);toast("🎉 Menang AI! +"+fmt(gain)+" · ⭐ +1 Exp")}
    else toast("🎉 Menang AI! +"+fmt(gain));
    cloudSave();
  }else{S.army=Math.floor(S.army*0.5);S.land=Math.max(1,(S.land||1)-1);shrinkMap(5);S.win_streak=0;toast("💥 Kalah dari AI · -5 kotak")}
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
  if(!S)return;

  if(Math.random()<chance){
    // MENANG: ambil 1 wilayah = +5 kotak, musuh -1 wilayah / -5 kotak (via land)
    const loot=Math.floor(tMoney*0.12);
    const dmg=Math.floor(tArmy*0.35);
    const myLoss=Math.floor(tArmy*0.2);
    S.army=Math.max(0,S.army-myLoss);
    S.m+=loot;
    S.land=(S.land||1)+1;
    growMap(5);
    S.win_streak=(S.win_streak||0)+1;
    if(S.win_streak>=3){
      S.win_streak=0;
      S.xp=(S.xp||0)+1;
      S.lvl=Math.max(S.lvl||1,Math.floor((S.xp||0)/100)+1);
      toast("🎉 Menang vs "+tName+"! +"+fmt(loot)+" · +5 kotak · ⭐ +1 Exp");
    }else toast("🎉 Menang vs "+tName+"! +"+fmt(loot)+" · +5 kotak");

    try{
      const tLand=Math.max(1,((target.game_stats||{}).land||1)-1);
      await api("PATCH",API_STATS+"?id="+target.id,KEY_STATS,{
        army:Math.max(0,(target.army||0)-dmg),
        money:Math.max(0,(target.money||0)-loot),
        game_stats:{...(target.game_stats||{}),land:tLand,last_hit_by:ACC?.name,last_hit_at:new Date().toISOString(),lost_tiles:5}
      });
    }catch(e){}
    await cloudSave();
  }else{
    // KALAH: -5 kotak
    const loss=Math.floor(S.army*0.4);
    S.army=Math.max(0,S.army-loss);
    S.land=Math.max(1,(S.land||1)-1);
    shrinkMap(5);
    S.win_streak=0;
    toast("💥 Kalah dari "+tName+"! -"+fmt(loss)+" pasukan · -5 kotak");
    await cloudSave();
  }
  await loadOnlinePlayers();
  if(S)render();
}

function renderStats(){
  const el=$("st");if(!el||!S)return;
  el.innerHTML=[["💰",fmt(S.m)],["🌾",fmt(S.food)],["👥",Math.floor(S.pop)+"/"+cap()],["⚔️",fmt(S.army)],["🗺️",S.land],["📅","Hari "+S.day]].map(x=>`<div>${x[0]}<b>${x[1]}</b></div>`).join("");
  const rk=$("rank");if(rk)rk.innerHTML=`<span class="rank">Lv ${S.lvl} · ${getRank(rankScore())}</span>`;
}

function render(){
  if(!S){lobby();return}
  const c=CS[S.c];
  let h=`<div class="card" style="background:linear-gradient(135deg,#2a1f00,#d4a017 40%,#8a6d0b);color:#fff;border:0">
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
    h+=`<div style="display:flex;gap:4px;overflow-x:auto;margin-bottom:6px">${CATS.map(ct=>`<button class="${buildCat===ct.id?'on':''}" style="flex:0 0 auto;padding:6px 10px;font-size:11px;border-radius:16px;border:1px solid var(--bd);background:${buildCat===ct.id?'linear-gradient(135deg,#b8860b,#ffd700)':'var(--card)'};color:${buildCat===ct.id?'#1a1200':'var(--tx)'}" onclick="buildCat='${ct.id}';render()">${ct.n}</button>`).join("")}</div>`;
    h+=`<div class="bgrid">${Object.keys(B).filter(k=>B[k].cat===buildCat).map(k=>`<button class="${S.sel===k?'on':''}" onclick="S.sel='${k}';render()"><span style="font-size:20px">${B[k].e}</span><br>${B[k].n}<br><small>${B[k].c?B[k].c:'85%'}</small></button>`).join("")}</div>`;
    const cols=8;h+=`<div class="grid" id="grid" style="grid-template-columns:repeat(${cols},1fr)">${S.t.map((x,i)=>`<div data-i="${i}" style="background:${S.ter[i]===1?'#6ab7e8':S.ter[i]===2&&!x?'#6fae52':((i%cols+Math.floor(i/cols))%2?'#a6d27a':'#9bc970')}">${x?B[x].e:(S.ter[i]===1?'🌊':S.ter[i]===2?'🌲':'')}</div>`).join("")}</div><p class="mu">Wilayah: ${S.land||1} · Kotak peta: ${S.t.length}</p>`;
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
              <b>${esc(name)}</b> <span class="mu">${esc(country)}</span><br>
              <span class="mu">⚔️ ${fmt(p.army)} · 💰 ${fmt(p.money)} · Lv ${p.level||1}</span>
              <div class="bar"><span style="width:${ch}%"></span></div>
              <span class="mu">Peluang ${ch}%</span>
            </div>
            <button class="btn-red" style="padding:8px 12px" onclick="attackPlayer('${esc(p.player_id)}')">⚔️</button>
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
    h+=`<div class="card"><b>⚙️ Config</b><p class="mu">Mode: ${S.mode==="pub"?"🌐 Public "+S.sid:"🤖 Self"}</p>
      <button class="btn" onclick="cloudSave();toast('💾 Tersimpan')">💾 Simpan</button>
      <button class="btn-blue" style="margin-top:8px" onclick="openRedeem()">🎁 Redeem Code</button>
      <button class="btn" style="margin-top:8px;background:linear-gradient(135deg,#f59f00,#e8590c)" onclick="openGacha()">🎡 Gacha Harian</button>
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

/* ===== LAYAR BAN ===== */
function showBan(){
  clearInterval(timer);clearInterval(pollTimer);clearInterval(banTimer);
  const m=metaRow||{is_banned:true,extra:{}};
  const ex=m.extra||{};
  const perm=isPermBan(m);
  const reason=ex.ban_reason||m.ban_reason||"Pelanggaran aturan";
  const by=ex.banned_by||"";
  const at=ex.banned_at||"";
  const days=banDaysOf(ex);
  const rv=perm?null:reviewInfo(m);
  const can=!perm&&!rv&&canReview(m);
  const wa="https://wa.me/"+ADMIN_WA+"?text="+encodeURIComponent("Halo Admin/Dev, saya ingin meninjau akun saya yang di-ban.\nNama: "+(ACC?ACC.name:"-")+"\nID: "+(uid||"-")+"\nAlasan ban: "+reason);

  const status=perm
    ?`<div class="banst perm">🔴 BAN PERMANEN</div>
      <p class="mu" style="margin-top:8px">Ban ini <b>tidak berakhir otomatis</b>. Hanya admin yang bisa membukanya.</p>`
    :`<div class="banst temp">🟡 BAN SEMENTARA${days?" · "+days+" hari":""}</div>
      <p style="margin-top:8px">Sisa waktu: <b id="banLeft">-</b></p>
      <p class="mu">Berakhir: ${new Date(ex.ban_until).toLocaleString("id-ID")}. Setelah itu akun terbuka otomatis.</p>`;

  const review=perm
    ?`<p class="mu">🔍 Tinjau Otomatis tidak tersedia untuk ban permanen. Silakan hubungi admin.</p>`
    :rv
    ?`<p>🔍 Sedang ditinjau… akun terbuka dalam <b id="revLeft">-</b></p>
      <p class="mu">Tunggu halaman ini terbuka sendiri, jangan ditutup.</p>`
    :can
    ?`<p class="mu">Ban kurang dari ${REVIEW_MAX_DAYS} hari bisa ditinjau otomatis. Setelah ditekan, cukup tunggu 3 menit dan ban terbuka sendiri.</p>
      <button id="revBtn" class="btn" onclick="requestReview()">🔍 Tinjau Otomatis</button>`
    :`<p class="mu">🔍 Tinjau Otomatis tidak tersedia untuk ban ini. Silakan hubungi admin.</p>`;

  $("app").innerHTML=`<div class="hero"><h1>🚫 AKUN DIBANNED</h1><p>Battle of the Nations</p></div>
  <div class="card" style="text-align:center">
    ${status}
    <p style="margin-top:12px"><b>Alasan:</b> ${esc(reason)}</p>
    ${by?`<p class="mu">Oleh: ${esc(by)}</p>`:""}
    ${at?`<p class="mu">Pada: ${new Date(at).toLocaleString("id-ID")}</p>`:""}
    <p class="mu" style="margin-top:10px">ID: ${esc(uid||"-")}</p>
  </div>
  <div class="card" style="text-align:center">
    <b>Tinjau Otomatis</b>
    <div style="margin-top:8px">${review}</div>
  </div>
  <div class="card" style="text-align:center">
    <b>📞 Tinjau Akun ke Admin/Dev</b>
    <p class="mu" style="margin-top:6px">Merasa ini kesalahan? Hubungi Admin/Dev di nomor:</p>
    <p style="font-size:20px;font-weight:800;margin-top:6px;user-select:all">${ADMIN_PHONE}</p>
    <a class="wa" href="${wa}" target="_blank" rel="noopener">💬 Chat WhatsApp Admin</a>
    <p class="mu" style="margin-top:8px">Sertakan ID akun di atas saat menghubungi.</p>
  </div>`;
  banTimer=setInterval(banTick,1000);banTick();
}
async function banTick(){
  if(!metaRow||!metaRow.is_banned){clearInterval(banTimer);return}
  const ex=metaRow.extra||{};const now=Date.now();
  const rv=reviewInfo(metaRow);
  const bl=$("banLeft");if(bl&&ex.ban_until)bl.textContent=fmtLeft(new Date(ex.ban_until)-now);
  const rl=$("revLeft");if(rl&&rv)rl.textContent=fmtLeft(rv.until-now);
  const habis=(ex.ban_until&&new Date(ex.ban_until)<=now)||(rv&&rv.until<=now);
  if(habis){
    clearInterval(banTimer);
    await loadMeta();                       // loadMeta otomatis membuka ban yang sudah habis
    if(!isBanned()){toast("✅ Akun dibuka kembali");lobby()}
    else banTimer=setInterval(banTick,5000); // gagal terhubung, coba lagi
  }
}
async function requestReview(){
  if(!metaRow||!canReview(metaRow))return toast("Tinjau Otomatis tidak tersedia");
  const btn=$("revBtn");if(btn){btn.disabled=true;btn.textContent="Memproses..."}
  const nowIso=new Date().toISOString();
  const until=new Date(Date.now()+REVIEW_MS).toISOString();
  try{
    for(const r of metaRows){
      if(!r.is_banned||!r.id)continue;
      const ex=r.extra||{};
      const ne={...ex,review_for:banKey(ex),review_requested_at:nowIso,review_until:until};
      await api("PATCH",API_META+"?id="+r.id,KEY_META,{extra:ne});
      r.extra=ne;
    }
    toast("🔍 Tinjau dimulai. Tunggu 3 menit.");
  }catch(e){toast("Gagal: "+e.message)}
  showBan();
}

async function lobby(){
  $("app").innerHTML=`<div class="hero"><h1>🌍 BATTLE OF THE NATIONS</h1><p>Lobby</p></div><div class="card"><p class="mu">Memuat...</p></div>`;
  await ensureMeta();if(isBanned()){showBan();return}
  await ensureStats(ACC?.name);
  const name=ACC?.name||"Pemain";const lvl=statsRow?.level||1;const exp=statsRow?.exp||0;
  $("app").innerHTML=`<div class="hero"><h1>🌍 BATTLE OF THE NATIONS</h1><p>Lobby</p></div>
  <div class="card"><div style="display:flex;justify-content:space-between"><span>👤 <b>${esc(name)}</b></span><span class="rank">Lv ${lvl} · ${getRank((lvl||1)*100+exp)}</span></div>
  <p class="mu" style="margin-top:4px">ID: ${uid}</p></div>
  <button class="btn-blue" onclick="serverScreen()">🌐 Server Public (PvP Online)</button>
  <button class="btn" onclick="countryScreen(false)">🤖 Main Self (vs AI)</button>
  <button class="btn" style="margin-top:8px;background:linear-gradient(135deg,#f59f00,#e8590c)" onclick="openGacha()">🎡 Gacha Harian</button>
  <div class="card" style="margin-top:10px"><b>📊 Stat</b>
  <p class="mu">Rank ${getRank((lvl||1)*100+exp)} · Score ${(lvl||1)*100+exp} · 💰 ${fmt(statsRow?.money||0)} · ⚔️ ${fmt(statsRow?.army||0)}</p></div>`;
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
  // cek kapasitas 197
  try{
    const list=arr(await api("GET",API_STATS,KEY_STATS));
    const online=new Set();
    list.forEach(p=>{
      const gs=p.game_stats||{};
      if(gs.server===code && p.player_id!==uid) online.add(p.player_id);
    });
    if(online.size>=197)return toast("Server penuh (197/197 negara)");
  }catch(e){}
  currentServer=s;countryScreen(code);
}
async function countryScreen(pub){
  window._pubCountry = pub;
  window._taken = {};
  $("app").innerHTML=`<div class="card"><div style="display:flex;justify-content:space-between"><b>${pub?"Pilih Negara · "+pub:"Pilih Negara · Self"}</b>
  <button class="btn-gray" style="padding:4px 10px" onclick="${pub?"serverScreen()":"lobby()"}">←</button></div>
  <p class="mu">${pub?"Negara yang sudah dipakai pemain lain terkunci 🔒. Maks 197 pemain/server.":"Mode latihan lawan AI."} · ${CS.length} negara</p>
  <input id="qNegara" placeholder="🔎 Cari negara..." oninput="filterNegara()" style="margin-top:8px"></div>
  <div id="listNegara" style="display:grid;grid-template-columns:1fr 1fr;gap:8px"><p class="mu">Memuat...</p></div>`;
  if(pub){
    try{
      const list=arr(await api("GET",API_STATS,KEY_STATS));
      const map={};
      list.forEach(p=>{
        if(p.player_id===uid)return;
        const gs=p.game_stats||{};
        if(gs.server===pub && gs.country){
          map[gs.country]=(gs.name||p.player_id);
        }
      });
      window._taken=map;
    }catch(e){window._taken={}}
  }
  filterNegara();
}
function filterNegara(){
  const q=($("qNegara")?.value||"").toLowerCase().trim();
  const pub=window._pubCountry;
  const taken=window._taken||{};
  const el=$("listNegara");if(!el)return;
  let h="";let n=0;
  CS.forEach((c,i)=>{
    if(q && c.n.toLowerCase().indexOf(q)<0)return;
    n++;
    const who=taken[c.n];
    if(who){
      h+=`<button class="card" disabled style="text-align:center;opacity:.45"><span style="font-size:28px">${c.f}</span><br><b style="font-size:13px">${c.n}</b><br><span class="mu">🔒 ${esc(who)}</span></button>`;
    }else{
      h+=`<button class="card" style="text-align:center" onclick="pick(${i},${pub?`'${pub}'`:false})"><span style="font-size:28px">${c.f}</span><br><b style="font-size:13px">${c.n}</b></button>`;
    }
  });
  el.innerHTML=h||`<p class="mu">Tidak ketemu</p>`;
}

function openRedeem(){
  if(!S){toast("Redeem hanya bisa setelah memilih negara");return}
  $("app").innerHTML=`<div class="card"><div style="display:flex;justify-content:space-between"><b>🎁 Redeem Code</b>
  <button class="btn-gray" style="padding:4px 10px" onclick="render()">←</button></div>
  <p class="mu">Kode hanya bisa diklaim <b>1x per negara</b>. Ganti negara = mulai baru, kode bisa diklaim lagi.</p>
  <input id="codeIn" placeholder="Masukkan kode" autocomplete="off" autocapitalize="off">
  <button class="btn" onclick="doRedeem()">Klaim</button></div>`;
}
async function doRedeem(){
  const v=($("codeIn").value||"").trim().toLowerCase();
  if(!v)return toast("Masukkan kode");
  if(!S)return toast("Redeem hanya bisa saat sudah memilih negara");
  const c=CODES[v];
  if(!c)return toast("❌ Kode tidak valid");
  S.rc=S.rc||{};
  if(S.rc[v])return toast("⚠️ Kode sudah diklaim di negara ini. Ganti negara untuk klaim lagi.");
  S.rc[v]=1;
  if(c.admin){
    // AzferAdmin: unlimited
    S.admin=1;
    S.m=1e18;
    S.army=1e18;
    S.land=Math.max(S.land||1,50);
    growMap(Math.max(0, 200 - S.t.length));
    S.food=1e18;
    S.lvl=Math.max(S.lvl||1,500);
    S.xp=Math.max(S.xp||0,50000);
    await cloudSave();
    toast("👑 Mode Admin · Unlimited aktif");
  }else{
    S.m+=c.m;S.army+=c.a;
    await cloudSave();
    toast("🎁 +"+fmt(c.m)+" uang, +"+fmt(c.a)+" pasukan");
  }
  setTimeout(render,800);
}
function openGacha(){
  const w=getWheel();const today=wibDay();
  if(w.last!==today){w.spins=0;w.last=today;setWheel(w)}
  const spins=w.spins||0;
  const sisa=Math.max(0,14-spins);
  const habis=sisa<=0;
  $("app").innerHTML=`<div class="card"><div style="display:flex;justify-content:space-between"><b>🎡 Gacha Harian</b>
  <button class="btn-gray" style="padding:4px 10px" onclick="S?render():lobby()">←</button></div>
  <p class="mu">Putar gratis <b>14x sehari</b>. Sisa hari ini: <b>${sisa}/14</b></p>
  <div style="text-align:center;padding:20px;font-size:64px" id="gachaIcon">🎡</div>
  <button class="btn" id="spinBtn" ${habis?"disabled style='opacity:.5'":""} onclick="spinGacha()">${habis?"Kuota hari ini habis":"🎡 PUTAR ("+sisa+" tersisa)"}</button>
  <div id="gachaRes" class="mu" style="margin-top:12px;text-align:center"></div></div>`;
}
function spinGacha(){
  const w=getWheel();const today=wibDay();
  if(w.last!==today){w.spins=0;w.last=today}
  if((w.spins||0)>=14)return toast("Kuota 14x hari ini sudah habis");
  const btn=$("spinBtn");if(btn){btn.disabled=true;btn.textContent="Memutar..."}
  const icon=$("gachaIcon");
  let n=0;const spin=setInterval(()=>{icon.textContent=["💰","⚔️","🎁","💎","🏆","🎡"][n++%6]},80);
  setTimeout(()=>{
    clearInterval(spin);
    const r=Math.random();
    let txt="";
    if(r<0.08){
      const keys=Object.keys(CODES).filter(k=>!CODES[k].admin);const k=keys[Math.floor(Math.random()*keys.length)];
      w.codes=w.codes||[];if(w.codes.indexOf(k)<0)w.codes.push(k);
      txt="🔑 Dapat kode: <b>"+k+"</b> (klaim di Redeem Code)";
      icon.textContent="🔑";
    }else if(r<0.5){
      const a=10+Math.floor(Math.random()*490);
      if(S){S.army+=a}else{w.pa=(w.pa||0)+a}
      txt="⚔️ <b>+"+a+" pasukan</b>";
      icon.textContent="⚔️";
    }else{
      const m=Math.floor(50*Math.pow(1e6,Math.random()));
      if(S){S.m+=m}else{w.pm=(w.pm||0)+m}
      txt="💰 <b>+"+fmt(m)+" uang</b>";
      icon.textContent="💰";
    }
    w.spins=(w.spins||0)+1;
    w.last=today;
    setWheel(w);
    if(S)cloudSave();
    const sisa=Math.max(0,14-w.spins);
    const res=$("gachaRes");if(res)res.innerHTML="<b>🎉 Selamat!</b><br>"+txt+"<br><span class='mu'>Sisa putaran: "+sisa+"/14</span>";
    if(btn){
      if(sisa<=0){btn.disabled=true;btn.textContent="Kuota hari ini habis";btn.style.opacity=".5"}
      else{btn.disabled=false;btn.textContent="🎡 PUTAR ("+sisa+" tersisa)"}
    }
    toast("🎡 Hadiah didapat! Sisa "+sisa);
  },2200);
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
  acStart();
  uid=ls("negara_uid");const name=ls("negara_name");
  if(uid&&name){ACC={name,id:uid};await ensureMeta();if(isBanned()){showBan();return}await ensureStats(name);lobby()}
  else nameScreen();
})();
</script>
</body>
</html>

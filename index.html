<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="utf-8">
<title>Z-SMO</title>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
/* ===== Настройки, которые удобно править ===== */
:root {
	--blood: #b3000c;
	--blood-dark: #5a0006;
	--bone: #e8e2d6;
	--ink: #050505;
	--dim: #7d776c;
}

* { box-sizing: border-box; margin: 0; padding: 0; }
html, body { width: 100%; height: 100%; overflow: hidden; background: var(--ink); cursor: default; }
body {
	font-family: "Bahnschrift", "Segoe UI", Arial, sans-serif;
	color: var(--bone);
	user-select: none;
	-webkit-user-select: none;
}

/* ===== Фон ===== */
.bg, .bg div { position: absolute; left: 0; top: 0; width: 100%; height: 100%; pointer-events: none; }
.bg { background: #040404; }

.glow {
	background:
		radial-gradient(ellipse 60% 55% at 12% 105%, rgba(140,0,10,.42), rgba(0,0,0,0) 70%),
		radial-gradient(ellipse 45% 40% at 100% 0%, rgba(90,0,6,.28), rgba(0,0,0,0) 70%);
	animation: pulse 7s ease-in-out infinite;
}
@keyframes pulse { 0%,100% { opacity: .75; } 50% { opacity: 1; } }

.vignette { background: radial-gradient(ellipse at 50% 45%, rgba(0,0,0,0) 35%, rgba(0,0,0,.88) 100%); }

.scan {
	background: repeating-linear-gradient(to bottom, rgba(255,255,255,.028) 0, rgba(255,255,255,.028) 1px, rgba(0,0,0,0) 1px, rgba(0,0,0,0) 3px);
	opacity: .55;
}

/* зерно (SVG-шум, смещается шагами) */
.grain {
	left: -50% !important; top: -50% !important; width: 200% !important; height: 200% !important;
	background-image: url("data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='220' height='220'><filter id='n'><feTurbulence type='fractalNoise' baseFrequency='.85' numOctaves='2' stitchTiles='stitch'/><feColorMatrix values='0 0 0 0 1  0 0 0 0 1  0 0 0 0 1  0 0 0 .55 0'/></filter><rect width='100%' height='100%' filter='url(%23n)'/></svg>");
	opacity: .09;
	animation: grain .6s steps(6) infinite;
}
@keyframes grain {
	0% { transform: translate(0,0); } 17% { transform: translate(-6%,4%); } 33% { transform: translate(5%,-7%); }
	50% { transform: translate(-4%,-3%); } 67% { transform: translate(7%,6%); } 83% { transform: translate(-3%,8%); } 100% { transform: translate(0,0); }
}

/* тонкие красные полосы-предупреждения сверху и снизу */
.hazard {
	position: absolute; left: 0; width: 100%; height: 7px; z-index: 5; opacity: .85;
	background: repeating-linear-gradient(-45deg, var(--blood) 0, var(--blood) 14px, #0a0a0a 14px, #0a0a0a 28px);
}
.hazard.top { top: 0; } .hazard.bot { bottom: 0; }

/* ===== Символ в правом верхнем углу ===== */
.sigil {
	position: absolute; top: 34px; right: 40px; width: 210px; height: 210px; z-index: 4;
	background: url("background/larp.png") center / contain no-repeat;
	opacity: .9;
	filter: drop-shadow(0 0 14px rgba(179,0,12,.75)) drop-shadow(0 0 40px rgba(120,0,8,.45));
	animation: spin 38s linear infinite;
}
.sigil-ring {
	position: absolute; top: 14px; right: 20px; width: 250px; height: 250px; z-index: 3; border-radius: 50%;
	border: 1px dashed rgba(179,0,12,.45);
	animation: spin 90s linear infinite reverse;
}
@keyframes spin { from { transform: rotate(0deg); } to { transform: rotate(360deg); } }

/* ===== Заголовок ===== */
.main { position: absolute; left: 7vw; top: 50%; transform: translateY(-58%); z-index: 6; }

.tag {
	font-size: 15px; letter-spacing: .55em; color: var(--blood); text-transform: uppercase; font-weight: 700;
	margin-bottom: 6px; padding-left: 4px;
}
.tag:before { content: ""; display: inline-block; width: 46px; height: 2px; background: var(--blood); vertical-align: middle; margin-right: 16px; }

.title-wrap { position: relative; display: inline-block; line-height: 1; }
.title {
	font-family: Impact, "Haettenschweiler", "Arial Black", "Bahnschrift", sans-serif;
	font-size: clamp(110px, 21vw, 330px);
	line-height: .98; letter-spacing: .02em; font-weight: 900;
	white-space: nowrap; position: relative;
	filter: drop-shadow(0 0 22px rgba(150,0,10,.55)) drop-shadow(0 6px 0 rgba(0,0,0,.6));
	animation: flick 9s infinite;
}
.title .z { color: var(--blood); text-shadow: 0 0 30px rgba(220,0,15,.55); }
.title .rest {
	background: linear-gradient(to bottom, #f1ece2 0%, #cfc8ba 46%, #8c1016 78%, #5a0006 100%);
	-webkit-background-clip: text; background-clip: text; -webkit-text-fill-color: transparent; color: transparent;
}
@keyframes flick {
	0%, 91%, 100% { opacity: 1; } 92% { opacity: .55; } 93% { opacity: 1; } 94.5% { opacity: .7; } 95% { opacity: 1; }
}

/* кровавые подтёки из-под букв */
.drips { position: absolute; left: 0; width: 100%; bottom: 17%; height: 0; z-index: 2; }
.drip {
	position: absolute; top: 0; width: var(--w, 9px); height: 0; border-radius: 0 0 6px 6px;
	background: linear-gradient(to bottom, #9a0009, #6b0007);
	animation: drip var(--t, 9s) cubic-bezier(.35,.1,.4,1) infinite;
	animation-delay: var(--d, 0s);
	opacity: 0;
}
.drip:after {
	content: ""; position: absolute; left: 50%; bottom: -5px; width: calc(var(--w, 9px) + 5px); height: calc(var(--w, 9px) + 8px);
	margin-left: calc((var(--w, 9px) + 5px) / -2);
	border-radius: 50% 50% 55% 55% / 40% 40% 60% 60%;
	background: radial-gradient(circle at 35% 30%, #c4101c 0, #8a0008 55%, #5e0006 100%);
}
@keyframes drip {
	0%   { height: 0; opacity: 0; }
	4%   { opacity: 1; }
	62%  { height: var(--l, 90px); opacity: 1; }
	88%  { height: var(--l, 90px); opacity: 1; }
	100% { height: calc(var(--l, 90px) + 40px); opacity: 0; }
}

.subtitle {
	margin-top: 8px; padding-left: 6px;
	font-size: clamp(16px, 1.9vw, 30px); letter-spacing: .62em; text-transform: uppercase; color: var(--dim); font-weight: 600;
}
.srv { margin-top: 26px; padding-left: 6px; font-size: 17px; color: var(--dim); letter-spacing: .08em; }
.srv b { color: var(--bone); font-weight: 700; }

/* ===== Нижняя панель ===== */
.bottom { position: absolute; left: 0; bottom: 0; width: 100%; padding: 0 7vw 38px; z-index: 6; }

.tips { height: 26px; margin-bottom: 18px; font-size: 18px; color: var(--bone); letter-spacing: .04em; }
.tips span { color: var(--blood); font-weight: 700; margin-right: 12px; }
.tips .txt { transition: opacity .45s; }

.status-row { display: flex; justify-content: space-between; align-items: flex-end; margin-bottom: 10px; }
.status { font-size: 14px; letter-spacing: .22em; text-transform: uppercase; color: var(--dim); }
.pct { font-family: Impact, "Arial Black", sans-serif; font-size: 40px; color: var(--bone); letter-spacing: .04em; line-height: 1; }

.bar { position: relative; width: 100%; height: 12px; background: #0e0e0e; border: 1px solid #2a2a2a; overflow: hidden; }
.fill {
	position: absolute; left: 0; top: 0; height: 100%; width: 0%;
	background: repeating-linear-gradient(-45deg, #c00010 0, #c00010 10px, #7a0008 10px, #7a0008 20px);
	background-size: 28px 28px;
	box-shadow: 0 0 16px rgba(200,0,15,.7);
	transition: width .4s ease-out;
	animation: march 1s linear infinite;
}
@keyframes march { from { background-position: 0 0; } to { background-position: 28px 0; } }

/* ===== Инфо справа внизу + плеер ===== */
.info {
	position: absolute; right: 40px; bottom: 150px; z-index: 6; text-align: right;
	font-size: 14px; letter-spacing: .18em; text-transform: uppercase; color: var(--dim); line-height: 1.9;
}
.info b { color: var(--bone); font-weight: 700; }

.player {
	position: absolute; right: 40px; top: 270px; z-index: 7; width: 250px; text-align: right;
}
.np { font-size: 11px; letter-spacing: .3em; color: var(--blood); text-transform: uppercase; font-weight: 700; }
.np-title { font-size: 14px; color: var(--bone); margin: 4px 0 10px; line-height: 1.35; letter-spacing: .03em; }
.eq { display: inline-block; height: 14px; margin-right: 8px; vertical-align: middle; }
.eq i { display: inline-block; width: 3px; margin-right: 2px; background: var(--blood); height: 4px; animation: eq .9s ease-in-out infinite; }
.eq i:nth-child(2) { animation-delay: -.3s; } .eq i:nth-child(3) { animation-delay: -.6s; } .eq i:nth-child(4) { animation-delay: -.15s; }
.paused .eq i { animation: none; height: 3px; opacity: .5; }
@keyframes eq { 0%,100% { height: 3px; } 50% { height: 14px; } }

.ctrl { display: flex; justify-content: flex-end; align-items: center; }
.btn {
	width: 34px; height: 30px; margin-left: 8px; cursor: pointer; background: rgba(15,15,15,.85);
	border: 1px solid #333; color: var(--bone); font-size: 13px; text-align: center; line-height: 28px;
}
.btn:hover { border-color: var(--blood); color: #fff; background: rgba(60,0,6,.8); }
input[type=range] {
	-webkit-appearance: none; appearance: none; width: 90px; height: 4px; margin-left: 12px; background: #2a2a2a; outline: none; cursor: pointer;
}
input[type=range]::-webkit-slider-thumb { -webkit-appearance: none; width: 10px; height: 16px; background: var(--blood); border: 0; }

@media (max-height: 640px) {
	.tips { display: none; }
	.player { top: 260px; }
}
</style>
</head>
<body>

<div class="bg">
	<div class="glow"></div>
	<div class="grain"></div>
	<div class="scan"></div>
	<div class="vignette"></div>
</div>
<div class="hazard top"></div>
<div class="hazard bot"></div>

<div class="sigil-ring"></div>
<div class="sigil"></div>

<div class="main">
	<div class="tag">Operation in progress</div>
	<div class="title-wrap">
		<div class="title"><span class="z">Z</span><span class="rest">-SMO</span></div>
		<div class="drips" id="drips"></div>
	</div>
	<div class="subtitle">Special Military Operation</div>
	<div class="srv" id="srv">Подключение к серверу…</div>
</div>

<div class="player" id="player">
	<div class="np"><span class="eq"><i></i><i></i><i></i><i></i></span>Сейчас играет</div>
	<div class="np-title" id="trackTitle">—</div>
	<div class="ctrl">
		<div class="btn" id="btnPlay" title="Пауза / играть">❚❚</div>
		<div class="btn" id="btnNext" title="Следующий трек">▶▶</div>
		<input type="range" id="vol" min="0" max="100" value="35" title="Громкость">
	</div>
</div>

<div class="info">
	КАРТА: <b id="map">—</b><br>
	ИГРОКОВ: <b id="players">—</b><br>
	РЕЖИМ: <b id="gm">Z-SMO</b>
</div>

<div class="bottom">
	<div class="tips"><span>///</span><b class="txt" id="tip"></b></div>
	<div class="status-row">
		<div class="status" id="status">Загрузка…</div>
		<div class="pct" id="pct">0%</div>
	</div>
	<div class="bar"><div class="fill" id="fill"></div></div>
</div>

<audio id="audio" preload="auto"></audio>

<script>
/* ============================================================
   НАСТРОЙКИ — правьте здесь
   ============================================================ */
var TRACKS = [
	{ file: "music/track1.mp3", title: "HYUK — LOLI / The Dark Triad" },
	{ file: "music/track2.mp3", title: "angelhard — BLADETEKK (Super Slowed)" },
	{ file: "music/track3.mp3", title: "onda andar, little_emptiness — cachalot slowed" },
	{ file: "music/track4.mp3", title: "РЕВОЛЬВЕР333" }
];
var START_VOLUME = 0.35;   // 0..1
var TIPS = [
	"F2 — выбери сторону: Ukraine или Russia",
	"Смерть — не конец. Подкрепление прибывает через 30 секунд.",
	"TAB — список игроков, разделённый по командам.",
	"Свои пресеты оружия, брони и внешнего вида сохраняются отдельно для каждой стороны.",
	"Берегись друзей по рации — враг тоже слушает вас.",
	"Держись группой. Одиночки умирают первыми."
];

/* ============================================================
   Кровавые подтёки
   ============================================================ */
(function () {
	var box = document.getElementById("drips");
	// left (%), width px, length px, time s, delay s
	var d = [
		[7, 8, 70, 9, 0.2], [17, 6, 110, 11, 3.1], [27, 10, 56, 8, 5.4], [41, 7, 130, 12, 1.4],
		[52, 9, 82, 10, 6.8], [63, 6, 150, 13, 2.2], [74, 10, 64, 9, 4.6], [84, 7, 104, 11, 7.5], [93, 8, 76, 10, 0.9]
	];
	for (var i = 0; i < d.length; i++) {
		var el = document.createElement("div");
		el.className = "drip";
		el.style.left = d[i][0] + "%";
		el.style.setProperty("--w", d[i][1] + "px");
		el.style.setProperty("--l", d[i][2] + "px");
		el.style.setProperty("--t", d[i][3] + "s");
		el.style.setProperty("--d", d[i][4] + "s");
		box.appendChild(el);
	}
})();

/* ============================================================
   Подсказки
   ============================================================ */
(function () {
	var el = document.getElementById("tip");
	var i = Math.floor(Math.random() * TIPS.length);
	el.textContent = TIPS[i];
	setInterval(function () {
		el.style.opacity = 0;
		setTimeout(function () {
			i = (i + 1) % TIPS.length;
			el.textContent = TIPS[i];
			el.style.opacity = 1;
		}, 450);
	}, 6500);
})();

/* ============================================================
   Музыка: случайный трек, дальше — другой случайный
   ============================================================ */
(function () {
	var audio = document.getElementById("audio");
	var titleEl = document.getElementById("trackTitle");
	var playBtn = document.getElementById("btnPlay");
	var nextBtn = document.getElementById("btnNext");
	var vol = document.getElementById("vol");
	var player = document.getElementById("player");
	var current = -1;
	var wantPlay = true;

	function setVol(v) { audio.volume = Math.max(0, Math.min(1, v)); }
	setVol(START_VOLUME);
	vol.value = Math.round(START_VOLUME * 100);
	vol.oninput = function () { setVol(vol.value / 100); };

	function pickNext() {
		if (TRACKS.length < 2) return 0;
		var n;
		do { n = Math.floor(Math.random() * TRACKS.length); } while (n === current);
		return n;
	}

	function load(n) {
		current = n;
		audio.src = TRACKS[n].file;
		titleEl.textContent = TRACKS[n].title;
	}

	function tryPlay() {
		var p = audio.play();
		if (p && p.catch) {
			p.catch(function () {
				// автозапуск заблокирован — запустим по первому клику
				var once = function () {
					document.removeEventListener("mousedown", once);
					document.removeEventListener("keydown", once);
					if (wantPlay) audio.play();
				};
				document.addEventListener("mousedown", once);
				document.addEventListener("keydown", once);
			});
		}
	}

	function next() { load(pickNext()); if (wantPlay) tryPlay(); }

	audio.onended = next;
	audio.onerror = function () { setTimeout(next, 800); };
	audio.onplay = function () { player.className = "player"; playBtn.textContent = "❚❚"; };
	audio.onpause = function () { player.className = "player paused"; playBtn.textContent = "▶"; };

	playBtn.onclick = function () {
		if (audio.paused) { wantPlay = true; tryPlay(); } else { wantPlay = false; audio.pause(); }
	};
	nextBtn.onclick = function () { wantPlay = true; next(); };

	// плавное нарастание громкости
	load(Math.floor(Math.random() * TRACKS.length));
	setVol(0);
	tryPlay();
	var step = 0;
	var fade = setInterval(function () {
		step++;
		setVol(START_VOLUME * Math.min(1, step / 25) * (vol.value / 100 / START_VOLUME));
		if (step >= 25) clearInterval(fade);
	}, 100);
})();

/* ============================================================
   Колбэки Garry's Mod
   ============================================================ */
var gmodConnected = false;
var filesTotal = 0, filesNeeded = 0;

function setProgress(p) {
	p = Math.max(0, Math.min(100, p));
	document.getElementById("fill").style.width = p + "%";
	document.getElementById("pct").textContent = Math.round(p) + "%";
}

function GameDetails(servername, serverurl, mapname, maxplayers, steamid, gamemode) {
	gmodConnected = true;
	document.getElementById("srv").innerHTML = "Сервер: <b>" + escapeHtml(servername || "Z-SMO") + "</b>";
	document.getElementById("map").textContent = mapname || "—";
	document.getElementById("players").textContent = "до " + (maxplayers || "—");
	if (gamemode) document.getElementById("gm").textContent = gamemode;
}

function SetFilesTotal(total) {
	gmodConnected = true;
	filesTotal = total || 0;
	updateFiles();
}

function SetFilesNeeded(needed) {
	gmodConnected = true;
	filesNeeded = needed || 0;
	updateFiles();
}

function updateFiles() {
	if (filesTotal > 0) {
		setProgress(((filesTotal - filesNeeded) / filesTotal) * 100);
	}
}

function DownloadingFile(fileName) {
	gmodConnected = true;
	document.getElementById("status").textContent = "Скачивание: " + shortName(fileName);
}

function SetStatusChanged(status) {
	gmodConnected = true;
	document.getElementById("status").textContent = status;
	// когда файлов нет, GMod шлёт только статусы — двигаем полосу по ключевым этапам
	if (filesTotal === 0) {
		var s = String(status).toLowerCase();
		if (s.indexOf("workshop") >= 0) setProgress(25);
		else if (s.indexOf("map") >= 0 || s.indexOf("карт") >= 0) setProgress(50);
		else if (s.indexOf("sending") >= 0 || s.indexOf("client info") >= 0 || s.indexOf("получение") >= 0) setProgress(75);
		else if (s.indexOf("lua") >= 0) setProgress(90);
	}
}

function shortName(f) {
	f = String(f || "");
	return f.length > 60 ? "…" + f.slice(-58) : f;
}
function escapeHtml(s) {
	return String(s).replace(/[&<>"']/g, function (c) {
		return { "&": "&amp;", "<": "&lt;", ">": "&gt;", '"': "&quot;", "'": "&#39;" }[c];
	});
}

/* Если страницу открыли в обычном браузере (не в игре) — крутим демо-прогресс для превью */
setTimeout(function () {
	if (gmodConnected) return;
	GameDetails("Z-SMO | Special Military Operation", "", "gm_construct", 32, "0", "Z-SMO");
	var p = 0, msgs = ["Получение списка файлов", "Скачивание материалов", "Загрузка карты", "Инициализация Lua"];
	var t = setInterval(function () {
		p += Math.random() * 2.5;
		if (p >= 100) { p = 100; clearInterval(t); }
		setProgress(p);
		document.getElementById("status").textContent = msgs[Math.min(3, Math.floor(p / 25))] + "…";
	}, 120);
}, 1500);
</script>
</body>
</html>

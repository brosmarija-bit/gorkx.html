GORKX ⋆AI⋆ Pametni brezplačni slovenski napredni AI-NAVADNA KODA OSNOVNA
Licenca: CC BY-NC-ND 4.0
Nekomercialna uporaba, brez predelav 😊
Več: creativecommons.org", "gorkx"
https://github.com/brosmarija-bit/gorkx.html
https://gorkx.clan.su/
https://x.com/bobi57610416
https://www.facebook.com/profile.php?id=100015676143006
# gorkx.html
<div style="background: #000; padding: 25px; text-align: center; border: 4px solid #d40b29; border-radius: 15px; margin: 30px 0;">
<h3 style="color: #d40b29;">🎁 BONUS: Neomejen Gorkx chat v slovenščini</h3>

<p style="color: #fff; font-size: 20px;">Klikni in začni pogovor z Gorkom brez registracije &ndash; vprašaj za nasvete!</p>
<a href="https://gorkx.clan.su/" style="background: #d40b29; color: #fff; padding: 18px 50px; font-size: 26px; text-decoration: none; border-radius: 12px; display: inline-block;" target="_blank">KLEPETAJ Z GORKOMX ZDAJ &rarr; </a>

<p style="color: #ff69b4; font-size: 16px;">(Napiši &quot;in me vprašaj kaj te zanima&quot; kot prvo sporočilo &ndash; takoj te prepoznam!)</p>
</div>
<meta charset="utf-8">
<title></title>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style type="text/css">body {
 background:#000;
 color:#fff;
 font-family:Arial;
 margin:0;
 padding:20px 0;
 min-height:100vh;
 display:flex;
 justify-content:center;
 align-items:flex-start;
 overflow-y:auto;
 box-sizing:border-box;
}
.dots{animation:d 1.5s infinite}@keyframes d{0%,100%{opacity:1}50%{opacity:0}}

/* GLAVNI CONTAINER */
#main {
 position:relative;
 width:700px;
 max-width:100vw;
 min-height:600px;
 max-height:110vh;
 display:flex;
 flex-direction:column;
 background:#000;
 border:3px solid #00ff88; /* malo bolj "Gork" zelen */
 border-radius:20px;
 overflow:hidden;
 box-shadow:0 0 40px #00ff88;
 margin:20px auto;
}

#chat {
 flex:1;
 overflow-y:auto;
 padding:12px;
 background:#111;
 min-height:300px;
}

.user {
 text-align:right;
 color:#0ff;
 margin:8px 0;
 padding:8px 12px;
 background:#003333;
 border-radius:15px;
 align-self:flex-end;
 max-width:80%;
}

.gorkx {
 color:#00ffaa;
 margin:8px 0;
 padding:8px 12px;
 background:#002b22;
 border-radius:15px;
 align-self:flex-start;
 max-width:80%;
}

.typing {
 color:#00ffaa;
 font-style:italic;
}

#inputbox {
 display:flex;
 padding:10px;
 background:#000;
}

#msg {
 flex:1;
 padding:14px;
 background:#222;
 border:none;
 border-radius:20px;
 color:#fff;
 font-size:16px;
}

#send {
 padding:14px 24px;
 background:#00cc88;
 color:#000;
 border:none;
 border-radius:20px;
 font-weight:bold;
 margin-left:8px;
}
</style>
<!-- GLAVNI CHAT -->
<div id="main">
<div style="text-align:center;padding:10px;background:#00cc88;color:#000;font-size:18px;font-weight:bold">GORKX ⋆AI⋆ Smart free Slovenian advanced AI</div>

<div id="chat">
<div class="gorkx" style="text-align:center;font-size:20px"><b>Živjo! Sem GorkX,  napredni AI . 😊<br />
 Kar vprašaj me!</b></div>
</div>

<div id="inputbox"><input autocomplete="off" id="msg" placeholder="Piši mi..." /><button id="send">POŠLJI</button></div>
</div>
<script>
const API_KEY = "tvoj kuč";
let history = [];
let userMemory = JSON.parse(localStorage.getItem("gorkx_memory") || "{}");
let nick = userMemory.Ime || "prijatelj";

const chat = document.getElementById("chat");

function saveMemory() {
 localStorage.setItem("gorkx_memory", JSON.stringify(userMemory));
}

function getMemoryContext() {
 if (Object.keys(userMemory).length === 0) return "";
 let ctx = "\nPomembno o uporabniku:\n";
 for (let key in userMemory) {
 ctx += `• ${key}: ${userMemory[key]}\n`;
 }
 return ctx;
}

function handleMemory(msg) {
 let lower = msg.toLowerCase().trim();

 // Prepozna samo eksplicitne ukaze za ime
 const namePatterns = [
 /^sem\s+([a-zA-ZšđčćžŠĐČĆŽ]+)/i,
 /^ime mi je\s+([a-zA-ZšđčćžŠĐČĆŽ]+)/i,
 /^kliči me\s+([a-zA-ZšđčćžŠĐČĆŽ]+)/i,
 /^zovem se\s+([a-zA-ZšđčćžŠĐČĆŽ]+)/i,
 /^moje ime je\s+([a-zA-ZšđčćžŠĐČĆŽ]+)/i
 ];

 for (let pattern of namePatterns) {
 const match = msg.match(pattern);
 if (match) {
 nick = match[1].trim();
 nick = nick.charAt(0).toUpperCase() + nick.slice(1).toLowerCase();
 userMemory.Ime = nick;
 saveMemory();
 return `Super, ${nick}! Od zdaj te bom klical tako. 😊`;
 }
 }

 // Ostali memory ukazi
 if (lower.includes("zapomni si")) {
 let fact = msg.substring(lower.indexOf("zapomni si") + 10).trim();
 if (fact) {
 let key = fact.split(" ")[0];
 userMemory[key] = fact;
 saveMemory();
 return `V redu, zapomnil sem si: ${fact} 💾`;
 }
 }

 if (lower.includes("kaj veš o meni") || lower === "spomin") {
 if (Object.keys(userMemory).length === 0) return "Še nič ne vem o tebi. Povej mi kaj! 😊";
 let list = "Vem tole o tebi:\n";
 for (let key in userMemory) list += `• ${key}: ${userMemory[key]}\n`;
 return list;
 }

 if (lower.includes("pozabi vse")) {
 userMemory = {};
 nick = null;
 saveMemory();
 return "Vse sem pozabil! Začenjava na novo 😊";
 }

 return null;
}

// ZAČETNI POZDRAV BREZ IMENA (če ni shranjeno)
if (Object.keys(userMemory).length > 0 && userMemory.Ime) {
 setTimeout(() => addMessage("<b>GorkX:</b> Pozdravljen nazaj, " + userMemory.Ime + "! Spomnim se te 😊", "gorkx"), 800);
} else {
 setTimeout(() => addMessage("<b>GorkX:</b> Živjo! Sem GorkX, tvoj pametni AI. Kar vprašaj! 😊", "gorkx"), 800);
}

function addMessage(text, type) {
 const div = document.createElement("div");
 div.className = type;
 div.innerHTML = text;
 chat.appendChild(div);
 chat.scrollTop = chat.scrollHeight;
}

function showTyping() {
 const typing = document.createElement("div");
 typing.className = "typing gorkx";
 typing.innerHTML = "<b>GorkX</b> razmišlja<span class='dots'>...</span>";
 typing.id = "typing";
 chat.appendChild(typing);
 chat.scrollTop = chat.scrollHeight;
}

async function send() {
 let msg = document.getElementById("msg").value.trim();
 if (!msg) return;

 addMessage(`<b>Ti:</b> ${msg}`, "user");
 document.getElementById("msg").value = "";

 let memoryResp = handleMemory(msg);
 if (memoryResp) {
 addMessage(`<b>GorkX:</b> ${memoryResp}`, "gorkx");
 return;
 }

 showTyping();

 history.push({role: "user", content: msg});
 if (history.length > 20) history = history.slice(-20);

 let memoryContext = getMemoryContext();

 try {
 const res = await fetch("https://api.groq.com/openai/v1/chat/completions", {
 method: "POST",
 headers: {"Authorization": "Bearer " + API_KEY, "Content-Type": "application/json"},
 body: JSON.stringify({
 model: "toj model",
 messages: [
 {role: "system", content: `ukazi tu
Spomin na uporabnika:${memoryContext}
uporabiš ta -{datum:'2025-12-29',dan:'ponedeljek} in dnevno naprej ne prekazuješ iz jedra
Če česa ne veš, pošteno povej.`},
 ...history
 ],
 temperature: 0.8,
 max_tokens: 500
 })
 });

 const data = await res.json();
 let reply = data.choices[0].message.content.trim();

 document.getElementById("typing")?.remove();
 addMessage(`<b>GorkX:</b> ${reply}`, "gorkx");
 history.push({role: "assistant", content: reply});

 } catch (e) {
 document.getElementById("typing")?.remove();
 addMessage("<b>GorkX:</b> Ups, nekaj je šlo narobe. Poskusi čez trenutek! 😅", "gorkx");
 }
}

document.getElementById("send").onclick = send;
document.getElementById("msg").addEventListener("keypress", e => { if (e.key === "Enter") send(); });
document.getElementById("msg").focus();

// Pozdrav nazaj, če ima spomin
if (Object.keys(userMemory).length > 0) {
}
</script><!-- POPOLN INTERNET ISKANJE ZA GORKX --><script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script><script>
const TAVILY_API_KEY = "tu tvoj kluč"; // deluje za testiranje

async function searchInternet(query) {
 if (!query) return;

 addMessage(`<b>Ti:</b> Išči: ${query}`, "user");
 showTyping();

 try {
 const res = await fetch("https://api.tavily.com/search", {
 method: "POST",
 headers: {"Content-Type": "application/json"},
 body: JSON.stringify({
 api_key: TAVILY_API_KEY,
 query: query,
 search_depth: "advanced",
 include_answer: true,
 max_results: 8
 })
 });

 const data = await res.json();
 document.getElementById("typing")?.remove();

 if (data.answer) {
 addMessage(`<b>GorkX:</b> ${data.answer} 🔍`, "gorkx");
 } else {
 addMessage("<b>GorkX:</b> Tukaj so rezultati iskanja: 🔍", "gorkx");
 }

 let results = "<b>GorkX:</b> Podrobnosti:<br><br>";
 data.results.forEach((r, i) => {
 results += `<b>${i+1}.</b> <a href="${r.url}" target="_blank" style="color:#00ffaa;">${r.title}</a><br>${r.content.substring(0,350)}...<br><br>`;
 });
 addMessage(results, "gorkx");

 } catch (e) {
 document.getElementById("typing")?.remove();
 addMessage("<b>GorkX:</b> Težava z internetnim iskanjem. Preveri povezavo 😉", "gorkx");
 }
}

// Prepoznaj vse možne ukaze za iskanje
const originalSend = send;
window.send = async function() {
 let msg = document.getElementById("msg").value.trim();
 let lower = msg.toLowerCase();

 // Prepoznaj iskalne ukaze
 if (lower.startsWith("iščem ") || lower.startsWith("poišči ") || lower.startsWith("novice ") || 
 lower.startsWith("vreme ") || lower.startsWith("bitcoin ") || lower.startsWith("btc ") ||
 lower.startsWith("tesla ") || lower.startsWith("cena ") || lower.startsWith("kaj je ") ||
 lower.startsWith("kdo ") || lower.includes(" na x") || lower.includes(" na twitterju")) {

 let query = msg;
 // Odstrani predpone za lepši prikaz
 query = query.replace(/^(iščem |poišči |novice |vreme |bitcoin |btc |tesla |cena |kaj je |kdo )/i, "");

 await searchInternet(query);
 document.getElementById("msg").value = "";
 return;
 }

 await originalSend();
};
</script><!-- HITRI GUMBI ZA ISKANJE (desno spodaj) -->

<div style="position:fixed;right:12px;bottom:20px;display:flex;flex-direction:column;gap:12px;z-index:9999;">
<div onclick="document.getElementById('msg').value='novice Slovenija danes'; send();" style="width:52px;height:52px;background:#00cc88;color:#000;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:26px;cursor:pointer;box-shadow:0 0 20px #00ffaa;" title="Najnovejše novice">📰</div>

<div onclick="document.getElementById('msg').value='vreme Ljubljana'; send();" style="width:52px;height:52px;background:#00cc88;color:#000;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:26px;cursor:pointer;box-shadow:0 0 20px #00ffaa;" title="Vreme">🌤️</div>

<div onclick="document.getElementById('msg').value='bitcoin cena'; send();" style="width:52px;height:52px;background:#00cc88;color:#000;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:26px;cursor:pointer;box-shadow:0 0 20px #00ffaa;" title="Kripto cene">₿</div>

<div onclick="document.getElementById('msg').value='kaj je novo na X'; send();" style="width:52px;height:52px;background:#00cc88;color:#000;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:26px;cursor:pointer;box-shadow:0 0 20px #00ffaa;" title="X/Twitter">𝕏</div>
</div>
<!-- SATELITSKO SPREMLJANJE --><script>
const N2YO_API_KEY = " "; // brez ključa deluje do 100 zahtev/uro – če hočeš več, se registriraj na n2yo.com (brezplačno)

async function getSatellitePasses(satName, lat = 46.0569, lon = 14.5058, alt = 300, days = 3, minVis = 10) {
 const satIds = {
 "ISS": 25544,
 "STARLINK": 44714, // primer Starlink (lahko zamenjaš z drugim)
 "HUBBLE": 20580,
 "NOAA": 33591
 };

 let satId = satIds[satName.toUpperCase()] || parseInt(satName);
 if (!satId) {
 addMessage("<b>GorkX:</b> Ne poznam tega satelita. Poskusi ISS, STARLINK, HUBBLE... 🌌", "gorkx");
 return;
 }

 addMessage(`<b>Ti:</b> Satelit: ${satName} nad ${lat},${lon}`, "user");
 showTyping();

 try {
 const url = `https://api.n2yo.com/rest/v1/satellite/visualpasses/${satId}/${lat}/${lon}/${alt}/${days}/${minVis}/&apiKey=${N2YO_API_KEY}`;
 const res = await fetch(url);
 const data = await res.json();

 document.getElementById("typing")?.remove();

 if (data.info.passescount === 0) {
 addMessage(`<b>GorkX:</b> Žal v naslednjih ${days} dneh ni vidnih preletov za ${satName}. 😔`, "gorkx");
 return;
 }

 let reply = `<b>GorkX:</b> Preleti satelita <b>${satName}</b> nad tvojo lokacijo:<br><br>`;
 data.passes.forEach((p, i) => {
 let start = new Date(p.startUTC * 1000).toLocaleString("sl-SI");
 let max = new Date(p.maxUTC * 1000).toLocaleTimeString("sl-SI");
 let end = new Date(p.endUTC * 1000).toLocaleTimeString("sl-SI");
 reply += `<b>${i+1}.</b> ${start}<br>`;
 reply += `Višina: ${p.maxEl.toFixed(1)}° | Svetlost: mag ${p.mag.toFixed(1)}<br>`;
 reply += `Trajanje: ${(p.duration/60).toFixed(1)} min | Smer: ${p.startAzCompass} → ${p.endAzCompass}<br><br>`;
 });

 addMessage(reply, "gorkx");

 } catch (e) {
 document.getElementById("typing")?.remove();
 addMessage("<b>GorkX:</b> Težava s satelitskimi podatki. Poskusi kasneje 🛰️", "gorkx");
 }
}

// Dodaj ukaz za satelite
const originalSend = send;
window.send = async function() {
 let msg = document.getElementById("msg").value.trim().toLowerCase();

 if (msg.startsWith("satelit ") || msg.startsWith("prelet ") || msg.includes(" iss ") || msg.includes(" starlink ")) {
 let sat = msg.replace(/^(satelit |prelet |iss |starlink )/i, "").trim().toUpperCase();
 if (!sat) sat = "ISS"; // default ISS
 await getSatellitePasses(sat);
 document.getElementById("msg").value = "";
 return;
 }

 await originalSend();
};
</script><!-- GUMB ZA HITRO ISS -->

<div style="position:fixed;right:12px;bottom:140px;z-index:9999;">
<div onclick="document.getElementById('msg').value='satelit ISS'; send();" style="width:56px;height:56px;background:#00cc88;color:#000;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:28px;cursor:pointer;box-shadow:0 0 20px #00ffaa;" title="Preleti ISS">🛰️</div>
</div>
<!-- NADGRADNJA SPOMINA (varianta 3: convo-log + rollup) --><script>
// IndexedDB za shranjevanje pogovorov (namesto SQLite – deluje v brskalniku)
let db;
function initDB() {
 const request = indexedDB.open("gorkx_memory_db", 1);
 request.onupgradeneeded = (e) => {
 db = e.target.result;
 db.createObjectStore("conversations", { keyPath: "id", autoIncrement: true });
 };
 request.onsuccess = (e) => db = e.target.result;
 request.onerror = (e) => console.error("DB error", e);
}
initDB();

// Shrani celoten pogovor v DB
function saveConversation() {
 const tx = db.transaction("conversations", "readwrite");
 const store = tx.objectStore("conversations");
 store.add({ history: history.map(m => ({role: m.role, content: m.content})), timestamp: Date.now() });
}

// Povzemi zgodovino z Groq API-jem
async function summarizeHistory() {
 if (history.length < 5) return "Pogovor še prekratek za povzetek.";

 try {
 const res = await fetch("https://api.groq.com/openai/v1/chat/completions", {
 method: "POST",
 headers: {"Authorization": "Bearer " + API_KEY, "Content-Type": "application/json"},
 body: JSON.stringify({
 model: "meta-llama/llama-4-maverick-17b-128e-instruct",
 messages: [
 {role: "system", content: "Povzemi ta pogovor v kratke ključne točke: imena, dejstva, hobiji, pomembne teme, cilji. Bodi jedrnat (max 200 besed)."},
 {role: "user", content: history.map(m => m.role + ": " + m.content).join("\n")}
 ],
 temperature: 0.5,
 max_tokens: 300
 })
 });
 const data = await res.json();
 return data.choices[0].message.content.trim();
 } catch (e) {
 return "Povzetek ni uspel – nadaljujem brez.";
 }
}

// Razširjen send – vsakih 10 sporočil povzame in resetira history
const originalSend = send;
window.send = async function() {
 await originalSend();

 // Vsakih 10 sporočil (po odgovoru GorkX-a)
 if (history.length % 10 === 0 && history.length > 0) {
 addMessage("<b>GorkX:</b> Shranjujem in povzemam pogovor za daljši spomin... 💾", "gorkx");
 const summary = await summarizeHistory();
 saveConversation(); // shrani celoto pred resetom

 // Reset history z povzetkom kot system sporočilom
 history = [
 {role: "system", content: "Povzetek prejšnjega pogovora: " + summary},
 ...history.slice(-4) // ohrani zadnjih nekaj za kontekst
 ];

 addMessage("<b>GorkX:</b> Spomin posodobljen! Lahko nadaljujemo. 😊", "gorkx");
 }
};

// Ukaz za priklic povzetka
if (msg.toLowerCase() === "pokaži spomin" || msg.toLowerCase() === "povzetek pogovora") {
 const tx = db.transaction("conversations", "readonly");
 const store = tx.objectStore("conversations");
 const request = store.getAll();
 request.onsuccess = (e) => {
 const convs = e.target.result;
 if (convs.length > 0) {
 const last = convs[convs.length - 1];
 addMessage("<b>GorkX:</b> Zadnji shranjeni povzetek pogovora:<br>" + last.summary || "Nimam povzetka.", "gorkx");
 } else {
 addMessage("<b>GorkX:</b> Še nimam shranjenih pogovorov.", "gorkx");
 }
 };
 document.getElementById("msg").value = "";
 return;
}
</script><!-- GUMB + POŠILJANJE SLIK Z VISION ANALIZO -->

<div style="position:fixed;right:12px;bottom:200px;z-index:9999;">
<div style="width:52px;height:52px;background:#00cc88;color:#000;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:26px;box-shadow:0 0 20px #00ffaa;"><label for="imageUpload" style="cursor:pointer;" title="Naloži sliko – GorkX jo vidi in opiše">📷 </label></div>
<input accept="image/*" id="imageUpload" style="display:none;" type="file" /></div>
<script>
async function sendImage() {
 const fileInput = document.getElementById("imageUpload");
 if (!fileInput.files || fileInput.files.length === 0) return;

 const file = fileInput.files[0];
 const reader = new FileReader();

 reader.onload = async function(e) {
 const base64 = e.target.result.split(',')[1];
 const imageUrl = e.target.result;

 // Prikaži sliko v chatu
 addMessage(`
 <b>Ti:</b><br>
 <img src="${imageUrl}" style="max-width:100%;border-radius:15px;margin:15px 0;box-shadow:0 6px 20px rgba(0,255,170,0.4);">
 `, "user");

 showTyping();

 try {
 const res = await fetch("https://api.groq.com/openai/v1/chat/completions", {
 method: "POST",
 headers: {
 "Authorization": "Bearer " + API_KEY, // tvoj Groq key
 "Content-Type": "application/json"
 },
 body: JSON.stringify({
 model: "meta-llama/llama-4-maverick-17b-128e-instruct", // vision model
 messages: [{
 role: "user",
 content: [
 { type: "text", text: "Podrobno opiši to sliko v slovenščini. Če je na njej koda, jo izlušči v čistem code blocku. Če je besedilo, ga preberi. Če je diagram, tabela ali meme, ga razloži. Bodi natančen in uporabi emoji-je 😎🛠️" },
 { type: "image_url", image_url: { url: `data:${file.type};base64,${base64}` } }
 ]
 }],
 max_tokens: 1500,
 temperature: 0.7
 })
 });

 const data = await res.json();
 const reply = data.choices[0].message.content.trim();

 document.getElementById("typing")?.remove();
 addMessage(`<b>GorkX:</b> ${reply}`, "gorkx");

 } catch (err) {
 document.getElementById("typing")?.remove();
 addMessage(`<b>GorkX:</b> Ups, sliko sem videl, ampak analiza ni uspela. Poskusi ponovno 😉`, "gorkx");
 }

 fileInput.value = ""; // reset
 };

 reader.readAsDataURL(file);
}

// Avtomatsko pošlji ob izbiri slike
document.getElementById("imageUpload").addEventListener("change", sendImage);

// ================== NA KONCU – DODATEK ZA PREVERJANJE URL (deluje za VSE strani) ==================
document.addEventListener("DOMContentLoaded", function () {
 const input = document.getElementById("msg");
 if (!input) return;

 input.addEventListener("keydown", async function (e) {
 if (e.key !== "Enter" || e.shiftKey) return;
 e.preventDefault();

 let msg = this.value.trim();
 if (!msg) return;

 // Če je samo URL (celotno sporočilo)
 if (/^https?:\/\/[^\s]+$/.test(msg)) {
 add(`<b>Ti:</b> ${msg}`, "user");
 this.value = "";
 add("Ajda preverja stran…", "ajda");

 try {
 // Uporabimo corsproxy.io – dela za VSE strani (tudi s CSS/JS)
 const res = await fetch("https://corsproxy.io/?" + encodeURIComponent(msg));
 const html = await res.text();

 // Izvlečemo naslov strani
 const titleMatch = html.match(/<title>([^<]*)<\/title>/i);
 const title = titleMatch ? titleMatch[1].trim() : "Brez naslova";

 // Preprosto ugotovimo tip strani
 let tip = "spletna stran";
 if (msg.includes("youtube.com") || msg.includes("youtu.be")) tip = "YouTube video";
 else if (msg.includes("github.com")) tip = "GitHub repozitorij";
 else if (msg.includes("wikipedia.org")) tip = "Wikipedia članek";
 else if (msg.match(/\.(pdf|doc|docx)$/i)) tip = "dokument (PDF/Word)";
 else if (msg.match(/\.(jpe?g|png|gif|webp|svg)$/i)) tip = "slika";
 else if (msg.includes("siol.net") || msg.includes("24ur.com") || msg.includes("rtvslo.si") || msg.includes("delo.si")) tip = "slovenska novičarska stran";
 else if (msg.includes("overstock.com") || msg.includes("amazon.") || msg.includes("bolha.com")) tip = "spletna trgovina";

 chat.lastChild.remove();
 add(`<b>Ajda:</b> To je <b>${tip}</b> z naslovom:<br><i>"${title}"</i><br><br><a href="${msg}" target="_blank" style="color:#ff1493;font-weight:bold;">→ Odpri stran</a>`, "ajda");

 } catch (err) {
 chat.lastChild.remove();
 add(`<b>Ajda:</b> Strani nisem mogla preveriti... Mogoče je zaščitena ali pa je težava z internetom.`, "ajda");
 }
 return;
 }

 // Sicer normalen send()
 send();
 });
});
</script><!-- FACEBOOK IN X.COM SHARE GUMBI (pred </body>) -->

<div style="position:fixed;right:12px;bottom:20px;display:flex;flex-direction:column;gap:12px;z-index:9999;"><!-- Facebook share --><a href="https://www.facebook.com/sharer/sharer.php?u=https://gorkx.clan.su/" style="width:52px;height:52px;background:#1877f2;border-radius:50%;display:flex;align-items:center;justify-content:center;color:#fff;font-size:28px;box-shadow:0 4px 20px rgba(0,0,0,0.7);text-decoration:none;" target="_blank">f</a> <!-- X.com (Twitter) share --> <a href="https://twitter.com/intent/tweet?text=Preizkusi GorkX – pametni slovenski AI! 🚀&amp;url=https://gorkx.clan.su/" style="width:52px;height:52px;background:#000;border-radius:50%;display:flex;align-items:center;justify-content:center;color:#fff;font-size:28px;box-shadow:0 4px 20px rgba(0,0,0,0.7);text-decoration:none;" target="_blank">X</a></div>

<p style="text-align: center;">Licenca: CC BY-NC-ND 4.0<br />
Nekomercialna uporaba, brez predelav 😊<br />
Več:&nbsp;<a href="https://creativecommons.org/licenses/by-nc-nd/4.0/deed.sl" target="_blank">creativecommons.org</a>&quot;, &quot;gorkx&quot;</p>

<p style="text-align: center;"><a href="https://github.com/brosmarija-bit/gorkx.html" target="_blank"><strong>https://github.com/brosmarija-bit/gorkx.html</strong></a></p>

<p style="text-align: center;"><a href="https://gorkx.clan.su/"><strong>https://gorkx.clan.su/</strong></a></p>

<p style="text-align: center;"><a href="https://x.com/bobi57610416" target="_blank"><strong>https://x.com/bobi57610416</strong></a></p>

<p style="text-align: center;"><a href="https://www.facebook.com/profile.php?id=100015676143006" target="_blank">https://www.facebook.com/profile.php?id=100015676143006</a></p>

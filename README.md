<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Affet beni 🥺</title>

<style>
body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: linear-gradient(135deg, #ff9ecb, #ffc0cb);
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    overflow: hidden;
}

.card {
    backdrop-filter: blur(20px);
    background: rgba(255,255,255,0.25);
    padding: 25px;
    border-radius: 25px;
    text-align: center;
    width: 90%;
    max-width: 360px;
    box-shadow: 0 10px 40px rgba(0,0,0,0.2);
    animation: fadeIn 0.8s ease;
}

h1 {
    font-size: 18px;
    color: white;
}

button {
    margin: 10px;
    padding: 12px 22px;
    border: none;
    border-radius: 14px;
    cursor: pointer;
    font-size: 16px;
    transition: 0.25s;
}

.yes {
    background: #ff4da6;
    color: white;
}

.no {
    background: white;
}

.full {
    position: fixed;
    top:0;
    left:0;
    width:100%;
    height:100%;
    font-size:40px;
    z-index:999;
}

img {
    width:120px;
    border-radius:20px;
}

@keyframes fadeIn {
    from {opacity:0; transform:scale(0.85);}
    to {opacity:1; transform:scale(1);}
}

/* ❤️ KALP YAĞMURU */
.heart {
    position: fixed;
    top: -10px;
    color: #ff4da6;
    font-size: 20px;
    animation: fall linear forwards;
}

@keyframes fall {
    to {
        transform: translateY(110vh);
        opacity: 0;
    }
}

</style>
</head>

<body>

<!-- 🎵 YOUTUBE MÜZİK -->
<iframe id="musicFrame" width="0" height="0"
src=""
allow="autoplay">
</iframe>

<div class="card" id="screen1">
    <h1>biraz kıskancımda eheheh beni affedebilirmisin🥰</h1>
    <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAA..." />
    <br>
    <button class="yes" id="yesBtn">Evet</button>
    <button class="no" id="noBtn">Hayır</button>
</div>

<div class="card" id="screen2" style="display:none;">
    <button class="yes" onclick="showMessage()">Mesajı Gör 💌</button>
</div>

<div class="card" id="screen3" style="display:none;">
    <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAA..." />
    <h1 id="text"></h1>
    <button class="yes">Evet 🥰</button>
    <button class="no" id="escapeBtn">Hayır</button>
</div>

<script>

const videoID = "7hJ3hFZ0F9U"; // Everybody Loves Somebody

function playMusic(){
    document.getElementById("musicFrame").src =
    `https://www.youtube.com/embed/${videoID}?autoplay=1&controls=0`;
}

// BUTTON LOGIC
let noCount = 0;
const noBtn = document.getElementById("noBtn");
const yesBtn = document.getElementById("yesBtn");

noBtn.onclick = () => {
    noCount++;
    yesBtn.style.transform = `scale(${1 + noCount * 0.4})`;
    if(noCount >= 5) yesBtn.classList.add("full");
};

yesBtn.onclick = () => {
    playMusic();
    document.getElementById("screen1").style.display="none";
    document.getElementById("screen2").style.display="block";
};

// MESAJ
function showMessage(){
    playMusic();
    document.getElementById("screen2").style.display="none";
    document.getElementById("screen3").style.display="block";

    document.getElementById("text").innerText =
    "seni bazen kırabiliyorum üzebiliyorum istemedende olsa sende beni kısırıyorsun ama ben kırıldığım şeyi söylemekten çekiniyor ve başkalarından utanıyorum😖, o yüzden kırıldığımda yada sinirlendiğimde benimle biraz daha ilgilenirmisin beraber kalıncada sana söylerim, biliyorum o duyguların yaşandığı zaman korkunç görünüyorum ama lütfen ,benim için yaparmısın?🥰";

    startHearts();
}

// ❤️ KALP YAĞMURU
function startHearts(){
    setInterval(()=>{
        let heart = document.createElement("div");
        heart.className="heart";
        heart.innerHTML="❤️";
        heart.style.left=Math.random()*100+"vw";
        heart.style.fontSize=(Math.random()*20+15)+"px";
        heart.style.animationDuration=(Math.random()*3+2)+"s";
        document.body.appendChild(heart);

        setTimeout(()=>heart.remove(),5000);
    },200);
}

// KAÇAN BUTON
const escapeBtn = document.getElementById("escapeBtn");
escapeBtn.onmouseover = () => {
    escapeBtn.style.position="absolute";
    escapeBtn.style.top=Math.random()*80+"%";
    escapeBtn.style.left=Math.random()*80+"%";
};

</script>

</body>
</html>

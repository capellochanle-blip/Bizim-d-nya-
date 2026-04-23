DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>sadece ömrüme özell 🤍💋</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Dancing+Script:wght@700&display=swap');

*{margin:0;padding:0;box-sizing:border-box;}

body{
    height:100vh;
    overflow:hidden;
    background:black;
    color:white;
    font-family:'Playfair Display', serif;
}

/* 🌌 YILDIZ */
#stars{
    position:fixed;
    width:100%;
    height:100%;
    z-index:0;
}

/* 🔐 LOGIN */
.login-container{
    position:fixed;
    top:50%;
    left:50%;
    transform:translate(-50%,-50%);
    width:340px;
    padding:40px 30px;
    border-radius:30px;
    background:rgba(255,255,255,0.06);
    backdrop-filter:blur(25px);
    border:1px solid rgba(255,255,255,0.2);
    box-shadow:0 0 40px rgba(255,105,180,0.4);
    text-align:center;
    z-index:20;
    animation:fadeIn 1s ease;
}

.lock-icon{font-size:45px;margin-bottom:10px;animation:float 2s infinite ease-in-out;}

.title{
    font-family:'Dancing Script';
    font-size:38px;
    color:#ff69b4;
    text-shadow:0 0 20px #ff69b4;
}

.subtitle{font-size:13px;opacity:0.7;margin-bottom:20px;}

input{
    width:100%;
    padding:14px;
    border:none;
    border-radius:15px;
    text-align:center;
    background:rgba(255,255,255,0.08);
    color:white;
    outline:none;
}

/* 🔥 VIP BUTTON */
button{
    width:100%;
    margin-top:15px;
    padding:14px;
    border:none;
    border-radius:20px;
    background:linear-gradient(45deg,#ff1493,#8a2be2);
    color:white;
    cursor:pointer;
    position:relative;
    overflow:hidden;
}

button::after{
    content:"";
    position:absolute;
    width:300%;
    height:300%;
    top:-100%;
    left:-100%;
    background:linear-gradient(120deg,transparent,rgba(255,255,255,0.4),transparent);
    transform:rotate(25deg);
    transition:0.6s;
}
button:hover::after{
    left:100%;
}

/* 💖 ANA */
.main-content{
    display:none;
    position:fixed;
    width:100%;
    height:100%;
    overflow:auto;
    padding:20px;
    z-index:5;
}
.main-content.show{display:block;}

.header{text-align:center;margin-top:40px;}
.header h1{
    font-family:'Dancing Script';
    font-size:48px;
    color:#ff69b4;
}

/* ⏱ */
.time{text-align:center;margin-top:20px;font-size:20px;}
.time span{color:#ff69b4;font-size:26px;margin:0 4px;}

/* 🎵 */
.music-player{text-align:center;margin:30px auto;}

.lyrics{
    margin:20px;
    padding:20px;
    background:rgba(255,255,255,0.1);
    border-radius:15px;
}

/* 📸 */
.slider{
    margin:20px auto;
    width:250px;
    height:250px;
    border-radius:20px;
    overflow:hidden;
}
.slider img{width:100%;height:100%;object-fit:cover;}

/* 🎁 */
.surprise-btn{
    width:200px;
    margin:20px auto;
    display:block;
    box-shadow:0 0 20px #ff69b4;
}

/* 🎁 POPUP */
.popup{
    position:fixed;
    top:50%;
    left:50%;
    transform:translate(-50%,-50%) scale(0.8);
    background:rgba(0,0,0,0.9);
    padding:30px;
    border-radius:20px;
    text-align:center;
    border:1px solid #ff69b4;
    box-shadow:0 0 40px #ff69b4;
    display:none;
    z-index:999;
    opacity:0;
    transition:0.4s;
}
.popup.show{
    display:block;
    opacity:1;
    transform:translate(-50%,-50%) scale(1);
}

.popup h2{
    color:#ff69b4;
    font-family:'Dancing Script';
}

/* 💖 KALP */
.heart{
    position:absolute;
    color:pink;
    animation:fall 5s linear infinite;
}
@keyframes fall{
    0%{top:-10%;}
    100%{top:110%;}
}

/* ⚡ */
@keyframes fadeIn{
    from{opacity:0;transform:translate(-50%,-60%);}
    to{opacity:1;transform:translate(-50%,-50%);}
}
@keyframes float{
    0%{transform:translateY(0);}
    50%{transform:translateY(-8px);}
    100%{transform:translateY(0);}
}
@keyframes shake{
    0%{transform:translate(-50%,-50%) translateX(0);}
    25%{transform:translate(-50%,-50%) translateX(-6px);}
    50%{transform:translate(-50%,-50%) translateX(6px);}
    75%{transform:translate(-50%,-50%) translateX(-6px);}
    100%{transform:translate(-50%,-50%) translateX(0);}
}
</style>
</head>

<body>

<canvas id="stars"></canvas>

<div class="login-container" id="loginScreen">
    <div class="lock-icon">🔐</div>
    <h1 class="title">Gizli Alan</h1>
    <p class="subtitle">Sadece sana özel erişim</p>

    <input type="password" id="password" placeholder="Şifreyi gir...">
    <button id="loginBtn">Kilidi Aç 💋</button>
    <div id="error"></div>
</div>

<div class="main-content" id="mainContent">

<div class="header">
<h1>Hoş geldin gönlümün sultanı 🫠🤍</h1>
</div>

<div class="time">
<span id="days">0</span>g 
<span id="hours">0</span>s 
<span id="minutes">0</span>d 
<span id="seconds">0</span>sn
</div>

<div class="music-player">
<h3>🎵 Maşallah 🎵</h3>
<div class="lyrics" id="typeText"></div>

<iframe width="300" height="170"
src="https://www.youtube.com/embed/1n7E5QZq8H0?autoplay=1&loop=1&playlist=1n7E5QZq8H0"
allow="autoplay"></iframe>
</div>

<div class="slider">
<img id="slide" src="foto1.jpg">
</div>

<button class="surprise-btn" onclick="surprise()">🎁 Sürpriz</button>

</div>

<div class="popup" id="popup">
<h2>💖 Sürpriz 💖</h2>
<p>ömrümmmm bebeğimm 
Ben seni çok ama çok seviom🫠
Biz senle kavga edelim tartışalım ama sonra barışalım ben seni çok seviomm ömrümm 
Ben ömrümün sonuna kadar seni seveceğim ve seninle evlenemezsen giyeceğim tek şey beyaz kefen olacak;)

Ömrümmmm ben çok seviomm kurban olduğummmm beni sensiz bırakma🫠
Sen ne kadar kızsanda etsende ama şunu unutma ben seni asla ve asla bırakmam ben seni iyi günde de kötü günde de yanında olacamm ve asla bırakmayacam canımı iste canım sana kurban olsun </p>
<button onclick="closePopup()">Kapat</button>
</div>

<script>

/* 🔐 FIXED LOGIN */
const passwordInput = document.getElementById("password");
const loginBtn = document.getElementById("loginBtn");
const loginScreen = document.getElementById("loginScreen");
const mainContent = document.getElementById("mainContent");
const errorText = document.getElementById("error");

loginBtn.addEventListener("click", checkPassword);
passwordInput.addEventListener("keypress", e=>{
if(e.key==="Enter") checkPassword();
});

function checkPassword(){
let pass = passwordInput.value.trim();

if(pass==="16.04.2026"){
loginScreen.style.opacity="0";
setTimeout(()=>{
loginScreen.style.display="none";
mainContent.classList.add("show");
startCounter();
typeWriter();
},500);
}else{
errorText.innerText="Yanlış şifre 💔";
loginScreen.classList.add("shake");
setTimeout(()=>loginScreen.classList.remove("shake"),400);
}
}

/* ⏱ */
let start=new Date(2026,3,16);
function startCounter(){
setInterval(()=>{
let now=new Date();
let diff=(now-start)/1000;
days.innerText=Math.floor(diff/86400);
hours.innerText=Math.floor(diff%86400/3600);
minutes.innerText=Math.floor(diff%3600/60);
seconds.innerText=Math.floor(diff%60);
},1000);
}

/* 💌 */
let msg="Bir şikayetim var bu kadar güzel olunmaz ki...🫠 bir delikanlı kalbinden böyle vurulmaz...";
let i=0;
function typeWriter(){
if(i<msg.length){
typeText.innerHTML+=msg[i];
i++;
setTimeout(typeWriter,50);
}
}

/* 📸 */
let fotos=["foto1.jpg","foto2.jpg","foto3.jpg"];
let x=0;
setInterval(()=>{
x=(x+1)%fotos.length;
slide.src=fotos[x];
},3000);

/* 💖 OPTIMIZED */
setInterval(()=>{
let h=document.createElement("div");
h.className="heart";
h.innerHTML="💖";
h.style.left=Math.random()*100+"vw";
document.body.appendChild(h);
setTimeout(()=>h.remove(),5000);
},800);

/* 🎁 */
function surprise(){
popup.classList.add("show");
}
function closePopup(){
popup.classList.remove("show");
}

/* 🌌 */
const c=stars;
const ctx=c.getContext("2d");
c.width=innerWidth;
c.height=innerHeight;

let s=[];
for(let i=0;i<100;i++){
s.push({x:Math.random()*c.width,y:Math.random()*c.height,r:Math.random()*2});
}

function draw(){
ctx.clearRect(0,0,c.width,c.height);
ctx.fillStyle="white";
s.forEach(a=>{
ctx.beginPath();
ctx.arc(a.x,a.y,a.r,0,Math.PI*2);
ctx.fill();
a.y+=0.3;
if(a.y>c.height)a.y=0;
});
requestAnimationFrame(draw);
}
draw();

</script>

</body>
</html>

<!DOCTYPE html>
<html lang="uz">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Sanjarbek & Malikaxon</title>

<link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;600&family=Poppins:wght@300;400;500&display=swap" rel="stylesheet">

<link rel="stylesheet" href="style.css">
</head>

<body>

<div id="particles"></div>

<section class="hero">

<div class="overlay"></div>

<div class="content">

<h3>TO‘Y TAKLIFNOMASI</h3>

<h1>SANJARBEK</h1>

<div class="and">&</div>

<h1>MALIKAXON</h1>

<p>Hurmatli mehmon!</p>

<p>Sizni nikoh to‘yimizga taklif etamiz.</p>

<h2>05 • AVGUST • 2026</h2>

<a href="#countdown" class="btn">Taklifnomani ochish</a>

</div>

</section>

<section id="countdown">

<h2>To‘ygacha qolgan vaqt</h2>

<div id="timer"></div>

</section>

<section>

<h2>Manzil</h2>

<a class="btn"
href="https://maps.google.com/?q=39.994284,66.229107">
Marshrutni ochish
</a>

</section>

<script src="script.js"></script>

</body>
</html>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

html{
    scroll-behavior:smooth;
}

body{
    background:#071521;
    color:#fff;
    font-family:'Poppins',sans-serif;
    overflow-x:hidden;
}

.hero{
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    text-align:center;
    position:relative;
    background:linear-gradient(rgba(0,0,0,.45),rgba(0,0,0,.65)),
    url("images/background.jpg");
    background-size:cover;
    background-position:center;
}

.overlay{
    position:absolute;
    inset:0;
    background:rgba(0,0,0,.25);
    backdrop-filter:blur(2px);
}

.content{
    position:relative;
    z-index:2;
    animation:fadeUp 2s ease;
    padding:20px;
}

.content h3{
    color:#d4af37;
    letter-spacing:6px;
    margin-bottom:20px;
    font-size:18px;
}

.content h1{
    font-family:'Cinzel',serif;
    font-size:64px;
    color:#f7d774;
    text-shadow:0 0 18px rgba(212,175,55,.35);
}

.and{
    font-size:42px;
    color:white;
    margin:10px 0;
}

.content p{
    margin-top:15px;
    font-size:20px;
    color:#f5f5f5;
}

.content h2{
    margin-top:35px;
    color:#d4af37;
    font-size:34px;
}

.btn{
    display:inline-block;
    margin-top:40px;
    padding:16px 42px;
    border:2px solid #d4af37;
    color:#d4af37;
    text-decoration:none;
    border-radius:50px;
    transition:.35s;
}

.btn:hover{
    background:#d4af37;
    color:#071521;
    box-shadow:0 0 30px #d4af37;
}

section{
    padding:100px 20px;
    text-align:center;
}

section h2{
    color:#d4af37;
    font-size:42px;
    margin-bottom:30px;
    font-family:'Cinzel',serif;
}

#timer{
    display:flex;
    justify-content:center;
    gap:20px;
    flex-wrap:wrap;
    font-size:30px;
    color:#fff;
}

.time-box{
    width:130px;
    padding:20px;
    border:1px solid rgba(212,175,55,.4);
    border-radius:18px;
    background:rgba(255,255,255,.05);
    backdrop-filter:blur(8px);
}

@keyframes fadeUp{
    from{
        opacity:0;
        transform:translateY(60px);
    }
    to{
        opacity:1;
        transform:translateY(0);
    }
}

@media(max-width:768px){

.content h1{
    font-size:42px;
}

.content h2{
    font-size:26px;
}

.content p{
    font-size:17px;
}

.time-box{
    width:100px;
}

}
// ===== To'y sanasi =====
const weddingDate = new Date("August 5, 2026 18:00:00").getTime();

const timer = document.getElementById("timer");

function updateTimer() {

    const now = new Date().getTime();
    const distance = weddingDate - now;

    if (distance <= 0) {
        timer.innerHTML = "<h2>🎉 To'y boshlandi!</h2>";
        return;
    }

    const days = Math.floor(distance / (1000 * 60 * 60 * 24));
    const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
    const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
    const seconds = Math.floor((distance % (1000 * 60)) / 1000);

    timer.innerHTML = `
    <div class="time-box">
        <h1>${days}</h1>
        <p>Kun</p>
    </div>

    <div class="time-box">
        <h1>${hours}</h1>
        <p>Soat</p>
    </div>

    <div class="time-box">
        <h1>${minutes}</h1>
        <p>Daqiqa</p>
    </div>

    <div class="time-box">
        <h1>${seconds}</h1>
        <p>Soniya</p>
    </div>
    `;
}

setInterval(updateTimer, 1000);
updateTimer();


// ===== Oltin zarralar =====

const particles = document.getElementById("particles");

for (let i = 0; i < 60; i++) {

    let dot = document.createElement("span");

    dot.style.position = "fixed";
    dot.style.width = "4px";
    dot.style.height = "4px";
    dot.style.borderRadius = "50%";
    dot.style.background = "#d4af37";

    dot.style.left = Math.random() * 100 + "vw";
    dot.style.top = Math.random() * 100 + "vh";

    dot.style.opacity = Math.random();

    dot.style.animation = `float ${5 + Math.random() * 10}s linear infinite`;

    particles.appendChild(dot);

}
#particles{
    position:fixed;
    inset:0;
    pointer-events:none;
    overflow:hidden;
    z-index:1;
}

@keyframes float{

0%{
transform:translateY(0);
opacity:.2;
}

50%{
opacity:1;
}

100%{
transform:translateY(-120vh);
opacity:0;
}

}
<!-- Sevgi hikoyasi -->
<section class="story">

<h2>❤️ Bizning hikoyamiz</h2>

<div class="story-box">

<p>
Har bir go'zal hikoya tasodifdan boshlanadi...
Bugun esa biz hayotimizning eng baxtli kunini siz bilan birga nishonlashni istaymiz.
</p>

</div>

</section>

<!-- To'y dasturi -->

<section class="program">

<h2>📅 To'y dasturi</h2>

<div class="timeline">

<div class="item">
<span>17:00</span>
<p>Mehmonlarni kutib olish</p>
</div>

<div class="item">
<span>18:00</span>
<p>Nikoh marosimi</p>
</div>

<div class="item">
<span>19:00</span>
<p>Bayram dasturining boshlanishi</p>
</div>

<div class="item">
<span>22:00</span>
<p>Tort kesish marosimi</p>
</div>

</div>

</section>

<!-- Manzil -->

<section class="location">

<h2>📍 Manzil</h2>

<iframe
src="https://maps.google.com/maps?q=39.994284,66.229107&z=15&output=embed"
loading="lazy">
</iframe>

<br><br>

<a
class="btn"
href="https://maps.google.com/?q=39.994284,66.229107"
target="_blank">

Marshrutni ochish

</a>

</section>
.story-box{

max-width:800px;
margin:auto;
padding:40px;

background:rgba(255,255,255,.05);

border:1px solid rgba(212,175,55,.35);

border-radius:20px;

backdrop-filter:blur(8px);

line-height:1.9;

}

.timeline{

max-width:700px;

margin:auto;

}

.item{

display:flex;

justify-content:space-between;

align-items:center;

padding:20px;

margin:15px 0;

border-left:3px solid #d4af37;

background:rgba(255,255,255,.04);

border-radius:12px;

}

.item span{

font-size:22px;

font-weight:bold;

color:#d4af37;

}

.location iframe{

width:100%;

height:400px;

border:none;

border-radius:20px;

box-shadow:0 0 25px rgba(212,175,55,.3);

}
<!-- GALEREYA -->

<section class="gallery">

<h2>📸 Bizning suratlarimiz</h2>

<div class="gallery-grid">

<img src="images/photo1.jpg">
<img src="images/photo2.jpg">
<img src="images/photo3.jpg">
<img src="images/photo4.jpg">
<img src="images/photo5.jpg">
<img src="images/photo6.jpg">

</div>

</section>


<!-- RSVP -->

<section class="rsvp">

<h2>Sizni kutamiz ❤️</h2>

<p>To'yimizga tashrif buyurasizmi?</p>

<div class="buttons">

<button class="yes">
✅ Albatta boraman
</button>

<button class="no">
❌ Bora olmayman
</button>

</div>

</section>


<!-- Footer -->

<footer>

<h2>SANJARBEK ❤️ MALIKAXON</h2>

<p>05 • AVGUST • 2026</p>

</footer>
.gallery{

padding:100px 20px;

}

.gallery-grid{

display:grid;

grid-template-columns:repeat(auto-fit,minmax(220px,1fr));

gap:20px;

margin-top:40px;

}

.gallery img{

width:100%;

border-radius:20px;

transition:.4s;

cursor:pointer;

border:2px solid rgba(212,175,55,.25);

}

.gallery img:hover{

transform:scale(1.05);

box-shadow:0 0 30px #d4af37;

}

.rsvp{

text-align:center;

padding:120px 20px;

}

.buttons{

margin-top:40px;

display:flex;

justify-content:center;

gap:20px;

flex-wrap:wrap;

}

.buttons button{

padding:18px 35px;

font-size:18px;

border:none;

border-radius:40px;

cursor:pointer;

transition:.35s;

}

.yes{

background:#d4af37;

color:#071521;

}

.no{

background:#222;

color:white;

}

.buttons button:hover{

transform:translateY(-5px);

box-shadow:0 0 25px #d4af37;

}

footer{

padding:60px;

text-align:center;

border-top:1px solid rgba(212,175,55,.3);

background:#04101b;

}

footer h2{

font-family:"Cinzel",serif;

color:#d4af37;

margin-bottom:10px;

}
document.querySelector(".yes").onclick = () => {
    alert("Tashrifingiz uchun rahmat! Sizni to'yimizda kutamiz ❤️");
};

document.querySelector(".no").onclick = () => {
    alert("Afsus! Umid qilamizki, keyingi uchrashuvlarda ko'rishamiz.");
};
<!-- Loading Screen -->
<div id="loader">
    <div class="gold-circle"></div>
    <h2>SANJARBEK ❤️ MALIKAXON</h2>
</div>

<!-- Musiqa -->
<audio id="music" loop>
    <source src="music/wedding.mp3" type="audio/mpeg">
</audio>

<button id="musicBtn">🎵</button>
/* Loading */

#loader{
position:fixed;
top:0;
left:0;
width:100%;
height:100%;
background:#071521;
display:flex;
flex-direction:column;
justify-content:center;
align-items:center;
z-index:9999;
transition:1.5s;
}

.gold-circle{
width:90px;
height:90px;
border:4px solid #d4af37;
border-top:4px solid transparent;
border-radius:50%;
animation:spin 2s linear infinite;
}

#loader h2{
margin-top:30px;
color:#d4af37;
font-family:"Cinzel",serif;
}

@keyframes spin{
100%{
transform:rotate(360deg);
}
}

/* Music Button */

#musicBtn{
position:fixed;
bottom:25px;
right:25px;
width:60px;
height:60px;
border-radius:50%;
border:none;
font-size:25px;
cursor:pointer;
background:#d4af37;
box-shadow:0 0 20px gold;
z-index:999;
transition:.3s;
}

#musicBtn:hover{
transform:scale(1.1);
}

/* Scroll */

::-webkit-scrollbar{
width:8px;
}

::-webkit-scrollbar-thumb{
background:#d4af37;
border-radius:20px;
}

::-webkit-scrollbar-track{
background:#071521;
}
// Loading

window.onload = () =>{

setTimeout(()=>{

document.getElementById("loader").style.opacity="0";

setTimeout(()=>{

document.getElementById("loader").style.display="none";

},1000);

},2500);

}


// Music

const music=document.getElementById("music");

const musicBtn=document.getElementById("musicBtn");

let playing=false;

musicBtn.onclick=()=>{

if(!playing){

music.play();

musicBtn.innerHTML="🔊";

playing=true;

}else{

music.pause();

musicBtn.innerHTML="🎵";

playing=false;

}

}

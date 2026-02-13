<!DOCTYPE html>
<html>
<head>

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>For You ❤️</title>

<style>

body{
margin:0;
overflow:hidden;
background:linear-gradient(to bottom right,#ff7eb3,#ff758c);
font-family:Arial;
}

/* Floating Hearts */
.heart{
position:absolute;
color:rgba(255,255,255,0.7);
font-size:20px;
animation:float 10s linear infinite;
}

@keyframes float{
from{transform:translateY(100vh);}
to{transform:translateY(-10vh);}
}

/* PAPER LETTER POPUP */
.popup{
position:fixed;
top:50%;
left:50%;
transform:translate(-50%,-50%);
background:#fffaf0;
width:90%;
max-width:420px;
padding:25px;
border-radius:15px;
box-shadow:0 15px 40px rgba(0,0,0,0.3);
text-align:center;
z-index:10;
}

.popup p{
text-align:left;
line-height:1.5;
font-size:15px;
}

.popup button{
margin-top:20px;
padding:10px 25px;
border:none;
border-radius:25px;
background-color:#ff4e78;
color:white;
}

/* Surprise Main */
.main{
position:absolute;
top:50%;
left:50%;
transform:translate(-50%,-50%);
color:white;
text-align:center;
display:none;
width:100%;
}

/* Sunflower Glow */
.sunflower{
font-size:70px;
animation:glow 2s ease-in-out infinite alternate;
}

@keyframes glow{
from{
text-shadow:0 0 10px #fff,0 0 20px #ffd700,0 0 30px #ffea00;
transform:scale(1);
}
to{
text-shadow:0 0 20px #fff,0 0 40px #ffd700,0 0 60px #ffea00;
transform:scale(1.2);
}
}

/* Typing Text */
#typingText{
padding:10px;
font-size:17px;
white-space:pre-line;
}

/* Gallery */
.gallery{
display:flex;
flex-wrap:wrap;
justify-content:center;
gap:10px;
margin-top:20px;
padding:10px;
}

.gallery img{
width:28vw;
max-width:130px;
height:28vw;
max-height:130px;
object-fit:cover;
border-radius:15px;
opacity:0;
transform:scale(0.5);
animation:fadeIn 1s forwards;
}

/* Fade One by One */
.gallery img:nth-child(1){animation-delay:0s;}
.gallery img:nth-child(2){animation-delay:1s;}
.gallery img:nth-child(3){animation-delay:2s;}
.gallery img:nth-child(4){animation-delay:3s;}
.gallery img:nth-child(5){animation-delay:4s;}

@keyframes fadeIn{
to{
opacity:1;
transform:scale(1);
}
}

</style>
</head>

<body>

<!-- MUSIC -->
<audio id="bgMusic" loop>
<source src="music.mp3" type="audio/mpeg">
</audio>

<!-- POPUP LETTER -->
<div class="popup" id="popup">
<h2>Hi My Love ❤️</h2>
<p>
Hi Normelen,<br><br>

It’s been 2 amazing years since we started this journey together.
Through all the ups and downs, challenges and happy moments,
we stayed strong and never gave up on each other.<br><br>

I’m so proud of how far we’ve come, Love.
Thank you for loving me, understanding me,
and always being there beside me no matter what.<br><br>

Our love grew stronger every single day,
and I can’t wait to make more memories with you.<br><br>

Click the button below for a little surprise 🌻
</p>

<button onclick="closePopup()">Open Surprise ❤️</button>
</div>

<!-- SURPRISE -->
<div class="main" id="main">

<div class="sunflower">🌻</div>

<h2 id="typingText"></h2>

<div class="gallery">
<img src="626474170_1917435798866190_7360438315416646286_n.jpg">
<img src="628462705_876223445242877_4005428426257665027_n.jpg">
<img src="631265316_773878738712204_6934332184240382434_n.jpg">
<img src="631079412_1233055554890720_254445144777351985_n.jpg">
<img src="626755290_1304506508151559_4620056559209312483_n.jpg">
</div>

</div>

<script>

/* Floating Hearts */
for(let i=0;i<25;i++){
const heart=document.createElement("div");
heart.classList.add("heart");
heart.innerHTML="❤";
heart.style.left=Math.random()*100+"vw";
heart.style.animationDuration=(5+Math.random()*5)+"s";
document.body.appendChild(heart);
}

/* Popup Open */
function closePopup(){
document.getElementById("popup").style.display="none";
document.getElementById("main").style.display="block";
document.getElementById("bgMusic").play();
typeWriter();
}

/* 2 YEAR LETTER TYPE EFFECT */
let i=0;

let text = `Hi Love,

It has already been 2 beautiful years since we started this journey together.

Two years of laughter, tears, late-night talks, misunderstandings,
and countless memories that I will always treasure in my heart.

Through every up and down,
we chose each other.
We stayed.
We fought for us.

Babi, thank you for being my safe place.

We are not perfect,
but what we have is real.

Our love continues to grow stronger every single day.

I will always choose you — in every lifetime.

Happy Valentine's Day, Love 💗`;

function typeWriter(){
if(i < text.length){
document.getElementById("typingText").innerHTML += text.charAt(i);
i++;
setTimeout(typeWriter,40);
}
}

</script>

</body>
</html>

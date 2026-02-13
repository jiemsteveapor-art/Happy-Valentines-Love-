
<html>
<head>

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>For You ❤️</title>

<style>

body{
margin:0;
background:linear-gradient(135deg,#f6c1cc,#e8a2b7,#f4b6c2);
font-family:Arial;
overflow-x:hidden;
}

/* Floating Hearts */
.heart{
position:absolute;
color:rgba(255,255,255,0.7);
font-size:18px;
animation:float 10s linear infinite;
}
@keyframes float{
from{transform:translateY(100vh);}
to{transform:translateY(-10vh);}
}

/* Popup */
.popup{
position:fixed;
top:50%;
left:50%;
transform:translate(-50%,-50%);
background:#fff8f8;
width:90%;
max-width:400px;
padding:20px;
border-radius:20px;
box-shadow:0 10px 25px rgba(0,0,0,0.3);
text-align:center;
z-index:10;
}

/* Button */
.popup button{
margin-top:20px;
padding:10px 25px;
border:none;
border-radius:25px;
background:#d96b8a;
color:white;
}

/* Main */
.main{
display:none;
padding:15px;
text-align:center;
}

/* Sunflower */
.sunflower{
font-size:65px;
animation:glow 2s ease-in-out infinite alternate;
}
@keyframes glow{
from{text-shadow:0 0 10px #fff,0 0 20px #ffd700;}
to{text-shadow:0 0 20px #fff,0 0 40px #ffd700;transform:scale(1.1);}
}

/* Paper Letter */
#typingText{
background:#fff8f8;
color:#333;
padding:15px;
border-radius:15px;
font-family:'Courier New', monospace;
text-align:left;
white-space:pre-line;
margin:15px auto;
max-width:95%;
}

/* POLAROID STYLE */
.gallery{
display:flex;
flex-wrap:wrap;
justify-content:center;
gap:15px;
margin-top:20px;
}

.polaroid{
background:white;
padding:10px 10px 25px 10px;
width:120px;
border-radius:5px;
box-shadow:0 5px 15px rgba(0,0,0,0.2);
transform:rotate(-2deg);
opacity:0;
animation:fadeIn 1s forwards;
position:relative;
}

.polaroid img{
width:100%;
height:110px;
object-fit:cover;
}

/* Tape Design */
.polaroid::before{
content:'';
width:40px;
height:15px;
background:rgba(255,255,255,0.6);
position:absolute;
top:-8px;
left:35px;
transform:rotate(-10deg);
}

/* Fade One by One */
.polaroid:nth-child(1){animation-delay:1s;}
.polaroid:nth-child(2){animation-delay:2s;}
.polaroid:nth-child(3){animation-delay:3s;}
.polaroid:nth-child(4){animation-delay:4s;}
.polaroid:nth-child(5){animation-delay:5s;}

@keyframes fadeIn{
to{
opacity:1;
transform:scale(1) rotate(0deg);
}
}

/* MOBILE */
@media(max-width:600px){
.polaroid{
width:100px;
}
.polaroid img{
height:90px;
}
.sunflower{
font-size:55px;
}
}

</style>
</head>

<body>

<audio id="bgMusic" loop>
<source src="music.mp3" type="audio/mpeg">
</audio>

<div class="popup" id="popup">
<h3>Hi My Love ❤️</h3>
<p>

Hi Normelen,

Wala koy regalo for you but i made this just for you love

Grabu it's been 2 amazing years since we started that first conversation
Through all the ups and downs, challenges and happy moments,
we stayed strong and never gave up on each other.<br><br>

I'm so proud of how far we've come, love.
Thank for loving me, understanding me miskan badlongon ko
and always being there deside me no matter what.<br><br>

Our love grew stronger every single day,
and I can't wait to make more memories with you.<br><br>

I have little surprised for you click the button🌻

</p>

<button onclick="closePopup()">Open Surprise ❤️</button>
</div>

<div class="main" id="main">

<div class="sunflower">🌻</div>

<div id="typingText"></div>

<div class="gallery">

<div class="polaroid">
<img src="626474170_1917435798866190_7360438315416646286_n.jpg">
</div>

<div class="polaroid">
<img src="628462705_876223445242877_4005428426257665027_n.jpg">
</div>

<div class="polaroid">
<img src="631265316_773878738712204_6934332184240382434_n.jpg">
</div>

<div class="polaroid">
<img src="631079412_1233055554890720_254445144777351985_n.jpg">
</div>

<div class="polaroid">
<img src="626755290_1304506508151559_4620056559209312483_n.jpg">
</div>

</div>

</div>

<script>

/* Hearts */
for(let i=0;i<20;i++){
const heart=document.createElement("div");
heart.classList.add("heart");
heart.innerHTML="❤";
heart.style.left=Math.random()*100+"vw";
heart.style.animationDuration=(5+Math.random()*5)+"s";
document.body.appendChild(heart);
}

function closePopup(){
document.getElementById("popup").style.display="none";
document.getElementById("main").style.display="block";
document.getElementById("bgMusic").play();
typeWriter();
}

let i=0;
let text=`Love,

Where you overthink and lose faith in us always look back
from where we started💗

Happy Valentine's Day 💗`;

let speed=45;

function typeWriter(){
if(i<text.length){
document.getElementById("typingText").innerHTML+=text.charAt(i);
i++;
setTimeout(typeWriter,speed);
}
}

</script>

</body>
</html>

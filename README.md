
<html>
  <meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<head>
<meta charset="UTF-8">
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

/* Popup */
.popup{
position:fixed;
top:50%;
left:50%;
transform:translate(-50%,-50%);
background:white;
width:90%;
max-width:500px;
max-height:90vh;
overflow-y:auto;
padding:20px;
border-radius:20px;
box-shadow:0 15px 40px rgba(0,0,0,0.3);
text-align:center;
animation:fadeIn 1.5s ease-in-out;
z-index:10;
}
@keyframes fadeIn{
from{opacity:0;transform:translate(-50%,-60%);}
to{opacity:1;transform:translate(-50%,-50%);}
}
.popup button{
margin-top:20px;
padding:10px 25px;
border:none;
border-radius:25px;
background-color:#ff4e78;
color:white;
cursor:pointer;
}
.popup button:hover{
background-color:#ff1e56;
transform:scale(1.1);
}

/* Surprise Main */
.popup button{
margin-top:20px;
padding:12px 30px;
font-size:16px;
border:none;
border-radius:25px;
background-color:#ff4e78;
color:white;
cursor:pointer;
}

/* Glowing Sunflower */
.sunflower{
font-size:60px;
animation:glow 2s ease-in-out infinite alternate;
}
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

/* Gallery */
.gallery{
display:flex;
flex-wrap:wrap;
justify-content:center;
gap:15px;
margin-top:20px;
}
.gallery img{
width:28vw;
height:28vw;
max-width:120px;
max-height:120px;
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
  
}
@keyframes pop{
to{
opacity:1;
transform:scale(1);
}
}
</style>
.letter{
background:#fffaf0;
padding:15px;
border-radius:10px;
box-shadow:0 0 20px rgba(0,0,0,0.2);
font-family:'Courier New', monospace;
border:2px solid #f4d19b;
background-image:linear-gradient(#fdf6e3 1px, transparent 1px);
background-size:100% 25px;
text-align:left;
color:#444;
line-height:1.6;
height:auto;
max-height:60vh;
overflow-y:auto;
font-size:14px;
}


</head>

<body>

<!-- MUSIC -->
<audio id="bgMusic" loop>
<source src="music.mp3" type="audio/mpeg">
</audio>

<!-- POPUP -->
<div class="popup" id="popup">

<div class="letter">
<h2>Hi My Love ❤️</h2>

<p id="letterText"></p>

<button onclick="closePopup()">Open Surprise ❤️</button>

</div>

</div>

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

<h1 id="typingText"></h1>

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

/* Typing Text */
let i=0;
let text="You are my sunshine 🌻 Thank you for making my life beautiful ❤️";
let speed=60;

function typeWriter(){
if(i<text.length){
document.getElementById("typingText").innerHTML+=text.charAt(i);
i++;
setTimeout(typeWriter,speed);
}
}
let j=0;
let message="Hi Normelen,\n\nIt’s been 2 amazing years since we started this journey together.\nThrough all the ups and downs, we stayed strong and never gave up on each other.\n\nI’m so proud of how far we've come, Love.\nThank you for always being there beside me no matter what.\n\nOur love grew stronger every single day,\nand I can’t wait to make more memories with you.\n\nClick the button below for a little surprise 🌻";

function typeLetter(){
if(j<message.length){
document.getElementById("letterText").innerHTML+=message.charAt(j);
j++;
setTimeout(typeLetter,40);
}
}

window.onload=typeLetter;

</script>

</body>

# Happy-Valentines-Love-


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
cursor:pointer;
transition:0.3s;
}

.polaroid:hover{
transform:scale(1.05);
}

.polaroid img{
width:100%;
height:110px;
object-fit:cover;
}

/* Tape */
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

/* ZOOM OVERLAY */
.zoomOverlay{
position:fixed;
top:0;
left:0;
width:100%;
height:100%;
background:rgba(0,0,0,0.8);
display:none;
justify-content:center;
align-items:center;
z-index:100;
}

.zoomOverlay img{
max-width:90%;
max-height:90%;
border-radius:10px;
animation:zoomIn 0.4s ease;
}

@keyframes zoomIn{
from{transform:scale(0.7); opacity:0;}
to{transform:scale(1); opacity:1;}
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

Wala koy regalo for you but i made this just for you love 💗

Grabe it's been 2 amazing years since we started that first conversation.
Through all the ups and downs, challenges and happy moments,
we stayed strong and never gave up on each other.

I'm so proud of how far we've come love.
Thank you for loving me, understanding me miskan badlongon ko,
and always being there beside me no matter what.

I have little surprise for you click the button 🌻

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

<!-- ZOOM CONTAINER -->
<div class="zoomOverlay" id="zoomOverlay" onclick="closeZoom()">
<img id="zoomedImg">
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

/* Typing */
let i=0;
let text=`Hi Love,

When you overthink and lose faith in us,
always look back from where we started 💗

Happy Valentine's Day babi 💗`;

let speed=45;

function typeWriter(){
if(i<text.length){
document.getElementById("typingText").innerHTML+=text.charAt(i);
i++;
setTimeout(typeWriter,speed);
}
}

/* IMAGE ZOOM */
const polaroids = document.querySelectorAll(".polaroid img");
const zoomOverlay = document.getElementById("zoomOverlay");
const zoomedImg = document.getElementById("zoomedImg");

polaroids.forEach(img=>{
img.addEventListener("click", function(){
zoomOverlay.style.display="flex";
zoomedImg.src=this.src;
});
});

function closeZoom(){
zoomOverlay.style.display="none";
}

</script>

</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta charset="UTF-8">
<title>For Normalen ❤️</title>

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:'Courier New', monospace;
}

body{
background:#000;
overflow:hidden;
text-align:center;
color:#000;
}

/* 🌻 Sunflower Glow */
.sunflower{
position:fixed;
top:10px;
right:10px;
width:80px;
animation:glow 2s infinite alternate;
z-index:5;
}

@keyframes glow{
from{filter:drop-shadow(0 0 5px yellow);}
to{filter:drop-shadow(0 0 25px gold);}
}

/* 📜 Letter Popup */
#popup{
position:fixed;
top:0;
left:0;
width:100%;
height:100%;
background:rgba(0,0,0,0.8);
display:flex;
justify-content:center;
align-items:center;
padding:20px;
z-index:10;
}

.letter{
background:#fffaf0;
padding:20px;
border-radius:10px;
width:90%;
max-width:400px;
min-height:300px;
box-shadow:0 0 20px rgba(0,0,0,0.3);
background-image:linear-gradient(#faf3dd 1px, transparent 1px);
background-size:100% 30px;
text-align:left;
line-height:30px;
}

button{
margin-top:20px;
padding:10px 20px;
border:none;
background:pink;
border-radius:5px;
}

/* 🎞️ Slideshow */
.slideshow{
position:fixed;
top:0;
left:0;
width:100%;
height:100%;
display:none;
justify-content:center;
align-items:center;
background:#000;
}

.slide{
position:absolute;
max-width:90%;
max-height:80%;
opacity:0;
transition:opacity 2s;
}

.show{
opacity:1;
}

</style>
</head>

<body>

<audio autoplay loop>
<source src="music.mp3" type="audio/mpeg">
</audio>

<img class="sunflower" src="https://cdn-icons-png.flaticon.com/512/766/766017.png">

<div id="popup">
<div class="letter">
<p id="typeText"></p>
<button onclick="startSurprise()">Open Surprise 💌</button>
</div>
</div>

<div class="slideshow" id="slides">
<img class="slide" src="1.jpg">
<img class="slide" src="2.jpg">
<img class="slide" src="3.jpg">
<img class="slide" src="4.jpg">
<img class="slide" src="5.jpg">
</div>

<script>

<script>

let text = `Hi Love,

It has already been 2 beautiful years since we started this journey together.

Two years of laughter, tears, late-night talks, misunderstandings, and countless memories that I will always treasure in my heart.

Through every up and down, every challenge that tried to test us, we chose each other. We stayed. We fought for us. And that means everything to me.

Babi, thank you for being my safe place.
Thank you for loving me even on days when I am difficult to love.
Thank you for your patience, your understanding, and your soft heart.

We are not perfect, but what we have is real.
And every single day, our love continues to grow stronger, deeper, and more beautiful.

I am so grateful that it’s you.
I will always choose you — in every lifetime, in every version of our story.

Happy Valentine’s Day, my love 💗`;

let i = 0;

function typeEffect(){
if(i < text.length){
document.getElementById("typeText").innerHTML += text.charAt(i);
i++;
setTimeout(typeEffect,40); // you can change speed here
}
}

typeEffect();

/* 🎞️ Fade Slideshow */
function startSurprise(){
document.getElementById("popup").style.display="none";
let slides=document.getElementById("slides");
slides.style.display="flex";

let imgs=document.querySelectorAll(".slide");
let index=0;

function showNext(){
imgs.forEach(img=>img.classList.remove("show"));
imgs[index].classList.add("show");
index=(index+1)%imgs.length;
}
showNext();
setInterval(showNext,3000);
}

</script>

</body>
</html>

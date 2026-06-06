<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Birthday Tannu ❤️</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

body{
    font-family:Arial,sans-serif;
    overflow:hidden;
}

.slide1{
    width:100vw;
    height:100vh;
    background:linear-gradient(135deg,#ffd6e7,#ffe8f0);
    display:flex;
    align-items:center;
    justify-content:center;
    padding:20px;
}

.slide1-container{
    width:100%;
    height:100%;
    display:flex;
    align-items:center;
    justify-content:space-between;
}

.hero-photo{
    width:45%;
    height:95vh;
    object-fit:contain;
    border-radius:25px;
    animation:float 4s ease-in-out infinite;
}

.hero-text{
    width:50%;
    text-align:center;
    padding:20px;
}

.hero-text h1{
    font-size:4rem;
    color:#ff4081;
    margin-bottom:20px;
}

.hero-text p{
    font-size:1.5rem;
    color:#555;
    margin-bottom:40px;
}

.ready-btn{
    padding:18px 45px;
    font-size:1.5rem;
    border:none;
    border-radius:50px;
    background:#ff4081;
    color:white;
    cursor:pointer;
    animation:shake 1s infinite;
    box-shadow:0 0 20px rgba(255,64,129,0.5);
}

.ready-btn:hover{
    transform:scale(1.08);
}

@keyframes shake{
    0%{transform:translateX(0);}
    25%{transform:translateX(-4px);}
    50%{transform:translateX(4px);}
    75%{transform:translateX(-4px);}
    100%{transform:translateX(0);}
}

@keyframes float{
    0%,100%{transform:translateY(0);}
    50%{transform:translateY(-12px);}
}

.sparkle{
    position:absolute;
    font-size:30px;
    pointer-events:none;
    animation:burst 1.2s forwards;
}

@keyframes burst{
    from{
        opacity:1;
        transform:translate(0,0) scale(1);
    }
    to{
        opacity:0;
        transform:translate(var(--x),var(--y)) scale(2);
    }
}

@media(max-width:768px){

.slide1-container{
    flex-direction:column;
}

.hero-photo{
    width:80%;
    height:50vh;
}

.hero-text{
    width:100%;
}

.hero-text h1{
    font-size:2.5rem;
}
}
</style>
</head>

<body>

<section class="slide1">

<div class="slide1-container">

<img src="img4.jpg" alt="Tannu" class="hero-photo">

<div class="hero-text">
    <h1>Happy Birthday Tannu 🎉</h1>

    <p>My Precious Beautiful Girl ❤️</p>

    <button class="ready-btn" onclick="startBirthday()">
        🎁 READY!
    </button>
</div>

</div>

</section>

<script>

function startBirthday(){

const emojis=['✨','🎉','💖','🌸','⭐'];

for(let i=0;i<40;i++){

let sparkle=document.createElement('div');
sparkle.classList.add('sparkle');
sparkle.innerHTML=emojis[Math.floor(Math.random()*emojis.length)];

sparkle.style.left=window.innerWidth/2+'px';
sparkle.style.top=window.innerHeight/2+'px';

sparkle.style.setProperty('--x',
(Math.random()*800-400)+'px');

sparkle.style.setProperty('--y',
(Math.random()*800-400)+'px');

document.body.appendChild(sparkle);

setTimeout(()=>{
sparkle.remove();
},1200);
}

setTimeout(()=>{
alert("Welcome Tannu ❤️");
},1000);

}

</script>

</body>
</html>

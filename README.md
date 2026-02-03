# Giselle-love-of-my-life
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For My Giselle ❤️</title>

<style>
html,body{
    margin:0;
    width:100%;
    height:100%;
    font-family:'Georgia',serif;
    background:radial-gradient(circle at top, #fff5f8, #ffe4ec);
    overflow:hidden;
    display:flex;
    justify-content:center;
    align-items:center;
}

/* Entrance */
#entrance{
    position:fixed;
    inset:0;
    background:white;
    z-index:999;
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
    transition:opacity 1.2s ease;
}

.heart{
    font-size:95px;
    animation:pulse 1.6s infinite;
    cursor:pointer;
}

@keyframes pulse{
    0%{transform:scale(1)}
    50%{transform:scale(1.18)}
    100%{transform:scale(1)}
}

/* Card */
.card{
    width:90vw;
    max-width:380px;
    height:85vh;
    background:linear-gradient(180deg,#ffffff,#fff6f9);
    border-radius:32px;
    padding:26px;
    display:flex;
    flex-direction:column;
    justify-content:space-between;
    text-align:center;
    box-shadow:0 25px 60px rgba(214,51,132,.25);
    border:2px solid #ffd1dc;
    animation:fadeIn 1.2s ease;
}

@keyframes fadeIn{
    from{opacity:0;transform:translateY(20px)}
    to{opacity:1;transform:translateY(0)}
}

h1{
    color:#d63384;
    margin:0;
    letter-spacing:.5px;
}

.subtitle{
    color:#9c4a6a;
    font-style:italic;
    font-size:.95rem;
}

img{
    width:100%;
    border-radius:22px;
    box-shadow:
        0 0 25px rgba(214,51,132,.35),
        0 12px 30px rgba(0,0,0,.25);
    animation:softGlow 3s ease-in-out infinite;
}

@keyframes softGlow{
    0%{box-shadow:0 0 20px rgba(214,51,132,.25)}
    50%{box-shadow:0 0 35px rgba(214,51,132,.5)}
    100%{box-shadow:0 0 20px rgba(214,51,132,.25)}
}

button{
    border:none;
    border-radius:50px;
    padding:15px;
    font-size:1.25rem;
    font-weight:bold;
    cursor:pointer;
    transition:transform .2s ease;
}

button:active{transform:scale(.95)}

#yes{background:#2a9d8f;color:white}
#no{background:#e63946;color:white;font-size:.9rem}

.sparkle{
    position:fixed;
    pointer-events:none;
    animation:fade 1.2s forwards;
}

@keyframes fade{
    to{opacity:0;transform:scale(0)}
}
</style>
</head>

<body>

<!-- MUSIC -->
<iframe id="music" width="0" height="0"
src="https://www.youtube.com/embed/l74uPrL-M6g?enablejsapi=1"
allow="autoplay"></iframe>

<!-- ENTRANCE -->
<div id="entrance">
    <div class="heart" onclick="start()">❤️</div>
    <p style="color:#d63384;font-weight:bold;letter-spacing:2px;">
        FOR GISELLE
    </p>
</div>

<!-- MAIN -->
<div class="card" id="card">
    <div>
        <h1>My Giselle</h1>
        <p class="subtitle">
            You are my favorite place to exist
        </p>
    </div>

    <!-- SAME EMBEDDED IMAGE AS BEFORE -->
    <img src="data:image/jpeg;base64,PASTE_THE_SAME_BASE64_IMAGE_HERE">

    <p style="font-size:1.15rem;line-height:1.6;color:#6b2c43;">
        Every laugh. Every memory.  
        Every moment that feels like home.  
        It’s always been you.
    </p>

    <div>
        <button id="yes" onclick="celebrate()">Yes ❤️</button><br><br>
        <button id="no" onclick="grow()">No</button>
    </div>

    <p style="font-size:.8rem;color:#b23a67;">
        And if I had to choose again — I’d choose you every time
    </p>
</div>

<script>
let size=1.2;

function start(){
    document.getElementById("entrance").style.opacity=0;
    setTimeout(()=>document.getElementById("entrance").remove(),1200);
    document.getElementById("music").src+="&autoplay=1";
    if(navigator.vibrate) navigator.vibrate([30,40,30]);
}

function grow(){
    size+=.3;
    document.getElementById("yes").style.fontSize=size+"rem";
}

function celebrate(){
    document.getElementById("card").innerHTML=`
    <div style="height:100%;display:flex;flex-direction:column;justify-content:center;gap:20px;">
        <h1 style="font-size:3rem;">She Said Yes 🥹</h1>
        <p style="font-size:1.3rem;color:#6b2c43;">
            Giselle, you are my today,  
            my tomorrow,  
            and every dream in between.
        </p>
        <p style="font-style:italic;color:#9c4a6a;">
            I love you — endlessly.
        </p>
        <div style="font-size:60px;">❤️✨❤️</div>
    </div>`;
    setInterval(heartRain,180);
    if(navigator.vibrate) navigator.vibrate([50,80,50]);
}

function heartRain(){
    const h=document.createElement("div");
    h.innerHTML="❤️";
    h.style.position="fixed";
    h.style.left=Math.random()*100+"vw";
    h.style.bottom="-50px";
    h.style.fontSize=(20+Math.random()*15)+"px";
    h.style.transition="4.5s linear";
    document.body.appendChild(h);
    setTimeout(()=>{
        h.style.transform="translateY(-120vh)";
        h.style.opacity=0;
    },50);
    setTimeout(()=>h.remove(),4500);
}

document.addEventListener("touchmove",e=>{
    const s=document.createElement("div");
    s.className="sparkle";
    s.innerHTML="✨";
    s.style.left=e.touches[0].pageX+"px";
    s.style.top=e.touches[0].pageY+"px";
    document.body.appendChild(s);
    setTimeout(()=>s.remove(),1200);
});
</script>

</body>
</html>

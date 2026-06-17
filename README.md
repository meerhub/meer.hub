
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Dark Video Feed</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial, Helvetica, sans-serif;
}

body{
    background:#000;
    color:white;
}

/* ================= BLUR WRAPPER ================= */
#site{
    filter: blur(10px);
    pointer-events:none;
    user-select:none;
}

/* ================= AGE GATE ================= */
#ageGate{
    position:fixed;
    top:0;
    left:0;
    width:100%;
    height:100%;
    display:flex;
    align-items:center;
    justify-content:center;
    z-index:9999;
    background:rgba(0,0,0,0.6);
}

.question{
    position:absolute;
    top:40px;
    text-align:center;
    width:100%;
    font-size:22px;
    font-weight:bold;
}

.question .orange{ color:#ff9800; }
.question .white{ color:white; }

.box{
    background:#111;
    padding:35px;
    border-radius:15px;
    text-align:center;
    border:1px solid #333;
    width:320px;
}

.box button{
    padding:12px 25px;
    margin:10px;
    border:none;
    border-radius:8px;
    cursor:pointer;
    font-size:16px;
}

.yes{ background:#ff9800; color:black; font-weight:bold; }
.no{ background:#d50000; color:white; }

.denied{
    display:none;
    color:red;
    margin-top:10px;
}

/* ================= TOP BAR ================= */

.topbar{
    width:100%;
    height:60px;
    background:#0a0a0a;
    display:flex;
    align-items:center;
    justify-content:space-between;
    padding:0 15px;
    position:sticky;
    top:0;
    border-bottom:1px solid #1c1c1c;
}

.menu{ font-size:30px; color:#ff9800; }

.logo{ font-size:26px; font-weight:bold; }

.logo span{
    background:#ff9800;
    color:black;
    padding:2px 7px;
    border-radius:5px;
}

.icons{ display:flex; gap:15px; font-size:24px; }

/* ================= CATEGORIES ================= */

.categories{
    display:flex;
    overflow-x:auto;
    background:#111;
    border-bottom:1px solid #1e1e1e;
}

.cat{
    padding:14px 18px;
    white-space:nowrap;
    font-size:14px;
}

/* ================= TAGS ================= */

.tags{
    display:flex;
    overflow-x:auto;
    gap:10px;
    padding:12px;
}

.tag{
    background:#171717;
    padding:8px 14px;
    border-radius:40px;
    font-size:13px;
}

/* ================= FEED ================= */

.feed{
    padding:8px;
}

/* CARD */
.card{
    background:#111;
    border-radius:14px;
    overflow:hidden;
    margin-bottom:15px;
    border:1px solid #1f1f1f;
}

/* 🔥 FULL IMAGE FIX (NO CROPPING) */
.thumbnail{
    width:100%;
    height:auto;
    max-height:90vh;
    object-fit:contain;
    background:#000;
}

/* INFO */
.info{
    padding:12px;
}

.title{
    font-size:16px;
    margin-bottom:6px;
}

.meta{
    color:#999;
    font-size:12px;
}

/* FLOAT BUTTON */
.float{
    position:fixed;
    bottom:15px;
    right:15px;
    width:65px;
    height:65px;
    border-radius:50%;
    background:#ff9800;
    color:black;
    display:flex;
    align-items:center;
    justify-content:center;
    font-size:30px;
}

/* ================= MOBILE ================= */

@media(max-width:600px){

    .thumbnail{
        max-height:85vh;
    }

    .title{
        font-size:15px;
    }
}
</style>
</head>

<body>

<!-- AGE GATE -->
<div id="ageGate">

    <div class="question">
        <span class="orange">Are you older than</span>
        <span class="white"> 18?</span>
    </div>

    <div class="box">
        <button class="yes" onclick="allow()">Yes</button>
        <button class="no" onclick="deny()">No</button>
        <div class="denied" id="deniedMsg">Access Denied ❌</div>
    </div>

</div>

<!-- WEBSITE -->
<div id="site">

<div class="topbar">
    <div class="menu">☰</div>
    <div class="logo">Meer.<span>hub</span></div>
    <div class="icons"><div>⌕</div><div>◉</div></div>
</div>

<div class="categories">
    <div class="cat">LIVE</div>
    <div class="cat">TREND</div>
    <div class="cat">NEW</div>
    <div class="cat">POPULAR</div>
</div>

<div class="tags">
    <div class="tag">Funny</div>
    <div class="tag">Gaming</div>
    <div class="tag">Cats</div>
    <div class="tag">Live</div>
</div>

<div class="feed">

    <div class="card">
        <img class="thumbnail" src="IMG_6451.png">
        <div class="info">
            <div class="title">injoy with meer.hub</div>
            <div class="meta">2.3M views • 3 days ago</div>
        </div>
    </div>




    <div class="card">
        <img class="thumbnail" src="pir.jpg">
        <div class="info">
            <div class="title">meer step pirazhn and make her 7izz</div>
            <div class="meta">2.3M views • 3 days ago</div>
        </div>
    </div>

    <div class="card">
        <img class="thumbnail" src="srb.jpg">
        <div class="info">
            <div class="title">meer and milfs in serbia</div>
            <div class="meta">875K views • 1 week ago</div>
        </div>
    </div>

    <div class="card">
        <img class="thumbnail" src="ludo.jpg">
        <div class="info">
            <div class="title">meer step ludo</div>
            <div class="meta">4.1M views • 6 hours ago</div>
        </div>
    </div>

</div>

<div class="float">+</div>

</div>

<script>
function allow(){
    document.getElementById("ageGate").style.display = "none";
    document.getElementById("site").style.filter = "none";
    document.getElementById("site").style.pointerEvents = "auto";
}

function deny(){
    document.getElementById("deniedMsg").style.display = "block";
}
</script>

</body>
</html>

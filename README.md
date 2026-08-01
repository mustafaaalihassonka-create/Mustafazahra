# Mustafazahra
لعبة
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>إلى زهراء ❤️</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700;800&display=swap');

*{
    box-sizing:border-box;
    margin:0;
    padding:0;
}

body{
    font-family:'Cairo',sans-serif;
    min-height:100vh;
    overflow:hidden;
    background:
    radial-gradient(circle at top,#ffb6d9,#ff6fae 45%,#b51659);
    color:white;
}

.screen{
    position:absolute;
    inset:0;
    display:flex;
    justify-content:center;
    align-items:center;
    padding:20px;
    opacity:0;
    visibility:hidden;
    transform:scale(1.08) rotateX(8deg);
    transition:1s ease;
    perspective:1000px;
}

.screen.active{
    opacity:1;
    visibility:visible;
    transform:scale(1) rotateX(0);
}

.card{
    width:min(92%,650px);
    padding:35px 25px;
    text-align:center;
    border-radius:35px;

    background:rgba(255,255,255,.16);
    border:1px solid rgba(255,255,255,.35);
    box-shadow:
    0 25px 70px rgba(100,0,50,.35),
    inset 0 0 30px rgba(255,255,255,.12);

    backdrop-filter:blur(18px);
    -webkit-backdrop-filter:blur(18px);

    transform-style:preserve-3d;
    animation:floatCard 5s ease-in-out infinite;
}

@keyframes floatCard{
    0%,100%{transform:translateY(0) rotateY(0deg)}
    50%{transform:translateY(-10px) rotateY(2deg)}
}

h1{
    font-size:clamp(30px,7vw,55px);
    margin-bottom:15px;
    text-shadow:0 5px 20px rgba(80,0,30,.35);
}

h2{
    font-size:clamp(24px,5vw,40px);
    margin-bottom:20px;
}

.message{
    font-size:clamp(18px,4vw,26px);
    line-height:2;
    margin:20px auto;
}

.highlight{
    color:#fff;
    font-weight:800;
    text-shadow:0 0 15px #ff2e79;
}

.buttons{
    display:flex;
    justify-content:center;
    gap:15px;
    flex-wrap:wrap;
    margin-top:25px;
}

button{
    border:none;
    padding:14px 28px;
    border-radius:50px;
    font-family:inherit;
    font-size:17px;
    font-weight:700;
    cursor:pointer;
    color:#b51659;
    background:white;
    box-shadow:0 10px 30px rgba(90,0,40,.3);
    transition:.3s;
}

button:hover{
    transform:translateY(-5px) scale(1.05);
    box-shadow:0 15px 35px rgba(90,0,40,.45);
}

button:active{
    transform:scale(.94);
}

.yes{
    background:#fff;
}

.love{
    background:linear-gradient(135deg,#ff174f,#ff72ad);
    color:white;
}

.back{
    background:rgba(255,255,255,.2);
    color:white;
    border:1px solid rgba(255,255,255,.4);
}

/* القلوب */

.heart{
    position:fixed;
    bottom:-50px;
    font-size:25px;
    animation:heartFloat linear infinite;
    pointer-events:none;
    z-index:-1;
}

@keyframes heartFloat{
    0%{
        transform:translateY(0) rotate(0);
        opacity:0;
    }
    15%{opacity:1}
    100%{
        transform:translateY(-110vh) rotate(360deg);
        opacity:0;
    }
}

/* الفراشات */

.butterfly{
    position:fixed;
    font-size:35px;
    animation:fly 12s linear infinite;
    pointer-events:none;
    z-index:-1;
}

@keyframes fly{
    0%{
        transform:translate(-10vw,100vh) rotate(0);
    }
    50%{
        transform:translate(50vw,30vh) rotate(20deg);
    }
    100%{
        transform:translate(110vw,-20vh) rotate(-20deg);
    }
}

/* هيلو كاتي كيوت */

.kitty{
    width:150px;
    height:125px;
    background:white;
    border-radius:48% 48% 42% 42%;
    margin:10px auto 25px;
    position:relative;
    box-shadow:0 12px 30px rgba(100,0,50,.25);
    border:4px solid #f2d5df;
}

.kitty:before,
.kitty:after{
    content:"";
    position:absolute;
    top:-20px;
    width:55px;
    height:55px;
    background:white;
    border-top:4px solid #f2d5df;
}

.kitty:before{
    right:5px;
    transform:rotate(35deg);
    border-radius:8px 35px 0 20px;
}

.kitty:after{
    left:5px;
    transform:rotate(-35deg);
    border-radius:35px 8px 20px 0;
}

.eye{
    position:absolute;
    top:52px;
    width:10px;
    height:15px;
    background:#222;
    border-radius:50%;
}

.eye.left{right:42px}
.eye.right{left:42px}

.nose{
    position:absolute;
    top:70px;
    left:50%;
    transform:translateX(-50%);
    width:14px;
    height:10px;
    background:#ffd21f;
    border-radius:50%;
}

.bow{
    position:absolute;
    right:-15px;
    top:20px;
    font-size:40px;
    z-index:3;
}

/* الرقم */

.big-number{
    font-size:clamp(20px,5vw,42px);
    font-weight:800;
    word-break:break-all;
    line-height:1.5;
    color:#fff;
    text-shadow:
    0 0 10px #ff2b75,
    0 0 30px #ff2b75,
    0 0 60px #ff2b75;

    animation:numberPulse 2s ease-in-out infinite;
}

@keyframes numberPulse{
    0%,100%{transform:scale(1)}
    50%{transform:scale(1.05)}
}

/* الجملة الأخيرة */

.final-love{
    font-size:clamp(25px,6vw,50px);
    font-weight:800;
    animation:glow 2s infinite alternate;
}

@keyframes glow{
    from{text-shadow:0 0 10px #fff}
    to{text-shadow:0 0 35px #ffb6d9,0 0 60px #ff2d75}
}

.small{
    font-size:14px;
    opacity:.8;
    margin-top:15px;
}

/* زر الصوت */

.music{
    position:fixed;
    top:15px;
    left:15px;
    z-index:100;
    padding:10px 15px;
    font-size:14px;
    background:rgba(255,255,255,.2);
    color:white;
    border:1px solid rgba(255,255,255,.3);
}

/* نجوم */

.sparkle{
    position:fixed;
    color:white;
    font-size:18px;
    animation:sparkle 3s infinite;
    pointer-events:none;
}

@keyframes sparkle{
    0%,100%{opacity:0;transform:scale(.5)}
    50%{opacity:1;transform:scale(1.5)}
}

@media(max-width:500px){
    .card{
        padding:28px 18px;
    }

    button{
        width:90%;
    }

    .kitty{
        transform:scale(.85);
    }
}
</style>
</head>

<body>

<!-- زر الموسيقى -->
<button class="music" onclick="toggleMusic()">🎵 موسيقى</button>

<!-- الشاشة الأولى -->

<section class="screen active" id="screen1">

<div class="card">

<h1>هل تحب مصطفى؟ ❤️</h1>

<p class="message">
سؤال بسيط...
بس الجواب ممكن يغير كلشي 😌💗
</p>

<div class="buttons">

<button class="yes" onclick="noEntry()">
نعم ❤️
</button>

<button class="love" onclick="nextScreen(2)">
أحبه كثيراً 💗
</button>

</div>

<p class="small">
اختاري جوابچ من قلبچ يا زهراء 🌸
</p>

</div>

</section>


<!-- الشاشة الثانية -->

<section class="screen" id="screen2">

<div class="card">

<div class="kitty">

<div class="eye left"></div>
<div class="eye right"></div>
<div class="nose"></div>
<div class="bow">🎀</div>

</div>

<h2>إلى أميرتي زهراء ❤️</h2>

<p class="message">

أحبج كد الدنيا يا أعز من روحي ❤️

<br>

<span class="highlight">
زهراء...
أميرتي ودنيتي وحبيبة روحي 💗
</span>

<br>

إنتِ مو بس حبيبتي...

<br>

إنتِ أجمل شي صار بحياتي 🌸

</p>

<button class="love" onclick="nextScreen(3)">
اضغطي هنا يا أميرتي 💗
</button>

</div>

</section>


<!-- الشاشة الثالثة -->

<section class="screen" id="screen3">

<div class="card">

<h2>يا أغلى مخلوقة بهالدنيا ❤️</h2>

<p class="message">

أريد أگولج شغلة...

<br>

من كل گلبي ❤️

<br>

وجودج بحياتي مو صدفة...

<br>

إنتِ الشي الحلو اللي أتمنى يبقى وياي للأبد 💗

</p>

<button class="love" onclick="nextScreen(4)">
اضغطي حتى تعرفين شكد أحبج 💕
</button>

</div>

</section>


<!-- الشاشة الرابعة -->

<section class="screen" id="screen4">

<div class="card">

<h2>زهراء... ركزي وياي 😌❤️</h2>

<p class="message">
أنا أحبج بنسبة...
</p>

<div class="big-number">

10000000000000000000000000000000000000000000000000000000000000000000000%

</div>

<p class="message">

والله حتى الآلة الحاسبة استسلمت 😂❤️

<br>

هذا الرقم بعده قليل بحقج...

<br>

لأن حبي إلج ما إله نهاية ❤️

</p>

<button class="love" onclick="nextScreen(5)">
آخر مفاجأة 💗
</button>

</div>

</section>


<!-- الشاشة الخامسة -->

<section class="screen" id="screen5">

<div class="card">

<h1>زهراء ❤️</h1>

<p class="message">

يا أميرتي ودنيتي وحبيبة روحي...

<br><br>

إذا أظل أكتب شكد أحبج...

<br>

ما راح أخلص...

<br>

لأن حبي إلج أكبر من كل الكلام...

<br>

وأكبر من كل الأرقام...

<br>

وأكبر من الدنيا كلها ❤️

</p>

<div class="final-love">
أحبج كد الدنيا وأكثر 💗
</div>

<div class="buttons">

<button class="love" onclick="celebrate()">
🎉 اضغطي هنا
</button>

<button class="back" onclick="nextScreen(1)">
🔄 من البداية
</button>

</div>

</div>

</section>


<script>

/* الانتقال بين الشاشات */

function nextScreen(number){

    document.querySelectorAll('.screen')
    .forEach(screen=>{
        screen.classList.remove('active');
    });

    document
    .getElementById('screen'+number)
    .classList.add('active');

}


/* زر نعم */

function noEntry(){

    alert(
    "بس نعم؟ 😭❤️\n\n" +
    "كنت أتوقع جواب أحلى من هيچ 😂💗\n\n" +
    "جربي الخيار الثاني يا زهراء 😌"
    );

}


/* إنشاء القلوب */

function createHeart(){

    const heart=document.createElement('div');

    heart.className='heart';

    const hearts=['❤️','💗','💖','💕','💘','💝'];

    heart.innerHTML=
    hearts[Math.floor(Math.random()*hearts.length)];

    heart.style.left=
    Math.random()*100+'vw';

    heart.style.animationDuration=
    (5+Math.random()*7)+'s';

    heart.style.fontSize=
    (15+Math.random()*30)+'px';

    document.body.appendChild(heart);

    setTimeout(()=>{
        heart.remove();
    },12000);

}

setInterval(createHeart,500);


/* الفراشات */

function createButterfly(){

    const butterfly=document.createElement('div');

    butterfly.className='butterfly';

    butterfly.innerHTML='🦋';

    butterfly.style.top=
    Math.random()*70+'vh';

    butterfly.style.animationDuration=
    (8+Math.random()*8)+'s';

    document.body.appendChild(butterfly);

    setTimeout(()=>{
        butterfly.remove();
    },16000);

}

setInterval(createButterfly,2500);


/* النجوم */

function createSparkle(){

    const sparkle=document.createElement('div');

    sparkle.className='sparkle';

    sparkle.innerHTML='✨';

    sparkle.style.left=
    Math.random()*100+'vw';

    sparkle.style.top=
    Math.random()*100+'vh';

    document.body.appendChild(sparkle);

    setTimeout(()=>{
        sparkle.remove();
    },3000);

}

setInterval(createSparkle,600);


/* الاحتفال النهائي */

function celebrate(){

    for(let i=0;i<80;i++){

        setTimeout(()=>{

            const heart=document.createElement('div');

            heart.innerHTML=
            ['❤️','💗','💖','💕','🎉','✨','🦋']
            [Math.floor(Math.random()*7)];

            heart.style.position='fixed';

            heart.style.left=
            Math.random()*100+'vw';

            heart.style.top=
            Math.random()*100+'vh';

            heart.style.fontSize=
            (20+Math.random()*40)+'px';

            heart.style.zIndex='999';

            heart.style.pointerEvents='none';

            heart.animate([

                {
                    transform:'scale(0) rotate(0deg)',
                    opacity:0
                },

                {
                    transform:
                    'scale(1.5) rotate(360deg)',
                    opacity:1
                },

                {
                    transform:
                    'translateY(-200px) scale(.5) rotate(720deg)',
                    opacity:0
                }

            ],{

                duration:2000,
                easing:'ease-out'

            });

            document.body.appendChild(heart);

            setTimeout(()=>{
                heart.remove();
            },2000);

        },i*30);

    }

}


/* موسيقى اختيارية */

let musicPlaying=false;

function toggleMusic(){

    if(!musicPlaying){

        alert(
        "🎵 أضف ملف موسيقى باسم music.mp3 إلى نفس مجلد index.html، ثم يمكنك تشغيله من هنا."
        );

        musicPlaying=true;

    }else{

        alert("الموسيقى متوقفة حالياً ❤️");

    }

}

</script>

</body>
</html>

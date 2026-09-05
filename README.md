<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>مملكة الأميرة نيلسي 👑</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Amiri:wght@400;700&family=Cairo:wght@400;600;700;800&display=swap');

*{
    box-sizing:border-box;
    margin:0;
    padding:0;
}

html,body{
    width:100%;
    min-height:100%;
}

body{
    font-family:'Cairo',sans-serif;
    background:linear-gradient(135deg,#fff4f7,#f8dce6,#fffaf5);
    color:#593b46;
    overflow-x:hidden;
}

button{
    font-family:inherit;
    cursor:pointer;
}

/* =====================================================
   شاشة الدخول الملكية
===================================================== */

#entrance{
    position:fixed;
    inset:0;
    z-index:99999;
    display:flex;
    align-items:center;
    justify-content:center;
    overflow:hidden;
    background:
        radial-gradient(circle at 50% 38%,
        rgba(255,220,235,.20),
        transparent 25%),
        linear-gradient(145deg,#1d1017,#4d2638 50%,#1c1017);
    transition:
        opacity 1.5s ease,
        visibility 1.5s ease;
}

#entrance.hide{
    opacity:0;
    visibility:hidden;
    pointer-events:none;
}

/* إضاءة خلفية */

.entrance-glow{
    position:absolute;
    width:600px;
    height:600px;
    border-radius:50%;
    background:
        radial-gradient(circle,
        rgba(255,216,164,.18),
        transparent 68%);
    filter:blur(10px);
    animation:royalGlow 4s ease-in-out infinite;
}

@keyframes royalGlow{
    50%{
        transform:scale(1.18);
        opacity:.65;
    }
}

/* النجوم */

.stars{
    position:absolute;
    inset:0;
    pointer-events:none;
}

.star{
    position:absolute;
    color:#fff0c4;
    font-size:15px;
    text-shadow:0 0 15px #fff0bd;
    animation:twinkle 2.5s ease-in-out infinite;
}

@keyframes twinkle{
    50%{
        opacity:.2;
        transform:scale(.55);
    }
}

/* المحتوى الملكي */

.royal-box{
    position:relative;
    z-index:5;
    width:min(92%,750px);
    text-align:center;
    padding:35px 20px;
}

.crown{
    display:block;
    font-size:75px;
    filter:drop-shadow(0 0 20px rgba(255,215,130,.75));
    animation:crownFloat 3s ease-in-out infinite;
}

@keyframes crownFloat{
    50%{
        transform:translateY(-12px) rotate(2deg);
    }
}

.royal-line{
    width:220px;
    height:1px;
    margin:18px auto;
    background:
        linear-gradient(
            90deg,
            transparent,
            #e8c479,
            transparent
        );
}

.royal-title{
    color:#fff8f3;
    font-family:'Amiri',serif;
    font-size:clamp(34px,8vw,62px);
    line-height:1.4;
    text-shadow:0 4px 25px rgba(0,0,0,.4);
}

.royal-sub{
    color:#ead5dd;
    margin:15px 0 30px;
    font-size:17px;
}

/* زرار الدخول */

.enter-btn,
.final-btn{
    border:1px solid #e8c77f;
    color:#fffaf3;
    background:
        linear-gradient(
            135deg,
            #a66a7e,
            #713d53
        );
    padding:15px 34px;
    border-radius:50px;
    font-size:17px;
    font-weight:800;
    box-shadow:
        0 10px 35px rgba(0,0,0,.3),
        inset 0 1px rgba(255,255,255,.25);
    transition:.3s;
}

.enter-btn:hover,
.final-btn:hover{
    transform:translateY(-4px);
    box-shadow:
        0 15px 40px rgba(0,0,0,.4);
}

.enter-btn:active,
.final-btn:active{
    transform:scale(.96);
}

/* البوابة */

.gate{
    position:absolute;
    inset:0;
    pointer-events:none;
    z-index:10;
}

.gate-left,
.gate-right{
    position:absolute;
    top:0;
    width:50%;
    height:100%;
    background:
        linear-gradient(
            90deg,
            rgba(33,15,25,.98),
            rgba(92,43,61,.94)
        );
    transition:transform 1.6s cubic-bezier(.7,0,.2,1);
}

.gate-left{
    right:50%;
    transform:translateX(0);
    border-left:1px solid rgba(255,220,160,.15);
}

.gate-right{
    left:50%;
    transform:translateX(0);
    background:
        linear-gradient(
            -90deg,
            rgba(33,15,25,.98),
            rgba(92,43,61,.94)
        );
}

#entrance.opening .gate-left{
    transform:translateX(100%);
}

#entrance.opening .gate-right{
    transform:translateX(-100%);
}

/* الترحيب */

.welcome-wrap{
    display:none;
    opacity:0;
}

.welcome-wrap.show{
    display:block;
    animation:fadeUp .8s forwards;
}

@keyframes fadeUp{
    from{
        opacity:0;
        transform:translateY(25px);
    }
    to{
        opacity:1;
        transform:translateY(0);
    }
}

.typewriter{
    min-height:300px;
    max-width:680px;
    margin:0 auto 25px;
    color:#fff8f5;
    font-family:'Amiri',serif;
    font-size:clamp(20px,4.5vw,29px);
    line-height:2;
    text-shadow:0 2px 15px rgba(0,0,0,.4);
}

.cursor{
    display:inline-block;
    width:2px;
    height:28px;
    background:#f3d28c;
    vertical-align:middle;
    animation:blink .7s infinite;
}

@keyframes blink{
    50%{
        opacity:0;
    }
}

.final-btn{
    display:none;
}

/* =====================================================
   الصفحة الرئيسية
===================================================== */

#mainPage{
    opacity:0;
    transform:scale(.97);
    transition:1.5s ease;
    padding:25px 12px 90px;
}

#mainPage.show{
    opacity:1;
    transform:scale(1);
}

.card{
    width:min(100%,900px);
    margin:auto;
    position:relative;
    overflow:hidden;
    border-radius:38px;
    padding:38px 18px 35px;
    background:rgba(255,250,248,.93);
    border:2px solid rgba(196,143,164,.35);
    box-shadow:
        0 25px 80px rgba(102,53,72,.2);
}

.frame{
    position:absolute;
    inset:10px;
    border:1px solid rgba(196,143,164,.3);
    border-radius:30px;
    pointer-events:none;
}

.hero{
    position:relative;
    text-align:center;
    padding-top:10px;
}

/* القمر */

.moon{
    width:100px;
    height:100px;
    border-radius:50%;
    margin:0 auto 12px;
    background:#fff0bf;
    box-shadow:
        0 0 40px rgba(255,220,130,.8);
    position:relative;
}

.moon:after{
    content:"";
    position:absolute;
    width:100px;
    height:100px;
    border-radius:50%;
    background:#fffaf8;
    left:28px;
    top:-14px;
}

/* الاسم */

.hero h1{
    font-family:'Amiri',serif;
    font-size:clamp(42px,9vw,70px);
    color:#9b6277;
    margin:5px 0;
}

.hero .en{
    font-family:'Amiri',serif;
    font-size:29px;
    color:#b98598;
}

.date{
    color:#9d7b88;
    font-size:16px;
    margin-top:5px;
}

/* البيبي */

.baby{
    width:185px;
    height:185px;
    margin:25px auto 5px;
    border-radius:50%;
    background:
        linear-gradient(
            #ffe5ed,
            #fff9f5
        );
    display:flex;
    align-items:center;
    justify-content:center;
    font-size:105px;
    box-shadow:
        0 18px 45px rgba(150,91,116,.18);
}

.bunny{
    font-size:42px;
    margin-top:-3px;
}

/* الآية */

.verse{
    font-family:'Amiri',serif;
    font-size:25px;
    line-height:2;
    color:#8c536b;
    margin:25px auto 15px;
    max-width:750px;
}

/* الرسالة */

.message{
    font-family:'Amiri',serif;
    font-size:21px;
    line-height:2;
    color:#72505d;
}

/* الأقسام */

.section{
    max-width:750px;
    margin:25px auto;
    padding:20px 14px;
    border-radius:27px;
    background:rgba(255,240,245,.7);
    border:1px solid rgba(185,126,150,.22);
}

.section-title{
    color:#9b6277;
    font-weight:800;
    font-size:18px;
    margin-bottom:12px;
}

/* العداد */

.counter{
    display:flex;
    justify-content:center;
    gap:9px;
    flex-wrap:wrap;
    direction:rtl;
}

.unit{
    min-width:82px;
    padding:12px 8px;
    border-radius:18px;
    background:white;
    border:1px solid #ead4dc;
    box-shadow:
        0 8px 22px rgba(125,72,94,.08);
}

.num{
    display:block;
    color:#9b6277;
    font-size:27px;
    font-weight:800;
}

.label{
    color:#997b87;
    font-size:12px;
}

/* الساعة */

.clock{
    font-size:40px;
    font-weight:800;
    letter-spacing:2px;
    color:#9b6277;
}

.heart{
    display:inline-block;
    margin-right:8px;
    color:#bd718d;
    animation:heartbeat 1s infinite;
}

@keyframes heartbeat{
    0%,100%{
        transform:scale(1);
    }
    15%{
        transform:scale(1.3);
    }
    30%{
        transform:scale(1);
    }
    45%{
        transform:scale(1.2);
    }
    60%{
        transform:scale(1);
    }
}

/* الدعاء */

.dua{
    font-family:'Amiri',serif;
    font-size:23px;
    line-height:2;
    color:#7b5261;
}

/* الأغنية */

audio{
    width:min(100%,550px);
    margin-top:8px;
}

/* البتلات */

.petals{
    position:absolute;
    inset:0;
    pointer-events:none;
    overflow:hidden;
}

.petal{
    position:absolute;
    top:-30px;
    font-size:18px;
    opacity:.65;
    animation:fall linear infinite;
}

@keyframes fall{
    to{
        transform:
            translateY(1000px)
            rotate(360deg);
    }
}

footer{
    margin-top:20px;
    color:#a27f8b;
    font-size:12px;
}

/* موبايل */

@media(max-width:600px){

    .royal-box{
        padding:25px 14px;
    }

    .crown{
        font-size:60px;
    }

    .royal-title{
        font-size:38px;
    }

    .royal-sub{
        font-size:14px;
    }

    .typewriter{
        min-height:330px;
        font-size:21px;
    }

    .enter-btn,
    .final-btn{
        font-size:15px;
        padding:

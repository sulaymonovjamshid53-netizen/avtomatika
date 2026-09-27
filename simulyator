<!DOCTYPE html>
<html lang="uz">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Texnologik jarayon laboratoriya simulyatori</title>

<style>

*{
    box-sizing:border-box;
}

body{
    margin:0;
    background:#07111e;
    color:#eef6ff;
    font-family:Arial, sans-serif;
}

header{
    background:linear-gradient(135deg,#0b1d31,#16466a);
    padding:20px 25px;
    border-bottom:2px solid #31577a;
}

header h1{
    margin:0;
    font-size:25px;
}

header p{
    color:#a9bdd2;
    margin:7px 0 0;
}

.container{
    width:96%;
    max-width:1600px;
    margin:15px auto;
}

.toolbar{
    display:flex;
    gap:8px;
    flex-wrap:wrap;
    align-items:center;
    background:#101d2e;
    border:1px solid #2b4662;
    border-radius:12px;
    padding:12px;
}

button{
    cursor:pointer;
}

.btn{
    border:1px solid #48627e;
    color:white;
    background:#1c3047;
    padding:11px 17px;
    border-radius:7px;
    font-weight:bold;
}

.btn:hover{
    filter:brightness(1.2);
}

.start{
    background:#087544;
    border-color:#25dc8a;
}

.stop{
    background:#7e2634;
    border-color:#f05262;
}

.reset{
    background:#745019;
}

.emergency{
    background:#941e2d;
    border-color:#ff4658;
}

.modeBox{
    margin-left:auto;
    display:flex;
    align-items:center;
    gap:8px;
}

select{
    background:#071525;
    color:white;
    border:1px solid #48627e;
    border-radius:6px;
    padding:9px;
}

.main{
    display:grid;
    grid-template-columns:minmax(0,3fr) 360px;
    gap:15px;
    margin-top:15px;
}

.panel{
    background:#101d2e;
    border:1px solid #2b4662;
    border-radius:12px;
    overflow:hidden;
}

.panelTitle{
    background:#17283d;
    padding:13px 16px;
    font-weight:bold;
    border-bottom:1px solid #2b4662;
}

.factory{
    padding:18px;
    overflow-x:auto;
}

.factoryInner{
    min-width:1050px;
}

.statusTop{
    display:flex;
    justify-content:space-between;
    align-items:center;
    margin-bottom:15px;
}

.status{
    padding:8px 14px;
    border-radius:7px;
    background:#722431;
}

.status.running{
    background:#087544;
}

.status.paused{
    background:#77531b;
}

.processLine{
    display:grid;
    grid-template-columns:repeat(7,1fr);
    gap:12px;
    position:relative;
}

.machine{
    min-height:180px;
    background:linear-gradient(180deg,#1b2d43,#101d2e);
    border:2px solid #405c79;
    border-radius:12px;
    padding:10px;
    text-align:center;
    position:relative;
    z-index:5;
    transition:.2s;
}

.machine.active{
    border-color:#1de28b;
    box-shadow:0 0 22px rgba(29,226,139,.25);
}

.machine.blocked{
    border-color:#d58d32;
    background:#2b2113;
}

.machine.done{
    border-color:#3377a7;
}

.machine.fault{
    border-color:#ff4052;
    background:#35161d;
}

.icon{
    font-size:42px;
    height:52px;
    display:flex;
    align-items:center;
    justify-content:center;
}

.machine h3{
    font-size:13px;
    margin:5px 0;
}

.machineStatus{
    font-size:11px;
    color:#829ab3;
    min-height:28px;
}

.led{
    width:13px;
    height:13px;
    border-radius:50%;
    background:#4c5c6d;
    margin:8px auto;
}

.active .led{
    background:#24e28c;
    box-shadow:0 0 15px #24e28c;
}

.blocked .led{
    background:#e5a23b;
}

.fault .led{
    background:#ff4052;
}

.machineValue{
    font-size:12px;
    color:#b9cde0;
}

.conveyor{
    position:absolute;
    left:3%;
    right:3%;
    top:92px;
    height:9px;
    border-radius:10px;
    background:#26394e;
    z-index:1;
}

.conveyor.running{
    background:repeating-linear-gradient(
        90deg,
        #16c878 0px,
        #16c878 25px,
        #075b3b 25px,
        #075b3b 45px
    );

    animation:belt .5s linear infinite;
}

@keyframes belt{
    from{
        background-position:0;
    }

    to{
        background-position:45px;
    }
}

.material{
    position:absolute;
    width:18px;
    height:18px;
    border-radius:50%;
    background:#ffd34e;
    box-shadow:0 0 12px #ffd34e;
    top:87px;
    left:4%;
    z-index:8;
    display:none;
}

.material.moving{
    display:block;
    animation:materialMove 5s linear infinite;
}

@keyframes materialMove{
    0%{
        left:4%;
    }

    100%{
        left:94%;
    }
}

.pipe{
    margin:25px 4%;
    height:8px;
    background:#26394e;
    border-radius:10px;
}

.pipe.flow{
    background:repeating-linear-gradient(
        90deg,
        #13c878 0,
        #13c878 25px,
        #075d3c 25px,
        #075d3c 45px
    );

    animation:pipe .6s linear infinite;
}

@keyframes pipe{
    from{
        background-position:0;
    }

    to{
        background-position:45px;
    }
}

.info{
    margin-top:20px;
    padding:15px;
    background:#091624;
    border:1px solid #29425e;
    border-radius:9px;
}

.now{
    font-size:20px;
    color:#50e7a5;
    font-weight:bold;
}

.description{
    color:#b2c6d9;
    margin-top:7px;
}

.progress{
    height:12px;
    background:#030a11;
    border-radius:10px;
    overflow:hidden;
    margin-top:12px;
}

.progressBar{
    height:100%;
    width:0%;
    background:linear-gradient(90deg,#087544,#48e9a5);
}

.side{
    padding:13px;
}

.card{
    background:#091624;
    border:1px solid #29425e;
    border-radius:9px;
    padding:13px;
    margin-bottom:10px;
}

.label{
    font-size:11px;
    color:#8197af;
}

.big{
    font-size:24px;
    font-weight:bold;
    margin-top:5px;
}

.sensor{
    margin-top:12px;
}

.sensorRow{
    margin:14px 0;
}

.sensorRow label{
    display:flex;
    justify-content:space-between;
    font-size:13px;
}

input[type=range]{
    width:100%;
}

.binaryTitle{
    color:#8197af;
    font-size:11px;
    margin-top:15px;
}

.xRow{
    display:grid;
    grid-template-columns:40px 1fr 70px;
    align-items:center;
    gap:6px;
    margin:6px 0;
}

.xValue{
    background:#050d15;
    border:1px solid #2b4662;
    padding:7px;
    text-align:center;
    border-radius:5px;
    font-family:monospace;
}

.xButton{
    background:#263a50;
    color:white;
    border:1px solid #45617c;
    border-radius:5px;
    padding:7px;
}

.xButton.on{
    background:#087544;
    border-color:#1de28b;
}

.register{
    margin-top:10px;
    background:#050d15;
    border:1px solid #29425e;
    padding:10px;
    border-radius:7px;
    color:#50e7a5;
    font-family:monospace;
    text-align:center;
    letter-spacing:3px;
}

.bottom{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:15px;
    margin-top:15px;
}

.log{
    max-height:250px;
    overflow:auto;
    padding:10px;
}

.logItem{
    background:#091624;
    padding:8px;
    margin-bottom:6px;
    border-left:3px solid #46627d;
    font-size:12px;
}

.good{
    border-color:#1ddd86;
}

.warn{
    border-color:#dda13b;
}

.bad{
    border-color:#ff4052;
}

@media(max-width:1000px){

    .main,
    .bottom{
        grid-template-columns:1fr;
    }

}

</style>
</head>

<body>

<header>

<h1>🏭 Texnologik ishlab chiqarish laboratoriya simulyatori</h1>

<p>
PLC boshqaruvi • X0–X7 kirish signallari • Y0–Y7 chiqish signallari •
real texnologik jarayon
</p>

</header>


<div class="container">


<!-- BOSHQARUV -->

<div class="toolbar">

<button class="btn start" id="start">
▶ START
</button>

<button class="btn stop" id="stop">
■ STOP
</button>

<button class="btn reset" id="reset">
↻ RESET
</button>

<button class="btn emergency" id="emergency">
🚨 AVARIYA
</button>

<div class="modeBox">

Rejim:

<select id="mode">
<option value="auto">AVTOMATIK</option>
<option value="manual">QO‘LDA</option>
</select>

</div>

</div>


<div class="main">


<!-- FABRIKA -->

<div class="panel">

<div class="panelTitle">
🎬 ISHLAB CHIQARISH JARAYONI
</div>

<div class="factory">

<div class="factoryInner">


<div class="statusTop">

<h2>
Xomashyodan tayyor mahsulotgacha
</h2>

<div class="status" id="status">
TO‘XTAGAN
</div>

</div>


<!-- 1-QATOR -->

<div class="processLine">

<div class="conveyor" id="conveyor"></div>

<div class="material" id="material"></div>


<div class="machine" data-id="1">

<div class="icon">🛢️</div>

<h3>1. BUNKER</h3>

<div class="machineStatus">
Kutilmoqda
</div>

<div class="led"></div>

<div class="machineValue">
Sath: <span id="bunkerLevel">80</span>%
</div>

</div>


<div class="machine" data-id="2">

<div class="icon">🚚</div>

<h3>2. KONVEYER</h3>

<div class="machineStatus">
Kutilmoqda
</div>

<div class="led"></div>

<div class="machineValue">
Tezlik: <span id="speed">0</span> m/s
</div>

</div>


<div class="machine" data-id="3">

<div class="icon">⚖️</div>

<h3>3. DOZALAGICH</h3>

<div class="machineStatus">
Kutilmoqda
</div>

<div class="led"></div>

<div class="machineValue">
Massa: <span id="mass">0</span> kg
</div>

</div>


<div class="machine" data-id="4">

<div class="icon" id="mixerIcon">🔄</div>

<h3>4. ARALASHTIRGICH</h3>

<div class="machineStatus">
Kutilmoqda
</div>

<div class="led"></div>

<div class="machineValue">
RPM: <span id="rpm">0</span>
</div>

</div>


<div class="machine" data-id="5">

<div class="icon" id="heaterIcon">🔥</div>

<h3>5. QIZDIRGICH</h3>

<div class="machineStatus">
Kutilmoqda
</div>

<div class="led"></div>

<div class="machineValue">
°C: <span id="heaterTemp">25</span>
</div>

</div>


<div class="machine" data-id="6">

<div class="icon">⚗️</div>

<h3>6. REAKTOR</h3>

<div class="machineStatus">
Kutilmoqda
</div>

<div class="led"></div>

<div class="machineValue">
Reaksiya: <span id="reaction">0</span>%
</div>

</div>


<div class="machine" data-id="7">

<div class="icon" id="pumpIcon">💧</div>

<h3>7. NASOS</h3>

<div class="machineStatus">
Kutilmoqda
</div>

<div class="led"></div>

<div class="machineValue">
Oqim: <span id="flow">0</span> L/min
</div>

</div>

</div>


<div class="pipe" id="pipe1"></div>


<!-- 2-QATOR -->

<div class="processLine">


<div class="machine" data-id="8">

<div class="icon">🧹</div>

<h3>8. FILTR</h3>

<div class="machineStatus">
Kutilmoqda
</div>

<div class="led"></div>

<div class="machineValue">
Filtrlash: <span id="filter">0</span>%
</div>

</div>


<div class="machine" data-id="9">

<div class="icon">❄️</div>

<h3>9. SOVUTGICH</h3>

<div class="machineStatus">
Kutilmoqda
</div>

<div class="led"></div>

<div class="machineValue">
°C: <span id="coolTemp">25</span>
</div>

</div>


<div class="machine" data-id="10">

<div class="icon">🧴</div>

<h3>10. TO‘LDIRGICH</h3>

<div class="machineStatus">
Kutilmoqda
</div>

<div class="led"></div>

<div class="machineValue">
To‘ldirish: <span id="fill">0</span>%
</div>

</div>


<div class="machine" data-id="11">

<div class="icon">📦</div>

<h3>11. QADOQLAGICH</h3>

<div class="machineStatus">
Kutilmoqda
</div>

<div class="led"></div>

<div class="machineValue">
Qadoq: <span id="pack">0</span>%
</div>

</div>


<div class="machine" data-id="12">

<div class="icon" id="robotIcon">🤖</div>

<h3>12. ROBOT</h3>

<div class="machineStatus">
Kutilmoqda
</div>

<div class="led"></div>

<div class="machineValue">
Quti: <span id="box">0</span>
</div>

</div>


<div class="machine" data-id="13">

<div class="icon">🚛</div>

<h3>13. YUKLASH</h3>

<div class="machineStatus">
Kutilmoqda
</div>

<div class="led"></div>

<div class="machineValue">
Yuk: <span id="load">0</span>%
</div>

</div>


<div class="machine" data-id="14">

<div class="icon">🏢</div>

<h3>14. OMBOR</h3>

<div class="machineStatus">
Kutilmoqda
</div>

<div class="led"></div>

<div class="machineValue">
Mahsulot: <span id="product">0</span> dona
</div>

</div>

</div>


<div class="pipe" id="pipe2"></div>


<!-- JARAYON IZOH -->

<div class="info">

<div class="now" id="now">
Jarayon boshlanishini kutmoqda
</div>

<div class="description" id="description">
START tugmasini bosing.
</div>

<div class="progress">

<div class="progressBar" id="progress"></div>

</div>

</div>


</div>
</div>
</div>


<!-- O‘NG TOMON -->

<div class="panel">

<div class="panelTitle">
📊 PLC VA SENSORLAR
</div>

<div class="side">


<div class="card">

<div class="label">
HOLAT
</div>

<div class="big" id="state">
TO‘XTAGAN
</div>

</div>


<div class="card">

<div class="label">
JORIY BOSQICH
</div>

<div class="big">
<span id="stage">0</span> / 14
</div>

</div>


<div class="card">

<div class="label">
HARORAT
</div>

<div class="big">
<span id="temperature">25</span> °C
</div>

</div>


<div class="card">

<div class="label">
BOSIM
</div>

<div class="big">
<span id="pressure">1.0</span> bar
</div>

</div>


<div class="sensor">

<div class="label">
SENSORLAR
</div>


<div class="sensorRow">

<label>
Xomashyo sathi
<span id="levelValue">80%</span>
</label>

<input
id="level"
type="range"
min="0"
max="100"
value="80">

</div>


<div class="sensorRow">

<label>
Harorat sozlamasi
<span id="tempSetValue">80°C</span>
</label>

<input
id="tempSet"
type="range"
min="20"
max="150"
value="80">

</div>

</div>


<div class="binaryTitle">
PLC KIRISHLARI — X0 ... X7
</div>

<div id="inputs"></div>


<div class="register">
X = <span id="xRegister">11110000</span>
</div>


<div class="register">
Y = <span id="yRegister">00000000</span>
</div>


</div>
</div>

</div>


<!-- PASTKI -->

<div class="bottom">


<div class="panel">

<div class="panelTitle">
🧠 PLC MANTIQI
</div>

<div style="padding:15px">

<p>
<b>X0</b> — START ruxsati
</p>

<p>
<b>X1</b> — Xomashyo mavjud
</p>

<p>
<b>X2</b> — Xavfsizlik
</p>

<p>
<b>X3</b> — Avtomatik rejim
</p>

<hr>

<p>
<b>Y0</b> — Bunker / Konveyer
</p>

<p>
<b>Y1</b> — Dozalagich
</p>

<p>
<b>Y2</b> — Aralashtirgich
</p>

<p>
<b>Y3</b> — Qizdirgich
</p>

<p>
<b>Y4</b> — Reaktor
</p>

<p>
<b>Y5</b> — Nasos / Filtr
</p>

<p>
<b>Y6</b> — Qadoqlash
</p>

<p>
<b>Y7</b> — Tayyor mahsulot
</p>

</div>

</div>


<div class="panel">

<div class="panelTitle">
📜 HODISALAR JURNALI
</div>

<div class="log" id="log"></div>

</div>


</div>


</div>


<script>

/* =====================================================
   ASOSIY O'ZGARUVCHILAR
===================================================== */

let running = false;

let emergency = false;

let stage = 0;

let stageStart = 0;

let timer = null;

let plcTimer = null;

let level = 80;

let temperature = 25;

let pressure = 1;

let mass = 0;

let reaction = 0;

let fill = 0;

let pack = 0;

let load = 0;

let product = 0;

let inputs = [
    1, // X0 START
    1, // X1 XOMASHYO
    1, // X2 XAVFSIZLIK
    1, // X3 AVTOMAT
    0,
    0,
    0,
    0
];


/* =====================================================
   BOSQICHLAR
===================================================== */

const stages = [

{
    name:"Xomashyo bunkeri",
    time:4000,
    text:"Bunker xomashyoni qabul qilmoqda va sath sensori nazorat qilmoqda."
},

{
    name:"Konveyer",
    time:5000,
    text:"Konveyer xomashyoni keyingi qurilmaga uzatmoqda."
},

{
    name:"Dozalagich",
    time:4500,
    text:"Dozalagich kerakli miqdordagi xomashyoni o‘lchamoqda."
},

{
    name:"Aralashtirgich",
    time:5000,
    text:"Aralashtirgich parraklari aylanib, xomashyoni aralashtirmoqda."
},

{
    name:"Qizdirgich",
    time:6000,
    text:"Qizdirgich mahsulot haroratini belgilangan qiymatga olib chiqmoqda."
},

{
    name:"Reaktor",
    time:6000,
    text:"Reaktor ichida texnologik reaksiya amalga oshmoqda."
},

{
    name:"Nasos",
    time:4500,
    text:"Nasos mahsulotni quvur orqali filtrga uzatmoqda."
},

{
    name:"Filtr",
    time:5000,
    text:"Filtr mahsulot tarkibidagi keraksiz zarrachalarni ajratmoqda."
},

{
    name:"Sovutgich",
    time:5000,
    text:"Sovutgich mahsulot haroratini pasaytirmoqda."
},

{
    name:"To‘ldirgich",
    time:4500,
    text:"Mahsulot idishlarga belgilangan miqdorda to‘ldirilmoqda."
},

{
    name:"Qadoqlagich",
    time:5000,
    text:"Qadoqlagich tayyor mahsulot idishlarini yopmoqda."
},

{
    name:"Robot",
    time:4500,
    text:"Robot qadoqlangan mahsulotlarni qutilarga joylashtirmoqda."
},

{
    name:"Yuklash",
    time:4500,
    text:"Tayyor mahsulot transport vositasiga yuklanmoqda."
},

{
    name:"Ombor",
    time:4000,
    text:"Tayyor mahsulot omborga joylashtirilmoqda."
}

];


/* =====================================================
   ELEMENTLAR
===================================================== */

const $ = id => document.getElementById(id);


/* =====================================================
   LOG
===================================================== */

function log(text,type=""){

    const item =
    document.createElement("div");

    item.className =
    "logItem "+type;

    item.innerHTML =
    "<b>"+
    new Date().toLocaleTimeString()+
    "</b> — "+
    text;

    $("log").prepend(item);

}


/* =====================================================
   X KIRISHLARINI CHIQARISH
===================================================== */

function createInputs(){

    const box =
    $("inputs");

    box.innerHTML = "";

    for(let i=0;i<8;i++){

        const row =
        document.createElement("div");

        row.className =
        "xRow";

        const name =
        document.createElement("b");

        name.textContent =
        "X"+i;

        const value =
        document.createElement("div");

        value.className =
        "xValue";

        value.textContent =
        inputs[i];

        const button =
        document.createElement("button");

        button.className =
        "xButton";

        if(inputs[i]===1){

            button.classList.add("on");

            button.textContent =
            "1 ON";

        }else{

            button.textContent =
            "0 OFF";

        }


        button.onclick =
        function(){

            toggleInput(i);

        };


        row.append(
            name,
            value,
            button
        );

        box.appendChild(row);

    }

}


/* =====================================================
   ENG MUHIM QISM:
   X SIGNALLARINI O'ZGARTIRISH
===================================================== */

function toggleInput(i){

    inputs[i] =
    inputs[i] === 1
    ? 0
    : 1;


    createInputs();

    updateRegisters();


    log(
        "X"+i+
        " signali = "+
        inputs[i],
        inputs[i] ? "good" : "warn"
    );


    /*
       X O'ZGARGAN ZAHOTI
       PLC TEKSHIRILADI
    */

    checkPLC(true);

}


/* =====================================================
   PLC NAZORATI
===================================================== */

function checkPLC(fromUser=false){

    /*
       X2 = XAVFSIZLIK
    */

    if(inputs[2]===0){

        if(running){

            running=false;

            clearTimeout(timer);

            timer=null;

            log(
                "🚨 X2=0 — XAVFSIZLIK UZILDI. BUTUN LINIYA TO‘XTADI!",
                "bad"
            );

        }

        render();

        return false;

    }


    /*
       X0 = START
    */

    if(inputs[0]===0){

        if(running){

            running=false;

            clearTimeout(timer);

            timer=null;

            log(
                "⛔ X0=0 — START RUXSATI O‘CHIRILDI. JARAYON TO‘XTADI!",
                "bad"
            );

        }

        render();

        return false;

    }


    /*
       X1 = XOMASHYO
    */

    if(
        inputs[1]===0 &&
        stage>=1 &&
        stage<=3
    ){

        if(running){

            running=false;

            clearTimeout(timer);

            timer=null;

            log(
                "⛔ X1=0 — XOMASHYO UZILDI. KONVEYER TO‘XTADI!",
                "warn"
            );

        }

        render();

        return false;

    }


    /*
       X3 = AVTOMATIK
    */

    if(
        inputs[3]===0 &&
        stage>0 &&
        stage<14
    ){

        if(running){

            running=false;

            clearTimeout(timer);

            timer=null;

            log(
                "X3=0 — AVTOMATIK REJIM O‘CHIRILDI.",
                "warn"
            );

        }

        render();

        return false;

    }


    return true;

}


/* =====================================================
   PLC OUTPUT
===================================================== */

function outputs(){

    let y =
    [0,0,0,0,0,0,0,0];


    /*
       Faqat PLC ruxsatlari mavjud bo‘lsa
       chiqish signallari ON bo‘ladi.
    */

    if(
        running &&
        inputs[0] &&
        inputs[2]
    ){

        if(stage>=1)
            y[0]=1;

        if(stage>=3)
            y[1]=1;

        if(stage>=4)
            y[2]=1;

        if(stage>=5)
            y[3]=1;

        if(stage>=6)
            y[4]=1;

        if(stage>=7)
            y[5]=1;

        if(stage>=11)
            y[6]=1;

        if(stage>=14)
            y[7]=1;

    }

    return y;

}


/* =====================================================
   REGISTERLAR
===================================================== */

function updateRegisters(){

    $("xRegister").textContent =
    inputs.join("");

    $("yRegister").textContent =
    outputs().join("");

}


/* =====================================================
   QURILMALAR
===================================================== */

function updateMachines(){

    const machines =
    document.querySelectorAll(".machine");


    machines.forEach(
    (machine,index)=>{

        const id =
        index+1;

        const status =
        machine.querySelector(
            ".machineStatus"
        );

        machine.classList.remove(
            "active",
            "blocked",
            "done",
            "fault"
        );


        if(emergency){

            machine.classList.add(
                "fault"
            );

            status.textContent =
            "AVARIYA";

            return;

        }


        if(id < stage){

            machine.classList.add(
                "done"
            );

            status.textContent =
            "BAJARILDI";

        }


        else if(id === stage){

            /*
               X signali sababli
               aynan shu qurilma bloklanganmi?
            */

            if(
                inputs[1]===0 &&
                id<=3
            ){

                machine.classList.add(
                    "blocked"
                );

                status.textContent =
                "X1=0 — XOMASHYO YO‘Q";

            }

            else if(
                inputs[2]===0
            ){

                machine.classList.add(
                    "fault"
                );

                status.textContent =
                "X2=0 — XAVFSIZLIK";

            }

            else if(
                inputs[0]===0
            ){

                machine.classList.add(
                    "blocked"
                );

                status.textContent =
                "X0=0 — STOP";

            }

            else if(running){

                machine.classList.add(
                    "active"
                );

                status.textContent =
                "ISHLAMOQDA";

            }

            else{

                machine.classList.add(
                    "blocked"
                );

                status.textContent =
                "PAUZADA";

            }

        }


        else{

            status.textContent =
            "KUTILMOQDA";

        }

    });

}


/* =====================================================
   REAL PROCESS PARAMETERS
===================================================== */

function updateProcessValues(){

    /*
       Faqat running bo‘lganda
       qiymatlar o‘zgaradi.
    */

    if(!running)
        return;


    if(stage===1){

        level -= 0.03;

        if(level<0)
            level=0;

        $("bunkerLevel").textContent =
        Math.round(level);

    }


    if(stage===2){

        $("speed").textContent =
        "1.8";

    }
    else{

        $("speed").textContent =
        "0";

    }


    if(stage===3){

        mass += 0.08;

        if(mass>5)
            mass=5;

        $("mass").textContent =
        mass.toFixed(1);

    }


    if(stage===4){

        $("rpm").textContent =
        "60";

    }
    else{

        $("rpm").textContent =
        "0";

    }


    if(stage===5){

        temperature += 0.35;

        if(temperature>80)
            temperature=80;

        $("heaterTemp").textContent =
        Math.round(temperature);

    }


    if(stage===6){

        reaction += 0.5;

        if(reaction>100)
            reaction=100;

        $("reaction").textContent =
        Math.round(reaction);

    }


    if(stage===7){

        $("flow").textContent =
        "42";

    }
    else{

        $("flow").textContent =
        "0";

    }


    if(stage===8){

        let v =
        Number(
            $("filter").textContent
        );

        v += .5;

        if(v>100)
            v=100;

        $("filter").textContent =
        Math.round(v);

    }


    if(stage===9){

        temperature -= .3;

        if(temperature<30)
            temperature=30;

        $("coolTemp").textContent =
        Math.round(temperature);

    }


    if(stage===10){

        fill += .8;

        if(fill>100)
            fill=100;

        $("fill").textContent =
        Math.round(fill);

    }


    if(stage===11){

        pack += .8;

        if(pack>100)
            pack=100;

        $("pack").textContent =
        Math.round(pack);

    }


    if(stage===12){

        $("box").textContent =
        "1";

    }


    if(stage===13){

        load += .8;

        if(load>100)
            load=100;

        $("load").textContent =
        Math.round(load);

    }


    if(stage===14){

        product=1;

        $("product").textContent =
        product;

    }


    $("temperature").textContent =
    Math.round(temperature);

}


/* =====================================================
   ANIMATSIYA
===================================================== */

function updateAnimation(){

    const active =
    running &&
    !emergency;


    $("conveyor")
    .classList.toggle(
        "running",
        active &&
        stage>=1 &&
        stage<=3
    );


    $("material")
    .classList.toggle(
        "moving",
        active &&
        stage>=2 &&
        stage<=6
    );


    $("pipe1")
    .classList.toggle(
        "flow",
        active &&
        stage>=7 &&
        stage<=9
    );


    $("pipe2")
    .classList.toggle(
        "flow",
        active &&
        stage>=10
    );


    /*
       Aralashtirgich
    */

    if(active && stage===4){

        $("mixerIcon").style.animation =
        "spin .7s linear infinite";

    }
    else{

        $("mixerIcon").style.animation =
        "none";

    }


    /*
       Qizdirgich
    */

    if(active && stage===5){

        $("heaterIcon").style.animation =
        "heat .35s infinite alternate";

    }
    else{

        $("heaterIcon").style.animation =
        "none";

    }


    /*
       Nasos
    */

    if(active && stage===7){

        $("pumpIcon").style.animation =
        "pump .5s infinite alternate";

    }
    else{

        $("pumpIcon").style.animation =
        "none";

    }


    /*
       Robot
    */

    if(active && stage===12){

        $("robotIcon").style.animation =
        "robot .7s infinite alternate";

    }
    else{

        $("robotIcon").style.animation =
        "none";

    }

}


/* =====================================================
   CSS ANIMATSIYALARI
===================================================== */

const style =
document.createElement("style");

style.textContent = `

@keyframes spin{

    from{
        transform:rotate(0deg);
    }

    to{
        transform:rotate(360deg);
    }

}

@keyframes heat{

    from{
        transform:scale(1);
    }

    to{
        transform:scale(1.2);
    }

}

@keyframes pump{

    from{
        transform:translateY(0);
    }

    to{
        transform:translateY(-8px);
    }

}

@keyframes robot{

    from{
        transform:translateX(-8px);
    }

    to{
        transform:translateX(8px);
    }

}

`;

document.head.appendChild(style);


/* =====================================================
   EKRANNI YANGILASH
===================================================== */

function render(){

    updateMachines();

    updateAnimation();

    updateRegisters();


    $("stage").textContent =
    stage;


    $("progress").style.width =
    ((stage/14)*100)+"%";


    $("levelValue").textContent =
    Math.round(level)+"%";


    $("temperature").textContent =
    Math.round(temperature);


    $("pressure").textContent =
    pressure.toFixed(1);


    if(stage===0){

        $("now").textContent =
        "⏸ Jarayon boshlanishini kutmoqda";

        $("description").textContent =
        "START tugmasini bosing.";

    }
    else{

        $("now").textContent =
        stages[stage-1].name+
        (
            running
            ? " — ISHLAMOQDA"
            : " — TO‘XTAGAN"
        );

        $("description").textContent =
        stages[stage-1].text;

    }


    /*
       HOLAT
    */

    if(emergency){

        $("state").textContent =
        "🚨 AVARIYA";

        $("status").textContent =
        "🚨 AVARIYA";

        $("status").className =
        "status";

    }

    else if(running){

        $("state").textContent =
        "ISHLAMOQDA";

        $("status").textContent =
        "● ISHLAMOQDA";

        $("status").className =
        "status running";

    }

    else if(stage>0 && stage<14){

        $("state").textContent =
        "PAUZADA";

        $("status").textContent =
        "Ⅱ TO‘XTAGAN";

        $("status").className =
        "status paused";

    }

    else if(stage>=14){

        $("state").textContent =
        "TUGALLANDI";

        $("status").textContent =
        "✓ TUGALLANDI";

        $("status").className =
        "status running";

    }

    else{

        $("state").textContent =
        "TO‘XTAGAN";

        $("status").textContent =
        "TO‘XTAGAN";

        $("status").className =
        "status";

    }

}


/* =====================================================
   START
===================================================== */

$("start").onclick =
function(){

    if(emergency){

        log(
            "🚨 Avariya faol. RESET bosing.",
            "bad"
        );

        return;

    }


    /*
       START oldidan PLC tekshiriladi
    */

    if(!checkPLC())
        return;


    if(stage>=14){

        log(
            "Jarayon tugagan. Yangi jarayon uchun RESET bosing.",
            "warn"
        );

        return;

    }


    running=true;


    log(
        stage===0
        ? "▶ Ishlab chiqarish liniyasi ishga tushdi."
        : "▶ Jarayon davom etdi.",
        "good"
    );


    render();


    /*
       Yangi bosqich boshlanadi
    */

    if(!timer){

        stageStart =
        Date.now();

        if(stage===0){

            startNextStage();

        }
        else{

            timer =
            setTimeout(
                finishStage,
                stages[stage-1].time
            );

        }

    }

};


/* =====================================================
   KEYINGI BOSQICH
===================================================== */

function startNextStage(){

    /*
       PLC ruxsatlarini tekshirish
    */

    if(!checkPLC())
        return;


    if(!running)
        return;


    if(stage>=14)
        return;


    stage++;


    stageStart =
    Date.now();


    const s =
    stages[stage-1];


    log(
        "▶ "+
        stage+
        "-bosqich boshlandi: "+
        s.name,
        "good"
    );


    render();


    timer =
    setTimeout(
        finishStage,
        s.time
    );

}


/* =====================================================
   BOSQICH TUGASHI
===================================================== */

function finishStage(){

    /*
       Agar STOP yoki X signali
       sabab running=false bo‘lsa,
       hech narsa qilinmaydi.
    */

    if(!running){

        timer=null;

        return;

    }


    /*
       PLC yana tekshiriladi
    */

    if(!checkPLC()){

        timer=null;

        return;

    }


    log(
        "✓ "+
        stages[stage-1].name+
        " tugadi.",
        "good"
    );


    timer=null;


    if(stage>=14){

        running=false;

        log(
            "🎉 Butun ishlab chiqarish jarayoni yakunlandi!",
            "good"
        );

        render();

        return;

    }


    startNextStage();

}


/* =====================================================
   STOP
===================================================== */

$("stop").onclick =
function(){

    running=false;

    clearTimeout(timer);

    timer=null;


    /*
       CSS animatsiyalar ham to‘xtaydi
    */

    render();


    log(
        "■ STOP — barcha texnologik jarayon muzlatildi.",
        "warn"
    );

};


/* =====================================================
   RESET
===================================================== */

$("reset").onclick =
function(){

    running=false;

    emergency=false;

    clearTimeout(timer);

    timer=null;


    stage=0;

    level=80;

    temperature=25;

    pressure=1;

    mass=0;

    reaction=0;

    fill=0;

    pack=0;

    load=0;

    product=0;


    inputs=[
        1,
        1,
        1,
        1,
        0,
        0,
        0,
        0
    ];


    $("level").value=80;

    $("tempSet").value=80;


    $("bunkerLevel").textContent="80";

    $("mass").textContent="0";

    $("rpm").textContent="0";

    $("heaterTemp").textContent="25";

    $("reaction").textContent="0";

    $("flow").textContent="0";

    $("filter").textContent="0";

    $("coolTemp").textContent="25";

    $("fill").textContent="0";

    $("pack").textContent="0";

    $("box").textContent="0";

    $("load").textContent="0";

    $("product").textContent="0";


    createInputs();

    render();


    log(
        "↻ Tizim boshlang‘ich holatga qaytarildi.",
        "good"
    );

};


/* =====================================================
   AVARIYA
===================================================== */

$("emergency").onclick =
function(){

    emergency=true;

    running=false;

    clearTimeout(timer);

    timer=null;


    render();


    log(
        "🚨 AVARIYAVIY STOP! Barcha qurilmalar o‘chirildi.",
        "bad"
    );

};


/* =====================================================
   SENSOR XOMASHYO
===================================================== */

$("level").oninput =
function(){

    level =
    Number(this.value);


    $("levelValue").textContent =
    level+"%";


    $("bunkerLevel").textContent =
    level;


    /*
       X1 = 1 bo‘lsa ham
       sath 0 ga tushsa
       xomashyo tugagan hisoblanadi.
    */

    if(
        level<=0 &&
        running
    ){

        inputs[1]=0;

        createInputs();

        checkPLC(true);

        log(
            "⛔ Xomashyo sathi 0%. X1 avtomatik ravishda 0 bo‘ldi.",
            "bad"
        );

    }

};


/* =====================================================
   HARORAT SOZLAMASI
===================================================== */

$("tempSet").oninput =
function(){

    $("tempSetValue").textContent =
    this.value+"°C";

};


/* =====================================================
   PLC NI DOIMIY TEKSHIRISH
===================================================== */

/*
   Bu qism juda muhim.

   Har 100 millisekundda
   X0-X7 signallari tekshiriladi.

   Shuning uchun foydalanuvchi
   jarayon ketayotgan paytda
   X1 ni 0 qilsa ham
   jarayon darhol javob beradi.
*/

plcTimer =
setInterval(
function(){

    if(emergency)
        return;


    if(running){

        checkPLC(false);

        updateProcessValues();

        render();

    }

},
100
);


/* =====================================================
   BOSHLANG‘ICH
===================================================== */

createInputs();

render();

log(
    "✓ Laboratoriya simulyatori tayyor.",
    "good"
);

log(
    "X0, X1, X2 yoki X3 ni o‘zgartirib jarayonga ta’sir ko‘ring.",
    "good"
);

</script>

</body>
</html>

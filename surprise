<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0">
<title>Birthday Surprise</title>
<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:Arial,sans-serif}
body{overflow:hidden;background:linear-gradient(135deg,#5b2be0,#ff4d8d,#ffb347);height:100vh;color:#fff}
.page{position:absolute;inset:0;display:none;justify-content:center;align-items:center;flex-direction:column;text-align:center}
.page.active{display:flex}
h1{font-size:3rem;text-shadow:0 0 20px #fff}
button{padding:14px 28px;border:0;border-radius:30px;font-size:1.1rem;cursor:pointer;margin-top:20px}
#count{font-size:6rem;font-weight:bold}
.cake{width:220px;height:120px;background:#ffbfd1;border-radius:10px;position:relative;margin:20px auto}
.cake:before{content:"";position:absolute;width:100%;height:20px;background:#fff;top:35px}
.candle{position:absolute;width:12px;height:45px;background:#fff;left:104px;top:-45px}
.flame{width:18px;height:18px;background:orange;border-radius:50%;position:absolute;left:-3px;top:-18px;animation:flicker .4s infinite alternate}
@keyframes flicker{from{transform:scale(1)}to{transform:scale(1.3)}}
.left,.right{position:absolute;top:0;width:50%;height:100%;background:#ffbfd1}
.left{left:0}.right{right:0}
.cutL{animation:l 1s forwards}.cutR{animation:r 1s forwards}
@keyframes l{to{transform:translateX(-25px) rotate(-8deg)}}
@keyframes r{to{transform:translateX(25px) rotate(8deg)}}
.balloon,.heart,.confetti,.fire{position:absolute;pointer-events:none}
.balloon{width:55px;height:75px;border-radius:50%;bottom:-90px;animation:up linear infinite}
.balloon:after{content:"";position:absolute;width:2px;height:60px;background:#fff;left:50%;top:75px}
@keyframes up{to{transform:translateY(-120vh)}}
.heart{font-size:22px;bottom:-30px;animation:up 8s linear infinite}
.confetti{width:8px;height:8px;top:-10px;animation:fall linear infinite}
@keyframes fall{to{transform:translateY(110vh) rotate(720deg)}}
.fire{font-size:34px;animation:boom 1s forwards}
@keyframes boom{to{transform:scale(2);opacity:0}}
#gift{font-size:90px;cursor:pointer;animation:bounce 1s infinite}
@keyframes bounce{50%{transform:translateY(-10px)}}
#msg{display:none;font-size:1.8rem;color:#ffe96b;padding:20px}
</style>
</head>
<body>

<div id="welcome" class="page active">
<h1>🎉 Birthday Surprise 🎉</h1>
<p style="margin:20px;font-size:1.3rem">Click below to start the celebration!</p>
<button onclick="start()">🎁 Open Surprise</button>
</div>

<div id="countdown" class="page">
<h1>Get Ready...</h1>
<div id="count">3</div>
</div>

<div id="party" class="page">
<h1>🎂 Happy Birthday! 🎂</h1>
<div class="cake">
<div id="left" class="left"></div>
<div id="right" class="right"></div>
<div class="candle"><div class="flame"></div></div>
</div>
<button onclick="cutCake()">🔪 Cut Cake</button>
<div id="gift" onclick="openGift()" style="display:none">🎁</div>
<div id="msg">
🥳 Happy Birthday!<br>
May your life be filled with happiness, health, success and joy! ❤️
</div>
</div>

<script>
function show(id){
 document.querySelectorAll('.page').forEach(p=>p.classList.remove('active'));
 document.getElementById(id).classList.add('active');
}
for(let i=0;i<25;i++){
 let b=document.createElement('div');
 b.className='balloon';
 b.style.left=Math.random()*100+'vw';
 b.style.background=`hsl(${Math.random()*360},100%,60%)`;
 b.style.animationDuration=(5+Math.random()*5)+'s';
 document.body.appendChild(b);
}
for(let i=0;i<100;i++){
 let c=document.createElement('div');
 c.className='confetti';
 c.style.left=Math.random()*100+'vw';
 c.style.background=`hsl(${Math.random()*360},100%,50%)`;
 c.style.animationDuration=(3+Math.random()*3)+'s';
 c.style.animationDelay=Math.random()*3+'s';
 document.body.appendChild(c);
}
for(let i=0;i<20;i++){
 let h=document.createElement('div');
 h.className='heart';
 h.innerHTML='❤️';
 h.style.left=Math.random()*100+'vw';
 h.style.animationDelay=Math.random()*5+'s';
 document.body.appendChild(h);
}
function fireworks(){
 for(let i=0;i<40;i++){
   let f=document.createElement('div');
   f.className='fire';
   f.innerHTML='🎆';
   f.style.left=Math.random()*100+'vw';
   f.style.top=Math.random()*60+'vh';
   document.body.appendChild(f);
   setTimeout(()=>f.remove(),1000);
 }
}
function start(){
 show('countdown');
 let n=3;
 let el=document.getElementById('count');
 let t=setInterval(()=>{
   el.textContent=n;
   n--;
   if(n<0){
      clearInterval(t);
      show('party');
      fireworks();
   }
 },1000);
}
function cutCake(){
 document.getElementById('left').classList.add('cutL');
 document.getElementById('right').classList.add('cutR');
 fireworks();
 setTimeout(()=>document.getElementById('gift').style.display='block',1200);
}
function openGift(){
 fireworks();
 document.getElementById('gift').textContent='🎂';
 document.getElementById('msg').style.display='block';
}
</script>
</body>
</html>

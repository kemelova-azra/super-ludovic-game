doctype html>
<html lang="ru">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Поймай звёздочку — SUPER Людовик XVI</title>
<style>
  html,body{margin:0;height:100%;font-family:system-ui;color:#fff;background:#000}
  body{display:flex;flex-direction:column;align-items:center;justify-content:center}
  #menu{display:flex;flex-direction:column;gap:12px;align-items:center}
  #gameWrap{display:none;width:min(760px,96vw);background:#0008;padding:12px;border-radius:12px}
  canvas{width:100%;height:420px;border-radius:10px;background:#000}
  button{background:#1e90ff;border:none;color:white;padding:12px 20px;border-radius:10px;font-size:18px;cursor:pointer}
</style>
</head>
<body>

<div id="menu">
<h1>SUPER Людовик XVI</h1>
<button id="playBtn">Играть</button>
</div>

<div id="gameWrap">
<div id="hud" style="display:flex;justify-content:space-between;padding:8px">
  <div>Очки: <strong id="score">0</strong></div>
  <div>Жизни: <strong id="lives">3</strong></div>
  <div>Щит: <strong id="shield">0</strong></div>
  <div>Время: <strong id="time">60</strong>с</div>
  <button id="exitBtn">Меню</button>
</div>

<canvas id="game"></canvas>

<div id="controls" style="display:flex;justify-content:center;gap:40px;margin-top:15px;">
  <button id="btnLeft" style="font-size:32px;padding:20px;">⬅️</button>
  <button id="btnRight" style="font-size:32px;padding:20px;">➡️</button>
</div>
</div>

<audio id="bgm" src="https://cdn.pixabay.com/download/audio/2022/10/19/audio_f0a8dabf58.mp3" loop></audio>
<audio id="pickup" src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_c8b0bb274b.mp3"></audio>
<audio id="hit" src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_0597a76a39.mp3"></audio>
<audio id="winSound" src="https://cdn.pixabay.com/audio/2022/03/15/audio_7c3a0b5a6e.mp3"></audio>
<audio id="loseSound" src="https://cdn.pixabay.com/audio/2022/03/10/audio_3f3b5c2c5d.mp3"></audio>

<script>
const canvas=document.getElementById('game');
const ctx=canvas.getContext('2d');
canvas.width=800; canvas.height=420;

const bgm=document.getElementById("bgm");
const sndPickup=document.getElementById("pickup");
const sndHit=document.getElementById("hit");
const winSound=document.getElementById("winSound");
const loseSound=document.getElementById("loseSound");

function unlockAudio(){
  [bgm, sndPickup, sndHit, winSound, loseSound].forEach(a=>{
    a.volume = 0.6;
    a.pause();
    a.currentTime = 0;
    a.play().then(()=>a.pause()).catch(()=>{});
  });
}

let keys={};
window.addEventListener('keydown',e=>keys[e.key]=true);
window.addEventListener('keyup',e=>keys[e.key]=false);

let player={x:150,y:350,speed:6};
let score=0,lives=3,shield=0,timeLeft=300,running=false;

let stars=[],meteors=[],gems=[],hearts=[],shields=[];
let starField=[];
for(let i=0;i<100;i++){
  starField.push({x:Math.random()*800, y:Math.random()*380, r:Math.random()*2+1, vy:Math.random()*0.5+0.2});
}

function rand(a,b){return Math.random()*(b-a)+a;}

function spawnObjects(){
  if(Math.random()<0.02) stars.push({x:rand(40,760),y:-20,vy:rand(2,3),r:10});
  if(Math.random()<0.015) meteors.push({x:rand(40,760),y:-40,vy:rand(3,6),r:16});
  if(Math.random()<0.01) gems.push({x:rand(40,760),y:-20,vy:2,r:12});
  if(Math.random()<0.008) hearts.push({x:rand(40,760),y:-20,vy:2,r:12});
  if(Math.random()<0.008) shields.push({x:rand(40,760),y:-20,vy:2,r:12});
}

const scoreEl=document.getElementById("score");
const livesEl=document.getElementById("lives");
const shieldEl=document.getElementById("shield");
const timeEl=document.getElementById("time");

function reset(){
  score=0; lives=3; shield=0; timeLeft=300;
  stars=[]; meteors=[]; gems=[]; hearts=[]; shields=[];
  scoreEl.textContent=0;
  livesEl.textContent=3;
  shieldEl.textContent=0;
  timeEl.textContent=60;
}

function showMenu(){
  document.getElementById("menu").style.display="flex";
  document.getElementById("gameWrap").style.display="none";
  bgm.pause();
}

function startGame(){
  unlockAudio();
  document.getElementById("menu").style.display="none";
  document.getElementById("gameWrap").style.display="block";
  reset();
  running=true;
  bgm.volume=0.4;
  bgm.play();
  requestAnimationFrame(loop);
}

document.getElementById("playBtn").onclick=startGame;
document.getElementById("exitBtn").onclick=showMenu;

function movePlayer(){
  if(keys["ArrowLeft"]) player.x-=player.speed;
  if(keys["ArrowRight"]) player.x+=player.speed;
  player.x=Math.max(20,Math.min(780,player.x));
}

function drawBackground(){
  let g=ctx.createLinearGradient(0,0,0,420);
  g.addColorStop(0,"#001"); 
  g.addColorStop(1,"#000"); 
  ctx.fillStyle=g;
  ctx.fillRect(0,0,800,420);

  ctx.fillStyle="white";
  for(let s of starField){
    ctx.beginPath();
    ctx.arc(s.x,s.y,s.r,0,Math.PI*2);
    ctx.fill();
    s.y += s.vy;
    if(s.y>380) s.y=0;
  }

  let earthGradient = ctx.createLinearGradient(0,380,0,420);
  earthGradient.addColorStop(0,"#3a9a40");
  earthGradient.addColorStop(1,"#1d5f20");
  ctx.fillStyle = earthGradient;
  ctx.fillRect(0,380,800,40);
}

function drawPlayer(){
  ctx.fillStyle="#f2d6b3";
  ctx.beginPath(); ctx.arc(player.x,player.y-18,16,0,Math.PI*2); ctx.fill();
  ctx.fillStyle="#345bdd";
  ctx.fillRect(player.x-18,player.y-5,36,45);
}

function update(list,color,radius,action){
  ctx.fillStyle=color;
  for(let i=list.length-1;i>=0;i--){
    let o=list[i]; o.y+=o.vy;
    ctx.beginPath(); ctx.arc(o.x,o.y,o.r,0,Math.PI*2); ctx.fill();
    if(Math.hypot(player.x-o.x,player.y-o.y)<radius){
      action(); list.splice(i,1);
    } else if(o.y>450) list.splice(i,1);
  }
}

function loop(t){
  if(!running) return;

  timeLeft=Math.max(0,300-Math.floor(t/1000));
  timeEl.textContent=timeLeft;

  if(timeLeft<=0){
    running=false;
    alert(score>=500 ? "🎉 You win!" : "You lose ❌");
    return showMenu();
  }

  movePlayer();
  spawnObjects();
  drawBackground();

  update(stars,"yellow",28,()=>{score+=10; sndPickup.play(); scoreEl.textContent=score;});
  update(gems,"#00eaff",28,()=>{score+=25; sndPickup.play(); scoreEl.textContent=score;});
  update(hearts,"#ff3366",28,()=>{lives++; sndPickup.play(); livesEl.textContent=lives;});
  update(shields,"#66ff66",28,()=>{shield++; sndPickup.play(); shieldEl.textContent=shield;});

  update(meteors,"red",30,()=>{
    sndHit.play();
    if(shield>0){shield--; shieldEl.textContent=shield;}
    else{
      lives--; livesEl.textContent=lives;
      if(lives<=0){
        running=false;
        alert("You lose ❌");
        showMenu();
      }
    }
  });

  drawPlayer();
  requestAnimationFrame(loop);
}

const btnLeft=document.getElementById("btnLeft");
const btnRight=document.getElementById("btnRight");
btnLeft.onmousedown=()=>keys["ArrowLeft"]=true;
btnLeft.onmouseup=()=>keys["ArrowLeft"]=false;
btnRight.onmousedown=()=>keys["ArrowRight"]=true;
btnRight.onmouseup=()=>keys["ArrowRight"]=false;
btnLeft.ontouchstart=()=>keys["ArrowLeft"]=true;
btnLeft.ontouchend=()=>keys["ArrowLeft"]=false;
btnRight.ontouchstart=()=>keys["ArrowRight"]=true;
btnRight.ontouchend=()=>keys["ArrowRight"]=false;
</script>
</body>
</html>

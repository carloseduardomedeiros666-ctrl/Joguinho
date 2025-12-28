<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1,user-scalable=no">
<title>Mini Brawl</title>

<style>
body{margin:0;overflow:hidden;background:#111;color:white;font-family:sans-serif}
canvas{display:block}

.btn{
 position:fixed;
 width:80px;height:80px;
 border-radius:50%;
 opacity:.75;
 text-align:center;
 line-height:80px;
 font-weight:bold;
 user-select:none;
}

#joy{left:30px;bottom:40px;width:120px;height:120px;background:rgba(255,255,255,.2)}
#atk{right:30px;bottom:40px;background:red}
#super{right:30px;bottom:140px;background:yellow;color:black}
#power{right:30px;bottom:240px;background:purple}

#lobby{
 position:fixed;
 inset:0;
 background:#222;
 display:flex;
 flex-direction:column;
 align-items:center;
 justify-content:center;
 gap:10px;
}
button{font-size:18px;padding:10px 20px}
</style>
</head>

<body>

<div id="lobby">
 <h2>Mini Brawl</h2>
 <button onclick="selectChar()">Selecionar Brawler</button>
 <button onclick="start()">Começar</button>
</div>

<canvas id="c"></canvas>

<div id="joy" class="btn"></div>
<div id="atk" class="btn">ATK</div>
<div id="super" class="btn">SUPER</div>
<div id="power" class="btn">ROXO</div>

<script>
const c=document.getElementById("c"),x=c.getContext("2d");
c.width=innerWidth;c.height=innerHeight;

let game=false;
const MAP=1000;
let bullets=[],bots=[];

const player={
 x:500,y:500,r:18,
 life:20000,max:20000,
 dmg:1500,spd:2,
 dx:0,dy:0,
 ammo:5,
 super:0,
 power:0,
 alive:true
};

function selectChar(){alert("Brawler selecionado");}

function start(){
 document.getElementById("lobby").style.display="none";
 spawnBots();
 game=true;
}

function spawnBots(){
 bots=[];
 for(let i=0;i<8;i++){
  bots.push({
   x:Math.random()*MAP,
   y:Math.random()*MAP,
   r:16,
   life:12000,
   dmg:1200,
   spd:1.3,
   ammo:5,
   alive:true
  });
 }
}

function shoot(owner,dirX,dirY){
 if(owner.ammo<=0)return;
 let d=Math.hypot(dirX,dirY);
 bullets.push({
  x:owner.x,y:owner.y,
  dx:dirX/d*6,
  dy:dirY/d*6,
  owner,
  life:80
 });
 owner.ammo--;
 owner.super++;
 owner.power++;
}

// JOYSTICK
let js=null;
joy.ontouchstart=e=>js=e.touches[0];
joy.ontouchmove=e=>{
 let t=e.touches[0];
 player.dx=(t.clientX-js.clientX)*.03;
 player.dy=(t.clientY-js.clientY)*.03;
};
joy.ontouchend=()=>player.dx=player.dy=0;

// ATAQUE NORMAL (atira pra frente)
atk.onclick=()=>{
 shoot(player,1,0);
};

// SUPER (tiros em círculo)
super.onclick=()=>{
 if(player.super<7)return;
 for(let a=0;a<360;a+=30){
  shoot(player,Math.cos(a*Math.PI/180),Math.sin(a*Math.PI/180));
 }
 player.super=0;
};

// PODER ROXO (buff)
power.onclick=()=>{
 if(player.power<10)return;
 player.life+=5000;
 player.dmg+=3000;
 setTimeout(()=>{
  player.dmg-=3000;
 },6000);
 player.power=0;
};

// IA DOS BOTS
function ai(b){
 if(!b.alive)return;
 let t=Math.random()<.5?player:bots[Math.floor(Math.random()*bots.length)];
 let dx=t.x-b.x,dy=t.y-b.y;
 let d=Math.hypot(dx,dy);

 b.x+=dx/d*b.spd;
 b.y+=dy/d*b.spd;

 if(d<200&&b.ammo>0){
  shoot(b,dx,dy);
 }
}

// LOOP
function loop(){
 if(!game){requestAnimationFrame(loop);return;}
 x.clearRect(0,0,c.width,c.height);
 let camX=player.x-c.width/2,camY=player.y-c.height/2;

 x.fillStyle="#7a5230";
 x.fillRect(-camX,-camY,MAP,MAP);

 player.x+=player.dx;
 player.y+=player.dy;

 x.fillStyle="yellow";
 x.beginPath();
 x.arc(c.width/2,c.height/2,player.r,0,7);
 x.fill();

 x.fillText(player.life,c.width/2-20,c.height/2-25);

 bots.forEach(b=>{
  ai(b);
  if(b.alive){
   x.fillStyle="red";
   x.beginPath();
   x.arc(b.x-camX,b.y-camY,b.r,0,7);
   x.fill();
  }
 });

 bullets.forEach((bu,i)=>{
  bu.x+=bu.dx;bu.y+=bu.dy;bu.life--;
  if(bu.owner!==player&&Math.hypot(bu.x-player.x,bu.y-player.y)<player.r){
   player.life-=1200;bullets.splice(i,1);
  }
  bots.forEach(b=>{
   if(b.alive&&bu.owner!==b&&Math.hypot(bu.x-b.x,bu.y-b.y)<b.r){
    b.life-=1500;
    if(b.life<=0)b.alive=false;
    bullets.splice(i,1);
   }
  });
  if(bu.life<=0)bullets.splice(i,1);
 });

 requestAnimationFrame(loop);
}
loop();
</script>
</body>
</html>

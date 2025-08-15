<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Dopamina Rápida</title>
<style>
*{margin:0;padding:0;box-sizing:border-box;}
body{font-family:'Arial',sans-serif;overflow-x:hidden;background:#0f2027;color:#fff;position:relative;}
canvas{position:fixed;top:0;left:0;width:100%;height:100%;z-index:-2;}
header{background:linear-gradient(135deg,#4facfe,#00f2fe);text-align:center;padding:3rem 1rem;z-index:1;position:relative;box-shadow:0 5px 20px rgba(0,0,0,0.3);}
header h1{font-size:3rem;margin-bottom:10px;text-shadow:0 0 20px #00f2fe;}
header p{font-size:1.2rem;text-shadow:0 0 10px #4facfe;}
section{padding:2rem 1rem;max-width:1000px;margin:auto;z-index:1;position:relative;}
h2{color:#4facfe;margin-bottom:1rem;text-align:center;text-shadow:0 0 10px #00f2fe;}
.cards{display:grid;grid-template-columns:repeat(auto-fit,minmax(250px,1fr));gap:1rem;margin-top:1rem;}
.card{background: rgba(255,255,255,0.1);padding:1.5rem;border-radius:15px;box-shadow:0 5px 20px rgba(0,0,0,0.3);transition:transform 0.6s,box-shadow 0.6s; transform-style: preserve-3d; cursor:pointer;}
.card:hover{transform:rotateY(15deg) scale(1.05);box-shadow:0 15px 35px rgba(0,0,0,0.6);}
.tips{background: rgba(0,188,212,0.2); border-left:5px solid #00bcd4; padding:1rem; margin:1rem 0; border-radius:10px; transition: transform 0.3s;}
.tips:hover{transform:scale(1.05);}
.test-container{background: rgba(0,0,0,0.5); padding:2rem; border-radius:20px; margin:3rem auto; max-width:800px; box-shadow:0 5px 20px rgba(0,0,0,0.5); position:relative; z-index:1;}
.question{margin-bottom:20px;text-align:left;padding:15px;border-left:5px solid #4facfe;border-radius:10px;background: rgba(255,255,255,0.1);transition:background 0.3s,transform 0.3s;position:relative;overflow:hidden;}
.question:hover{transform:translateY(-3px) scale(1.01);}
.question label{display:block;padding:8px 15px;margin:5px 0;border-radius:10px;cursor:pointer;transition: background 0.3s, color 0.3s; position:relative; z-index:1;}
input[type="radio"]{margin-right:10px;}
button{display:block;margin:auto;padding:15px 25px;font-size:1.2rem;border:none;border-radius:15px;cursor:pointer;background:linear-gradient(135deg,#4facfe,#00f2fe);color:white;transition:transform 0.3s, box-shadow 0.3s, background 0.3s;text-shadow:0 0 10px #00f2fe;}
button:hover{transform:scale(1.05);box-shadow:0 10px 25px rgba(0,0,0,0.5);background:linear-gradient(135deg,#00f2fe,#4facfe);}
#result{margin-top:25px;padding:20px;border-radius:20px;display:none;font-weight:bold;text-align:center;transition:all 0.5s ease-in-out;position:relative;}
#result.show{display:block;animation:fadeIn 1s ease;}
@keyframes fadeIn{from{opacity:0;}to{opacity:1;}}
#result.green{background:#d4edda;border:3px solid #28a745;color:#155724;}
#result.yellow{background:#fff3cd;border:3px solid #ffc107;color:#856404;}
#result.red{background:#f8d7da;border:3px solid #dc3545;color:#721c24;}
#timer{font-size:1.5rem;text-align:center;margin-bottom:20px;text-shadow:0 0 10px #00f2fe;}
footer{text-align:center;padding:2rem;background:linear-gradient(135deg,#4facfe,#00f2fe);margin-top:3rem;font-size:1.2rem;box-shadow:0 -5px 20px rgba(0,0,0,0.3);}
.selected-green{background:rgba(40,167,69,0.2);}
.selected-yellow{background:rgba(255,193,7,0.2);}
.selected-red{background:rgba(220,53,69,0.2);}
</style>
</head>
<body>

<canvas id="particles"></canvas>
<canvas id="confetti"></canvas>

<header>
<h1>Dopamina Rápida - Ultimate 4.0</h1>
<p>Interactúa, aprende y controla tu dopamina como un pro</p>
</header>

<section>
<h2>¿Qué es la Dopamina Rápida?</h2>
<p>Es la liberación instantánea de placer que sentimos al usar el celular, jugar videojuegos, comer comida chatarra o ver series sin parar. 
Nos da satisfacción inmediata, pero si abusamos de ella puede afectar nuestra motivación y bienestar.</p>
</section>

<section>
<h2>Ejemplos Comunes</h2>
<div class="cards">
<div class="card"><h3>📱 Redes Sociales</h3><p>Scroll infinito que libera dopamina al instante.</p></div>
<div class="card"><h3>🎮 Videojuegos</h3><p>Partidas rápidas y recompensas constantes.</p></div>
<div class="card"><h3>🍔 Comida Chatarra</h3><p>Sabores intensos que engañan a tu cerebro.</p></div>
<div class="card"><h3>📺 Series/YouTube</h3><p>Episodios o videos cortos uno tras otro sin parar.</p></div>
</div>
</section>

<section>
<h2>Consecuencias del Exceso</h2>
<div class="cards">
<div class="card"><h3>😴 Falta de Energía</h3><p>Te sientes cansado y sin ganas de hacer cosas productivas.</p></div>
<div class="card"><h3>📉 Menos Motivación</h3><p>Actividades importantes parecen aburridas.</p></div>
<div class="card"><h3>🧠 Ansiedad</h3><p>Tu cerebro pide más estímulo y cuesta concentrarse.</p></div>
<div class="card"><h3>💤 Sueño Alterado</h3><p>El uso excesivo de pantallas afecta tu descanso.</p></div>
</div>
</section>

<section>
<h2>Cómo Equilibrar la Dopamina</h2>
<div class="tips"><p>✅ Establece horarios para usar redes sociales.</p></div>
<div class="tips"><p>✅ Haz ejercicio físico regularmente.</p></div>
<div class="tips"><p>✅ Practica hobbies que te den satisfacción a largo plazo.</p></div>
<div class="tips"><p>✅ Prioriza el descanso y el sueño.</p></div>
</section>

<section class="test-container">
<h2>Test: ¿Cómo manejas tu dopamina?</h2>
<div id="timer">Tiempo: <span id="time">60</span>s</div>
<form id="dopamineTest">
<div class="question"><p>1. ¿Revisas el celular apenas despiertas?</p>
<label><input type="radio" name="q1" value="2"> Siempre</label>
<label><input type="radio" name="q1" value="1"> A veces</label>
<label><input type="radio" name="q1" value="0"> Nunca</label>
</div>
<div class="question"><p>2. ¿Cuántas horas al día pasas en redes sociales?</p>
<label><input type="radio" name="q2" value="2"> Más de 4 horas</label>
<label><input type="radio" name="q2" value="1"> 2 a 4 horas</label>
<label><input type="radio" name="q2" value="0"> Menos de 2 horas</label>
</div>
<div class="question"><p>3. ¿Te cuesta concentrarte en tus estudios o trabajo sin distraerte?</p>
<label><input type="radio" name="q3" value="2"> Mucho</label>
<label><input type="radio" name="q3" value="1"> A veces</label>
<label><input type="radio" name="q3" value="0"> No</label>
</div>
<div class="question"><p>4. ¿Sueles comer snacks o comida rápida cuando estás aburrido?</p>
<label><input type="radio" name="q4" value="2"> Sí, muy seguido</label>
<label><input type="radio" name="q4" value="1"> A veces</label>
<label><input type="radio" name="q4" value="0"> No</label>
</div>
<div class="question"><p>5. ¿Qué tanto usas series/películas como escape de tus problemas?</p>
<label><input type="radio" name="q5" value="2"> Muy seguido</label>
<label><input type="radio" name="q5" value="1"> Algunas veces</label>
<label><input type="radio" name="q5" value="0"> Casi nunca</label>
</div>
<div class="question"><p>6. ¿Duermes menos de 7 horas por quedarte en redes o videojuegos?</p>
<label><input type="radio" name="q6" value="2"> Siempre</label>
<label><input type="radio" name="q6" value="1"> A veces</label>
<label><input type="radio" name="q6" value="0"> No</label>
</div>
<div class="question"><p>7. ¿Reemplazas actividades productivas por entretenimiento rápido?</p>
<label><input type="radio" name="q7" value="2"> Sí, casi siempre</label>
<label><input type="radio" name="q7" value="1"> A veces</label>
<label><input type="radio" name="q7" value="0"> No</label>
</div>
<div class="question"><p>8. ¿Haces ejercicio o alguna actividad física al menos 3 veces por semana?</p>
<label><input type="radio" name="q8" value="0"> Sí</label>
<label><input type="radio" name="q8" value="1"> Rara vez</label>
<label><input type="radio" name="q8" value="2"> Nunca</label>
</div>
<button type="button" onclick="calcularResultado()">Ver resultado</button>
</form>
<div id="result"></div>
</section>

<footer>
🌱 El equilibrio está en disfrutar, pero sin dejar que la dopamina rápida controle tu vida.
</footer>

<script>
const canvas=document.getElementById('particles'), ctx=canvas.getContext('2d');
let w=canvas.width=window.innerWidth,h=canvas.height=window.innerHeight;
const particles=[]; for(let i=0;i<150;i++){particles.push({x:Math.random()*w,y:Math.random()*h,r:Math.random()*4+1,dx:(Math.random()-0.5)*1.5,dy:(Math.random()-0.5)*1.5});}
function animate(){ctx.clearRect(0,0,w,h);for(let p of particles){p.x+=p.dx;p.y+=p.dy;if(p.x<0||p.x>w)p.dx*=-1;if(p.y<0||p.y>h)p.dy*=-1;ctx.beginPath();ctx.arc(p.x,p.y,p.r,0,Math.PI*2);ctx.fillStyle='rgba(255,255,255,0.3)';ctx.fill();}requestAnimationFrame(animate);}
animate(); window.addEventListener('resize',()=>{w=canvas.width=window.innerWidth;h=canvas.height=window.innerHeight;});

const clickSound=new Audio('https://freesound.org/data/previews/256/256113_3263906-lq.mp3');

function crearBurbuja(pregunta){
const bubble=document.createElement('span');
bubble.style.position='absolute';
bubble.style.width='15px'; bubble.style.height='15px';
bubble.style.background='rgba(255,255,255,0.8)';
bubble.style.borderRadius='50%';
bubble.style.top=Math.random()*50+'%';
bubble.style.left=Math.random()*90+'%';
bubble.style.pointerEvents='none';
bubble.style.animation='subir 1s ease-out forwards';
pregunta.appendChild(bubble);
setTimeout(()=>bubble.remove(),1000);
}
const style=document.createElement('style'); style.innerHTML='@keyframes subir{0%{transform:translateY(0) scale(1);}100%{transform:translateY(-50px) scale(0);opacity:0;}}';
document.head.appendChild(style);

const preguntas=document.querySelectorAll(".question");
preguntas.forEach(p=>{
const radios=p.querySelectorAll("input[type='radio']");
radios.forEach(radio=>{
radio.addEventListener("change",()=>{
clickSound.currentTime=0; clickSound.play();
crearBurbuja(p);
radios.forEach(r=>r.parentElement.classList.remove("selected-green","selected-yellow","selected-red"));
if(radio.value=="0") radio.parentElement.classList.add("selected-green");
else if(radio.value=="1") radio.parentElement.classList.add("selected-yellow");
else radio.parentElement.classList.add("selected-red");
});
});
});

// Confetti
const confettiCanvas=document.getElementById('confetti'), cctx=confettiCanvas.getContext('2d');
confettiCanvas.width=window.innerWidth; confettiCanvas.height=window.innerHeight;
const confettiParticles=[];
function lanzarConfetti(){
for(let i=0;i<100;i++){
confettiParticles.push({x:Math.random()*w,y:Math.random()*h,dx:(Math.random()-0.5)*10,dy:Math.random()*5+2,r:Math.random()*6+2,color:`hsl(${Math.random()*360},100%,50%)`});
}
function confettiAnimate(){cctx.clearRect(0,0,confettiCanvas.width,confettiCanvas.height);
confettiParticles.forEach((p,i)=>{p.x+=p.dx;p.y+=p.dy;p.dy+=0.05;if(p.y>confettiCanvas.height){confettiParticles.splice(i,1);}
cctx.fillStyle=p.color;cctx.beginPath();cctx.arc(p.x,p.y,p.r,0,Math.PI*2);cctx.fill();});
requestAnimationFrame(confettiAnimate);}
confettiAnimate();
} 

// Test
let tiempo=60; const timeDisplay=document.getElementById('time');
setInterval(()=>{if(tiempo>0){tiempo--;timeDisplay.textContent=tiempo;}},1000);

function calcularResultado(){
let total=0; const form=document.forms['dopamineTest'];
for(let i=1;i<=8;i++){total+=parseInt(form['q'+i].value);}
let mensaje="",color="";
if(total<=5){mensaje="<h2>✅ Estás equilibrado</h2><p>Tu autocontrol es bueno. Sigue hábitos saludables.</p>";color="green";}
else if(total<=10){mensaje="<h2>⚠️ Debes mejorar tu autocontrol</h2><p>A veces caes en la dopamina rápida. Refuerza hábitos saludables.</p>";color="yellow";}
else{mensaje="<h2>🚨 Alerta: exceso de dopamina rápida</h2><p>Reduce tiempo en pantallas y prioriza descanso.</p>";color="red";}
document.getElementById("result").innerHTML=mensaje;
document.getElementById("result").className="show "+color;
lanzarConfetti();
}
</script>

</body>
</html>

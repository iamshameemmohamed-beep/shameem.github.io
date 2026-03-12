# shameem.github.io
<!DOCTYPE html>
<html lang="en">
<head>

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Shameem Mohamed | Systems & IoT Engineer</title>

<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">

<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:Inter,sans-serif;
scroll-behavior:smooth;
}

body{
background:#050505;
color:white;
overflow-x:hidden;
}

#bg{
position:fixed;
top:0;
left:0;
z-index:-1;
}

nav{
position:fixed;
top:0;
width:100%;
display:flex;
justify-content:space-between;
padding:24px 8%;
background:rgba(0,0,0,.35);
backdrop-filter:blur(12px);
z-index:1000;
}

nav a{
margin-left:25px;
text-decoration:none;
color:white;
font-size:14px;
opacity:.75;
}

nav a:hover{
opacity:1;
}

.hero{
height:100vh;
display:flex;
flex-direction:column;
align-items:center;
justify-content:center;
text-align:center;
padding:20px;
}

.hero h1{
font-size:72px;
background:linear-gradient(90deg,#00f5ff,#6a7bff);
-webkit-background-clip:text;
-webkit-text-fill-color:transparent;
}

.typing{
margin-top:15px;
color:#aaa;
font-size:20px;
height:24px;
}

.hero p{
margin-top:25px;
max-width:650px;
color:#bbb;
line-height:1.7;
}

.btn{
margin-top:35px;
padding:14px 32px;
border-radius:30px;
border:1px solid #00f5ff;
color:#00f5ff;
text-decoration:none;
transition:.3s;
}

.btn:hover{
background:#00f5ff;
color:black;
}

section{
padding:120px 10%;
}

.section-title{
font-size:38px;
margin-bottom:60px;
}

.grid{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
gap:30px;
}

.card{
background:rgba(255,255,255,.05);
border:1px solid rgba(255,255,255,.08);
border-radius:18px;
padding:30px;
backdrop-filter:blur(12px);
transition:.4s;
}

.card:hover{
transform:translateY(-10px);
border-color:#00f5ff;
}

.timeline{
border-left:2px solid #222;
padding-left:30px;
}

.timeline-item{
margin-bottom:45px;
}

.timeline-item h3{
color:#6a7bff;
}

.skill-chart{
max-width:500px;
margin:auto;
}

footer{
text-align:center;
padding:50px;
color:#666;
font-size:14px;
}

.fade{
opacity:0;
transform:translateY(40px);
transition:all 1s;
}

.fade.show{
opacity:1;
transform:translateY(0);
}

</style>
</head>

<body>

<canvas id="bg"></canvas>

<nav>
<div><b>Shameem</b></div>

<div>
<a href="#about">About</a>
<a href="#skills">Skills</a>
<a href="#experience">Experience</a>
<a href="#projects">Projects</a>
<a href="#contact">Contact</a>
</div>
</nav>

<section class="hero">

<h1>Shameem Mohamed</h1>

<div class="typing" id="typing"></div>

<p>
Engineer working at the intersection of smart home technology,
IoT ecosystems and connected access systems. Currently supporting
Yale smart lock platforms and integration environments across
the Middle East.
</p>

<a class="btn" href="#">Download CV</a>

</section>


<section id="about" class="fade">

<h2 class="section-title">What I Work On</h2>

<div class="grid">

<div class="card">
<h3>IoT Platforms</h3>
<p>
Smart lock ecosystems, device onboarding,
firmware lifecycle and integration workflows.
</p>
</div>

<div class="card">
<h3>Access Control</h3>
<p>
Connected locks, intercom systems,
and cloud based access solutions.
</p>
</div>

<div class="card">
<h3>Technical Operations</h3>
<p>
Diagnostics, troubleshooting,
and deployment support across large scale installations.
</p>
</div>

</div>

</section>


<section id="skills" class="fade">

<h2 class="section-title">Skill Intelligence</h2>

<div class="skill-chart">
<canvas id="skillsChart"></canvas>
</div>

</section>


<section id="experience" class="fade">

<h2 class="section-title">Career</h2>

<div class="timeline">

<div class="timeline-item">
<h3>Technical Support Engineer</h3>
<p>ASSA ABLOY – Yale Smart Locks</p>
<p>2024 – Present</p>
</div>

<div class="timeline-item">
<h3>Marine Technical Specialist</h3>
<p>F3 Marine / Royal Marine Group</p>
<p>2018 – 2024</p>
</div>

</div>

</section>


<section id="projects" class="fade">

<h2 class="section-title">Highlighted Work</h2>

<div class="grid">

<div class="card">
<h3>Holiday Home Smart Access</h3>
<p>
QR based access system planning for
short term rental operators.
</p>
</div>

<div class="card">
<h3>Yale Smart Lock Integrations</h3>
<p>
Integration workflows with
home automation ecosystems.
</p>
</div>

<div class="card">
<h3>IoT Diagnostics</h3>
<p>
Device troubleshooting and
technical support architecture.
</p>
</div>

</div>

</section>


<section id="contact" class="fade">

<h2 class="section-title">Contact</h2>

<p>Dubai, United Arab Emirates</p>

<p>Email: shamimohd22@gmail.com</p>

<p>Phone: +971 50 254 2955</p>

<p>LinkedIn: linkedin.com/in/shameem95mohamed</p>

</section>

<footer>
© 2026 Shameem Mohamed
</footer>


<script>

const text=["IoT Systems Engineer",
"Smart Lock Ecosystems",
"Technical Product Support"];

let i=0;
let j=0;
let current="";
let isDeleting=false;

function type(){

current=text[i];

if(!isDeleting){
document.getElementById("typing").innerHTML=current.substring(0,j++);
}else{
document.getElementById("typing").innerHTML=current.substring(0,j--);
}

if(j==current.length){
isDeleting=true;
setTimeout(type,1500);
return;
}

if(j==0){
isDeleting=false;
i=(i+1)%text.length;
}

setTimeout(type,isDeleting?40:80);
}

type();


const ctx=document.getElementById("skillsChart");

new Chart(ctx,{
type:"radar",
data:{
labels:["IoT","Access Control","API","Troubleshooting","Automation","Engineering"],
datasets:[{
data:[90,85,75,92,80,78]
}]
},
options:{
plugins:{legend:{display:false}},
scales:{r:{grid:{color:"#333"},pointLabels:{color:"#aaa"}}}
}
});


const canvas=document.getElementById("bg");
const c=canvas.getContext("2d");

canvas.width=window.innerWidth;
canvas.height=window.innerHeight;

let particles=[];

for(let i=0;i<70;i++){
particles.push({
x:Math.random()*canvas.width,
y:Math.random()canvas.height,
dx:(Math.random()-0.5),
dy:(Math.random()-0.5)
});
}

function animate(){

c.clearRect(0,0,canvas.width,canvas.height);

particles.forEach(p=>{

c.beginPath();
c.arc(p.x,p.y,2,0,Math.PI2);
c.fillStyle="#00f5ff";
c.fill();

p.x+=p.dx;
p.y+=p.dy;

});

requestAnimationFrame(animate);

}

animate();


const observer=new IntersectionObserver(entries=>{
entries.forEach(e=>{
if(e.isIntersecting){
e.target.classList.add("show");
}
});
});

document.querySelectorAll(".fade").forEach(el=>{
observer.observe(el);
});

</script>

</body>
</html>
<!DOCTYPE html><html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Jayvee Portfolio</title><link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet"><style>
*{
  margin:0;
  padding:0;
  box-sizing:border-box;
  scroll-behavior:smooth;
}

body{
  font-family:'Poppins',sans-serif;
  background:#0f172a;
  color:#e2e8f0;
}

header{
  display:flex;
  justify-content:space-between;
  align-items:center;
  padding:15px 40px;
  background:#020617;
  position:sticky;
  top:0;
}

.logo{
  font-weight:700;
  color:#38bdf8;
}

nav a{
  margin-left:20px;
  text-decoration:none;
  color:#e2e8f0;
  font-size:14px;
}

nav a:hover{color:#38bdf8;}

.hero{
  text-align:center;
  padding:100px 20px;
}

.profile{
  width:150px;
  height:150px;
  border-radius:50%;
  object-fit:cover;
  border:4px solid #38bdf8;
  margin-bottom:20px;
}

.hero h1{font-size:36px;}
.hero span{color:#38bdf8;}
.hero p{margin-top:10px;color:#94a3b8;}

.btn{
  display:inline-block;
  margin-top:25px;
  padding:12px 25px;
  background:#38bdf8;
  color:#000;
  border-radius:8px;
  text-decoration:none;
  font-weight:600;
}

.btn:hover{transform:scale(1.05);}

section{
  padding:70px 20px;
  max-width:1000px;
  margin:auto;
}

h2{
  color:#38bdf8;
  margin-bottom:20px;
}

.card{
  background:#1e293b;
  padding:20px;
  border-radius:12px;
  margin-bottom:20px;
  transition:0.3s;
}

.card:hover{transform:translateY(-5px);}

.skills span{
  display:inline-block;
  background:#38bdf8;
  color:#000;
  padding:6px 12px;
  border-radius:6px;
  margin:5px;
}

.projects{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:20px;
}

@media(max-width:700px){
  .projects{grid-template-columns:1fr;}
}

footer{
  text-align:center;
  padding:20px;
  background:#020617;
  margin-top:40px;
  color:#94a3b8;
}

/* CALCULATOR */
.overlay{
  position:fixed;
  width:100%;
  height:100%;
  background:rgba(0,0,0,0.6);
  display:none;
  z-index:999;
}

.calculator{
  position:fixed;
  top:50%;
  left:50%;
  transform:translate(-50%,-50%);
  background:#1e293b;
  padding:20px;
  border-radius:12px;
  display:none;
  width:260px;
  z-index:1000;
}

.display{
  width:100%;
  height:50px;
  margin-bottom:10px;
  text-align:right;
  font-size:20px;
  border:none;
  border-radius:5px;
  padding:5px;
}

.buttons{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:10px;
}

button{
  padding:12px;
  border:none;
  border-radius:5px;
  cursor:pointer;
}

.operator{background:#38bdf8;}
.equal{background:#22c55e;}
.clear{background:#ef4444;}
</style></head><body><header>
  <div class="logo">Jayvee</div>
  <nav>
    <a href="#about">About</a>
    <a href="#skills">Skills</a>
    <a href="#projects">Projects</a>
    <a href="#contact">Contact</a>
  </nav>
</header><section class="hero">
  <img src="profile.jpg" alt="Profile" class="profile">
  <h1>Hello, I'm <span>Jayvee</span></h1>
  <p>Aspiring Web Developer</p>
  <a class="btn" href="#projects">View My Work</a>
</section><section id="about">
  <h2>About Me</h2>
  <div class="card">
    <p>I’m an aspiring web developer focused on building clean and responsive websites. I enjoy learning and improving my coding skills every day.</p>
  </div>
</section><section id="skills">
  <h2>Skills</h2>
  <div class="card skills">
    <span>HTML</span>
    <span>CSS</span>
    <span>JavaScript</span>
  </div>
</section><section id="projects">
  <h2>Projects</h2>
  <div class="projects">
    <div class="card">
      <h3>Portfolio Website</h3>
      <p>Responsive personal portfolio design.</p>
    </div><div class="card">
  <h3>Calculator App</h3>
  <p>Interactive popup calculator.</p>
  <p style="color:#38bdf8;cursor:pointer;" onclick="openCalc()">Open Calculator</p>
</div>

  </div>
</section><section id="contact">
  <h2>Contact</h2>
  <div class="card">
    <p>Email: jayveecastro@gmail.com</p>
  </div>
</section><footer>
  <p>© 2026 Jayvee Portfolio</p>
</footer><div class="overlay" onclick="closeCalc()"></div><div class="calculator" id="calc">
  <input type="text" id="display" class="display" disabled>  <div class="buttons">
    <button class="clear" onclick="clearDisplay()">C</button>
    <button class="operator" onclick="append('/')">/</button>
    <button class="operator" onclick="append('*')">*</button>
    <button onclick="closeCalc()">X</button><button onclick="append('7')">7</button>
<button onclick="append('8')">8</button>
<button onclick="append('9')">9</button>
<button class="operator" onclick="append('-')">-</button>

<button onclick="append('4')">4</button>
<button onclick="append('5')">5</button>
<button onclick="append('6')">6</button>
<button class="operator" onclick="append('+')">+</button>

<button onclick="append('1')">1</button>
<button onclick="append('2')">2</button>
<button onclick="append('3')">3</button>

<button onclick="append('0')">0</button>
<button onclick="append('.')">.</button>
<button class="equal" onclick="calculate()">=</button>

  </div>
</div><script>
function openCalc(){
  document.getElementById("calc").style.display="block";
  document.querySelector(".overlay").style.display="block";
}

function closeCalc(){
  document.getElementById("calc").style.display="none";
  document.querySelector(".overlay").style.display="none";
}

function append(val){
  document.getElementById("display").value += val;
}

function clearDisplay(){
  document.getElementById("display").value = "";
}

function calculate(){
  try{
    let expr = document.getElementById("display").value;
    if(!expr) return;
    let result = Function('"use strict";return (' + expr + ')')();
    document.getElementById("display").value = result;
  }catch{
    alert("Invalid input");
  }
}
</script></body>
</html>

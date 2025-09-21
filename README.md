<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Nischal Raut | Aerospace Portfolio</title>
  <!-- Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@600;700&family=Open+Sans:wght@400;500&display=swap" rel="stylesheet">
  <style>
    :root {
      --primary-dark: #0b1432;
      --primary-blue: #0B3D91;
      --accent-red: #FC3D21;
      --accent-silver: #A9A9A9;
      --text-light: #f1f1f1;
    }
    *{margin:0;padding:0;box-sizing:border-box;scroll-behavior:smooth}
    body{font-family:'Open Sans',sans-serif;background:var(--primary-dark);color:var(--text-light);line-height:1.6;}
    h1,h2,h3,h4{font-family:'Montserrat',sans-serif;margin-bottom:.5em}
    nav{position:fixed;width:100%;top:0;padding:1em 0;background:rgba(11,61,145,0.9);
      backdrop-filter: blur(8px);display:flex;justify-content:center;z-index:999;}
    nav a{color:var(--text-light);margin:0 1em;font-weight:600;position:relative;transition:.3s;}
    nav a:hover{color:var(--accent-red);}
    nav a::after{content:"";position:absolute;bottom:-4px;left:0;width:0%;height:2px;background:var(--accent-red);transition:.3s;}
    nav a:hover::after{width:100%;}
    section{padding:6em 1.5em;max-width:1100px;margin:auto;min-height:100vh}
    /* Hero */
    #hero{min-height:100vh;display:flex;flex-direction:column;justify-content:center;align-items:center;text-align:center;
      background:linear-gradient(rgba(11,20,50,0.9),rgba(0,0,0,0.9)),url('https://upload.wikimedia.org/wikipedia/commons/e/e2/CFD_visualization.png') center/cover no-repeat;}
    #hero h1{font-size:3em;color:var(--accent-red);}
    #hero h2{color:var(--accent-silver);margin-bottom:.8em}
    #hero p{max-width:600px;}
    .cta{margin-top:1.5em;}
    .btn{display:inline-block;padding:.7em 1.3em;border-radius:5px;font-weight:bold;text-decoration:none;color:white;
      background:var(--accent-red);transition:.3s;}
    .btn:hover{background:#e02815;}
    /* Cards */
    .card{background:rgba(255,255,255,0.05);border:1px solid var(--accent-silver);
      padding:1.2em;border-radius:10px;transition:.4s;cursor:pointer;overflow:hidden;}
    .card:hover{transform:translateY(-4px);box-shadow:0 0 14px rgba(252,61,33,0.4);}
    .card h3{display:flex;justify-content:space-between;align-items:center;cursor:pointer;}
    .card h3::after{content:"▼";font-size:.8em;transition:transform .3s;}
    .card.active h3::after{transform:rotate(-180deg);}
    .card-content{max-height:0;overflow:hidden;transition:max-height 0.6s ease,opacity 0.6s ease;padding-top:0;opacity:0;}
    .card.active .card-content{max-height:1000px;opacity:1;padding-top:1em;}
    .grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:1.2em;}
    /* Animations */
    .fade-in{opacity:0;transform:translateY(30px);transition:all 1s ease;}
    .fade-in.visible{opacity:1;transform:translateY(0);}
  </style>
</head>
<body>
  <nav>
    <a href="#hero">Home</a><a href="#interests">Interests</a>
    <a href="#skills">Skills</a><a href="#education">Education</a>
    <a href="#experience">Experience</a><a href="#projects">Projects</a>
    <a href="#contact">Contact</a>
  </nav>
  <!-- Hero -->
  <section id="hero">
    <h1>Nischal Raut</h1>
    <h2>Aerospace Engineer</h2>
    <p>"Bridging Computational Models and Experimental Validation."</p>
    <div class="cta"><a href="Nischal_Raut_CV.pdf" class="btn" target="_blank">📄 Download CV</a></div>
  </section>
  <!-- Projects -->
  <section id="projects" class="fade-in">
    <h2>Projects</h2>
    <div class="grid">
      <!-- Project Card -->
      <div class="card">
        <h3>Subsonic Wind Tunnel (FYP)</h3>
        <div class="card-content">
          <p>Designed and fabricated subsonic open-jet tunnel with cosine-profile gust generator integrated for unsteady aerodynamics research.</p>
          <ul>
            <li>Achieved low turbulence intensity of 0.88% (test section).</li>
            <li>50-point grid experimental testing with smoke visualization.</li>
            <li>Now used as platform for multiple peer student projects.</li>
          </ul>
        </div>
      </div>
      <!-- Project Card -->
      <div class="card">
        <h3>B-52 Air Launch to Orbit</h3>
        <div class="card-content">
          <p>Conceptual modification of B-52 airframe for rocket carriage and release (~28,000 lbs rocket at 50,000 ft altitude).</p>
          <ul>
            <li>Preliminary aircraft/mission design: MTOW, CG, structural loads.</li>
            <li>Simulated deployment sequence using X-Plane 12 for aerodynamics.</li>
            <li>Analyzed performance using Excel: velocity, pitch, altitude profiles.</li>
          </ul>
        </div>
      </div>
      <!-- Project Card -->
      <div class="card">
        <h3>F-15 Scale Model Study</h3>
        <div class="card-content">
          <p>Performed lift-drag coefficient scaling study for subsonic F-15 model.</p>
          <p>Tools Used: MATLAB + CFD integration.</p>
        </div>
      </div>
      <!-- Project Card -->
      <div class="card">
        <h3>U-2 Aircraft Conversion</h3>
        <div class="card-content">
          <p>Converted U-2 as aerial testbed platform for payload deployment experiments, focusing on aerodynamic and structural redesign feasibility.</p>
        </div>
      </div>
      <!-- Project Card -->
      <div class="card">
        <h3>Styrofoam Glider</h3>
        <div class="card-content">
          <p>Designed and fabricated low-speed, high-lift glider using XFLR5 analysis.</p>
          <p>Fabricated with styrofoam and reinforcements, validated in real flights.</p>
        </div>
      </div>
      <!-- Project Card -->
      <div class="card">
        <h3>Canteen Billing System (C)</h3>
        <div class="card-content">
          <p>Developed a C program for billing system with VAT computation, file saving, searching, and automated receipts.</p>
        </div>
      </div>
    </div>
  </section>
  <!-- Contact -->
  <section id="contact" class="fade-in">
    <h2>Contact</h2>
    <p>Email: <a href="mailto:nischalraut6@gmail.com">nischalraut6@gmail.com</a></p>
    <p>Phone: +977-9813980068</p>
    <p>LinkedIn: <a href="https://www.linkedin.com/in/nischal-raut-1b2227314/" target="_blank">linkedin.com/in/nischal-raut-1b2227314/</a></p>
    <p>Location: Pulchowk, Lalitpur, Nepal</p>
  </section>
  <script>
    // Card expand/collapse
    document.querySelectorAll('.card').forEach(card=>{
      card.addEventListener('click',()=>{
        card.classList.toggle('active');
      });
    });
    // Fade animation
    const faders=document.querySelectorAll('.fade-in');
    const appearOnScroll=new IntersectionObserver((entries,observer)=>{
      entries.forEach(entry=>{
        if(entry.isIntersecting){
          entry.target.classList.add('visible');
          observer.unobserve(entry.target);
        }
      });
    },{threshold:0.15,rootMargin:"0px 0px -50px"});
    faders.forEach(f=>appearOnScroll.observe(f));
  </script>
</body>
</html>

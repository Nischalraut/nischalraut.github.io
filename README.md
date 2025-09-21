<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Nischal Raut | Aerospace Engineer</title>

  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600;700&family=Lato:wght@400;500;600&display=swap" rel="stylesheet">

  <style>
    :root {
      --accent-red: #FC3D21;
      --text-main: #f8f9fa;
      --text-muted: #d1d5db;
      --nav-bg: rgba(17,24,39,0.7);
    }
    *{margin:0;padding:0;box-sizing:border-box;scroll-behavior:smooth;}
    body {
      font-family:'Lato',sans-serif;
      color:var(--text-main);
      background: linear-gradient(-45deg,#0b1432,#0B3D91,#162447,#2b2e4a);
      background-size: 400% 400%;
      animation: bgShift 30s ease infinite;
    }
    @keyframes bgShift {
      0%{background-position:0% 50%}
      50%{background-position:100% 50%}
      100%{background-position:0% 50%}
    }
    h1,h2,h3,h4 {
      font-family:'Playfair Display',serif;
    }
    a{text-decoration:none;color:inherit;}

    /* Navbar */
    nav {position:fixed;top:0;width:100%;background:var(--nav-bg);backdrop-filter: blur(8px);
      display:flex;justify-content:space-between;align-items:center;padding:1em 2em;z-index:1000;}
    nav .brand{font-size:1.4em;font-weight:700;color:var(--accent-red);}
    nav ul{list-style:none;display:flex;gap:1.5em;margin:0;}
    nav ul li a{color:var(--text-main);font-weight:500;}
    nav ul li a:hover{color:var(--accent-red);}
    .menu-toggle{display:none;font-size:1.8em;cursor:pointer;color:white;}
    @media(max-width:768px){
      nav ul{display:none;flex-direction:column;background:#111827;padding:1em;position:absolute;right:0;top:100%;width:200px;}
      nav ul.active{display:flex;}
      .menu-toggle{display:block;}
    }

    /* Hero */
    #hero {padding-top:7em;min-height:100vh;display:flex;align-items:center;justify-content:center;}
    .hero-container{display:flex;align-items:center;gap:2.5em;flex-wrap:wrap;max-width:1100px;margin:auto;}
    .hero-img img{width:260px;height:260px;object-fit:cover;border-radius:50%;box-shadow:0 0 20px rgba(252,61,33,.7);}
    .hero-text{flex:1;}
    #hero h1{font-size:3em;font-weight:700;color:var(--accent-red);margin-bottom:.3em;}
    #hero h2{font-size:1.6em;color:var(--text-main);font-weight:500;margin-bottom:.6em;}
    .typing{font-size:1.1em;color:var(--text-muted);margin-bottom:1em;height:1.2em;}
    .intro{font-size:1.05em;line-height:1.6;margin-bottom:1.3em;max-width:650px;}
    .btn{background:var(--accent-red);color:white;padding:.7em 1.2em;border-radius:5px;font-weight:600;transition:.3s;}
    .btn:hover{background:white;color:var(--accent-red);}
    .scroll-down{margin-top:3em;font-size:2em;color:var(--accent-red);animation:bounce 1.5s infinite;}
    @keyframes bounce{0%,20%,50%,80%,100%{transform:translateY(0);}40%{transform:translateY(8px);}60%{transform:translateY(4px);}}

    section{padding:5em 1.5em;max-width:1100px;margin:auto;}

    /* Skills */
    #skills h2{margin-bottom:1em;color:var(--accent-red);}
    .skill-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:1.2em;}
    .skill-card{background:rgba(255,255,255,0.05);padding:1em;border-radius:8px;text-align:center;transition:.3s;}
    .skill-card:hover{transform:translateY(-3px);box-shadow:0 0 12px rgba(252,61,33,.5);}

    /* Education */
    #education h2{margin-bottom:1em;color:var(--accent-red);}
    .edu-grid{display:grid;grid-template-columns:70px 1fr;gap:1em;align-items:center;margin-bottom:1em;}
    .edu-grid img{width:70px;height:70px;object-fit:contain;}
    .edu-card{background:rgba(255,255,255,0.05);padding:1em;border-radius:8px;}

    /* Projects */
    #projects h2{margin-bottom:1em;color:var(--accent-red);}
    .projects-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(250px,1fr));gap:1em;}
    .project-card{background:rgba(255,255,255,.05);padding:1.2em;border-radius:8px;cursor:pointer;transition:.3s;}
    .project-card:hover{transform:translateY(-3px);box-shadow:0 0 12px rgba(252,61,33,.4);}
    .project-card h3{margin:.3em 0;color:var(--accent-red);}

    /* Modals */
    .modal{display:none;position:fixed;z-index:9999;top:0;left:0;width:100%;height:100%;
      background:rgba(0,0,0,0.9);align-items:center;justify-content:center;padding:1em;}
    .modal-content{background:#1f2937;color:white;padding:2em;border-radius:10px;max-width:800px;width:100%;
      max-height:90vh;overflow-y:auto;position:relative;}
    .modal h2{margin-top:0;color:var(--accent-red);}
    .modal .close{position:absolute;top:10px;right:15px;font-size:1.5em;cursor:pointer;}
    .carousel{position:relative;margin-top:1em;}
    .carousel img{width:100%;display:none;border-radius:8px;}
    .carousel img.active{display:block;}
    .carousel button{position:absolute;top:50%;transform:translateY(-50%);background:rgba(0,0,0,0.4);border:none;color:white;font-size:1.5em;cursor:pointer;}
    .carousel .prev{left:10px}.carousel .next{right:10px}

    /* Contact */
    #contact h2{margin-bottom:1em;color:var(--accent-red);}
    #contact p{margin:.3em 0;}
  </style>
</head>
<body>

  <!-- Navbar -->
  <nav>
    <div class="brand">Nischal Raut</div>
    <div class="menu-toggle">&#9776;</div>
    <ul>
      <li><a href="#hero">Home</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#education">Education</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>

  <!-- Hero -->
  <section id="hero">
    <div class="hero-container">
      <div class="hero-img"><img src="profile.jpg" alt="Profile Picture"></div>
      <div class="hero-text">
        <h1>Nischal Raut</h1>
        <h2>Aerospace Engineer</h2>
        <div class="typing" id="typing"></div>
        <p class="intro">Hi! I'm Nischal Raut, aerospace engineer with a deep interest in experimental aerodynamics & CFD.  
          Bridging computational models with fabrication drives my research. <br> Current Bachelor's aggregate: <b>76.71%</b>.
        </p>
        <a href="Nischal_Raut_CV.pdf" class="btn">📄 Download CV</a>
      </div>
    </div>
    <div class="scroll-down">&#8595;</div>
  </section>

  <!-- Skills -->
  <section id="skills">
    <h2>Skills & Tools</h2>
    <div class="skill-grid">
      <div class="skill-card">CAD & Analysis: CATIA, ANSYS, SolidWorks, MATLAB</div>
      <div class="skill-card">Programming: C, Python, MATLAB scripting</div>
      <div class="skill-card">Simulation: Wind Tunnel Testing, Flow Visualization</div>
      <div class="skill-card">Productivity: MS Office, LaTeX, AutoCAD</div>
    </div>
  </section>

  <!-- Education -->
  <section id="education">
    <h2>Education</h2>
    <div class="edu-grid"><img src="ioe.png"><div class="edu-card"><h3>Institute of Engineering, Pulchowk</h3><p>Bachelor’s in Aerospace Engineering (2019–2025)</p><p><b>Aggregate: 76.71%</b></p></div></div>
    <div class="edu-grid"><img src="omega.png"><div class="edu-card"><h3>Omega International College</h3><p>+2 Science, GPA: 3.5</p></div></div>
    <div class="edu-grid"><img src="westwing.png"><div class="edu-card"><h3>West Wing Secondary School</h3><p>SEE GPA: 4.0</p></div></div>
  </section>

  <!-- Projects -->
  <section id="projects">
    <h2>Projects</h2>
    <div class="projects-grid">
      <div class="project-card" onclick="openModal('modal1')"><h3>Subsonic Wind Tunnel</h3><p>Final Year Project with gust generator</p></div>
      <div class="project-card" onclick="openModal('modal2')"><h3>B-52 Air Launch</h3><p>B-52 modification for rocket air-launch</p></div>
      <div class="project-card" onclick="openModal('modal3')"><h3>Styrofoam Glider</h3><p>Low-speed glider project</p></div>
      <div class="project-card" onclick="openModal('modal4')"><h3>U-2 Conversion</h3><p>Modified U‑2 for payload tests</p></div>
      <div class="project-card" onclick="openModal('modal5')"><h3>F-15 Scale Study</h3><p>Lift-drag aerodynamic scaling</p></div>
      <div class="project-card" onclick="openModal('modal6')"><h3>Canteen System</h3><p>C programming billing project</p></div>
    </div>
  </section>

  <!-- Project Modals -->
  <div class="modal" id="modal1"><div class="modal-content"><span class="close" onclick="closeModal('modal1')">&times;</span>
    <h2>Subsonic Wind Tunnel</h2><p>Designed & fabricated subsonic tunnel with gust generator. Flow studies + turbulence validation.</p>
    <div class="carousel"><button class="prev" onclick="prevSlide(this)">&#10094;</button>
      <img src="windtunnel1.jpeg" class="active"><img src="windtunnel2.jpeg"><img src="windtunnel3.jpeg">
      <button class="next" onclick="nextSlide(this)">&#10095;</button></div></div></div>

  <div class="modal" id="modal2"><div class="modal-content"><span class="close" onclick="closeModal('modal2')">&times;</span>
    <h2>B-52 Air Launch</h2><p>Conceptual B‑52 modification for rocket release, simulated in X‑Plane 12.</p>
    <div class="carousel"><button class="prev" onclick="prevSlide(this)">&#10094;</button><img src="b521.png" class="active"><img src="b522.png"><button class="next" onclick="nextSlide(this)">&#10095;</button></div>
  </div></div>

  <div class="modal" id="modal3"><div class="modal-content"><span class="close" onclick="closeModal('modal3')">&times;</span>
    <h2>Styrofoam Glider</h2><p>Lightweight glider designed in XFLR5, fabricated and test flown.</p>
    <div class="carousel"><button class="prev" onclick="prevSlide(this)">&#10094;</button><img src="glider1.jpeg" class="active"><img src="glider2.jpeg"><button class="next" onclick="nextSlide(this)">&#10095;</button></div>
  </div></div>

  <div class="modal" id="modal4"><div class="modal-content"><span class="close" onclick="closeModal('modal4')">&times;</span>
    <h2>U‑2 Conversion</h2><p>Converted U‑2 reconnaissance aircraft design for payload deployment testbed.</p>
  </div></div>

  <div class="modal" id="modal5"><div class="modal-content"><span class="close" onclick="closeModal('modal5')">&times;</span>
    <h2>F‑15 Scale Model</h2><p>CFD + MATLAB based study on subsonic F‑15 model drag/lift performance.</p>
  </div></div>

  <div class="modal" id="modal6"><div class="modal-content"><span class="close" onclick="closeModal('modal6')">&times;</span>
    <h2>Canteen Billing System</h2><p>C language program: VAT billing, file handling, and receipts.</p>
  </div></div>

  <!-- Contact -->
  <section id="contact">
    <h2>Contact</h2>
    <p>Email: <a href="mailto:nischalraut6@gmail.com">nischalraut6@gmail.com</a></p>
    <p>Phone: +977-9813980068</p>
    <p>LinkedIn: <a href="https://www.linkedin.com/in/nischal-raut-1b2227314/" target="_blank">linkedin.com/in/nischal-raut</a></p>
  </section>

  <script>
    // Mobile menu
    document.querySelector('.menu-toggle').onclick=()=>document.querySelector('nav ul').classList.toggle('active');

    // Typing effect
    const roles=["CFD Enthusiast","Innovator","Researcher","UAV Developer"];
    let el=document.getElementById("typing");
    let i=0,char=0,del=false;
    function type(){let word=roles[i];
      if(!del && char<=word.length){el.textContent=word.substring(0,char);char++;}
      else if(del && char>=0){el.textContent=word.substring(0,char);char--;}
      if(char===word.length+1){del=true;setTimeout(type,1000);return;}
      if(char===0 && del){del=false;i=(i+1)%roles.length;}
      setTimeout(type,del?80:140);}
    type();

    // Modals
    function openModal(id){document.getElementById(id).style.display='flex';}
    function closeModal(id){document.getElementById(id).style.display='none';}

    // Carousel inside modal
    function nextSlide(btn){const imgs=btn.parentElement.querySelectorAll('img');let idx=[...imgs].findIndex(im=>im.classList.contains('active'));
      imgs[idx].classList.remove('active');imgs[(idx+1)%imgs.length].classList.add('active');}
    function prevSlide(btn){const imgs=btn.parentElement.querySelectorAll('img');let idx=[...imgs].findIndex(im=>im.classList.contains('active'));
      imgs[idx].classList.remove('active');imgs[(idx-1+imgs.length)%imgs.length].classList.add('active');}
  </script>
</body>
</html>

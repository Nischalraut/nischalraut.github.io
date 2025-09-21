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
    * { margin:0; padding:0; box-sizing:border-box; scroll-behavior:smooth; }
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
    h1,h2,h3,h4 {font-family:'Playfair Display',serif;}
    a{text-decoration:none;color:inherit;}

    /* Navbar */
    nav {
      position:fixed;top:0;width:100%;
      background:var(--nav-bg);backdrop-filter: blur(8px);
      display:flex;justify-content:space-between;align-items:center;
      padding:1em 2em;z-index:1000;
    }
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

    section{padding:5em 1.5em;max-width:1200px;margin:auto;}

    /* Hero */
    #hero {
      min-height:100vh;
      display:flex;align-items:center;justify-content:center;
      padding: 7em 2em 4em;
    }
    .hero-container {
      display:grid;grid-template-columns:1fr 1fr;align-items:center;gap:2em;
    }
    .hero-text h1 {font-size:3em;color:var(--accent-red);}
    .hero-text h2 {font-size:1.5em;margin-bottom:.8em;color:var(--text-main);}
    .hero-text p {font-size:1.1em;line-height:1.7;margin-bottom:1.5em;}
    .btn {background:var(--accent-red);color:white;padding:.8em 1.3em;border-radius:6px;font-weight:600;transition:.3s;}
    .btn:hover {background:white;color:var(--accent-red);}
    .hero-img img {
      width: 320px; height: 320px;border-radius:50%;object-fit:cover;
      box-shadow:0 0 25px rgba(0,0,0,.4);
    }
    @media(max-width:900px){.hero-container{grid-template-columns:1fr;text-align:center;} .hero-img img{margin:auto;}}

    /* Skills */
    #skills h2{margin-bottom:1em;color:var(--accent-red);}
    .skill-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:1.2em;}
    .skill-card{background:rgba(255,255,255,0.05);padding:1em;border-radius:8px;text-align:center;transition:.3s;}
    .skill-card:hover{transform:translateY(-3px);box-shadow:0 0 12px rgba(252,61,33,.5);}

    /* Education / Experience with two-column layout */
    h2.section-title {margin-bottom:1.5em;color:var(--accent-red);}
    .item-row {
      display:grid;grid-template-columns:90px 1fr;gap:1.5em;
      align-items:center;background:rgba(255,255,255,0.05);
      padding:1.2em;border-radius:10px;margin-bottom:1em;
    }
    .item-row img {
      width:80px;height:80px;object-fit:contain;
      background:white;padding:.3em;border-radius:8px;
    }
    .item-info h3 {margin:0;color:var(--accent-red);}
    .item-info p{margin:.3em 0;color:var(--text-muted);}

    /* Projects */
    #projects h2{margin-bottom:1em;color:var(--accent-red);}
    .projects-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(250px,1fr));gap:1em;}
    .project-card{background:rgba(255,255,255,.05);padding:1.2em;border-radius:8px;cursor:pointer;transition:.3s;}
    .project-card:hover{transform:translateY(-3px);box-shadow:0 0 12px rgba(252,61,33,.4);}
    .project-card h3{margin:.3em 0;color:var(--accent-red);}

    /* Modals */
    .modal{display:none;position:fixed;z-index:9999;top:0;left:0;width:100%;height:100%;
      background:rgba(0,0,0,0.9);align-items:center;justify-content:center;padding:2em;}
    .modal-content{background:#1f2937;color:white;border-radius:10px;padding:2em;max-width:1000px;width:100%;
      display:grid;grid-template-columns:1fr 1fr;gap:2em;max-height:90vh;overflow-y:auto;position:relative;}
    .modal h2{margin-top:0;color:var(--accent-red);}
    .modal .close{position:absolute;top:10px;right:15px;font-size:1.5em;cursor:pointer;}
    .details p{line-height:1.7;}
    .carousel img{width:100%;display:none;border-radius:8px;}
    .carousel img.active{display:block;}
    .carousel button{position:absolute;top:50%;transform:translateY(-50%);background:rgba(0,0,0,0.4);border:none;color:white;font-size:1.5em;cursor:pointer;}
    .carousel .prev{left:10px}.carousel .next{right:10px}
    @media(max-width:900px){.modal-content{grid-template-columns:1fr;}}

    /* Contact */
    #contact h2{margin-bottom:1em;color:var(--accent-red);}
    #contact p{margin:.4em 0;}
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
      <li><a href="#experience">Experience</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>

  <!-- Hero -->
  <section id="hero">
    <div class="hero-container">
      <div class="hero-text">
        <h1>Nischal Raut</h1>
        <h2>Aerospace Engineer</h2>
        <p>
          Hi! I'm an aspiring aerospace engineer passionate about experimental aerodynamics & CFD.  
          Bridging computational models with experimental validation. <br> Bachelor’s Aggregate: <b>76.71%</b>.
        </p>
        <a href="Nischal_Raut_CV.pdf" class="btn">📄 Download CV</a>
      </div>
      <div class="hero-img"><img src="profile.jpg" alt="Profile Picture"></div>
    </div>
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
    <h2 class="section-title">Education</h2>
    <div class="item-row">
      <img src="ioe.png" alt="Pulchowk IOE">
      <div class="item-info"><h3>Institute of Engineering, Pulchowk</h3><p>Bachelor’s in Aerospace Engineering (2019–2025)</p><p>Aggregate: 76.71%</p></div>
    </div>
    <div class="item-row">
      <img src="omega.png" alt="Omega College">
      <div class="item-info"><h3>Omega International College</h3><p>+2 Science, GPA: 3.5</p></div>
    </div>
    <div class="item-row">
      <img src="westwing.png" alt="West Wing">
      <div class="item-info"><h3>West Wing Secondary School</h3><p>SEE GPA: 4.0</p></div>
    </div>
  </section>

  <!-- Experience -->
  <section id="experience">
    <h2 class="section-title">Experience</h2>
    <div class="item-row">
      <img src="airlift.png" alt="Airlift Tech">
      <div class="item-info"><h3>Engineering Intern – Airlift Technology, Nepal</h3><p>2024 – Present</p>
        <p>• Drone mapping & photogrammetry for Kathmandu Metropolitan City.</p>
        <p>• Generated 3D terrain models & orthomosaics.</p>
        <p>• Supported UAV mission planning & calibration.</p></div>
    </div>
  </section>

  <!-- Projects -->
  <section id="projects">
    <h2>Projects</h2>
    <div class="projects-grid">
      <div class="project-card" onclick="openModal('modal1')"><h3>Subsonic Wind Tunnel</h3><p>Final Year Project</p></div>
      <div class="project-card" onclick="openModal('modal2')"><h3>B-52 Air Launch</h3><p>Conceptual Rocket Carrier</p></div>
      <div class="project-card" onclick="openModal('modal3')"><h3>Styrofoam Glider</h3><p>Design + Test flights</p></div>
      <div class="project-card" onclick="openModal('modal4')"><h3>U-2 Conversion</h3><p>Payload Testbed Study</p></div>
      <div class="project-card" onclick="openModal('modal5')"><h3>F-15 Scale Model</h3><p>Lift-Drag CFD Study</p></div>
      <div class="project-card" onclick="openModal('modal6')"><h3>Canteen Billing System</h3><p>C Program</p></div>
    </div>
  </section>

  <!-- Example Project Modal -->
  <div class="modal" id="modal1"><div class="modal-content">
    <span class="close" onclick="closeModal('modal1')">&times;</span>
    <div class="details">
      <h2>Subsonic Wind Tunnel</h2>
      <p>Designed & built open-jet tunnel with gust generator. Turbulent Intensity 0.88% validated experimentally.</p>
    </div>
    <div class="carousel">
      <button class="prev" onclick="prevSlide(this)">&#10094;</button>
      <img src="windtunnel1.jpeg" class="active">
      <img src="windtunnel2.jpeg">
      <img src="windtunnel3.jpeg">
      <button class="next" onclick="nextSlide(this)">&#10095;</button>
    </div>
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

  // Modal controls
  function openModal(id){document.getElementById(id).style.display='flex';}
  function closeModal(id){document.getElementById(id).style.display='none';}

  // Carousel
  function nextSlide(btn){
    const imgs=btn.parentElement.querySelectorAll('img');
    let idx=[...imgs].findIndex(im=>im.classList.contains('active'));
    imgs[idx].classList.remove('active');
    imgs[(idx+1)%imgs.length].classList.add('active');
  }
  function prevSlide(btn){
    const imgs=btn.parentElement.querySelectorAll('img');
    let idx=[...imgs].findIndex(im=>im.classList.contains('active'));
    imgs[idx].classList.remove('active');
    imgs[(idx-1+imgs.length)%imgs.length].classList.add('active');
  }
</script>

</body>
</html>

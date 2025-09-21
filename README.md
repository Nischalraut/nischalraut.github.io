<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Nischal Raut | Aerospace Engineer</title>
  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Montserrat+Alternates:wght@600;900&family=Poppins:wght@400;500;600&display=swap" rel="stylesheet">
  <style>
    :root {
      --primary-blue: #0B3D91;
      --accent-red: #FC3D21;
      --light-text: #f1f1f1;
      --silver: #A9A9A9;
    }
    *{margin:0;padding:0;box-sizing:border-box;scroll-behavior:smooth}
    body{
      font-family:'Poppins',sans-serif;
      color:var(--light-text);
      /* smooth gradient bg animation */
      background: linear-gradient(-45deg,#0b1432,#0B3D91,#162447,#2b2e4a);
      background-size:400% 400%;
      animation:bgShift 30s ease infinite;
    }
    @keyframes bgShift {0%{background-position:0% 50%;}50%{background-position:100% 50%;}100%{background-position:0% 50%;}}
    h1,h2,h3,h4{font-family:'Montserrat Alternates',sans-serif;letter-spacing:1px;margin-bottom:.5em}
    a{text-decoration:none;color:inherit}

    /* Navbar */
    nav{position:fixed;top:0;left:0;width:100%;background:rgba(11,61,145,0.9);
      display:flex;justify-content:space-between;align-items:center;
      padding:1em 2em;z-index:1000;}
    nav .brand{font-size:1.3em;font-weight:700;color:white;}
    nav ul{list-style:none;display:flex;gap:1.5em;}
    nav ul li a{font-weight:600;position:relative;color:white;}
    nav ul li a::after{content:"";position:absolute;bottom:-4px;left:0;width:0;height:2px;background:var(--accent-red);transition:.3s;}
    nav ul li a:hover::after{width:100%;}
    .menu-toggle{display:none;font-size:1.8em;cursor:pointer;color:white;}
    @media(max-width:768px){
      nav ul{display:none;flex-direction:column;background:var(--primary-blue);
      position:absolute;top:100%;right:0;width:200px;padding:1em;}
      nav ul.active{display:flex;}
      .menu-toggle{display:block;}
    }

    /* Hero (with intro integrated) */
    #hero{padding-top:6em;padding-bottom:3em;display:flex;justify-content:center;align-items:center;text-align:left;}
    .hero-container{display:flex;align-items:center;gap:2em;flex-wrap:wrap;max-width:1100px;margin:auto;}
    .hero-img img{width:240px;height:240px;object-fit:cover;border-radius:50%;box-shadow:0 0 20px rgba(252,61,33,0.6);}
    .hero-text{flex:1;}
    #hero h1{font-size:3.2em;font-weight:900;
      background:linear-gradient(90deg,#FC3D21,#ff6b6b,#FC3D21);
      background-size:200%;-webkit-background-clip:text;-webkit-text-fill-color:transparent;
      animation:gradientMove 6s infinite linear;}
    @keyframes gradientMove{0%{background-position:0%}100%{background-position:200%}}
    #hero h2{margin-top:.3em;font-size:1.4em;color:var(--light-text);}
    #hero .tagline{margin:.4em 0;font-style:italic;opacity:.9;}
    #hero .intro{margin:.8em 0 1.2em;font-size:1.05em;line-height:1.6;max-width:650px;opacity:0.95;}
    .btn{margin-top:1em;padding:.7em 1.3em;background:var(--accent-red);color:white;font-weight:bold;border-radius:6px;cursor:pointer;transition:.3s;}
    .btn:hover{background:white;color:var(--accent-red);transform:scale(1.05);}
    .scroll-down{margin-top:2em;font-size:2em;color:var(--accent-red);animation:bounce 1.5s infinite;}
    @keyframes bounce{0%,20%,50%,80%,100%{transform:translateY(0);}40%{transform:translateY(8px);}60%{transform:translateY(4px);}}

    /* Sections */
    section{padding:4.5em 1.5em;max-width:1100px;margin:auto;position:relative}
    .fade-in{opacity:0;transform:translateY(30px);transition:all 1s ease;}
    .fade-in.visible{opacity:1;transform:translateY(0);}

    /* Skills */
    .skill-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:1.2em;margin-top:1.5em;}
    .skill-card{background:rgba(255,255,255,0.08);border:1px solid var(--silver);border-radius:8px;padding:1em;text-align:center;transition:.3s;font-weight:500;}
    .skill-card:hover{box-shadow:0 0 12px rgba(252,61,33,.5);transform:translateY(-4px);}

    /* Education */
    .edu-grid{display:grid;grid-template-columns:70px 1fr;gap:1em;align-items:center;margin-bottom:1em;}
    .edu-grid img{width:70px;height:70px;object-fit:contain;background:transparent;}
    .edu-card{background:rgba(255,255,255,0.08);padding:.8em;border-radius:8px;}

    /* Experience / Projects */
    .card{background:rgba(255,255,255,0.08);border:1px solid var(--silver);
      padding:1em;border-radius:10px;transition:.4s;cursor:pointer;margin-bottom:1em;}
    .card h3{display:flex;justify-content:space-between;align-items:center;font-size:1.1em;}
    .card h3::after{content:"▼";font-size:.8em;transition:.3s;}
    .card.active h3::after{transform:rotate(-180deg);}
    .card-content{max-height:0;overflow:hidden;transition:max-height .6s ease,opacity .6s ease;padding-top:0;opacity:0;}
    .card.active .card-content{max-height:1000px;opacity:1;padding-top:1em;}

    /* Projects with carousel + lightbox */
    .grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(270px,1fr));gap:1em;}
    .carousel{position:relative;margin-top:1em;overflow:hidden;border-radius:8px;}
    .carousel img{width:100%;display:none;border-radius:6px;cursor:pointer;}
    .carousel img.active{display:block;}
    .carousel button{position:absolute;top:50%;transform:translateY(-50%);
      background:rgba(0,0,0,0.4);border:none;color:white;font-size:1.5em;
      padding:.2em .5em;cursor:pointer;border-radius:50%;}
    .carousel .prev{left:10px}.carousel .next{right:10px}

    /* Lightbox */
    #lightbox{display:none;position:fixed;z-index:9999;left:0;top:0;width:100%;height:100%;background:rgba(0,0,0,0.9);}
    #lightbox img{margin:auto;display:block;max-width:80%;max-height:75%;}
    #lightbox .caption{color:white;text-align:center;margin-top:10px;font-size:1.05em;}
    #lightbox .close{position:absolute;top:15px;right:25px;color:#fff;font-size:36px;cursor:pointer;}
    .lightbox-prev,.lightbox-next{cursor:pointer;position:absolute;top:50%;color:white;font-size:2.5em;font-weight:bold;padding:10px;}
    .lightbox-prev{left:15px}.lightbox-next{right:15px}
    .lightbox-prev:hover,.lightbox-next:hover,#lightbox .close:hover{color:var(--accent-red);}
  </style>
</head>
<body>
  <!-- Navbar -->
  <nav>
    <div class="brand">Nischalraut</div>
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
      <div class="hero-img"><img src="profile.jpg" alt="Profile Picture"></div>
      <div class="hero-text">
        <h1>Nischal Raut</h1>
        <h2>Aerospace Engineer</h2>
        <p class="tagline">"Bridging Computational Models and Experimental Validation."</p>
        <p class="intro">Hi! I'm Nischal Raut, aerospace engineer with deep interest in experimental aerodynamics & CFD. 
          I combine computational flow modeling with hands-on fabrication to create innovative research setups. 
          Passionate about resilience and continuous growth, my current aggregate across my bachelor's is <b>76.71%</b>.
        </p>
        <a href="Nischal_Raut_CV.pdf" class="btn">📄 Download CV</a>
      </div>
    </div>
    <div class="scroll-down">&#8595;</div>
  </section>

  <!-- Skills -->
  <section id="skills" class="fade-in">
    <h2>Skills & Tools</h2>
    <div class="skill-grid">
      <div class="skill-card">CAD & Analysis: CATIA, ANSYS, SolidWorks, MATLAB</div>
      <div class="skill-card">Programming: C (basic), Python, MATLAB scripting</div>
      <div class="skill-card">Simulation: Wind Tunnel Testing, Flow Visualization</div>
      <div class="skill-card">Productivity: MS Office, LaTeX, AutoCAD</div>
    </div>
  </section>

  <!-- Education -->
  <section id="education" class="fade-in">
    <h2>Education</h2>
    <div class="edu-grid">
      <img src="ioe.png" alt="Pulchowk IOE">
      <div class="edu-card"><h3>Institute of Engineering, Pulchowk</h3><p>Bachelor's in Aerospace Engineering (2019–2025)</p><p><b>Aggregate: 76.71%</b></p></div>
    </div>
    <div class="edu-grid">
      <img src="omega.png" alt="Omega International College">
      <div class="edu-card"><h3>Omega International College</h3><p>+2 Science, GPA: 3.5</p></div>
    </div>
    <div class="edu-grid">
      <img src="westwing.png" alt="West Wing Secondary School">
      <div class="edu-card"><h3>West Wing Secondary School</h3><p>SEE GPA: 4.0</p></div>
    </div>
  </section>

  <!-- Experience -->
  <section id="experience" class="fade-in">
    <h2>Experience</h2>
    <div class="card active"><h3>Intern – Airlift Technology Nepal (2024–Present)</h3>
      <div class="card-content" style="max-height:1000px;opacity:1;">
        <ul><li>Drone mapping & photogrammetry projects.</li><li>3D terrain model generation.</li><li>UAV operations & calibration.</li></ul>
      </div>
    </div>
  </section>

  <!-- Projects -->
  <section id="projects" class="fade-in">
    <h2>Projects</h2>
    <div class="grid">
      <div class="card"><h3>Subsonic Wind Tunnel (FYP)</h3>
        <div class="card-content"><p>Designed & fabricated an open-jet wind tunnel with gust generator.</p>
          <div class="carousel"><button class="prev">&#10094;</button><div class="carousel-images">
              <img src="windtunnel1.jpeg" class="active" alt="Wind Tunnel Front View" data-caption="Wind Tunnel Front View">
              <img src="windtunnel2.jpeg" alt="Wind Tunnel Side" data-caption="Wind Tunnel Side view">
              <img src="windtunnel3.jpeg" alt="Wind Tunnel Under Construction" data-caption="Wind Tunnel Under Construction">
          </div><button class="next">&#10095;</button></div>
        </div></div>
      <div class="card"><h3>B-52 Air Launch to Orbit</h3>
        <div class="card-content"><p>B-52 modified as rocket carrier, simulated in X-Plane 12.</p>
          <div class="carousel"><button class="prev">&#10094;</button><div class="carousel-images">
            <img src="b521.png" class="active" alt="B-52 Payload" data-caption="Model Aircraft">
            <img src="b522.png" alt="B-52 Simulation" data-caption="Mission Profile">
          </div><button class="next">&#10095;</button></div>
        </div></div>
      <div class="card"><h3>Styrofoam Glider</h3><div class="card-content"><p>Glider designed in XFLR5, fabricated and tested.</p>
        <div class="carousel"><button class="prev">&#10094;</button><div class="carousel-images">
          <img src="glider1.jpeg" class="active" alt="Glider CAD" data-caption="Glider CAD">
          <img src="glider2.jpeg" alt="Glider Test" data-caption="Glider Test Flights">
        </div><button class="next">&#10095;</button></div>
      </div></div>
      <div class="card"><h3>U-2 Aircraft Conversion</h3><div class="card-content"><p>Adapted U-2 as payload test platform.</p></div></div>
      <div class="card"><h3>Canteen Billing System (C)</h3><div class="card-content"><p>C program implementing billing with VAT and file storage.</p></div></div>
    </div>
  </section>

  <!-- Lightbox -->
  <div id="lightbox">
    <span class="close">&times;</span>
    <img class="lightbox-content" id="lightbox-img">
    <div class="caption" id="lightbox-caption"></div>
    <a class="lightbox-prev">&#10094;</a><a class="lightbox-next">&#10095;</a>
  </div>

  <!-- Contact -->
  <section id="contact" class="fade-in">
    <h2>Contact</h2>
    <p>Email: <a href="mailto:nischalraut6@gmail.com">nischalraut6@gmail.com</a></p>
    <p>Phone: +977-9813980068</p>
    <p>LinkedIn: <a href="https://www.linkedin.com/in/nischal-raut-1b2227314/" target="_blank">linkedin.com/in/nischal-raut-1b2227314/</a></p>
  </section>

  <script>
    // Mobile nav toggle
    document.querySelector('.menu-toggle').onclick=()=>document.querySelector('nav ul').classList.toggle('active');
    // Expandable cards
    document.querySelectorAll('.card h3').forEach(h=>h.addEventListener('click',()=>h.parentElement.classList.toggle('active')));
    // Carousels
    document.querySelectorAll('.carousel').forEach(c=>{
      const imgs=c.querySelectorAll('img'); let cur=0;
      function show(i){imgs.forEach((im,x)=>im.classList.toggle('active',x===i));}
      c.querySelector('.prev').onclick=()=>{cur=(cur-1+imgs.length)%imgs.length;show(cur);}
      c.querySelector('.next').onclick=()=>{cur=(cur+1)%imgs.length;show(cur);}
      imgs.forEach((im,i)=>im.onclick=()=>openLightbox(imgs,i));
    });
    // Lightbox
    const lb=document.getElementById('lightbox'),lbImg=document.getElementById('lightbox-img'),lbCap=document.getElementById('lightbox-caption');
    let lbImgs=[],cur=0;
    function openLightbox(imgs,i){lb.style.display='block';lbImgs=[...imgs];cur=i;update();}
    function update(){lbImg.src=lbImgs[cur].src;lbCap.textContent=lbImgs[cur].dataset.caption||lbImgs[cur].alt;}
    document.querySelector('.close').onclick=()=>lb.style.display='none';
    document.querySelector('.lightbox-prev').onclick=()=>{cur=(cur-1+lbImgs.length)%lbImgs.length;update();}
    document.querySelector('.lightbox-next').onclick=()=>{cur=(cur+1)%lbImgs.length;update();}
    lb.onclick=e=>{if(e.target===lb)lb.style.display='none';}
    // Scroll fade animations
    const faders=document.querySelectorAll('.fade-in');
    const obs=new IntersectionObserver((entries,o)=>{entries.forEach(ent=>{if(ent.isIntersecting){ent.target.classList.add('visible');o.unobserve(ent.target);}});},{threshold:.15});
    faders.forEach(f=>obs.observe(f));
  </script>
</body>
</html>

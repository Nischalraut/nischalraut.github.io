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
    a{text-decoration:none;color:inherit}
    /* Navbar */
    nav{position:fixed;width:100%;top:0;padding:1em 0;background:rgba(11,61,145,0.9);
      backdrop-filter: blur(8px);display:flex;justify-content:center;z-index:999;}
    nav a{color:var(--text-light);margin:0 1em;font-weight:600;position:relative;transition:.3s;}
    nav a:hover{color:var(--accent-red);}
    nav a::after{content:"";position:absolute;bottom:-4px;left:0;width:0%;height:2px;background:var(--accent-red);transition:.3s;}
    nav a:hover::after{width:100%;}
    /* Sections with background textures */
    section{padding:6em 1.5em;max-width:1100px;margin:auto;min-height:100vh;position:relative;z-index:1}
    section::before{content:"";position:absolute;inset:0;background:rgba(11,20,50,0.85);z-index:-2;}
    section::after{content:"";position:absolute;inset:0;background-size:cover;background-position:center;opacity:0.08;z-index:-1;}
    #hero::after{background-image:url('https://upload.wikimedia.org/wikipedia/commons/e/e2/CFD_visualization.png');}
    #interests::after{background-image:url('https://upload.wikimedia.org/wikipedia/commons/5/54/Airplane_blueprint.png');}
    #skills::after{background-image:url('https://upload.wikimedia.org/wikipedia/commons/1/1e/Fluid_flow_streamlines.svg');}
    #education::after{background-image:url('https://upload.wikimedia.org/wikipedia/commons/3/32/Technical_drawing_tools.jpg');}
    #experience::after{background-image:url('https://upload.wikimedia.org/wikipedia/commons/2/2c/UAV_drone_in_flight.jpg');}
    #projects::after{background-image:url('https://upload.wikimedia.org/wikipedia/commons/f/f6/Airfoil_geometry.png');}
    #contact::after{background-image:url('https://upload.wikimedia.org/wikipedia/commons/6/6f/Hexagonal_grid.svg');}
    /* Hero */
    #hero{min-height:100vh;display:flex;flex-direction:column;justify-content:center;align-items:center;text-align:center;}
    #hero h1{font-size:3em;color:var(--accent-red);}
    #hero h2{color:var(--accent-silver);margin-bottom:.8em}
    .cta{margin-top:1.5em;}
    .btn{display:inline-block;padding:.7em 1.3em;border-radius:5px;font-weight:bold;text-decoration:none;color:white;
      background:var(--accent-red);transition:.3s;}
    .btn:hover{background:#e02815;}
    /* Fade animation */
    .fade-in{opacity:0;transform:translateY(30px);transition:all 1s ease;}
    .fade-in.visible{opacity:1;transform:translateY(0);}
    /* Cards */
    .grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:1.2em;}
    .card{background:rgba(255,255,255,0.05);border:1px solid var(--accent-silver);
      padding:1.2em;border-radius:10px;transition:.4s;cursor:pointer;overflow:hidden;}
    .card:hover{transform:translateY(-4px);box-shadow:0 0 14px rgba(252,61,33,0.4);}
    .card h3{display:flex;justify-content:space-between;align-items:center;cursor:pointer;}
    .card h3::after{content:"▼";font-size:.8em;transition:transform .3s;}
    .card.active h3::after{transform:rotate(-180deg);}
    .card-content{max-height:0;overflow:hidden;transition:max-height 0.6s ease,opacity 0.6s ease;padding-top:0;opacity:0;}
    .card.active .card-content{max-height:1000px;opacity:1;padding-top:1em;}
    /* Carousel */
    .carousel{position:relative;margin-top:1em;overflow:hidden;border-radius:8px;}
    .carousel-images{display:flex;}
    .carousel img{width:100%;display:none;border-radius:6px;cursor:pointer;}
    .carousel img.active{display:block;}
    .carousel button{position:absolute;top:50%;transform:translateY(-50%);
      background:rgba(0,0,0,0.4);border:none;color:white;font-size:1.5em;
      padding:0.4em 0.6em;cursor:pointer;border-radius:50%;transition:background 0.3s;}
    .carousel button:hover{background:rgba(0,0,0,0.7);}
    .carousel .prev{left:10px;} .carousel .next{right:10px;}
    /* Lightbox */
    #lightbox{display:none;position:fixed;z-index:99999;left:0;top:0;width:100%;height:100%;
      background:rgba(0,0,0,0.9);}
    #lightbox img{margin:auto;display:block;max-width:85%;max-height:80%;border-radius:8px;}
    #lightbox .close{position:absolute;top:20px;right:35px;color:#fff;font-size:40px;font-weight:bold;cursor:pointer;}
    .lightbox-prev,.lightbox-next{cursor:pointer;position:absolute;top:50%;color:white;font-size:2.5em;font-weight:bold;
      padding:10px;user-select:none;}
    .lightbox-prev{left:15px;} .lightbox-next{right:15px;}
    .lightbox-prev:hover,.lightbox-next:hover,#lightbox .close:hover{color:var(--accent-red);}
  </style>
</head>
<body>
  <!-- Navbar -->
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
  <!-- Interests -->
  <section id="interests" class="fade-in">
    <h2>Research & Career Interests</h2>
    <p>Aircraft Design · Propulsion Systems · Experimental Aerodynamics · Structural Dynamics · UAV Systems</p>
  </section>
  <!-- Skills -->
  <section id="skills" class="fade-in">
    <h2>Skills & Tools</h2>
    <div class="grid">
      <div class="card"><b>CAD & Analysis:</b><br> CATIA, ANSYS, SolidWorks, MATLAB</div>
      <div class="card"><b>Programming:</b><br> C (basic)</div>
      <div class="card"><b>Simulation:</b><br> Wind Tunnel Testing, Flow Visualization</div>
      <div class="card"><b>Productivity:</b><br> Word, Excel, PowerPoint, Google Workspace, LaTeX, AutoCAD, OriginLab</div>
    </div>
    <h3 style="margin-top:2em;">Soft Skills</h3>
    <ul>
      <li>Collaboration & leadership in multidisciplinary teams</li>
      <li>Clear scientific writing & presentations</li>
      <li>Problem-solving in experimental setups</li>
      <li>Adaptability & continuous learning</li>
    </ul>
  </section>
  <!-- Education -->
  <section id="education" class="fade-in">
    <h2>Education</h2>
    <div class="card active">
      <h3>Bachelor’s in Aerospace Engineering</h3>
      <div class="card-content" style="max-height:1000px;opacity:1;">
        <p>Institute of Engineering, Pulchowk Campus (Expected 2025)</p>
        <p>Average % up to 7th sem: <b>72.85</b></p>
        <p>Relevant Coursework: Aerodynamics, Structures, Propulsion, Control, CFD</p>
      </div>
    </div>
    <div class="card"><h3>+2 Science</h3>
      <div class="card-content"><p>Omega International College, GPA: 3.5</p></div>
    </div>
    <div class="card"><h3>Secondary Education Examination</h3>
      <div class="card-content"><p>West Wing Secondary School, GPA: 4.0</p></div>
    </div>
    <h3 style="margin-top:2em;">Workshops</h3>
    <ul><li>SolidWorks Workshop – SOMAES</li><li>ANSYS Workshop – SOMAES</li></ul>
  </section>
  <!-- Experience -->
  <section id="experience" class="fade-in">
    <h2>Experience</h2>
    <div class="card active">
      <h3>Engineering Intern – Airlift Technology, Nepal (2024–Present)</h3>
      <div class="card-content" style="max-height:1000px;opacity:1;">
        <ul>
          <li>Drone mapping & photogrammetry missions for Kathmandu Metropolitan City.</li>
          <li>Generated 3D terrain models & orthomosaics using photogrammetry tools.</li>
          <li>Supported UAV mission planning, calibration, and maintenance.</li>
        </ul>
      </div>
    </div>
  </section>
  <!-- Projects -->
  <section id="projects" class="fade-in">
    <h2>Projects</h2>
    <div class="grid">
      <div class="card">
        <h3>Subsonic Wind Tunnel (FYP)</h3>
        <div class="card-content">
          <p>Designed and fabricated subsonic open-jet tunnel with cosine-profile gust generator.</p>
          <ul><li>Low turbulence intensity: 0.88% (test section).</li><li>50-point grid testing & smoke visualization.</li></ul>
          <!-- Carousel -->
          <div class="carousel">
            <button class="prev">&#10094;</button>
            <div class="carousel-images">
              <img src="images/windtunnel1.jpg" class="active" alt="">
              <img src="images/windtunnel2.jpg" alt="">
              <img src="images/windtunnel3.jpg" alt="">
            </div>
            <button class="next">&#10095;</button>
          </div>
        </div>
      </div>
      <div class="card">
        <h3>B-52 Air Launch to Orbit</h3>
        <div class="card-content">
          <p>Conceptual B-52 modification for rocket carriage & release at 50,000 ft.</p>
          <div class="carousel">
            <button class="prev">&#10094;</button>
            <div class="carousel-images">
              <img src="images/b52_1.jpg" class="active" alt="">
              <img src="images/b52_2.jpg" alt="">
            </div>
            <button class="next">&#10095;</button>
          </div>
        </div>
      </div>
      <div class="card">
        <h3>Styrofoam Glider</h3>
        <div class="card-content">
          <p>Hand-launched styrofoam glider, modeled in XFLR5 and tested.</p>
          <div class="carousel">
            <button class="prev">&#10094;</button>
            <div class="carousel-images">
              <img src="images/glider1.jpg" class="active" alt="">
              <img src="images/glider2.jpg" alt="">
            </div>
            <button class="next">&#10095;</button>
          </div>
        </div>
      </div>
    </div>
  </section>
  <!-- Lightbox Modal -->
  <div id="lightbox">
    <span class="close">&times;</span>
    <img class="lightbox-content" id="lightbox-img">
    <a class="lightbox-prev">&#10094;</a>
    <a class="lightbox-next">&#10095;</a>
  </div>
  <!-- Contact -->
  <section id="contact" class="fade-in">
    <h2>Contact</h2>
    <p>Email: <a href="mailto:nischalraut6@gmail.com">nischalraut6@gmail.com</a></p>
    <p>Phone: +977-9813980068</p>
    <p>LinkedIn: <a href="https://www.linkedin.com/in/nischal-raut-1b2227314/" target="_blank">linkedin.com/in/nischal-raut-1b2227314/</a></p>
    <p>Location: Pulchowk, Lalitpur, Nepal</p>
  </section>
  <!-- JS -->
  <script>
    // Expand/collapse
    document.querySelectorAll('.card h3').forEach(header=>{
      header.addEventListener('click',()=>{header.parentElement.classList.toggle('active');});
    });
    // Carousel
    document.querySelectorAll('.carousel').forEach(carousel=>{
      const images=carousel.querySelectorAll('img');
      const prevBtn=carousel.querySelector('.prev');
      const nextBtn=carousel.querySelector('.next');
      let current=0;
      function showImage(idx){images.forEach((img,i)=>img.classList.toggle('active',i===idx));}
      prevBtn.addEventListener('click',()=>{current=(current-1+images.length)%images.length;showImage(current);});
      nextBtn.addEventListener('click',()=>{current=(current+1)%images.length;showImage(current);});
      images.forEach((img,idx)=>{img.addEventListener('click',()=>openLightbox(images,idx));});
    });
    // Lightbox
    const lightbox=document.getElementById("lightbox");
    const lightImg=document.getElementById("lightbox-img");
    const closeBtn=document.querySelector("#lightbox .close");
    const prev=document.querySelector(".lightbox-prev");
    const next=document.querySelector(".lightbox-next");
    let lightboxImages=[];let currentLight=0;
    function openLightbox(images,index){
      lightbox.style.display="block";lightboxImages=Array.from(images);currentLight=index;showLightboxImg();}
    function showLightboxImg(){lightImg.src=lightboxImages[currentLight].src;}
    closeBtn.onclick=()=>{lightbox.style.display="none";}
    prev.onclick=()=>{currentLight=(currentLight-1+lightboxImages.length)%lightboxImages.length;showLightboxImg();}
    next.onclick=()=>{currentLight=(currentLight+1)%lightboxImages.length;showLightboxImg();}
    lightbox.onclick=(e)=>{if(e.target===lightbox)lightbox.style.display="none";}
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

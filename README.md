
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Nischal Raut | Aerospace Portfolio</title>

  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@600;700&family=Open+Sans:wght@400;500&display=swap" rel="stylesheet">

  <!-- Chart.js CDN -->
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

  <style>
    :root {
      --primary-dark: #0b1432;
      --primary-blue: #0B3D91;
      --accent-red: #FC3D21;
      --accent-silver: #A9A9A9;
      --text-light: #f1f1f1;
      --bg-gradient: linear-gradient(135deg, #0b1432, #0B3D91);
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      scroll-behavior: smooth;
    }

    body {
      font-family: 'Open Sans', sans-serif;
      background: var(--primary-dark);
      color: var(--text-light);
      line-height: 1.6;
    }

    h1, h2, h3, h4 {
      font-family: 'Montserrat', sans-serif;
      margin-bottom: 0.5em;
    }

    a { text-decoration: none; }

    /* Navbar */
    nav {
      position: fixed;
      width: 100%;
      top: 0;
      left: 0;
      background: rgba(11,61,145,0.9);
      backdrop-filter: blur(6px);
      display: flex;
      justify-content: center;
      padding: 1em 0;
      z-index: 999;
      transition: background 0.4s;
    }
    nav a {
      color: var(--text-light);
      font-weight: 600;
      margin: 0 1em;
      position: relative;
      transition: color 0.3s;
    }
    nav a:hover {
      color: var(--accent-red);
    }
    nav a::after {
      content: '';
      position: absolute;
      width: 0%;
      height: 2px;
      bottom: -4px;
      left: 0;
      background: var(--accent-red);
      transition: width .3s;
    }
    nav a:hover::after {
      width: 100%;
    }

    section {
      padding: 6em 1.5em;
      max-width: 1100px;
      margin: auto;
      min-height: 100vh;
      transition: background 1s ease;
    }

    /* Hero Section */
    #hero {
      background: linear-gradient(rgba(11,20,50,0.9), rgba(0,0,0,0.9)), url('https://upload.wikimedia.org/wikipedia/commons/e/e2/CFD_visualization.png') center/cover no-repeat;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      color: var(--text-light);
    }
    #hero h1 { font-size: 2.8em; color: var(--accent-red); }
    #hero h2 { font-size: 1.2em; color: var(--accent-silver); }
    #hero p { font-size: 1.1em; margin-top: 0.5em; }

    /* About */
    #about p {
      max-width: 800px;
      margin: auto;
      font-size: 1.1em;
      text-align: center;
    }

    /* Academic Journey */
    #academic canvas {
      max-width: 800px !important;
      margin: 2em auto;
      display: block;
      background: rgba(255,255,255,0.05);
      border-radius: 10px;
      padding: 1em;
    }
    #academic .note {
      text-align: center;
      color: var(--accent-silver);
    }

    /* Skills */
    #skills .skill-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 1.5em;
      margin-top: 2em;
    }
    .skill-card {
      border: 1px solid var(--accent-silver);
      border-radius: 8px;
      padding: 1.2em;
      text-align: center;
      transition: all .4s ease;
      background: rgba(255,255,255,0.05);
    }
    .skill-card:hover {
      transform: translateY(-6px) scale(1.04);
      border-color: var(--accent-red);
      box-shadow: 0px 0px 18px rgba(252,61,33,0.4);
    }

    /* Projects */
    .project {
      margin-bottom: 3em;
      background: rgba(255,255,255,0.05);
      padding: 2em;
      border-radius: 10px;
      transition: transform .4s ease;
    }
    .project:hover {
      transform: translateY(-4px);
      box-shadow: 0px 0px 14px rgba(252,61,33,0.3);
    }
    .achievements { margin-top: 1em; padding-left: 1.2em; }

    .small-projects {
      display: grid;
      grid-template-columns: repeat(auto-fit,minmax(250px,1fr));
      gap: 1.2em;
      margin-top: 2em;
    }
    .proj-card {
      border: 1px solid var(--accent-silver);
      border-radius: 6px;
      padding: 1em;
      background: rgba(255,255,255,0.05);
      transition: all .3s;
    }
    .proj-card:hover {
      transform: scale(1.05);
      border-color: var(--primary-blue);
      box-shadow: 0px 0px 12px rgba(11,61,145,0.4);
    }

    /* Contact */
    #contact form {
      display: flex;
      flex-direction: column;
      max-width: 500px;
      margin: auto;
    }
    #contact input, #contact textarea {
      padding: 0.8em;
      margin-bottom: 1em;
      border: none;
      border-radius: 4px;
      background: rgba(255,255,255,0.1);
      color: var(--text-light);
    }
    #contact button {
      background: var(--accent-red);
      color: white;
      border: none;
      padding: 0.9em;
      border-radius: 4px;
      cursor: pointer;
      font-weight: bold;
      transition: background 0.3s;
    }
    #contact button:hover {
      background: #e02815;
    }
    #contact .social {
      text-align: center;
      margin-top: 1.5em;
    }
    #contact .social a {
      margin: 0 0.5em;
      color: var(--accent-red);
      font-weight: bold;
      transition: color 0.3s;
    }
    #contact .social a:hover {
      color: var(--accent-silver);
    }

    /* Animations */
    .fade-in {
      opacity: 0;
      transform: translateY(30px);
      transition: all 1s ease-out;
    }
    .fade-in.visible {
      opacity: 1;
      transform: translateY(0);
    }
  </style>
</head>
<body>
  <!-- Navbar -->
  <nav>
    <a href="#hero">Home</a>
    <a href="#about">About</a>
    <a href="#academic">Academic</a>
    <a href="#skills">Skills</a>
    <a href="#projects">Projects</a>
    <a href="#contact">Contact</a>
  </nav>

  <!-- Hero -->
  <section id="hero">
    <h1>Nischal Raut</h1>
    <h2>Aerospace Engineer | PhD Aspirant</h2>
    <p>"Bridging Computational Models and Experimental Validation."</p>
  </section>

  <!-- About -->
  <section id="about" class="fade-in">
    <h2>About Me</h2>
    <p>
      I am an aspiring researcher pursuing excellence in Aerospace Engineering, driven to contribute to Experimental Aerodynamics and Fluid Dynamics. 
      My journey demonstrates resilience and steady growth, empowering me to combine computational and experimental perspectives 
      in turbulence and flow analysis towards innovative aerospace solutions.
    </p>
  </section>

  <!-- Academic -->
  <section id="academic" class="fade-in">
    <h2>Academic Journey</h2>
    <p class="note">From 59.6% in Semester 1 to 89.2% in Semester 8.</p>
    <canvas id="gpaChart"></canvas>
    <p>An early challenge in Control Systems strengthened my resolve, leading to consistent improvement and academic maturity.</p>
  </section>

  <!-- Skills -->
  <section id="skills" class="fade-in">
    <h2>Technical Skills</h2>
    <div class="skill-grid">
      <div class="skill-card">CFD Analysis (ANSYS/OpenFOAM)</div>
      <div class="skill-card">Wind Tunnel Design & Operation</div>
      <div class="skill-card">Turbulence Analysis</div>
      <div class="skill-card">CAD (SolidWorks)</div>
      <div class="skill-card">Data Acquisition Systems</div>
      <div class="skill-card">Fabrication (CNC, Welding, Carpentry)</div>
      <div class="skill-card">Python/MATLAB for Data Processing</div>
    </div>
  </section>

  <!-- Projects -->
  <section id="projects" class="fade-in">
    <h2>Key Projects</h2>
    <div class="project">
      <h3>Subsonic Wind Tunnel with Oscillating Vane Gust Generator</h3>
      <p>Computational design, structural fabrication, and rigorous experimental validation of a low-turbulence wind tunnel.</p>
      <ul class="achievements">
        <li>Turbulence Intensity: <b>0.88% (test section)</b>, <b>2.32% (outlet)</b></li>
        <li>Average flow velocity: <b>8.6 m/s</b> (modeled: 10.15 m/s)</li>
        <li>Oscillating vane gust generator with smoke visualization</li>
        <li>50-point grid experimental testing</li>
        <li>Redesigned via CNC fabrication overcoming turbulence in prior model</li>
      </ul>
      <p><b>Impact:</b> Now used as a foundational research tool supporting other peer projects.</p>
    </div>

    <div class="small-projects">
      <div class="proj-card">
        <h4>Hypersonics & Propulsion</h4>
        <p>Elective coursework projects on high-speed aerodynamics and propulsion thermodynamics.</p>
      </div>
      <div class="proj-card">
        <h4>Peer Collaborations</h4>
        <p>Supported projects on wing vibration analysis and active fin control using wind tunnel experiments.</p>
      </div>
    </div>
  </section>

  <!-- Contact -->
  <section id="contact" class="fade-in">
    <h2>Contact</h2>
    <form>
      <input type="text" placeholder="Your Name" required>
      <input type="email" placeholder="Your Email" required>
      <textarea rows="5" placeholder="Your Message" required></textarea>
      <button type="submit">Send Message</button>
    </form>
    <div class="social">
      <p>Email: <a href="mailto:nischalraut6@gmail.com">nischalraut6@gmail.com</a></p>
      <p>LinkedIn: <a href="https://www.linkedin.com/in/nischal-raut-1b2227314/" target="_blank">My LinkedIn Profile</a></p>
      <p>Location: Your City, Country</p>
    </div>
  </section>

  <script>
    // GPA Chart
    const ctx = document.getElementById('gpaChart').getContext('2d');
    new Chart(ctx, {
      type: 'line',
      data: {
        labels: ['Sem 1','Sem 2','Sem 3','Sem 4','Sem 5','Sem 6','Sem 7','Sem 8'],
        datasets: [{
          label: 'Semester %',
          data: [59.63, 67.43, 65.92, 69.14, 78.4, 83.25, 86.15, 89.2],
          borderColor: '#FC3D21',
          backgroundColor: 'rgba(252,61,33,0.2)',
          fill: true,
          tension: 0.3,
          pointBackgroundColor: '#fff',
          pointRadius: 5
        }]
      },
      options: {
        responsive: true,
        plugins: { legend: { display: false } },
        scales: {
          y: { min: 50, max: 100, title: { display: true, text: '% Score' } }
        }
      }
    });

    // Scroll animation
    const faders = document.querySelectorAll('.fade-in');
    const appearOnScroll = new IntersectionObserver((entries, obs)=>{
      entries.forEach(entry=>{
        if(entry.isIntersecting){ entry.target.classList.add('visible'); obs.unobserve(entry.target); }
      });
    },{threshold:0.15, rootMargin:"0px 0px -50px 0px"});

    faders.forEach(f=>appearOnScroll.observe(f));
  </script>
</body>
</html>

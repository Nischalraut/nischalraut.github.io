<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Nischal Raut | Aerospace Engineering Portfolio</title>

  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@600;700&family=Open+Sans:wght@400;500&display=swap" rel="stylesheet">

  <!-- Chart.js CDN for GPA Graph -->
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

  <style>
    :root {
      --blue: #0B3D91;
      --red: #FC3D21;
      --silver: #A9A9A9;
      --white: #FFFFFF;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      scroll-behavior: smooth;
    }

    body {
      font-family: 'Open Sans', sans-serif;
      background: var(--white);
      color: #333;
      line-height: 1.6;
    }

    h1, h2, h3, h4 {
      font-family: 'Montserrat', sans-serif;
      color: var(--blue);
      margin-bottom: 0.5em;
    }

    nav {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      background: var(--blue);
      z-index: 999;
      display: flex;
      justify-content: center;
      padding: 1em 0;
    }
    nav a {
      color: var(--white);
      text-decoration: none;
      margin: 0 1em;
      font-weight: 600;
      position: relative;
    }
    nav a::after {
      content: '';
      position: absolute;
      width: 0%;
      height: 2px;
      bottom: -4px;
      left: 0;
      background: var(--red);
      transition: width .3s;
    }
    nav a:hover::after {
      width: 100%;
    }

    section {
      padding: 5em 1.5em;
      max-width: 1100px;
      margin: auto;
    }

    /* Hero Section */
    #hero {
      height: 100vh;
      color: var(--white);
      background: linear-gradient(rgba(11,61,145,0.85), rgba(11,61,145,0.85)), url('https://upload.wikimedia.org/wikipedia/commons/e/e2/CFD_visualization.png') center/cover no-repeat;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
    }
    #hero h1 {
      font-size: 2.8em;
      margin-bottom: .3em;
    }
    #hero h2 {
      font-size: 1.3em;
      margin-bottom: .5em;
      font-weight: 400;
    }
    #hero p {
      font-size: 1.1em;
      font-style: italic;
      color: var(--silver);
    }

    /* About */
    #about p {
      max-width: 800px;
      margin: auto;
      font-size: 1.1em;
    }

    /* Academic Journey */
    #academic canvas {
      max-width: 800px !important;
      margin: 2em auto;
      display: block;
    }
    #academic .note {
      font-style: italic;
      color: #555;
      text-align: center;
    }

    /* Skills */
    #skills .skill-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 1.5em;
      margin-top: 2em;
    }
    .skill-card {
      border: 1px solid var(--silver);
      border-radius: 8px;
      padding: 1.2em;
      text-align: center;
      transition: transform .3s;
    }
    .skill-card:hover {
      transform: translateY(-4px);
      border-color: var(--red);
    }

    /* Projects */
    #projects .project {
      margin-bottom: 3em;
    }
    .project h3 {
      color: var(--red);
    }
    .achievements {
      margin-top: 1em;
      padding-left: 1.2em;
    }
    .small-projects {
      display: grid;
      grid-template-columns: repeat(auto-fit,minmax(250px,1fr));
      gap: 1.2em;
    }
    .proj-card {
      border: 1px solid var(--silver);
      border-radius: 6px;
      padding: 1em;
      transition: transform .3s;
    }
    .proj-card:hover {
      transform: translateY(-5px);
      border-color: var(--blue);
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
      border: 1px solid var(--silver);
      border-radius: 4px;
      font-family: inherit;
    }
    #contact button {
      background: var(--red);
      color: var(--white);
      border: none;
      padding: 0.8em;
      border-radius: 4px;
      cursor: pointer;
      font-weight: bold;
    }
    #contact .social {
      text-align: center;
      margin-top: 1.5em;
    }
    #contact .social a {
      margin: 0 0.5em;
      color: var(--blue);
      font-weight: bold;
    }

    /* Scroll animations */
    .fade-in {
      opacity: 0;
      transform: translateY(20px);
      transition: all 0.8s ease-out;
    }
    .fade-in.visible {
      opacity: 1;
      transform: translateY(0);
    }

  </style>
</head>
<body>

  <!-- Navigation -->
  <nav>
    <a href="#hero">Home</a>
    <a href="#about">About</a>
    <a href="#academic">Academic Journey</a>
    <a href="#skills">Skills</a>
    <a href="#projects">Projects</a>
    <a href="#contact">Contact</a>
  </nav>

  <!-- Hero -->
  <section id="hero">
    <h1>Nischal Raut</h1>
    <h2>Bachelor of Engineering in Aerospace Engineering</h2>
    <p>"Bridging Computational Models and Experimental Validation."</p>
  </section>

  <!-- About -->
  <section id="about" class="fade-in">
    <h2>About Me</h2>
    <p>
      I am an aspiring researcher with a strong foundation in Aerospace Engineering, eager to pursue a PhD in Experimental Aerodynamics & Fluid Dynamics. 
      My academic journey reflects transformative growth, resilience, and a hands-on approach to solving complex challenges. With a passion for blending computational and experimental methods, 
      I aim to contribute innovative methods in turbulence, flow visualization, and propulsion systems, advancing the frontiers of aerospace engineering.
    </p>
  </section>

  <!-- Academic Journey -->
  <section id="academic" class="fade-in">
    <h2>Academic Journey</h2>
    <p class="note">GPA improvement from 59.6% in the first semester to 89.2% in the eighth semester.</p>
    <canvas id="gpaChart"></canvas>
    <p>"An early challenge in Control Systems refined my focus and demonstrated my resilience, culminating in my final year success with 89.2%."</p>
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
    <h2>Projects</h2>
    <div class="project">
      <h3>Design and Development of a Subsonic Wind Tunnel with an Oscillating Vane Gust Generator</h3>
      <p>A comprehensive final year project involving the computational design, structural fabrication, and experimental validation of a low-turbulence wind tunnel.</p>
      <ul class="achievements">
        <li>Achieved a Turbulent Intensity of <b>0.88%</b> at test section & <b>2.32%</b> at outlet.</li>
        <li>Attained average flow velocity of <b>8.6 m/s</b> (modeled for 10.15 m/s).</li>
        <li>Designed & integrated oscillating vane gust generator; smoke flow visualization.</li>
        <li>Implemented 50-point grid testing with vane anemometer.</li>
        <li>Redesigned/fabricated tunnel with CNC laser cutting after turbulence issues in prior design.</li>
      </ul>
      <p><b>Impact:</b> Tunnel is now a foundational research tool, supporting projects like wing vibration analysis and active fin control.</p>
    </div>

    <h3>Other Projects</h3>
    <div class="small-projects">
      <div class="proj-card">
        <h4>Hypersonics & Advanced Propulsion Coursework</h4>
        <p>Explored high-speed flow regimes, propulsion thermodynamics, and aerodynamic heating studies.</p>
      </div>
      <div class="proj-card">
        <h4>Peer Collaborations</h4>
        <p>Contributed experimental data via my wind tunnel for projects on wing vibration analysis and active fin control.</p>
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
      <p>Email: <a href="nischalraut6@gmail.com">your-email@example.com</a></p>
      <p>LinkedIn: <a href=https://www.linkedin.com/in/nischal-raut-1b2227314/"" target="_blank">Connect with me</a></p>
      <p>Location: Your City, Country</p>
    </div>
  </section>

  <script>
    // GPA data
    const ctx = document.getElementById('gpaChart').getContext('2d');
    const gpaChart = new Chart(ctx, {
      type: 'line',
      data: {
        labels: ['Sem 1', 'Sem 2', 'Sem 3', 'Sem 4', 'Sem 5', 'Sem 6', 'Sem 7', 'Sem 8'],
        datasets: [{
          label: 'Semester Percentage',
          data: [59.63, 67.43, 65.92, 69.14, 78.4, 83.25, 86.15, 89.2],
          borderColor: '#FC3D21',
          backgroundColor: 'rgba(252,61,33,0.2)',
          tension: 0.2,
          fill: true,
          pointBackgroundColor: '#0B3D91',
          pointRadius: 5
        }]
      },
      options: {
        responsive: true,
        plugins: {
          legend: {
            display: false
          }
        },
        scales: {
          y: {
            min: 50,
            max: 100,
            title: {
              display: true,
              text: '% Score'
            }
          }
        }
      }
    });

    // Scroll fade-in effect
    const faders = document.querySelectorAll('.fade-in');
    const appearOptions = {
      threshold: 0.15,
      rootMargin: "0px 0px -50px 0px"
    };
    const appearOnScroll = new IntersectionObserver(function(entries, appearOnScroll){
      entries.forEach(entry => {
        if (!entry.isIntersecting) { return; }
        entry.target.classList.add('visible');
        appearOnScroll.unobserve(entry.target);
      });
    }, appearOptions);

    faders.forEach(fader => {
      appearOnScroll.observe(fader);
    });
  </script>
</body>
</html>

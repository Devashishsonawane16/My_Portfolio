<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Devashish Sonawane — Portfolio</title>
  <meta name="description" content="Portfolio homepage of Devashish Sonawane — MCA student & Full-stack developer (Java, Python, React, JS)." />
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg: #0b0f17;
      --panel: #121826;
      --text: #e6edf6;
      --muted: #a7b0c0;
      --brand: #7c5cff;
      --brand-2:#2dd4bf;
      --ring: rgba(124,92,255,.35);
      --border: #1e2636;
      --shadow: 0 10px 30px rgba(0,0,0,.35);
      --radius: 18px;
      --radius-lg: 24px;
      --gap: 20px;
    }

    .light{
      --bg:#f6f8fc; --panel:#ffffff; --text:#0d1220; --muted:#485266; --border:#e8ecf3; --ring: rgba(124,92,255,.25);
      --shadow: 0 10px 30px rgba(16,24,40,.08);
    }

    html{scroll-behavior:smooth}
    *{box-sizing:border-box}
    body{margin:0;font-family:Inter, system-ui, -apple-system, Segoe UI, Roboto, "Helvetica Neue", Arial, "Noto Sans"; background:var(--bg); color:var(--text); line-height:1.6}
    a{color:inherit;text-decoration:none}
    img{max-width:100%;display:block}

    .container{width:min(1100px, 92%); margin-inline:auto}

    /* NAVBAR */
    .nav{position:sticky; top:0; z-index:50; backdrop-filter:saturate(180%) blur(8px); background:color-mix(in oklab, var(--bg) 85%, transparent); border-bottom:1px solid var(--border)}
    .nav-wrap{display:flex; align-items:center; justify-content:space-between; padding:14px 0}
    .brand{display:flex; align-items:center; gap:10px; font-weight:800; letter-spacing:.2px}
    .brand .dot{width:12px; height:12px; border-radius:50%; background:linear-gradient(135deg, var(--brand), var(--brand-2)); box-shadow:0 0 0 6px var(--ring)}
    .nav-links{display:flex; gap:20px; align-items:center}
    .nav-links a{padding:10px 14px; border-radius:999px; color:var(--muted)}
    .nav-links a:hover{background:var(--panel); color:var(--text); box-shadow:var(--shadow)}
    .btn{display:inline-flex; align-items:center; gap:10px; padding:12px 16px; border-radius:999px; background:linear-gradient(135deg, var(--brand), var(--brand-2)); color:#0b0f17; font-weight:700; border:0; cursor:pointer; text-align:center; justify-content:center}
    .btn:hover{filter:brightness(1.05)}
    .ghost{background:transparent; border:1px solid var(--border); color:var(--text)}

    .menu-btn{display:none}
    @media (max-width:820px){
      .menu-btn{display:inline-flex}
      .nav-links{display:none}
      .nav-links.open{display:flex; position:absolute; top:60px; right:4%; flex-direction:column; background:var(--panel); border:1px solid var(--border); padding:12px; border-radius:14px; width:220px}
      .nav-links.open a{width:100%; text-align:left}
    }

    /* HERO */
    .hero{display:grid; grid-template-columns: 1.2fr .8fr; gap:var(--gap); align-items:center; padding:56px 0}
    .chip{display:inline-flex; align-items:center; gap:8px; padding:8px 12px; border:1px dashed var(--border); color:var(--muted); border-radius:999px}
    .hero h1{font-size:clamp(2rem, 5vw, 3.25rem); line-height:1.2; margin:16px 0}
    .hero p{color:var(--muted); font-size:1rem}
    .hero-cta{display:flex; gap:12px; margin-top:22px; flex-wrap:wrap}

    .portrait{width:250px; height:250px; border-radius:50%; overflow:hidden; border:3px solid var(--border); margin:auto; box-shadow:var(--shadow)}
    .portrait img{width:100%; height:100%; object-fit:cover}

    @media (max-width:900px){
      .hero{grid-template-columns:1fr; text-align:center; padding:40px 0}
      .hero-cta{justify-content:center}
    }

    /* SECTIONS */
    section{padding:28px 0}
    .section-head{display:flex; align-items:baseline; justify-content:space-between; margin-bottom:14px; flex-wrap:wrap}
    .section-head h2{font-size:1.6rem}
    .muted{color:var(--muted)}

    /* ABOUT */
    .about{display:grid; grid-template-columns: 1fr 1fr; gap:var(--gap)}
    .about-card{background:var(--panel); border:1px solid var(--border); border-radius:var(--radius); padding:22px; box-shadow:var(--shadow)}
    @media (max-width:900px){.about{grid-template-columns:1fr}}

    .skills{display:flex; gap:10px; flex-wrap:wrap}
    .skill{padding:8px 12px; background:color-mix(in oklab, var(--panel) 80%, black 0%); border:1px solid var(--border); border-radius:12px; font-weight:600}

    /* GRID */
    .grid{display:grid; gap:var(--gap)}
    .grid.cols-3{grid-template-columns:repeat(3, 1fr)}
    .grid.cols-2{grid-template-columns:repeat(2, 1fr)}
    @media (max-width:1024px){.grid.cols-3{grid-template-columns:repeat(2, 1fr)}}
    @media (max-width:720px){.grid.cols-3, .grid.cols-2{grid-template-columns:1fr}}
    .card{background:var(--panel); border:1px solid var(--border); border-radius:var(--radius); overflow:hidden; box-shadow:var(--shadow); display:flex; flex-direction:column}
    .card-media{aspect-ratio:16/9; background:linear-gradient(135deg, color-mix(in oklab, var(--brand) 25%, transparent), color-mix(in oklab, var(--brand-2) 20%, transparent)); border-bottom:1px solid var(--border); position:relative}
    .card-media img{position:absolute; inset:0; width:100%; height:100%; object-fit:cover}
    .card-body{padding:16px}
    .card h3{margin:0 0 8px 0}
    .tags{display:flex; gap:8px; flex-wrap:wrap; margin-top:10px}
    .tag{font-size:.85rem; padding:6px 10px; border-radius:999px; border:1px solid var(--border); color:var(--muted)}
    .card-actions{display:flex; gap:10px; padding:16px; margin-top:auto; flex-wrap:wrap}

    /* CONTACT */
    .contact{display:grid; grid-template-columns: 1.1fr .9fr; gap:var(--gap)}
    @media (max-width:900px){.contact{grid-template-columns:1fr}}
    .form{background:var(--panel); border:1px solid var(--border); border-radius:var(--radius); padding:18px; box-shadow:var(--shadow)}
    label{display:block; font-weight:600; margin:14px 0 8px}
    input, textarea{width:100%; padding:12px 14px; border-radius:12px; border:1px solid var(--border); background:transparent; color:var(--text); outline:none}
    input:focus, textarea:focus{box-shadow:0 0 0 6px var(--ring); border-color:transparent}
    textarea{resize:vertical; min-height:120px}

    footer{margin-top:36px; border-top:1px solid var(--border); padding:24px 0; color:var(--muted); text-align:center}
    .socials{display:flex; gap:10px; justify-content:center; flex-wrap:wrap}
    .social{display:inline-flex; align-items:center; gap:8px; padding:9px 12px; border:1px solid var(--border); border-radius:12px}

    .row{display:flex; gap:10px; flex-wrap:wrap}
    .mono{font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", monospace}

    /* ACHIEVEMENTS */
    .cert-note{font-size:.95rem; color:var(--muted)}
    .achievements{list-style: none; padding-left: 0; display:grid; gap:10px}
    .achievements li{background:color-mix(in oklab, var(--panel) 80%, black 0%); border:1px solid var(--border); padding:12px 14px; border-radius:12px}

    /* --- Extra Mobile Friendly Adjustments --- */
    @media (max-width: 600px) {
      .container {width: 94%;}
      .nav-wrap {flex-wrap: wrap; gap: 10px;}
      .nav-links.open {right: 2%; width: 180px;}
      .hero {padding: 28px 0;}
      .portrait {width: 180px; height: 180px;}
      .hero h1 {font-size: clamp(1.5rem, 6vw, 2.2rem);}
      .about, .contact, .grid.cols-3, .grid.cols-2 {grid-template-columns: 1fr !important;}
      .card {border-radius: 14px;}
      .btn, .social {padding: 10px 14px; font-size: 0.9rem;}
    }
    @media (max-width: 400px) {
      .nav-wrap {justify-content: center;}
      .hero h1 {font-size: 1.4rem;}
      .chip {font-size: 0.8rem; padding: 6px 10px;}
      .btn, .social {flex: 1; text-align: center; justify-content: center;}
      footer .row {flex-direction: column; gap: 8px;}
    }
  </style>
</head>
<body>
  <header class="nav">
    <div class="container nav-wrap">
      <div class="brand"><span class="dot"></span><b> Devashish</b>&nbsp;Sonawane</div>
      <nav>
        <button class="menu-btn ghost" aria-label="Menu" onclick="toggleMenu()">☰</button>
        <div id="navLinks" class="nav-links">
          <a href="#home">Home</a>
          <a href="#about">About</a>
          <a href="#projects">Projects</a>
          <a href="#certifications">Certifications</a>
          <a href="#contact">Contact</a>
          <a href="mailto:devashish@example.com" class="social">Gmail</a>
          <a href="https://www.linkedin.com/" target="_blank" rel="noopener" class="social">LinkedIn</a>
          <a href="https://www.instagram.com/" target="_blank" rel="noopener" class="social">Instagram</a>
          <button class="ghost" onclick="toggleTheme()" aria-label="Toggle theme">🌓</button>
        </div>
      </nav>
    </div>
  </header>

  <main id="home" class="container">
    <!-- Hero -->
    <section class="hero">
      <div>
        <span class="chip mono"><i>MCA Student (Final Year) & Full-stack Developer</i></span>
        <h1>Building clean, fast websites with <span style="background:linear-gradient(90deg,var(--brand),var(--brand-2)); -webkit-background-clip:text; background-clip:text; color:transparent">Java/Python</span>.</h1>
        <p>
          Perceiving Masters (MCA) at Institute of Management and Research, Chinchwad, Pune || SPPU || Full stack web-developer Java || Python || C++ || C
        </p>
        <div class="hero-cta">
          <a class="btn" href="#projects">View Projects ➜</a>
          <a class="btn ghost" href="#contact">Contact Me</a>
          <a class="btn ghost" href="devashishresume2025.pdf" download>Download Résumé</a>
        </div>
      </div>
      <div class="portrait">
        <img alt="Developer portrait" src="project.jpg" />
      </div>
    </section>

    <!-- About -->
    <section id="about">
      <div class="section-head">
        <h2>About</h2>
        <span class="muted">Who I am & what I do</span>
      </div>
      <div class="about">
        <article class="about-card">
          <h3>Education.</h3>
          <p>
            Savitribai Phule Pune University<br>  
            <b>Masters in Computer Applications (MCA)</b><br>
            <i>ASM’s IMBR Pune, India (Perceiving)</i>
          </p>
          <p>
            Disha Computer’s Pune<br>
            <b>Full Stack Java Developer (Perceiving)</b><br>
            <i>Disha Institute Chinchawad branch, Pune</i>
          </p>
          <p>
            North Maharashtra University Jalgaon<br> 
            <b>Bachelors in Chemistry (8.3 CGPA)</b><br>
            <i>SSVPS, Dhule (Completed)</i>
          </p>
          <div class="skills">
            <span class="skill">Java</span><span class="skill">Python</span><span class="skill">HTML</span>
            <span class="skill">CSS</span><span class="skill">JavaScript</span><span class="skill">React/Node JS</span>
            <span class="skill">C++/C</span><span class="skill">MySQL</span><span class="skill">Django</span><span class="skill">Angular</span>
          </div>
        </article>
        <article class="about-card">
          <h3>What I’m focusing on</h3>
          <p>
            I am seeking an opportunity as a Full Stack Web Developer in the IT industry, where I can apply my skills in HTML, CSS, JavaScript, React, Node.js, and databases to build scalable and user-centered applications. 
          </p>
          <div class="row">
            <div class="chip">Open to Internships</div>
            <div class="chip">Part-time • Full-time</div>
            <div class="chip">Remote-friendly</div>
          </div>
        </article>
      </div>
    </section>

    <!-- Projects -->
    <section id="projects">
      <div class="section-head"><h2>Projects</h2></div>
      <div class="grid cols-3">
        <article class="card"><div class="card-media"><img src="travel2.png" alt="travelmanagementimg" loading="lazy"></div><div class="card-body"><h3>Travel Management Website</h3><p class="muted">A responsive website built with Java, HTML, CSS, and Bootstrap to streamline trip planning, booking, and itinerary management.</p><div class="tags"><span class="tag">Java</span><span class="tag">HTML/CSS</span><span class="tag">Bootstrap</span><span class="tag">SQL/Javascript</span></div></div></article>
        <article class="card"><div class="card-media"><img src="travel2.png" alt="travelmanagementimg" loading="lazy"></div><div class="card-body"><h3>Travel Management Website</h3><p class="muted">A responsive website built with Java, HTML, CSS, and Bootstrap to streamline trip planning, booking, and itinerary management.</p><div class="tags"><span class="tag">Java</span><span class="tag">HTML/CSS</span><span class="tag">Bootstrap</span><span class="tag">SQL/Javascript</span></div></div></article>
        <article class="card"><div class="card-media"><img src="jobview2.png" alt="Jobviewimg" loading="lazy"></div><div class="card-body"><h3>Joview.com</h3><p class="muted">Worked on UI components, bug fixes, and performance improvements across the frontend.</p><div class="tags"><span class="tag">Java</span><span class="tag">HTml/CSS</span><span class="tag">PostgreSQL/GooleMaps</span><span class="tag">PostgreSQL/Google Maps</span><span class="tag">Bootstrap</span><span class="tag">SQL/Javascript</span></div></div></article>
      </div>
    </section>

    <!-- Certifications -->
    <section id="certifications">
      <div class="section-head"><h2>Certifications & Achievements</h2></div>
      <div class="grid cols-3">
        <article class="card"><div class="card-media"><img src="Clangcertificate.jpeg" alt="C Language certificate" loading="lazy"></div><div class="card-body"><h3>C Language Certificate</h3><p class="muted">Foundational programming, pointers, memory, data structures.</p><div class="tags"><span class="tag">C</span><span class="tag">Procedural</span></div></div><div class="card-actions"><a class="btn ghost" href="Clangcertificate.jpeg" download>Download</a><a class="btn" href="Clangcertificate.jpeg" target="_blank">View</a></div></article>
        <article class="card"><div class="card-media"><img src="certificates/cpp-language.jpg" alt="C++ certificate" loading="lazy"></div><div class="card-body"><h3>C++ Certificate</h3><p class="muted">OOP, STL, templates, problem solving.</p><div class="tags"><span class="tag">C++</span><span class="tag">OOP</span></div></div><div class="card-actions"><a class="btn ghost" href="certificates/cpp-language.jpg" download>Download</a><a class="btn" href="certificates/cpp-language.jpg" target="_blank">View</a></div></article>
        <article class="card"><div class="card-media"><img src="certificates/fullstack.jpg" alt="Full Stack certificate" loading="lazy"></div><div class="card-body"><h3>Full Stack Certificate</h3><p class="muted">Frontend + Backend foundations with databases.</p><div class="tags"><span class="tag">HTML/CSS/JS</span><span class="tag">React/Node</span><span class="tag">DB</span></div></div><div class="card-actions"><a class="btn ghost" href="certificates/fullstack.jpg" download>Download</a><a class="btn" href="certificates/fullstack.jpg" target="_blank">View</a></div></article>
        <article class="card"><div class="card-media"><img src="javaimg.jpg" alt="Java certificate" loading="lazy"></div><div class="card-body"><h3>Java Certificate By Anudip Foundation</h3><p class="muted">Frontend + Backend foundations with databases.</p><div class="tags"><span class="tag">HTML/CSS/JS</span><span class="tag">React/Node</span><span class="tag">DB</span></div></div><div class="card-actions"><a class="btn ghost" href="javaimg.jpg" download>Download</a><a class="btn" href="javaimg.jpg" target="_blank">View</a></div></article>
      </div>
    </section>

    <!-- Contact -->
    <section id="contact">
      <div class="section-head"><h2>Contact</h2><span class="muted">Let’s build something great</span></div>
      <div class="contact">
        <div class="form">
          <form action="https://formspree.io/f/your-endpoint" method="POST">
            <label for="name">Name</label>
            <input id="name" name="name" type="text" placeholder="Your name" required>
            <label for="email">Email</label>
            <input id="email" name="email" type="email" placeholder="you@example.com" required>
            <label for="message">Message</label>
            <textarea id="message" name="message" placeholder="Tell me about your project" required></textarea>
            <div class="row" style="margin-top:14px">
              <button class="btn" type="submit">Send Message</button>
              <a class="btn ghost" href="mailto:devashishsonawane788@gmail.com">Email Instead</a>
            </div>
          </form>
        </div>
        <div class="form">
          <h3>Links</h3>
          <p class="muted">I’m most active on LinkedIn.</p>
          <div class="row">
            <a class="social" href="mailto:devashish@example.com">📧 Gmail</a>
            <a class="social" target="_blank" href="https://www.linkedin.com/">💼 LinkedIn</a>
            <a class="social" target="_blank" href="https://github.com/">🐙 GitHub</a>
            <a class="social" target="_blank" href="https://www.instagram.com/">📸 Instagram</a>
          </div>
        </div>
      </div>
    </section>

    <footer class="container">
      <div class="row" style="align-items:center; justify-content:space-between; flex-wrap:wrap; text-align:center">
        <span class="muted">© <span id="year"></span> Devashish Sonawane</span>
        <div class="socials">
          <a class="social" target="_blank" href="https://github.com/">GitHub</a>
          <a class="social" target="_blank" href="https://www.linkedin.com/">LinkedIn</a>
        </div>
      </div>
    </footer>
  </main>

  <script>
    (function(){
      const saved = localStorage.getItem('theme');
      const prefersLight = window.matchMedia && window.matchMedia('(prefers-color-scheme: light)').matches;
      if(saved === 'light' || (!saved && prefersLight)){
        document.documentElement.classList.add('light');
      }
      document.getElementById('year').textContent = new Date().getFullYear();
    })();

    function toggleMenu(){
      document.getElementById('navLinks').classList.toggle('open');
    }

    function toggleTheme(){
      document.documentElement.classList.toggle('light');
      localStorage.setItem('theme', document.documentElement.classList.contains('light') ? 'light' : 'dark');
    }
  </script>
</body>
</html>

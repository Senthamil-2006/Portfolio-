<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Senthamil Senvan.P — ECE Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Syne:wght@400;600;700;800&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #080d14;
    --bg2: #0c1420;
    --bg3: #101c2c;
    --cyan: #00e5c8;
    --cyan-dim: #00b89f;
    --amber: #ffb347;
    --text: #d4e4f0;
    --text-muted: #6b8499;
    --border: #1a2e42;
    --card: #0e1a28;
    --mono: 'Share Tech Mono', monospace;
    --head: 'Syne', sans-serif;
    --body: 'DM Sans', sans-serif;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--body);
    font-weight: 300;
    overflow-x: hidden;
    cursor: default;
  }

  /* ── CIRCUIT BACKGROUND ── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,229,200,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,229,200,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  /* ── NOISE OVERLAY ── */
  body::after {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.03'/%3E%3C/svg%3E");
    opacity: 0.4;
    pointer-events: none;
    z-index: 0;
  }

  section, nav, footer { position: relative; z-index: 1; }

  /* ── NAV ── */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1.2rem 4rem;
    background: rgba(8,13,20,0.85);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid var(--border);
    z-index: 100;
  }

  .nav-logo {
    font-family: var(--mono);
    font-size: 0.9rem;
    color: var(--cyan);
    letter-spacing: 0.1em;
  }

  .nav-logo span { color: var(--text-muted); }

  nav ul {
    list-style: none;
    display: flex;
    gap: 2.5rem;
  }

  nav ul a {
    font-family: var(--mono);
    font-size: 0.78rem;
    color: var(--text-muted);
    text-decoration: none;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    transition: color 0.2s;
  }

  nav ul a:hover { color: var(--cyan); }

  /* ── HERO ── */
  #hero {
    min-height: 100vh;
    display: grid;
    place-items: center;
    padding: 6rem 4rem 4rem;
    position: relative;
  }

  .hero-inner {
    max-width: 1100px;
    width: 100%;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    align-items: center;
  }

  .hero-tag {
    font-family: var(--mono);
    font-size: 0.75rem;
    color: var(--cyan);
    letter-spacing: 0.2em;
    text-transform: uppercase;
    margin-bottom: 1.2rem;
    display: flex;
    align-items: center;
    gap: 0.8rem;
  }

  .hero-tag::before {
    content: '';
    display: block;
    width: 2rem;
    height: 1px;
    background: var(--cyan);
  }

  h1 {
    font-family: var(--head);
    font-weight: 800;
    font-size: clamp(2.8rem, 5vw, 4.2rem);
    line-height: 1.05;
    letter-spacing: -0.02em;
    color: #fff;
    margin-bottom: 1rem;
  }

  h1 .accent { color: var(--cyan); }

  .hero-sub {
    color: var(--text-muted);
    font-size: 1rem;
    line-height: 1.7;
    max-width: 420px;
    margin-bottom: 2.5rem;
  }

  .hero-cta {
    display: flex;
    gap: 1rem;
    flex-wrap: wrap;
  }

  .btn {
    font-family: var(--mono);
    font-size: 0.78rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    text-decoration: none;
    padding: 0.85rem 2rem;
    border: 1px solid var(--cyan);
    color: var(--cyan);
    background: transparent;
    transition: all 0.25s;
    clip-path: polygon(0 0, calc(100% - 12px) 0, 100% 12px, 100% 100%, 12px 100%, 0 calc(100% - 12px));
  }

  .btn:hover {
    background: var(--cyan);
    color: var(--bg);
  }

  .btn-ghost {
    border-color: var(--border);
    color: var(--text-muted);
  }

  .btn-ghost:hover {
    border-color: var(--text-muted);
    background: transparent;
    color: var(--text);
  }

  /* HERO RIGHT — STATUS PANEL */
  .hero-panel {
    background: var(--card);
    border: 1px solid var(--border);
    padding: 2rem;
    position: relative;
    clip-path: polygon(0 0, calc(100% - 20px) 0, 100% 20px, 100% 100%, 20px 100%, 0 calc(100% - 20px));
  }

  .hero-panel::before {
    content: 'STATUS — ONLINE';
    font-family: var(--mono);
    font-size: 0.65rem;
    color: var(--cyan);
    letter-spacing: 0.15em;
    position: absolute;
    top: 0.6rem;
    right: 1.5rem;
  }

  .panel-row {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    padding: 0.9rem 0;
    border-bottom: 1px solid var(--border);
  }

  .panel-row:last-child { border-bottom: none; }

  .panel-key {
    font-family: var(--mono);
    font-size: 0.7rem;
    color: var(--text-muted);
    letter-spacing: 0.1em;
    text-transform: uppercase;
  }

  .panel-val {
    font-family: var(--mono);
    font-size: 0.82rem;
    color: var(--text);
    text-align: right;
  }

  .panel-val.cyan { color: var(--cyan); }

  .dot {
    display: inline-block;
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: var(--cyan);
    margin-right: 0.4rem;
    animation: pulse 2s infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.3; }
  }

  /* ── SECTION BASE ── */
  section {
    padding: 6rem 4rem;
    max-width: 1100px;
    margin: 0 auto;
  }

  .sec-label {
    font-family: var(--mono);
    font-size: 0.7rem;
    color: var(--cyan);
    letter-spacing: 0.25em;
    text-transform: uppercase;
    margin-bottom: 0.6rem;
    display: flex;
    align-items: center;
    gap: 0.8rem;
  }

  .sec-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
    max-width: 60px;
  }

  h2 {
    font-family: var(--head);
    font-weight: 700;
    font-size: clamp(1.8rem, 3vw, 2.6rem);
    color: #fff;
    letter-spacing: -0.02em;
    margin-bottom: 3rem;
  }

  /* ── SKILLS ── */
  #skills { background: var(--bg2); max-width: 100%; padding: 6rem 0; }
  #skills .inner { max-width: 1100px; margin: 0 auto; padding: 0 4rem; }

  .skills-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.5rem;
  }

  .skill-card {
    background: var(--card);
    border: 1px solid var(--border);
    padding: 1.8rem;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s, transform 0.3s;
  }

  .skill-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: var(--cyan);
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.3s;
  }

  .skill-card:hover { border-color: rgba(0,229,200,0.3); transform: translateY(-4px); }
  .skill-card:hover::before { transform: scaleX(1); }

  .skill-icon {
    font-family: var(--mono);
    font-size: 1.6rem;
    color: var(--cyan);
    margin-bottom: 1rem;
    line-height: 1;
  }

  .skill-title {
    font-family: var(--head);
    font-weight: 700;
    font-size: 1rem;
    color: #fff;
    margin-bottom: 0.6rem;
  }

  .skill-list {
    font-family: var(--mono);
    font-size: 0.72rem;
    color: var(--text-muted);
    line-height: 1.9;
    letter-spacing: 0.05em;
  }

  /* ── PROJECTS ── */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 1.5rem;
  }

  .proj-card {
    background: var(--card);
    border: 1px solid var(--border);
    padding: 2rem;
    position: relative;
    overflow: hidden;
    transition: all 0.3s;
    clip-path: polygon(0 0, calc(100% - 16px) 0, 100% 16px, 100% 100%, 0 100%);
  }

  .proj-card:hover { border-color: rgba(0,229,200,0.25); }

  .proj-card::after {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(ellipse at top left, rgba(0,229,200,0.04) 0%, transparent 60%);
    opacity: 0;
    transition: opacity 0.3s;
  }

  .proj-card:hover::after { opacity: 1; }

  .proj-num {
    font-family: var(--mono);
    font-size: 0.65rem;
    color: var(--text-muted);
    letter-spacing: 0.15em;
    margin-bottom: 1rem;
  }

  .proj-title {
    font-family: var(--head);
    font-weight: 700;
    font-size: 1.05rem;
    color: #fff;
    margin-bottom: 1rem;
    line-height: 1.3;
  }

  .proj-desc {
    font-size: 0.85rem;
    color: var(--text-muted);
    line-height: 1.7;
    margin-bottom: 1.5rem;
  }

  .proj-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 0.4rem;
  }

  .tag {
    font-family: var(--mono);
    font-size: 0.65rem;
    letter-spacing: 0.08em;
    padding: 0.25rem 0.6rem;
    background: rgba(0,229,200,0.07);
    border: 1px solid rgba(0,229,200,0.2);
    color: var(--cyan-dim);
  }

  /* ── EDUCATION ── */
  #education { background: var(--bg2); max-width: 100%; padding: 6rem 0; }
  #education .inner { max-width: 1100px; margin: 0 auto; padding: 0 4rem; }

  .edu-timeline {
    position: relative;
    padding-left: 2rem;
  }

  .edu-timeline::before {
    content: '';
    position: absolute;
    left: 0;
    top: 0.5rem;
    bottom: 0;
    width: 1px;
    background: var(--border);
  }

  .edu-item {
    position: relative;
    margin-bottom: 2.5rem;
  }

  .edu-item::before {
    content: '';
    position: absolute;
    left: -2.3rem;
    top: 0.4rem;
    width: 8px;
    height: 8px;
    border: 2px solid var(--cyan);
    background: var(--bg);
    transform: rotate(45deg);
  }

  .edu-period {
    font-family: var(--mono);
    font-size: 0.7rem;
    color: var(--cyan);
    letter-spacing: 0.1em;
    margin-bottom: 0.4rem;
  }

  .edu-degree {
    font-family: var(--head);
    font-weight: 700;
    font-size: 1.1rem;
    color: #fff;
    margin-bottom: 0.3rem;
  }

  .edu-school {
    font-size: 0.88rem;
    color: var(--text-muted);
  }

  .edu-cgpa {
    display: inline-block;
    margin-top: 0.5rem;
    font-family: var(--mono);
    font-size: 0.72rem;
    color: var(--amber);
    background: rgba(255,179,71,0.08);
    border: 1px solid rgba(255,179,71,0.2);
    padding: 0.2rem 0.7rem;
  }

  /* ── CONTACT ── */
  .contact-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 3rem;
    align-items: start;
  }

  .contact-intro {
    color: var(--text-muted);
    font-size: 1rem;
    line-height: 1.7;
    margin-bottom: 2rem;
  }

  .contact-links { display: flex; flex-direction: column; gap: 1rem; }

  .contact-link {
    display: flex;
    align-items: center;
    gap: 1rem;
    text-decoration: none;
    padding: 1rem 1.2rem;
    background: var(--card);
    border: 1px solid var(--border);
    transition: all 0.25s;
  }

  .contact-link:hover {
    border-color: rgba(0,229,200,0.3);
    background: rgba(0,229,200,0.03);
  }

  .contact-link-icon {
    font-family: var(--mono);
    font-size: 1rem;
    color: var(--cyan);
    width: 1.4rem;
    text-align: center;
  }

  .contact-link-info { flex: 1; }

  .contact-link-label {
    font-family: var(--mono);
    font-size: 0.65rem;
    color: var(--text-muted);
    letter-spacing: 0.15em;
    text-transform: uppercase;
  }

  .contact-link-val {
    font-size: 0.85rem;
    color: var(--text);
    margin-top: 0.15rem;
  }

  .contact-link-arrow {
    font-size: 0.7rem;
    color: var(--text-muted);
    transition: color 0.2s, transform 0.2s;
  }

  .contact-link:hover .contact-link-arrow {
    color: var(--cyan);
    transform: translateX(3px);
  }

  /* ── WORKSHOP BADGE ── */
  .workshop-badge {
    background: var(--card);
    border: 1px solid var(--border);
    padding: 1.5rem 2rem;
    display: flex;
    gap: 1.5rem;
    align-items: flex-start;
  }

  .badge-icon {
    font-family: var(--mono);
    font-size: 1.5rem;
    color: var(--amber);
    line-height: 1;
  }

  .badge-title {
    font-family: var(--head);
    font-weight: 700;
    font-size: 0.95rem;
    color: #fff;
    margin-bottom: 0.3rem;
  }

  .badge-sub {
    font-size: 0.8rem;
    color: var(--text-muted);
    line-height: 1.5;
  }

  /* ── FOOTER ── */
  footer {
    border-top: 1px solid var(--border);
    padding: 2rem 4rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: relative;
    z-index: 1;
  }

  .footer-text {
    font-family: var(--mono);
    font-size: 0.7rem;
    color: var(--text-muted);
    letter-spacing: 0.1em;
  }

  .footer-text span { color: var(--cyan); }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .hero-inner > * {
    animation: fadeUp 0.8s ease both;
  }

  .hero-inner > *:nth-child(2) { animation-delay: 0.15s; }

  /* ── RESPONSIVE ── */
  @media (max-width: 768px) {
    nav { padding: 1rem 1.5rem; }
    nav ul { gap: 1.2rem; }
    section { padding: 4rem 1.5rem; }
    .hero-inner { grid-template-columns: 1fr; gap: 2.5rem; }
    .skills-grid { grid-template-columns: 1fr; }
    .projects-grid { grid-template-columns: 1fr; }
    .contact-grid { grid-template-columns: 1fr; }
    footer { flex-direction: column; gap: 0.8rem; text-align: center; }
    #skills .inner, #education .inner { padding: 0 1.5rem; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo"><span>// </span>SENVAN.ECE</div>
  <ul>
    <li><a href="#about">About</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#education">Education</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="about">
  <div class="hero-inner">
    <div>
      <div class="hero-tag">ECE Undergraduate · Anna University</div>
      <h1>SENTHAMIL<br><span class="accent">SENVAN.P</span></h1>
      <p class="hero-sub">
        Electronics & Communication Engineer building at the intersection of hardware design, signal processing, and intelligent systems. Specialising in FPGA, IoT, and AI-integrated applications.
      </p>
      <div class="hero-cta">
        <a href="#projects" class="btn">View Projects</a>
        <a href="mailto:senthamil1632006@gmail.com" class="btn btn-ghost">Get In Touch</a>
      </div>
    </div>

    <div class="hero-panel">
      <div class="panel-row">
        <span class="panel-key">Status</span>
        <span class="panel-val cyan"><span class="dot"></span>Available</span>
      </div>
      <div class="panel-row">
        <span class="panel-key">Location</span>
        <span class="panel-val">Trichy, Tamil Nadu, IN</span>
      </div>
      <div class="panel-row">
        <span class="panel-key">Programme</span>
        <span class="panel-val">B.E. ECE · 2023–present</span>
      </div>
      <div class="panel-row">
        <span class="panel-key">CGPA</span>
        <span class="panel-val cyan">7.62</span>
      </div>
      <div class="panel-row">
        <span class="panel-key">Domain</span>
        <span class="panel-val">VLSI · IoT · AI/ML</span>
      </div>
      <div class="panel-row">
        <span class="panel-key">Languages</span>
        <span class="panel-val">English · Tamil</span>
      </div>
      <div class="panel-row">
        <span class="panel-key">GitHub</span>
        <span class="panel-val cyan">Senthamil-2006</span>
      </div>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section id="skills">
  <div class="inner">
    <div class="sec-label">01 — Capabilities</div>
    <h2>Skills & Tools</h2>
    <div class="skills-grid">

      <div class="skill-card">
        <div class="skill-icon">{ }</div>
        <div class="skill-title">Programming</div>
        <div class="skill-list">
          C — Systems & Embedded<br>
          Python — ML & Automation<br>
          Java — OOP & Applications<br>
        </div>
      </div>

      <div class="skill-card">
        <div class="skill-icon">⊞</div>
        <div class="skill-title">Hardware Design</div>
        <div class="skill-list">
          Verilog HDL<br>
          FPGA (Vivado / ModelSim)<br>
          EDA Simulation<br>
          MATLAB
        </div>
      </div>

      <div class="skill-card">
        <div class="skill-icon">⌁</div>
        <div class="skill-title">IoT & Embedded</div>
        <div class="skill-list">
          Arduino IDE<br>
          IoT Protocols<br>
          Sensor Integration<br>
          Microcontroller Systems
        </div>
      </div>

      <div class="skill-card">
        <div class="skill-icon">◈</div>
        <div class="skill-title">VLSI & SOC</div>
        <div class="skill-list">
          SOC Design Flow<br>
          Verification Methodologies<br>
          FPGA Prototyping<br>
          Timing Analysis
        </div>
      </div>

      <div class="skill-card">
        <div class="skill-icon">⚡</div>
        <div class="skill-title">EM & Simulation</div>
        <div class="skill-list">
          FDTD Method<br>
          Maxwell Equations<br>
          Wave Propagation Analysis<br>
          Boundary Condition Modelling
        </div>
      </div>

      <div class="skill-card">
        <div class="skill-icon">⬡</div>
        <div class="skill-title">Web & AI</div>
        <div class="skill-list">
          Flask Framework<br>
          Cybersecurity Tools<br>
          Prediction Modelling<br>
          API Integration
        </div>
      </div>

    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="sec-label">02 — Work</div>
  <h2>Projects</h2>
  <div class="projects-grid">

    <div class="proj-card">
      <div class="proj-num">// PROJ-01</div>
      <div class="proj-title">EM Boundary Behaviour Simulator</div>
      <p class="proj-desc">
        A 1D Maxwell Equation Visualiser using the FDTD (Finite-Difference Time-Domain) method. Simulates EM wave propagation, reflection, and transmission across different materials with real-time boundary analysis.
      </p>
      <div class="proj-tags">
        <span class="tag">FDTD</span>
        <span class="tag">Python</span>
        <span class="tag">MATLAB</span>
        <span class="tag">Maxwell Equations</span>
        <span class="tag">Visualisation</span>
      </div>
    </div>

    <div class="proj-card">
      <div class="proj-num">// PROJ-02</div>
      <div class="proj-title">Accident Risk Predictor</div>
      <p class="proj-desc">
        A Flask web application that predicts road accident risk by analysing speed, geolocation, and weather data. Features interactive map visualisation and real-time voice alerts to improve driving safety decision-making.
      </p>
      <div class="proj-tags">
        <span class="tag">Flask</span>
        <span class="tag">Python</span>
        <span class="tag">Maps API</span>
        <span class="tag">ML</span>
        <span class="tag">Voice Alerts</span>
      </div>
    </div>

    <div class="proj-card">
      <div class="proj-num">// PROJ-03</div>
      <div class="proj-title">Smart Low-Power 12-bit Multiplexer</div>
      <p class="proj-desc">
        Designed and implemented a 12-bit Multiplexer using Verilog HDL on an FPGA platform with an integrated ultrasonic sensor for adaptive power control. Verified via Vivado/ModelSim for functional correctness and timing performance.
      </p>
      <div class="proj-tags">
        <span class="tag">Verilog HDL</span>
        <span class="tag">FPGA</span>
        <span class="tag">Vivado</span>
        <span class="tag">ModelSim</span>
        <span class="tag">Low Power</span>
      </div>
    </div>

    <div class="proj-card">
      <div class="proj-num">// PROJ-04</div>
      <div class="proj-title">Keylogger — Cybersecurity Tracker</div>
      <p class="proj-desc">
        A Python-based system activity tracker built for cybersecurity analysis research. Captures keystrokes, generates automated activity reports, and implements scheduled email notifications for system monitoring.
      </p>
      <div class="proj-tags">
        <span class="tag">Python</span>
        <span class="tag">Cybersecurity</span>
        <span class="tag">Automation</span>
        <span class="tag">Email API</span>
        <span class="tag">Monitoring</span>
      </div>
    </div>

  </div>
</section>

<!-- EDUCATION -->
<section id="education">
  <div class="inner">
    <div class="sec-label">03 — Background</div>
    <h2>Education & Training</h2>

    <div class="edu-timeline">
      <div class="edu-item">
        <div class="edu-period">2023 — PRESENT</div>
        <div class="edu-degree">B.E. Electronics & Communication Engineering</div>
        <div class="edu-school">Anna University Regional Campus, Coimbatore</div>
        <div class="edu-cgpa">CGPA: 7.62</div>
      </div>

      <div class="edu-item">
        <div class="edu-period">2021 — 2023</div>
        <div class="edu-degree">Higher Secondary Certificate</div>
        <div class="edu-school">Sowdaambika Matric Higher Secondary School</div>
      </div>
    </div>

    <br><br>

    <div class="sec-label">04 — Certifications</div>
    <h2>Workshops & Training</h2>

    <div class="workshop-badge">
      <div class="badge-icon">◉</div>
      <div>
        <div class="badge-title">SOC Design Flow & Verification Methodologies — VLSI</div>
        <div class="badge-sub">TICEL Bio Park, Maruthamalai Rd, Coimbatore – 641046<br>Intensive hands-on workshop covering system-on-chip design workflows and formal verification techniques in the VLSI domain.</div>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="sec-label">05 — Connect</div>
  <h2>Get In Touch</h2>
  <div class="contact-grid">
    <div>
      <p class="contact-intro">
        Currently a second-year ECE student, open to internship opportunities, collaborative projects, and research engagements in VLSI, IoT, and AI-integrated systems.
      </p>
      <a href="#projects" class="btn">View My Work →</a>
    </div>
    <div class="contact-links">
      <a href="mailto:senthamil1632006@gmail.com" class="contact-link">
        <span class="contact-link-icon">✉</span>
        <div class="contact-link-info">
          <div class="contact-link-label">Email</div>
          <div class="contact-link-val">senthamil1632006@gmail.com</div>
        </div>
        <span class="contact-link-arrow">→</span>
      </a>
      <a href="tel:6369976642" class="contact-link">
        <span class="contact-link-icon">✆</span>
        <div class="contact-link-info">
          <div class="contact-link-label">Phone</div>
          <div class="contact-link-val">+91 6369976642</div>
        </div>
        <span class="contact-link-arrow">→</span>
      </a>
      <a href="https://www.linkedin.com/in/senthamil-selvan-2b2b942a0" target="_blank" class="contact-link">
        <span class="contact-link-icon">in</span>
        <div class="contact-link-info">
          <div class="contact-link-label">LinkedIn</div>
          <div class="contact-link-val">senthamil-selvan-2b2b942a0</div>
        </div>
        <span class="contact-link-arrow">→</span>
      </a>
      <a href="https://github.com/Senthamil-2006" target="_blank" class="contact-link">
        <span class="contact-link-icon">⌥</span>
        <div class="contact-link-info">
          <div class="contact-link-label">GitHub</div>
          <div class="contact-link-val">Senthamil-2006</div>
        </div>
        <span class="contact-link-arrow">→</span>
      </a>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-text">© 2025 <span>SENTHAMIL SENVAN.P</span> · ECE Engineer</div>
  <div class="footer-text">Built with <span>precision</span> · Trichy, India</div>
</footer>

</body>
</html>

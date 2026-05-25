<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>K E Watson · Full Stack Developer</title>
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=DM+Sans:wght@300;400;500&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet" />
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@latest/tabler-icons.min.css" />

<style>
  :root {
    --sunset-deep:    #1a3240;
    --sunset-navy:    #264653;
    --sunset-orange:  #e76f51;
    --sunset-coral:   #f4a261;
    --sunset-gold:    #e9c46a;
    --sunset-cream:   #fdf6ec;
    --sunset-muted:   #8fa8b0;
    --font-display:   'Playfair Display', Georgia, serif;
    --font-body:      'DM Sans', Arial, sans-serif;
    --font-mono:      'DM Mono', monospace;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--sunset-cream);
    color: var(--sunset-navy);
    font-family: var(--font-body);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* ── NOISE TEXTURE OVERLAY ── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.03'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 0;
    opacity: 0.6;
  }

  .page { position: relative; z-index: 1; max-width: 860px; margin: 0 auto; padding: 0 24px 80px; }

  /* ── HERO ── */
  .hero {
    position: relative;
    background: var(--sunset-deep);
    border-radius: 0 0 32px 32px;
    padding: 64px 52px 52px;
    margin-bottom: 56px;
    overflow: hidden;
  }

  .hero::before {
    content: '';
    position: absolute;
    top: -60px; right: -60px;
    width: 300px; height: 300px;
    background: var(--sunset-orange);
    border-radius: 50%;
    opacity: 0.12;
  }

  .hero::after {
    content: '';
    position: absolute;
    bottom: -40px; left: 40%;
    width: 200px; height: 200px;
    background: var(--sunset-gold);
    border-radius: 50%;
    opacity: 0.08;
  }

  .hero-top {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    gap: 24px;
    flex-wrap: wrap;
    margin-bottom: 32px;
  }

  .hero-avatar {
    width: 72px; height: 72px;
    border-radius: 50%;
    background: var(--sunset-orange);
    display: flex; align-items: center; justify-content: center;
    font-family: var(--font-display);
    font-size: 28px; font-weight: 900;
    color: #fff;
    border: 3px solid var(--sunset-gold);
    flex-shrink: 0;
  }

  .hero-status {
    display: flex; align-items: center; gap: 8px;
    background: rgba(233,196,106,0.15);
    border: 1px solid rgba(233,196,106,0.35);
    border-radius: 24px;
    padding: 6px 14px;
    font-size: 12px;
    color: var(--sunset-gold);
    font-weight: 500;
    letter-spacing: 0.04em;
  }

  .status-dot {
    width: 7px; height: 7px;
    border-radius: 50%;
    background: #4ade80;
    animation: pulse 2s ease-in-out infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.5; transform: scale(0.8); }
  }

  .hero-name {
    font-family: var(--font-display);
    font-size: clamp(40px, 6vw, 64px);
    font-weight: 900;
    color: #fff;
    line-height: 1;
    margin-bottom: 6px;
    letter-spacing: -1px;
  }

  .hero-name span { color: var(--sunset-gold); }

  .hero-role {
    font-size: 15px;
    color: var(--sunset-coral);
    font-weight: 500;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    margin-bottom: 20px;
    display: flex; align-items: center; gap: 8px;
  }

  .hero-role i { font-size: 16px; }

  .hero-bio {
    font-size: 16px;
    color: rgba(255,255,255,0.75);
    line-height: 1.8;
    max-width: 560px;
    margin-bottom: 32px;
  }

  .hero-bio strong { color: var(--sunset-gold); font-weight: 500; }

  .hero-badges {
    display: flex; flex-wrap: wrap; gap: 8px;
    margin-bottom: 32px;
  }

  .badge {
    display: inline-flex; align-items: center; gap: 6px;
    padding: 6px 14px;
    border-radius: 24px;
    font-size: 12px; font-weight: 500;
    font-family: var(--font-body);
    letter-spacing: 0.03em;
    border: 1px solid;
    transition: transform 0.2s;
  }

  .badge:hover { transform: translateY(-2px); }
  .badge i { font-size: 13px; }

  .badge-green  { background: rgba(74,222,128,0.12); color: #86efac; border-color: rgba(74,222,128,0.3); }
  .badge-orange { background: rgba(231,111,81,0.18); color: #fca18a; border-color: rgba(231,111,81,0.4); }
  .badge-gold   { background: rgba(233,196,106,0.15); color: var(--sunset-gold); border-color: rgba(233,196,106,0.35); }

  .hero-socials {
    display: flex; gap: 10px; flex-wrap: wrap;
  }

  .social-btn {
    display: inline-flex; align-items: center; gap: 8px;
    padding: 10px 20px;
    border-radius: 10px;
    border: 1.5px solid rgba(233,196,106,0.4);
    color: var(--sunset-gold);
    background: rgba(233,196,106,0.07);
    font-size: 13px; font-weight: 500;
    text-decoration: none;
    transition: all 0.2s;
    cursor: pointer;
  }

  .social-btn:hover {
    background: rgba(233,196,106,0.18);
    border-color: var(--sunset-gold);
    transform: translateY(-2px);
  }

  .social-btn i { font-size: 16px; }

  /* ── SECTION ── */
  .section { margin-bottom: 52px; }

  .section-header {
    display: flex; align-items: center; gap: 12px;
    margin-bottom: 24px;
  }

  .section-icon {
    width: 38px; height: 38px;
    border-radius: 10px;
    background: var(--sunset-orange);
    display: flex; align-items: center; justify-content: center;
    color: #fff;
    font-size: 18px;
    flex-shrink: 0;
  }

  .section-title {
    font-family: var(--font-display);
    font-size: 22px;
    font-weight: 700;
    color: var(--sunset-navy);
  }

  .section-line {
    flex: 1;
    height: 1.5px;
    background: linear-gradient(90deg, var(--sunset-orange) 0%, transparent 100%);
  }

  /* ── ABOUT ── */
  .about-text {
    font-size: 15px;
    line-height: 1.9;
    color: #3d5a66;
    max-width: 680px;
  }

  .about-text strong { color: var(--sunset-orange); font-weight: 500; }

  /* ── PROJECTS ── */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 16px;
  }

  .project-card {
    background: #fff;
    border: 1.5px solid #e8ddd0;
    border-radius: 16px;
    padding: 24px;
    position: relative;
    overflow: hidden;
    transition: all 0.25s;
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 3px;
    background: var(--sunset-orange);
  }

  .project-card:hover {
    border-color: var(--sunset-coral);
    transform: translateY(-4px);
    box-shadow: 0 12px 32px rgba(231,111,81,0.12);
  }

  .project-icon-wrap {
    width: 44px; height: 44px;
    border-radius: 12px;
    background: rgba(231,111,81,0.1);
    display: flex; align-items: center; justify-content: center;
    margin-bottom: 14px;
    color: var(--sunset-orange);
    font-size: 22px;
  }

  .project-name {
    font-family: var(--font-display);
    font-size: 17px; font-weight: 700;
    color: var(--sunset-navy);
    margin-bottom: 8px;
  }

  .project-desc {
    font-size: 13px;
    color: #5f7a85;
    line-height: 1.65;
    margin-bottom: 14px;
  }

  .project-tags { display: flex; flex-wrap: wrap; gap: 5px; }

  .ptag {
    font-size: 11px; font-weight: 500;
    padding: 3px 9px;
    border-radius: 20px;
    background: #fdf2e9;
    color: #854f0b;
    border: 1px solid #f4c77580;
    font-family: var(--font-mono);
  }

  /* ── TECH STACK ── */
  .stack-sections { display: flex; flex-direction: column; gap: 20px; }

  .stack-row { display: flex; flex-wrap: wrap; align-items: center; gap: 12px; }

  .stack-cat {
    font-size: 11px; font-weight: 500;
    color: var(--sunset-muted);
    text-transform: uppercase;
    letter-spacing: 0.1em;
    width: 110px;
    flex-shrink: 0;
    font-family: var(--font-mono);
  }

  .stack-pills { display: flex; flex-wrap: wrap; gap: 8px; }

  .tech-pill {
    display: inline-flex; align-items: center; gap: 7px;
    padding: 7px 14px;
    border-radius: 10px;
    border: 1.5px solid #e0d0c0;
    background: #fff;
    font-size: 13px; font-weight: 500;
    color: var(--sunset-navy);
    transition: all 0.2s;
  }

  .tech-pill:hover {
    border-color: var(--sunset-orange);
    background: #fff8f3;
    transform: translateY(-2px);
  }

  .tech-pill i { font-size: 17px; }
  .tech-pill img { width: 17px; height: 17px; object-fit: contain; }

  .tech-pill-learn {
    border-color: #f4c77580;
    background: #fdf2e9;
    color: #854f0b;
  }

  .tech-pill-learn:hover {
    border-color: var(--sunset-gold);
    background: #fdf2e9;
  }

  .stack-divider {
    width: 100%;
    height: 1px;
    background: #e8ddd0;
  }

  /* ── CURRENTLY ── */
  .currently-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 14px;
  }

  .currently-card {
    background: var(--sunset-navy);
    border-radius: 14px;
    padding: 20px;
    position: relative;
    overflow: hidden;
  }

  .currently-card::after {
    content: '';
    position: absolute;
    bottom: -20px; right: -20px;
    width: 80px; height: 80px;
    border-radius: 50%;
    opacity: 0.08;
  }

  .cc-building::after { background: var(--sunset-orange); }
  .cc-learning::after { background: var(--sunset-coral); }
  .cc-exploring::after { background: var(--sunset-gold); }
  .cc-open::after { background: #86efac; }

  .cc-icon {
    font-size: 26px;
    margin-bottom: 10px;
    display: block;
  }

  .cc-building .cc-icon  { color: var(--sunset-orange); }
  .cc-learning .cc-icon  { color: var(--sunset-coral); }
  .cc-exploring .cc-icon { color: var(--sunset-gold); }
  .cc-open .cc-icon      { color: #86efac; }

  .cc-label {
    font-size: 10px;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.12em;
    margin-bottom: 6px;
    font-family: var(--font-mono);
  }

  .cc-building .cc-label  { color: var(--sunset-orange); }
  .cc-learning .cc-label  { color: var(--sunset-coral); }
  .cc-exploring .cc-label { color: var(--sunset-gold); }
  .cc-open .cc-label      { color: #86efac; }

  .cc-text {
    font-size: 13px;
    color: rgba(255,255,255,0.75);
    line-height: 1.6;
  }

  /* ── STATS ── */
  .stats-row {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
    gap: 14px;
  }

  .stat-card {
    background: #fff;
    border: 1.5px solid #e8ddd0;
    border-radius: 14px;
    padding: 20px;
    text-align: center;
    transition: all 0.2s;
  }

  .stat-card:hover {
    border-color: var(--sunset-coral);
    transform: translateY(-3px);
  }

  .stat-icon { font-size: 26px; color: var(--sunset-orange); margin-bottom: 8px; }
  .stat-val {
    font-family: var(--font-display);
    font-size: 30px; font-weight: 900;
    color: var(--sunset-navy);
    line-height: 1;
    margin-bottom: 4px;
  }

  .stat-lbl {
    font-size: 12px;
    color: var(--sunset-muted);
    font-family: var(--font-mono);
    letter-spacing: 0.05em;
  }

  /* ── CONTACT ── */
  .contact-card {
    background: var(--sunset-deep);
    border-radius: 20px;
    padding: 40px 44px;
    position: relative;
    overflow: hidden;
  }

  .contact-card::before {
    content: '';
    position: absolute;
    top: -50px; right: -50px;
    width: 200px; height: 200px;
    background: var(--sunset-orange);
    border-radius: 50%;
    opacity: 0.1;
  }

  .contact-card::after {
    content: '';
    position: absolute;
    bottom: -60px; left: 30%;
    width: 160px; height: 160px;
    background: var(--sunset-gold);
    border-radius: 50%;
    opacity: 0.07;
  }

  .contact-title {
    font-family: var(--font-display);
    font-size: 28px; font-weight: 900;
    color: #fff;
    margin-bottom: 8px;
  }

  .contact-sub {
    font-size: 14px;
    color: rgba(255,255,255,0.55);
    margin-bottom: 28px;
  }

  .contact-links {
    display: flex; flex-wrap: wrap; gap: 10px;
    position: relative; z-index: 1;
  }

  .contact-btn {
    display: inline-flex; align-items: center; gap: 9px;
    padding: 12px 22px;
    border-radius: 12px;
    font-size: 14px; font-weight: 500;
    text-decoration: none;
    transition: all 0.2s;
    cursor: pointer;
  }

  .contact-btn i { font-size: 18px; }

  .contact-btn-primary {
    background: var(--sunset-orange);
    color: #fff;
    border: none;
  }

  .contact-btn-primary:hover {
    background: #d4614a;
    transform: translateY(-2px);
  }

  .contact-btn-ghost {
    background: transparent;
    color: var(--sunset-gold);
    border: 1.5px solid rgba(233,196,106,0.4);
  }

  .contact-btn-ghost:hover {
    background: rgba(233,196,106,0.12);
    border-color: var(--sunset-gold);
    transform: translateY(-2px);
  }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    padding-top: 40px;
    font-size: 12px;
    color: var(--sunset-muted);
    font-family: var(--font-mono);
    letter-spacing: 0.05em;
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  .hero            { animation: fadeUp 0.6s ease both; }
  .section:nth-child(1) { animation: fadeUp 0.6s 0.1s ease both; }
  .section:nth-child(2) { animation: fadeUp 0.6s 0.2s ease both; }
  .section:nth-child(3) { animation: fadeUp 0.6s 0.3s ease both; }
  .section:nth-child(4) { animation: fadeUp 0.6s 0.4s ease both; }
  .section:nth-child(5) { animation: fadeUp 0.6s 0.5s ease both; }
  .section:nth-child(6) { animation: fadeUp 0.6s 0.6s ease both; }

  /* ── ICON COLORS ── */
  .i-js      { color: #f7df1e; }
  .i-java    { color: #ed8b00; }
  .i-react   { color: #61dafb; }
  .i-node    { color: #6cc24a; }
  .i-spring  { color: #6db33f; }
  .i-docker  { color: #2496ed; }
  .i-pg      { color: #336791; }
  .i-mongo   { color: #47a248; }
  .i-redis   { color: #dc382d; }
  .i-mysql   { color: #4479a1; }
  .i-tailwind{ color: #06b6d4; }
  .i-git     { color: #f05032; }
  .i-vite    { color: #646cff; }
  .i-html    { color: #e34f26; }
  .i-css     { color: #1572b6; }
  .i-express { color: #999; }

  @media (max-width: 600px) {
    .hero { padding: 40px 28px 36px; }
    .contact-card { padding: 28px 24px; }
    .stack-cat { width: 80px; font-size: 10px; }
  }
</style>
</head>
<body>
<div class="page">

  <!-- ── HERO ── -->
  <div class="hero">
    <div class="hero-top">
      <div class="hero-avatar">W</div>
      <div class="hero-status">
        <span class="status-dot"></span>
        Open to opportunities
      </div>
    </div>

    <div class="hero-name">Watson<span>.</span></div>
    <div class="hero-role">
      <i class="ti ti-code"></i>
      Full Stack Developer
    </div>

    <p class="hero-bio">
      I build <strong>end-to-end web applications</strong> — from React frontends to Java/Node backends,
      to databases that hold up at scale. Right now I'm deep in backend architecture:
      learning how to design systems that are <strong>fast, reliable, and built to grow</strong>.
    </p>

    <div class="hero-badges">
      <span class="badge badge-green">
        <i class="ti ti-map-pin"></i> Open to remote
      </span>
      <span class="badge badge-orange">
        <i class="ti ti-briefcase"></i> Available for freelance
      </span>
      <span class="badge badge-gold">
        <i class="ti ti-trending-up"></i> Levelling up backend
      </span>
    </div>

    <div class="hero-socials">
      <a class="social-btn" href="https://www.linkedin.com/in/karri-emmanuel-watson/">
        <i class="ti ti-brand-linkedin"></i> LinkedIn
      </a>
      <a class="social-btn" href="https://karriemmanuelwatson.github.io/Portfolio/">
        <i class="ti ti-world"></i> Portfolio
      </a>
      <a class="social-btn" href="mailto:watsoemmanuel04@gmail.com">
        <i class="ti ti-mail"></i> Email
      </a>
      <a class="social-btn" href="https://github.com/KarriEmmanuelWatson">
        <i class="ti ti-brand-github"></i> GitHub
      </a>
    </div>
  </div>

  <!-- ── ABOUT ── -->
  <div class="section">
    <div class="section-header">
      <div class="section-icon"><i class="ti ti-user"></i></div>
      <div class="section-title">Who I am</div>
      <div class="section-line"></div>
    </div>
    <p class="about-text">
      Full-stack developer focused on building <strong>complete, production-ready web applications</strong>.
      I work across the entire stack — React UIs, REST APIs in Node.js and Spring Boot,
      relational and document databases, and containerised deployments with Docker.<br><br>
      Right now I'm going deep on backend development: learning how to design systems
      that are fast, reliable, and built to grow. <strong>Scalable architecture</strong> isn't just
      a buzzword for me — it's what I'm actively working toward.
    </p>
  </div>

  <!-- ── PROJECTS ── -->
  <div class="section">
    <div class="section-header">
      <div class="section-icon"><i class="ti ti-rocket"></i></div>
      <div class="section-title">Projects</div>
      <div class="section-line"></div>
    </div>
    <div class="projects-grid">
      <div class="project-card">
        <div class="project-icon-wrap"><i class="ti ti-layout-dashboard"></i></div>
        <div class="project-name">Your Project</div>
        <p class="project-desc">Add your real project here — one line on what it does and the problem it solves for real users.</p>
        <div class="project-tags">
          <span class="ptag">React</span>
          <span class="ptag">Node.js</span>
          <span class="ptag">PostgreSQL</span>
        </div>
      </div>
      <div class="project-card">
        <div class="project-icon-wrap"><i class="ti ti-server"></i></div>
        <div class="project-name">Your Project</div>
        <p class="project-desc">Second project. Mention something technically interesting — scale, performance, or a design decision.</p>
        <div class="project-tags">
          <span class="ptag">Spring Boot</span>
          <span class="ptag">MySQL</span>
          <span class="ptag">Docker</span>
        </div>
      </div>
      <div class="project-card">
        <div class="project-icon-wrap"><i class="ti ti-database"></i></div>
        <div class="project-name">Your Project</div>
        <p class="project-desc">Third project. Even a learning project counts — be specific about what you built and what you learned.</p>
        <div class="project-tags">
          <span class="ptag">React</span>
          <span class="ptag">MongoDB</span>
          <span class="ptag">Redis</span>
        </div>
      </div>
    </div>
  </div>

  <!-- ── TECH STACK ── -->
  <div class="section">
    <div class="section-header">
      <div class="section-icon"><i class="ti ti-stack"></i></div>
      <div class="section-title">Tech Stack</div>
      <div class="section-line"></div>
    </div>

    <div class="stack-sections">

      <div class="stack-row">
        <div class="stack-cat">Languages</div>
        <div class="stack-pills">
          <div class="tech-pill">
            <i class="ti ti-brand-javascript i-js"></i> JavaScript
          </div>
          <div class="tech-pill">
            <svg width="17" height="17" viewBox="0 0 24 24" fill="none"><path d="M8.851 18.56s-.917.534.653.714c1.902.218 2.874.187 4.969-.211 0 0 .552.346 1.321.646-4.699 2.013-10.633-.118-6.943-1.149M8.276 15.933s-1.028.761.542.924c2.032.209 3.636.227 6.413-.308 0 0 .384.389.987.602-5.679 1.661-12.007.13-7.942-1.218M13.116 11.475c1.158 1.333-.304 2.533-.304 2.533s2.939-1.518 1.589-3.418c-1.261-1.772-2.228-2.652 3.007-5.688 0 0-8.216 2.051-4.292 6.573" fill="#ed8b00"/><path d="M19.33 20.504s.679.559-.747.991c-2.712.822-11.288 1.069-13.669.033-.856-.373.75-.89 1.254-.998.527-.114.828-.093.828-.093-.953-.671-6.156 1.317-2.643 1.887 9.58 1.553 17.462-.7 14.977-1.82M9.292 13.21s-4.362 1.036-1.544 1.412c1.189.159 3.561.123 5.77-.062 1.806-.152 3.618-.477 3.618-.477s-.637.272-1.098.587c-4.429 1.165-12.986.623-10.522-.568 2.082-1.006 3.776-.892 3.776-.892M17.116 17.584c4.503-2.34 2.421-4.589.968-4.285-.355.074-.515.138-.515.138s.132-.207.385-.297c2.875-1.011 5.086 2.981-.928 4.562 0 0 .07-.063.09-.118M14.401 0s2.494 2.494-2.365 6.33c-3.896 3.077-.888 4.832-.001 6.836-2.274-2.053-3.943-3.858-2.824-5.542 1.644-2.469 6.197-3.665 5.19-7.624M9.734 23.924c4.322.277 10.959-.153 11.116-2.198 0 0-.302.775-3.572 1.391-3.688.694-8.239.613-10.937.168 0 0 .553.457 3.393.639" fill="#ed8b00"/></svg>
            Java
          </div>
        </div>
      </div>

      <div class="stack-divider"></div>

      <div class="stack-row">
        <div class="stack-cat">Frontend</div>
        <div class="stack-pills">
          <div class="tech-pill">
            <i class="ti ti-brand-react i-react"></i> React
          </div>
          <div class="tech-pill">
            <i class="ti ti-brand-html5 i-html"></i> HTML5
          </div>
          <div class="tech-pill">
            <i class="ti ti-brand-css3 i-css"></i> CSS3
          </div>
          <div class="tech-pill">
            <i class="ti ti-brand-tailwind i-tailwind"></i> Tailwind
          </div>
          <div class="tech-pill">
            <i class="ti ti-bolt i-vite"></i> Vite
          </div>
        </div>
      </div>

      <div class="stack-divider"></div>

      <div class="stack-row">
        <div class="stack-cat">Backend</div>
        <div class="stack-pills">
          <div class="tech-pill">
            <i class="ti ti-brand-nodejs i-node"></i> Node.js
          </div>
          <div class="tech-pill">
            <i class="ti ti-server i-express"></i> Express
          </div>
          <div class="tech-pill">
            <i class="ti ti-leaf i-spring"></i> Spring Boot
          </div>
        </div>
      </div>

      <div class="stack-divider"></div>

      <div class="stack-row">
        <div class="stack-cat">Databases</div>
        <div class="stack-pills">
          <div class="tech-pill">
            <i class="ti ti-database i-pg"></i> PostgreSQL
          </div>
          <div class="tech-pill">
            <i class="ti ti-database i-mysql"></i> MySQL
          </div>
          <div class="tech-pill">
            <i class="ti ti-database i-mongo"></i> MongoDB
          </div>
          <div class="tech-pill">
            <i class="ti ti-brand-redis i-redis"></i> Redis
          </div>
        </div>
      </div>

      <div class="stack-divider"></div>

      <div class="stack-row">
        <div class="stack-cat">DevOps</div>
        <div class="stack-pills">
          <div class="tech-pill">
            <i class="ti ti-brand-docker i-docker"></i> Docker
          </div>
          <div class="tech-pill">
            <i class="ti ti-brand-git i-git"></i> Git
          </div>
          <div class="tech-pill">
            <i class="ti ti-tool"></i> Postman
          </div>
        </div>
      </div>

      <div class="stack-divider"></div>

      <div class="stack-row">
        <div class="stack-cat">Learning</div>
        <div class="stack-pills">
          <div class="tech-pill tech-pill-learn">
            <i class="ti ti-coffee"></i> Java deep dive
          </div>
          <div class="tech-pill tech-pill-learn">
            <i class="ti ti-leaf"></i> Spring Boot
          </div>
          <div class="tech-pill tech-pill-learn">
            <i class="ti ti-chart-arrows"></i> System design
          </div>
          <div class="tech-pill tech-pill-learn">
            <i class="ti ti-topology-star"></i> Scalable arch
          </div>
        </div>
      </div>

    </div>
  </div>

  <!-- ── CURRENTLY ── -->
  <div class="section">
    <div class="section-header">
      <div class="section-icon"><i class="ti ti-bolt"></i></div>
      <div class="section-title">Currently</div>
      <div class="section-line"></div>
    </div>
    <div class="currently-grid">
      <div class="currently-card cc-building">
        <i class="ti ti-hammer cc-icon"></i>
        <div class="cc-label">Building</div>
        <p class="cc-text">Scalable end-to-end web applications with robust backend architecture — APIs, databases, caching, and deployment</p>
      </div>
      <div class="currently-card cc-learning">
        <i class="ti ti-book cc-icon"></i>
        <div class="cc-label">Learning</div>
        <p class="cc-text">Java and Spring Boot deeply — REST API design, JPA/Hibernate, Spring Security, and structuring backend systems</p>
      </div>
      <div class="currently-card cc-exploring">
        <i class="ti ti-bulb cc-icon"></i>
        <div class="cc-label">Exploring</div>
        <p class="cc-text">System design fundamentals — load balancing, caching strategies, database indexing, microservices patterns</p>
      </div>
      <div class="currently-card cc-open">
        <i class="ti ti-eye cc-icon"></i>
        <div class="cc-label">Open to</div>
        <p class="cc-text">Remote full-stack or backend roles and freelance projects where I can contribute and keep growing</p>
      </div>
    </div>
  </div>

  <!-- ── GITHUB STATS ── -->
  <div class="section">
    <div class="section-header">
      <div class="section-icon"><i class="ti ti-chart-bar"></i></div>
      <div class="section-title">GitHub Stats</div>
      <div class="section-line"></div>
    </div>
    <div class="stats-row">
      <div class="stat-card">
        <div class="stat-icon"><i class="ti ti-git-commit"></i></div>
        <div class="stat-val">—</div>
        <div class="stat-lbl">Total commits</div>
      </div>
      <div class="stat-card">
        <div class="stat-icon"><i class="ti ti-flame"></i></div>
        <div class="stat-val">—</div>
        <div class="stat-lbl">Day streak</div>
      </div>
      <div class="stat-card">
        <div class="stat-icon"><i class="ti ti-source-code"></i></div>
        <div class="stat-val">—</div>
        <div class="stat-lbl">Repositories</div>
      </div>
      <div class="stat-card">
        <div class="stat-icon"><i class="ti ti-star"></i></div>
        <div class="stat-val">—</div>
        <div class="stat-lbl">Stars earned</div>
      </div>
    </div>
  </div>

  <!-- ── CONTACT ── -->
  <div class="section">
    <div class="contact-card">
      <div class="contact-title">Let's build something.</div>
      <p class="contact-sub">Hiring, collaborating, or have an interesting problem — reach out. I reply fast.</p>
      <div class="contact-links">
        <a href="mailto:watsoemmanuel04@gmail.com" class="contact-btn contact-btn-primary">
          <i class="ti ti-mail"></i> watsoemmanuel04@gmail.com
        </a>
        <a href="https://www.linkedin.com/in/karri-emmanuel-watson/" class="contact-btn contact-btn-ghost">
          <i class="ti ti-brand-linkedin"></i> LinkedIn
        </a>
        <a href="https://karriemmanuelwatson.github.io/Portfolio/" class="contact-btn contact-btn-ghost">
          <i class="ti ti-world"></i> Portfolio
        </a>
        <a href="https://github.com/KarriEmmanuelWatson" class="contact-btn contact-btn-ghost">
          <i class="ti ti-brand-github"></i> GitHub
        </a>
      </div>
    </div>
  </div>

  <div class="footer">
    crafted with intention · watson · full stack developer
  </div>

</div>
</body>
</html>

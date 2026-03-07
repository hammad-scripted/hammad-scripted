<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Mohammad Hammad Ansari – GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;800&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #0b0f1a;
    --surface: #111827;
    --card: #141c2e;
    --border: #1e2d47;
    --cyan: #00e5ff;
    --violet: #a855f7;
    --green: #22d3a0;
    --text: #e2e8f0;
    --muted: #64748b;
    --font-display: 'Syne', sans-serif;
    --font-mono: 'Space Mono', monospace;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--font-display);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* ─── Animated BG grid ─── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,229,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,229,255,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .wrapper {
    position: relative;
    z-index: 1;
    max-width: 860px;
    margin: 0 auto;
    padding: 48px 24px 80px;
  }

  /* ─── Hero ─── */
  .hero {
    text-align: center;
    padding: 64px 0 40px;
    position: relative;
  }

  .hero-glow {
    position: absolute;
    top: 0; left: 50%;
    transform: translateX(-50%);
    width: 600px; height: 300px;
    background: radial-gradient(ellipse at center, rgba(0,229,255,0.12) 0%, transparent 70%);
    pointer-events: none;
  }

  .status-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: rgba(0,229,255,0.08);
    border: 1px solid rgba(0,229,255,0.2);
    border-radius: 999px;
    padding: 6px 16px;
    font-family: var(--font-mono);
    font-size: 12px;
    color: var(--cyan);
    margin-bottom: 28px;
    animation: fadeDown 0.6s ease both;
  }

  .status-dot {
    width: 7px; height: 7px;
    border-radius: 50%;
    background: var(--green);
    box-shadow: 0 0 8px var(--green);
    animation: pulse 2s infinite;
  }

  @keyframes pulse {
    0%,100% { opacity:1; transform:scale(1); }
    50% { opacity:0.5; transform:scale(1.3); }
  }

  .hero h1 {
    font-size: clamp(2rem, 5vw, 3.4rem);
    font-weight: 800;
    letter-spacing: -1px;
    line-height: 1.1;
    animation: fadeDown 0.7s 0.1s ease both;
  }

  .hero h1 span {
    background: linear-gradient(135deg, var(--cyan), var(--violet));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-sub {
    margin-top: 14px;
    font-family: var(--font-mono);
    font-size: 14px;
    color: var(--muted);
    animation: fadeDown 0.7s 0.2s ease both;
  }

  .hero-sub b { color: var(--cyan); font-weight: 400; }

  /* ─── Typing bar ─── */
  .typing-bar {
    margin: 28px auto 0;
    display: inline-block;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 10px 20px;
    font-family: var(--font-mono);
    font-size: 13px;
    color: var(--cyan);
    animation: fadeDown 0.7s 0.3s ease both;
    min-width: 320px;
    white-space: nowrap;
    overflow: hidden;
  }

  #typed-text::after {
    content: '▌';
    animation: blink 0.8s step-end infinite;
    margin-left: 2px;
    color: var(--violet);
  }

  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

  /* ─── Section headers ─── */
  .section {
    margin-top: 56px;
    animation: fadeUp 0.6s ease both;
  }

  .section-label {
    font-family: var(--font-mono);
    font-size: 11px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--cyan);
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(to right, var(--border), transparent);
  }

  /* ─── About card ─── */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }

  @media(max-width:600px){ .about-grid{ grid-template-columns:1fr; } }

  .about-item {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 14px 18px;
    font-size: 13.5px;
    display: flex;
    align-items: flex-start;
    gap: 10px;
    transition: border-color 0.2s, transform 0.2s;
  }

  .about-item:hover {
    border-color: rgba(0,229,255,0.3);
    transform: translateY(-2px);
  }

  .about-icon { font-size: 18px; flex-shrink: 0; margin-top: 1px; }
  .about-text { color: var(--muted); line-height: 1.5; }
  .about-text b { color: var(--text); font-weight: 600; }

  /* ─── Socials ─── */
  .social-row {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
  }

  .social-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 10px 18px;
    font-family: var(--font-mono);
    font-size: 12px;
    color: var(--text);
    text-decoration: none;
    transition: all 0.2s;
  }

  .social-btn:hover {
    border-color: var(--cyan);
    color: var(--cyan);
    transform: translateY(-2px);
    box-shadow: 0 4px 20px rgba(0,229,255,0.1);
  }

  .social-btn svg { width:16px; height:16px; }

  /* ─── Tech Stack ─── */
  .tech-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }

  .tech-pill {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 7px 14px;
    font-family: var(--font-mono);
    font-size: 12px;
    color: var(--muted);
    display: flex;
    align-items: center;
    gap: 6px;
    transition: all 0.2s;
  }

  .tech-pill:hover {
    color: var(--cyan);
    border-color: rgba(0,229,255,0.3);
  }

  .tech-pill .dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--cyan);
    opacity: 0.5;
  }

  /* ─── Stats ─── */
  .stats-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
  }

  .stat-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
    transition: border-color 0.2s;
  }

  .stat-card:hover { border-color: rgba(168,85,247,0.4); }

  .stat-card img {
    width: 100%;
    display: block;
    filter: brightness(0.95);
  }

  /* ─── Projects ─── */
  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 14px;
  }

  @media(max-width:700px){ .projects-grid{ grid-template-columns:1fr; } }

  .project-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px;
    text-decoration: none;
    display: block;
    transition: all 0.25s;
    position: relative;
    overflow: hidden;
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--cyan), var(--violet));
    opacity: 0;
    transition: opacity 0.2s;
  }

  .project-card:hover {
    border-color: rgba(0,229,255,0.25);
    transform: translateY(-3px);
    box-shadow: 0 8px 30px rgba(0,0,0,0.3);
  }

  .project-card:hover::before { opacity: 1; }

  .project-emoji { font-size: 22px; margin-bottom: 10px; }

  .project-name {
    font-size: 14px;
    font-weight: 600;
    color: var(--text);
    margin-bottom: 6px;
  }

  .project-desc {
    font-size: 12px;
    color: var(--muted);
    line-height: 1.5;
    margin-bottom: 12px;
    font-family: var(--font-mono);
  }

  .project-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 5px;
  }

  .tag {
    font-family: var(--font-mono);
    font-size: 10px;
    padding: 3px 8px;
    border-radius: 4px;
    background: rgba(0,229,255,0.07);
    color: var(--cyan);
    border: 1px solid rgba(0,229,255,0.15);
  }

  /* ─── Quote ─── */
  .quote-block {
    border-left: 2px solid var(--violet);
    padding: 16px 24px;
    background: rgba(168,85,247,0.05);
    border-radius: 0 10px 10px 0;
    font-family: var(--font-mono);
    font-size: 13px;
    color: var(--muted);
    font-style: italic;
  }

  .quote-block span { color: var(--text); }

  /* ─── Footer ─── */
  .footer {
    margin-top: 64px;
    text-align: center;
    font-family: var(--font-mono);
    font-size: 12px;
    color: var(--muted);
    border-top: 1px solid var(--border);
    padding-top: 28px;
  }

  .footer a { color: var(--cyan); text-decoration: none; }

  /* ─── Animations ─── */
  @keyframes fadeDown {
    from { opacity:0; transform:translateY(-16px); }
    to { opacity:1; transform:translateY(0); }
  }

  @keyframes fadeUp {
    from { opacity:0; transform:translateY(16px); }
    to { opacity:1; transform:translateY(0); }
  }

  .section:nth-child(2) { animation-delay: 0.1s; }
  .section:nth-child(3) { animation-delay: 0.2s; }
  .section:nth-child(4) { animation-delay: 0.3s; }
  .section:nth-child(5) { animation-delay: 0.4s; }
</style>
</head>
<body>
<div class="wrapper">

  <!-- HERO -->
  <div class="hero">
    <div class="hero-glow"></div>
    <div class="status-badge">
      <span class="status-dot"></span>
      Available for opportunities
    </div>
    <h1>Hi, I'm <span>Mohammad<br/>Hammad Ansari</span> 👋</h1>
    <p class="hero-sub">
      <b>Full Stack Developer</b> &nbsp;·&nbsp; Java · React · Node.js · MongoDB
    </p>
    <div class="typing-bar"><span id="typed-text"></span></div>
  </div>

  <!-- ABOUT -->
  <div class="section">
    <div class="section-label">// about me</div>
    <div class="about-grid">
      <div class="about-item">
        <span class="about-icon">🔭</span>
        <div class="about-text">Currently building <b>MERN Stack Projects</b></div>
      </div>
      <div class="about-item">
        <span class="about-icon">🌱</span>
        <div class="about-text">Learning <b>Next.js</b>, <b>TypeScript</b> &amp; <b>GraphQL</b></div>
      </div>
      <div class="about-item">
        <span class="about-icon">💬</span>
        <div class="about-text">Ask me about <b>Java, React, Node.js, APIs</b></div>
      </div>
      <div class="about-item">
        <span class="about-icon">⚡</span>
        <div class="about-text">I debug faster with <b>☕ + lo-fi music</b> 🎧</div>
      </div>
    </div>
  </div>

  <!-- SOCIALS -->
  <div class="section">
    <div class="section-label">// connect</div>
    <div class="social-row">
      <a href="https://linkedin.com/in/your-linkedin" class="social-btn" target="_blank">
        <svg fill="currentColor" viewBox="0 0 24 24"><path d="M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6zM2 9h4v12H2z"/><circle cx="4" cy="4" r="2"/></svg>
        LinkedIn
      </a>
      <a href="mailto:your.email@example.com" class="social-btn">
        <svg fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
        Email
      </a>
      <a href="https://twitter.com/your-twitter" class="social-btn" target="_blank">
        <svg fill="currentColor" viewBox="0 0 24 24"><path d="M23 3a10.9 10.9 0 01-3.14 1.53 4.48 4.48 0 00-7.86 3v1A10.66 10.66 0 013 4s-4 9 5 13a11.64 11.64 0 01-7 2c9 5 20 0 20-11.5a4.5 4.5 0 00-.08-.83A7.72 7.72 0 0023 3z"/></svg>
        Twitter
      </a>
      <a href="https://your-portfolio.com" class="social-btn" target="_blank">
        <svg fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><circle cx="12" cy="12" r="10"/><line x1="2" y1="12" x2="22" y2="12"/><path d="M12 2a15.3 15.3 0 014 10 15.3 15.3 0 01-4 10 15.3 15.3 0 01-4-10 15.3 15.3 0 014-10z"/></svg>
        Portfolio
      </a>
    </div>
  </div>

  <!-- TECH STACK -->
  <div class="section">
    <div class="section-label">// tech stack</div>
    <div class="tech-grid">
      <div class="tech-pill"><span class="dot"></span>HTML5</div>
      <div class="tech-pill"><span class="dot"></span>CSS3</div>
      <div class="tech-pill"><span class="dot"></span>JavaScript</div>
      <div class="tech-pill"><span class="dot"></span>TypeScript</div>
      <div class="tech-pill"><span class="dot"></span>React</div>
      <div class="tech-pill"><span class="dot"></span>Next.js</div>
      <div class="tech-pill"><span class="dot"></span>Node.js</div>
      <div class="tech-pill"><span class="dot"></span>Express</div>
      <div class="tech-pill"><span class="dot"></span>MongoDB</div>
      <div class="tech-pill"><span class="dot"></span>Java</div>
      <div class="tech-pill"><span class="dot"></span>Python</div>
      <div class="tech-pill"><span class="dot"></span>Tailwind</div>
      <div class="tech-pill"><span class="dot"></span>Git</div>
      <div class="tech-pill"><span class="dot"></span>Postman</div>
      <div class="tech-pill"><span class="dot"></span>Figma</div>
    </div>
  </div>

  <!-- GITHUB STATS -->
  <div class="section">
    <div class="section-label">// github analytics</div>
    <div class="stats-row">
      <div class="stat-card">
        <img src="https://github-readme-stats.vercel.app/api?username=hammad-scripted&show_icons=true&theme=tokyonight&hide_border=true&bg_color=141c2e" alt="GitHub Stats"/>
      </div>
      <div class="stat-card">
        <img src="https://github-readme-streak-stats.herokuapp.com/?user=hammad-scripted&theme=tokyonight&hide_border=true&background=141c2e" alt="Streak Stats"/>
      </div>
    </div>
  </div>

  <!-- PROJECTS -->
  <div class="section">
    <div class="section-label">// featured projects</div>
    <div class="projects-grid">
      <a class="project-card" href="https://github.com/hammad-scripted/portfolio" target="_blank">
        <div class="project-emoji">🌐</div>
        <div class="project-name">Portfolio Website</div>
        <div class="project-desc">Personal portfolio showcasing my work and skills</div>
        <div class="project-tags">
          <span class="tag">React</span>
          <span class="tag">Tailwind</span>
          <span class="tag">Vite</span>
        </div>
      </a>
      <a class="project-card" href="https://github.com/hammad-scripted/ecommerce-api" target="_blank">
        <div class="project-emoji">🛍️</div>
        <div class="project-name">E-Commerce API</div>
        <div class="project-desc">RESTful API backend for e-commerce platform</div>
        <div class="project-tags">
          <span class="tag">Node.js</span>
          <span class="tag">Express</span>
          <span class="tag">MongoDB</span>
        </div>
      </a>
      <a class="project-card" href="https://github.com/hammad-scripted/todo-app" target="_blank">
        <div class="project-emoji">✅</div>
        <div class="project-name">Task Manager</div>
        <div class="project-desc">Manage daily tasks in a clean, modern UI</div>
        <div class="project-tags">
          <span class="tag">React</span>
          <span class="tag">Tailwind</span>
        </div>
      </a>
    </div>
  </div>

  <!-- QUOTE -->
  <div class="section">
    <div class="section-label">// philosophy</div>
    <div class="quote-block">
      <span>"Code is like art — elegant, expressive, and built to last."</span>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <p>⭐ Enjoyed my work? <a href="https://github.com/hammad-scripted">Star my repos</a> — it means a lot!</p>
    <p style="margin-top:8px; opacity:0.4">hammad-scripted · GitHub Profile · 2025</p>
  </div>

</div>

<script>
  const lines = [
    "Full Stack Developer",
    "Java | React | Node.js | MongoDB",
    "Building modern web experiences",
    "Writing clean, scalable code"
  ];
  let li = 0, ci = 0, deleting = false;
  const el = document.getElementById('typed-text');

  function type() {
    const current = lines[li];
    if (!deleting) {
      el.textContent = current.slice(0, ++ci);
      if (ci === current.length) { deleting = true; setTimeout(type, 1800); return; }
    } else {
      el.textContent = current.slice(0, --ci);
      if (ci === 0) { deleting = false; li = (li + 1) % lines.length; }
    }
    setTimeout(type, deleting ? 40 : 80);
  }
  type();
</script>
</body>
</html>

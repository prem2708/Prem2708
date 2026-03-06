<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Prem Kumar — Full Stack Developer</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet"/>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #0a0a0f;
    --surface: #111118;
    --card: #16161f;
    --border: #1e1e2e;
    --accent: #7c3aed;
    --accent2: #06b6d4;
    --accent3: #f59e0b;
    --text: #e2e8f0;
    --muted: #64748b;
    --white: #ffffff;
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Syne', sans-serif;
    overflow-x: hidden;
    min-height: 100vh;
  }

  /* Animated background grid */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(124,58,237,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(124,58,237,0.04) 1px, transparent 1px);
    background-size: 60px 60px;
    pointer-events: none;
    z-index: 0;
  }

  /* Orb blobs */
  .orb {
    position: fixed;
    border-radius: 50%;
    filter: blur(100px);
    pointer-events: none;
    z-index: 0;
    animation: floatOrb 12s ease-in-out infinite;
  }
  .orb1 { width: 500px; height: 500px; background: rgba(124,58,237,0.12); top: -150px; right: -100px; animation-delay: 0s; }
  .orb2 { width: 400px; height: 400px; background: rgba(6,182,212,0.08); bottom: 100px; left: -150px; animation-delay: 4s; }
  .orb3 { width: 300px; height: 300px; background: rgba(245,158,11,0.06); top: 50%; left: 50%; animation-delay: 8s; }

  @keyframes floatOrb {
    0%, 100% { transform: translate(0, 0) scale(1); }
    33% { transform: translate(30px, -20px) scale(1.05); }
    66% { transform: translate(-20px, 30px) scale(0.95); }
  }

  /* Container */
  .container { max-width: 900px; margin: 0 auto; padding: 0 24px; position: relative; z-index: 1; }

  /* ---- HEADER ---- */
  header {
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 60px 24px;
    position: relative;
  }

  .header-inner { max-width: 700px; }

  .status-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: rgba(124,58,237,0.12);
    border: 1px solid rgba(124,58,237,0.3);
    color: #a78bfa;
    padding: 6px 16px;
    border-radius: 999px;
    font-family: 'Space Mono', monospace;
    font-size: 12px;
    letter-spacing: 0.08em;
    margin-bottom: 32px;
    animation: fadeSlideDown 0.6s ease both;
  }

  .status-dot {
    width: 7px; height: 7px;
    background: #22c55e;
    border-radius: 50%;
    animation: pulse 2s ease-in-out infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; transform: scale(1); box-shadow: 0 0 0 0 rgba(34,197,94,0.5); }
    50% { opacity: 0.8; transform: scale(1.2); box-shadow: 0 0 0 6px rgba(34,197,94,0); }
  }

  .greeting {
    font-size: clamp(14px, 2vw, 16px);
    font-family: 'Space Mono', monospace;
    color: var(--accent2);
    letter-spacing: 0.15em;
    text-transform: uppercase;
    margin-bottom: 12px;
    animation: fadeSlideDown 0.7s 0.1s ease both;
  }

  h1 {
    font-size: clamp(48px, 8vw, 88px);
    font-weight: 800;
    line-height: 0.95;
    letter-spacing: -0.03em;
    margin-bottom: 16px;
    animation: fadeSlideDown 0.7s 0.2s ease both;
  }

  h1 .first { color: var(--white); }
  h1 .last {
    background: linear-gradient(135deg, #7c3aed, #06b6d4);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .role-line {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 12px;
    margin-bottom: 28px;
    animation: fadeSlideDown 0.7s 0.3s ease both;
  }

  .role-sep { width: 40px; height: 1px; background: var(--border); }

  .role {
    font-family: 'Space Mono', monospace;
    font-size: 14px;
    color: var(--muted);
    letter-spacing: 0.1em;
  }

  .bio {
    font-size: clamp(15px, 2vw, 17px);
    color: #94a3b8;
    line-height: 1.7;
    max-width: 540px;
    margin: 0 auto 36px;
    animation: fadeSlideDown 0.7s 0.4s ease both;
  }

  .cta-row {
    display: flex;
    gap: 14px;
    justify-content: center;
    flex-wrap: wrap;
    animation: fadeSlideDown 0.7s 0.5s ease both;
  }

  .btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 12px 24px;
    border-radius: 8px;
    font-family: 'Syne', sans-serif;
    font-weight: 600;
    font-size: 14px;
    text-decoration: none;
    transition: all 0.25s ease;
    cursor: pointer;
  }

  .btn-primary {
    background: var(--accent);
    color: white;
    border: 1px solid transparent;
  }
  .btn-primary:hover {
    background: #6d28d9;
    transform: translateY(-2px);
    box-shadow: 0 12px 30px rgba(124,58,237,0.35);
  }

  .btn-outline {
    background: transparent;
    color: var(--text);
    border: 1px solid var(--border);
  }
  .btn-outline:hover {
    border-color: var(--accent2);
    color: var(--accent2);
    transform: translateY(-2px);
    box-shadow: 0 12px 30px rgba(6,182,212,0.12);
  }

  .scroll-hint {
    position: absolute;
    bottom: 40px;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
    color: var(--muted);
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    animation: fadeSlideDown 1s 1s ease both;
  }

  .scroll-line {
    width: 1px;
    height: 40px;
    background: linear-gradient(to bottom, transparent, var(--accent));
    animation: scrollLine 2s ease-in-out infinite;
  }

  @keyframes scrollLine {
    0% { transform: scaleY(0); transform-origin: top; }
    50% { transform: scaleY(1); transform-origin: top; }
    51% { transform: scaleY(1); transform-origin: bottom; }
    100% { transform: scaleY(0); transform-origin: bottom; }
  }

  /* ---- SECTIONS ---- */
  section { padding: 100px 0; position: relative; z-index: 1; }

  .section-label {
    display: flex;
    align-items: center;
    gap: 12px;
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--accent);
    letter-spacing: 0.2em;
    text-transform: uppercase;
    margin-bottom: 16px;
  }
  .section-label::after { content: ''; flex: 1; height: 1px; background: var(--border); }

  .section-title {
    font-size: clamp(28px, 4vw, 42px);
    font-weight: 800;
    letter-spacing: -0.02em;
    margin-bottom: 48px;
    color: var(--white);
  }

  /* ---- ABOUT ---- */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 24px;
  }

  @media (max-width: 640px) { .about-grid { grid-template-columns: 1fr; } }

  .about-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 28px;
    transition: border-color 0.3s, transform 0.3s;
  }
  .about-card:hover {
    border-color: rgba(124,58,237,0.4);
    transform: translateY(-4px);
  }

  .about-card .icon {
    font-size: 28px;
    margin-bottom: 14px;
  }

  .about-card h3 {
    font-size: 16px;
    font-weight: 700;
    color: var(--white);
    margin-bottom: 8px;
  }

  .about-card p {
    font-size: 14px;
    color: var(--muted);
    line-height: 1.6;
  }

  /* ---- SKILLS ---- */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 12px;
  }

  .skill-chip {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 14px 18px;
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 14px;
    font-weight: 600;
    transition: all 0.25s;
    cursor: default;
  }

  .skill-chip:hover {
    border-color: rgba(124,58,237,0.5);
    background: rgba(124,58,237,0.08);
    transform: translateY(-2px);
  }

  .skill-chip .dot {
    width: 8px; height: 8px;
    border-radius: 50%;
    flex-shrink: 0;
  }

  /* ---- PROJECTS ---- */
  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
  }

  @media (max-width: 640px) { .projects-grid { grid-template-columns: 1fr; } }

  .project-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 28px;
    text-decoration: none;
    color: inherit;
    transition: all 0.3s;
    display: flex;
    flex-direction: column;
    gap: 12px;
    position: relative;
    overflow: hidden;
  }

  .project-card::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, rgba(124,58,237,0.05), transparent 60%);
    opacity: 0;
    transition: opacity 0.3s;
  }

  .project-card:hover {
    border-color: rgba(124,58,237,0.4);
    transform: translateY(-5px);
    box-shadow: 0 20px 40px rgba(0,0,0,0.4);
  }

  .project-card:hover::before { opacity: 1; }

  .project-emoji { font-size: 28px; }

  .project-name {
    font-size: 17px;
    font-weight: 700;
    color: var(--white);
  }

  .project-desc {
    font-size: 13px;
    color: var(--muted);
    line-height: 1.6;
    flex: 1;
  }

  .project-link {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--accent2);
    letter-spacing: 0.08em;
    text-transform: uppercase;
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .arrow-icon {
    transition: transform 0.2s;
  }
  .project-card:hover .arrow-icon { transform: translate(3px, -3px); }

  .project-tag {
    display: inline-block;
    background: rgba(245,158,11,0.12);
    border: 1px solid rgba(245,158,11,0.3);
    color: #f59e0b;
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.08em;
    padding: 3px 10px;
    border-radius: 999px;
    width: fit-content;
  }

  /* ---- STATS ---- */
  .stats-row {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px;
    margin-bottom: 32px;
  }

  @media (max-width: 640px) { .stats-row { grid-template-columns: 1fr; } }

  .stat-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 28px 20px;
    text-align: center;
    transition: all 0.3s;
  }

  .stat-card:hover {
    border-color: rgba(6,182,212,0.4);
    transform: translateY(-4px);
  }

  .stat-value {
    font-size: 36px;
    font-weight: 800;
    color: var(--white);
    letter-spacing: -0.02em;
    margin-bottom: 4px;
  }

  .stat-label {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 0.1em;
    text-transform: uppercase;
  }

  .github-img-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  @media (max-width: 640px) { .github-img-row { grid-template-columns: 1fr; } }

  .github-img-row img {
    width: 100%;
    border-radius: 12px;
    border: 1px solid var(--border);
  }

  /* ---- CONTACT ---- */
  .contact-inner {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 24px;
    padding: 60px 40px;
    text-align: center;
    position: relative;
    overflow: hidden;
  }

  .contact-inner::before {
    content: '';
    position: absolute;
    top: -100px;
    left: 50%;
    transform: translateX(-50%);
    width: 400px;
    height: 200px;
    background: radial-gradient(ellipse, rgba(124,58,237,0.2), transparent 70%);
    pointer-events: none;
  }

  .contact-inner h2 {
    font-size: clamp(28px, 4vw, 42px);
    font-weight: 800;
    color: var(--white);
    letter-spacing: -0.02em;
    margin-bottom: 12px;
  }

  .contact-inner p {
    color: var(--muted);
    font-size: 16px;
    margin-bottom: 36px;
    max-width: 400px;
    margin-left: auto;
    margin-right: auto;
  }

  .contact-links {
    display: flex;
    gap: 12px;
    justify-content: center;
    flex-wrap: wrap;
  }

  /* ---- FOOTER ---- */
  footer {
    border-top: 1px solid var(--border);
    padding: 32px 0;
    text-align: center;
    color: var(--muted);
    font-family: 'Space Mono', monospace;
    font-size: 12px;
    position: relative;
    z-index: 1;
  }

  footer span { color: #f43f5e; }

  /* ---- ANIMATIONS ---- */
  @keyframes fadeSlideDown {
    from { opacity: 0; transform: translateY(-20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .reveal {
    opacity: 0;
    transform: translateY(30px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }
  .reveal.visible {
    opacity: 1;
    transform: translateY(0);
  }

  /* ---- QUOTE ---- */
  .quote-section {
    padding: 60px 0;
    position: relative;
    z-index: 1;
  }

  .quote-inner {
    border-left: 3px solid var(--accent);
    padding: 24px 32px;
    background: rgba(124,58,237,0.05);
    border-radius: 0 12px 12px 0;
  }

  .quote-text {
    font-size: clamp(18px, 2.5vw, 24px);
    font-weight: 700;
    color: var(--white);
    margin-bottom: 8px;
    font-style: italic;
  }

  .quote-author {
    font-family: 'Space Mono', monospace;
    font-size: 12px;
    color: var(--accent2);
    letter-spacing: 0.1em;
  }

  /* Scrollbar */
  ::-webkit-scrollbar { width: 6px; }
  ::-webkit-scrollbar-track { background: var(--bg); }
  ::-webkit-scrollbar-thumb { background: var(--border); border-radius: 3px; }
  ::-webkit-scrollbar-thumb:hover { background: var(--accent); }

</style>
</head>
<body>

<!-- Background orbs -->
<div class="orb orb1"></div>
<div class="orb orb2"></div>
<div class="orb orb3"></div>

<!-- ===== HEADER ===== -->
<header>
  <div class="header-inner">
    <div class="status-badge">
      <span class="status-dot"></span>
      Available for collaboration
    </div>
    <p class="greeting">👋 Hey there, I'm</p>
    <h1>
      <span class="first">Prem</span><br>
      <span class="last">Kumar</span>
    </h1>
    <div class="role-line">
      <span class="role-sep"></span>
      <span class="role">Full Stack Developer · AI Enthusiast · Open Source</span>
      <span class="role-sep"></span>
    </div>
    <p class="bio">
      Passionate about building scalable web apps, AI-powered tools, and open source solutions. Always learning, always shipping.
    </p>
    <div class="cta-row">
      <a href="https://portfoliobyprem.netlify.app/" target="_blank" class="btn btn-primary">
        🌐 View Portfolio
      </a>
      <a href="mailto:preminnovator2708@gmail.com" class="btn btn-outline">
        ✉️ Get in Touch
      </a>
      <a href="https://github.com/prem2708" target="_blank" class="btn btn-outline">
        <svg width="16" height="16" fill="currentColor" viewBox="0 0 24 24"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg>
        GitHub
      </a>
    </div>
  </div>
  <div class="scroll-hint">
    <span>Scroll</span>
    <div class="scroll-line"></div>
  </div>
</header>

<!-- ===== ABOUT ===== -->
<section id="about">
  <div class="container">
    <div class="section-label">01 // About</div>
    <h2 class="section-title">Who am I?</h2>
    <div class="about-grid reveal">
      <div class="about-card">
        <div class="icon">🚀</div>
        <h3>Builder at Heart</h3>
        <p>I build full-stack web applications, AI-powered tools, and automation systems. From concept to deployment — I love seeing ideas come to life.</p>
      </div>
      <div class="about-card">
        <div class="icon">🤖</div>
        <h3>AI & Automation</h3>
        <p>Deeply fascinated by AI, machine learning, and how they can be harnessed to solve real-world problems and create delightful user experiences.</p>
      </div>
      <div class="about-card">
        <div class="icon">☁️</div>
        <h3>Cloud & DevOps</h3>
        <p>Currently focused on cloud deployments and scalable infrastructure using Docker, Vercel, Railway, and Netlify.</p>
      </div>
      <div class="about-card">
        <div class="icon">🌱</div>
        <h3>Lifelong Learner</h3>
        <p>Growth mindset drives everything I do. I explore new technologies daily, contribute to open source, and share knowledge with the community.</p>
      </div>
    </div>
  </div>
</section>

<!-- ===== TECH STACK ===== -->
<section id="skills">
  <div class="container">
    <div class="section-label">02 // Stack</div>
    <h2 class="section-title">Tech Stack</h2>
    <div class="skills-grid reveal">
      <!-- Frontend -->
      <div class="skill-chip"><span class="dot" style="background:#f7df1e"></span> JavaScript</div>
      <div class="skill-chip"><span class="dot" style="background:#3178c6"></span> TypeScript</div>
      <div class="skill-chip"><span class="dot" style="background:#61dafb"></span> React</div>
      <div class="skill-chip"><span class="dot" style="background:#e34f26"></span> HTML5</div>
      <div class="skill-chip"><span class="dot" style="background:#1572b6"></span> CSS3</div>
      <!-- Backend -->
      <div class="skill-chip"><span class="dot" style="background:#68a063"></span> Node.js</div>
      <div class="skill-chip"><span class="dot" style="background:#000"></span> Express</div>
      <div class="skill-chip"><span class="dot" style="background:#3776ab"></span> Python</div>
      <div class="skill-chip"><span class="dot" style="background:#092e20"></span> Django</div>
      <div class="skill-chip"><span class="dot" style="background:#f89820"></span> Java</div>
      <!-- DevOps & Tools -->
      <div class="skill-chip"><span class="dot" style="background:#2496ed"></span> Docker</div>
      <div class="skill-chip"><span class="dot" style="background:#f05032"></span> Git</div>
      <div class="skill-chip"><span class="dot" style="background:#00c7b7"></span> Netlify</div>
      <div class="skill-chip"><span class="dot" style="background:#000"></span> Vercel</div>
      <div class="skill-chip"><span class="dot" style="background:#0066ff"></span> Railway</div>
      <div class="skill-chip"><span class="dot" style="background:#00add8"></span> C++</div>
    </div>
  </div>
</section>

<!-- ===== PROJECTS ===== -->
<section id="projects">
  <div class="container">
    <div class="section-label">03 // Work</div>
    <h2 class="section-title">Featured Projects</h2>
    <div class="projects-grid reveal">

      <a href="https://github.com/prem2708/Ai_image_generator_tool" target="_blank" class="project-card">
        <div class="project-emoji">🖼️</div>
        <div class="project-name">AI Image Generator</div>
        <div class="project-desc">Instantly create unique images with the power of AI. Simple, fast, and perfect for experimenting with generative art.</div>
        <div class="project-link">View on GitHub <span class="arrow-icon">↗</span></div>
      </a>

      <a href="https://github.com/prem2708/AI_DOCTOR" target="_blank" class="project-card">
        <div class="project-emoji">🩺</div>
        <div class="project-name">AI Doctor</div>
        <div class="project-desc">A smart AI-powered health assistant that provides preliminary medical advice based on user symptoms.</div>
        <div class="project-link">View on GitHub <span class="arrow-icon">↗</span></div>
      </a>

      <a href="https://github.com/prem2708/aibot-musebot-byvoxnova" target="_blank" class="project-card">
        <div class="project-emoji">🤖</div>
        <div class="project-name">Musebot by VoxNova</div>
        <div class="project-desc">An intelligent chat and music bot combining conversational AI with music discovery for a unique interactive experience.</div>
        <div class="project-link">View on GitHub <span class="arrow-icon">↗</span></div>
      </a>

      <a href="https://github.com/prem2708/AI-resume-builder" target="_blank" class="project-card">
        <div class="project-emoji">📄</div>
        <div class="project-name">AI Resume Builder</div>
        <div class="project-desc">Effortlessly generate professional resumes powered by AI. Customize, preview, and download your CV in minutes.</div>
        <div class="project-link">View on GitHub <span class="arrow-icon">↗</span></div>
      </a>

      <a href="https://github.com/prem2708/Portfolio" target="_blank" class="project-card">
        <div class="project-emoji">🌐</div>
        <div class="project-name">Portfolio</div>
        <div class="project-desc">My personal portfolio showcasing projects, skills, and achievements — built to highlight my journey and connect with the tech community.</div>
        <div class="project-link">View on GitHub <span class="arrow-icon">↗</span></div>
      </a>

      <a href="https://github.com/prem2708/yoga_and_asan_website-" target="_blank" class="project-card">
        <div class="project-emoji">🧘</div>
        <div class="project-name">Yoga & Asana</div>
        <div class="project-desc">A comprehensive platform to explore yoga postures, asanas, and their health benefits with a clean, intuitive interface.</div>
        <div class="project-link">View on GitHub <span class="arrow-icon">↗</span></div>
      </a>

      <a href="https://github.com/prem2708/AI-Powered-Study-Buddy" target="_blank" class="project-card">
        <div class="project-emoji">📚</div>
        <div class="project-name">AI-Powered Study Buddy</div>
        <div class="project-desc">An intelligent study companion powered by AI that helps students learn faster, revise smarter, and stay on top of their academics.</div>
        <div class="project-tag">✨ New</div>
        <div class="project-link">View on GitHub <span class="arrow-icon">↗</span></div>
      </a>

      <a href="https://github.com/prem2708/prem_new_portfolio" target="_blank" class="project-card">
        <div class="project-emoji">💼</div>
        <div class="project-name">New Portfolio v2</div>
        <div class="project-desc">The latest iteration of my personal portfolio — redesigned from the ground up with a fresh look, smoother animations, and updated projects.</div>
        <div class="project-tag">✨ New</div>
        <div class="project-link">View on GitHub <span class="arrow-icon">↗</span></div>
      </a>

      <a href="https://github.com/prem2708/Lecture_notes_generator" target="_blank" class="project-card">
        <div class="project-emoji">📝</div>
        <div class="project-name">Lecture Notes Generator</div>
        <div class="project-desc">Automatically generate clean, structured lecture notes from audio or text input using AI — making studying more efficient than ever.</div>
        <div class="project-tag">✨ New</div>
        <div class="project-link">View on GitHub <span class="arrow-icon">↗</span></div>
      </a>

      <a href="https://github.com/prem2708/Hackthon_website" target="_blank" class="project-card">
        <div class="project-emoji">⚡</div>
        <div class="project-name">Hackathon Website</div>
        <div class="project-desc">A dynamic hackathon event website — built fast, deployed fast. Complete with registration, schedules, and team management features.</div>
        <div class="project-tag">✨ New</div>
        <div class="project-link">View on GitHub <span class="arrow-icon">↗</span></div>
      </a>

    </div>
  </div>
</section>

<!-- ===== STATS ===== -->
<section id="stats">
  <div class="container">
    <div class="section-label">04 // Metrics</div>
    <h2 class="section-title">GitHub Stats</h2>
    <div class="stats-row reveal">
      <div class="stat-card">
        <div class="stat-value" data-target="10">0</div>
        <div class="stat-label">Repositories</div>
      </div>
      <div class="stat-card">
        <div class="stat-value" data-target="5">0</div>
        <div class="stat-label">Languages</div>
      </div>
      <div class="stat-card">
        <div class="stat-value" data-target="100">0</div>
        <div class="stat-label">Commits +</div>
      </div>
    </div>
    <div class="github-img-row reveal">
      <img src="https://github-readme-stats.vercel.app/api?username=prem2708&show_icons=true&theme=radical&hide_border=true&bg_color=16161f" alt="Prem's GitHub Stats" loading="lazy" />
      <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=prem2708&layout=compact&theme=radical&hide_border=true&bg_color=16161f" alt="Top Languages" loading="lazy" />
    </div>
  </div>
</section>

<!-- ===== QUOTE ===== -->
<div class="quote-section">
  <div class="container reveal">
    <div class="quote-inner">
      <p class="quote-text">"Code is like humor. When you have to explain it, it's bad."</p>
      <p class="quote-author">— Cory House</p>
    </div>
  </div>
</div>

<!-- ===== CONTACT ===== -->
<section id="contact">
  <div class="container reveal">
    <div class="contact-inner">
      <h2>Let's Build Together</h2>
      <p>Have an exciting project or just want to say hi? My inbox is always open.</p>
      <div class="contact-links">
        <a href="mailto:preminnovator2708@gmail.com" class="btn btn-primary">✉️ Email Me</a>
        <a href="https://portfoliobyprem.netlify.app/" target="_blank" class="btn btn-outline">🌐 Portfolio</a>
        <a href="https://linktr.ee/premkumar2708" target="_blank" class="btn btn-outline">🔗 Linktree</a>
        <a href="https://github.com/prem2708" target="_blank" class="btn btn-outline">
          <svg width="14" height="14" fill="currentColor" viewBox="0 0 24 24"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg>
          GitHub
        </a>
      </div>
    </div>
  </div>
</section>

<!-- ===== FOOTER ===== -->
<footer>
  <div class="container">
    Built with <span>♥</span> by Prem Kumar · 2025 · <a href="https://github.com/prem2708" style="color:var(--accent2);text-decoration:none;">@prem2708</a>
  </div>
</footer>

<script>
  // Scroll reveal
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
      if (entry.isIntersecting) {
        setTimeout(() => entry.target.classList.add('visible'), i * 80);
      }
    });
  }, { threshold: 0.1 });
  reveals.forEach(el => observer.observe(el));

  // Counter animation
  function animateCounter(el, target, duration = 1500) {
    let start = 0;
    const step = target / (duration / 16);
    const timer = setInterval(() => {
      start += step;
      if (start >= target) { start = target; clearInterval(timer); }
      el.textContent = Math.floor(start) + (target >= 100 ? '+' : '');
    }, 16);
  }

  const statsObserver = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        document.querySelectorAll('[data-target]').forEach(el => {
          animateCounter(el, parseInt(el.dataset.target));
        });
        statsObserver.disconnect();
      }
    });
  }, { threshold: 0.3 });

  const statsSection = document.querySelector('#stats');
  if (statsSection) statsObserver.observe(statsSection);
</script>
</body>
</html>

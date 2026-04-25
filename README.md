# Portfolio
<!index.html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Motion Designer Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700;800&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }
  :root {
    --bg: #090909; --bg2: #111111; --card: #141414;
    --border: rgba(255,255,255,0.07); --border2: rgba(255,255,255,0.13);
    --text: #f0ede8; --muted: #888580;
    --accent: #D4F45A; --accent2: #B8E040;
    --accent-dim: rgba(212,244,90,0.12);
  }
  html { scroll-behavior: smooth; }
  body { background: var(--bg); color: var(--text); font-family: 'DM Sans', sans-serif; font-size: 16px; line-height: 1.7; overflow-x: hidden; }

  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 1.25rem 5%;
    background: rgba(9,9,9,0.88); backdrop-filter: blur(18px);
    border-bottom: 1px solid var(--border);
  }
  .logo { font-family: 'Syne', sans-serif; font-weight: 800; font-size: 1.2rem; letter-spacing: -0.02em; color: var(--text); text-decoration: none; }
  .logo span { color: var(--accent); }
  nav ul { display: flex; gap: 2.5rem; list-style: none; }
  nav ul a { text-decoration: none; color: var(--muted); font-size: 0.88rem; font-weight: 400; transition: color 0.2s; }
  nav ul a:hover { color: var(--text); }
  .nav-cta { background: var(--accent); color: #090909 !important; padding: 0.5rem 1.25rem; border-radius: 100px; font-weight: 500 !important; }
  .nav-cta:hover { background: var(--accent2) !important; }

  .hero {
    min-height: 100vh; display: flex; flex-direction: column; justify-content: center;
    padding: 8rem 5% 5rem; position: relative; overflow: hidden;
  }
  .hero-grid-bg {
    position: absolute; inset: 0;
    background-image: linear-gradient(rgba(255,255,255,0.025) 1px, transparent 1px), linear-gradient(90deg, rgba(255,255,255,0.025) 1px, transparent 1px);
    background-size: 60px 60px;
    mask-image: radial-gradient(ellipse 80% 60% at 50% 40%, black 30%, transparent 100%);
  }
  .hero-glow {
    position: absolute; top: 20%; left: 50%; transform: translateX(-50%);
    width: 700px; height: 400px;
    background: radial-gradient(ellipse, rgba(212,244,90,0.08) 0%, transparent 70%);
    pointer-events: none;
  }
  .hero-tag {
    display: inline-flex; align-items: center; gap: 0.5rem;
    background: var(--accent-dim); border: 1px solid rgba(212,244,90,0.25);
    color: var(--accent); font-size: 0.8rem; font-weight: 500;
    padding: 0.35rem 0.9rem; border-radius: 100px; margin-bottom: 2rem; width: fit-content;
    animation: fadeUp 0.8s ease both;
  }
  .hero-tag::before { content: ''; width: 6px; height: 6px; border-radius: 50%; background: var(--accent); animation: pulse 2s infinite; }
  @keyframes pulse { 0%, 100% { opacity: 1; } 50% { opacity: 0.4; } }
  .hero h1 { font-family: 'Syne', sans-serif; font-weight: 800; font-size: clamp(3rem, 7vw, 6.5rem); line-height: 1.0; letter-spacing: -0.03em; max-width: 900px; animation: fadeUp 0.8s 0.1s ease both; }
  .hero h1 em { font-style: normal; color: var(--accent); }
  .hero p { font-size: 1.1rem; color: var(--muted); max-width: 520px; margin-top: 1.5rem; font-weight: 300; animation: fadeUp 0.8s 0.2s ease both; }
  .hero-actions { display: flex; gap: 1rem; margin-top: 2.5rem; animation: fadeUp 0.8s 0.3s ease both; }
  .btn-primary { background: var(--accent); color: #090909; border: none; padding: 0.85rem 2rem; border-radius: 100px; font-family: 'DM Sans', sans-serif; font-size: 0.95rem; font-weight: 500; cursor: pointer; text-decoration: none; display: inline-block; transition: background 0.2s, transform 0.15s; }
  .btn-primary:hover { background: var(--accent2); transform: translateY(-1px); }
  .btn-secondary { background: transparent; color: var(--text); border: 1px solid var(--border2); padding: 0.85rem 2rem; border-radius: 100px; font-family: 'DM Sans', sans-serif; font-size: 0.95rem; font-weight: 400; cursor: pointer; text-decoration: none; display: inline-block; transition: border-color 0.2s, transform 0.15s; }
  .btn-secondary:hover { border-color: rgba(255,255,255,0.35); transform: translateY(-1px); }
  .hero-stats { display: flex; gap: 3rem; margin-top: 5rem; padding-top: 2.5rem; border-top: 1px solid var(--border); animation: fadeUp 0.8s 0.4s ease both; }
  .stat-num { font-family: 'Syne', sans-serif; font-size: 2rem; font-weight: 700; }
  .stat-num span { color: var(--accent); }
  .stat-label { font-size: 0.82rem; color: var(--muted); margin-top: 0.15rem; }
  @keyframes fadeUp { from { opacity: 0; transform: translateY(28px); } to { opacity: 1; transform: translateY(0); } }

  section { padding: 7rem 5%; }
  .section-label { font-size: 0.75rem; font-weight: 500; letter-spacing: 0.15em; text-transform: uppercase; color: var(--accent); margin-bottom: 1rem; }
  .section-title { font-family: 'Syne', sans-serif; font-weight: 700; font-size: clamp(2rem, 4vw, 3.2rem); line-height: 1.1; letter-spacing: -0.02em; max-width: 600px; }

  .skills-section { background: var(--bg2); }
  .skills-inner { display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; align-items: center; }
  .skills-text p { color: var(--muted); margin-top: 1.25rem; font-size: 1.05rem; font-weight: 300; }
  .skills-cards { display: flex; flex-direction: column; gap: 1rem; }
  .skill-card { background: var(--card); border: 1px solid var(--border); border-radius: 16px; padding: 1.5rem; display: flex; align-items: center; gap: 1.25rem; transition: border-color 0.3s, transform 0.3s; }
  .skill-card:hover { border-color: rgba(212,244,90,0.3); transform: translateX(6px); }
  .skill-icon { width: 48px; height: 48px; border-radius: 12px; background: var(--accent-dim); border: 1px solid rgba(212,244,90,0.2); display: flex; align-items: center; justify-content: center; font-size: 1.3rem; flex-shrink: 0; }
  .skill-name { font-family: 'Syne', sans-serif; font-weight: 600; font-size: 1rem; margin-bottom: 0.2rem; }
  .skill-desc { font-size: 0.83rem; color: var(--muted); font-weight: 300; }

  .works-header { display: flex; justify-content: space-between; align-items: flex-end; margin-bottom: 3rem; }
  .works-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 1.5rem; }
  .work-card { background: var(--card); border: 1px solid var(--border); border-radius: 20px; overflow: hidden; transition: border-color 0.3s, transform 0.3s; }
  .work-card:hover { border-color: rgba(212,244,90,0.25); transform: translateY(-4px); }

  /* Video thumbnail */
  .work-thumb { position: relative; width: 100%; padding-top: 56.25%; background: #000; overflow: hidden; }
  .work-thumb.vertical { padding-top: 75%; }
  .work-thumb iframe { position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: none; pointer-events: none; }
  .thumb-overlay { position: absolute; inset: 0; display: flex; align-items: center; justify-content: center; background: rgba(0,0,0,0.35); cursor: pointer; z-index: 2; transition: background 0.3s; }
  .work-card:hover .thumb-overlay { background: rgba(0,0,0,0.15); }
  .play-btn { width: 58px; height: 58px; border-radius: 50%; background: rgba(9,9,9,0.8); border: 1.5px solid rgba(255,255,255,0.25); display: flex; align-items: center; justify-content: center; backdrop-filter: blur(8px); transition: background 0.2s, transform 0.2s; }
  .work-card:hover .play-btn { background: var(--accent); transform: scale(1.08); }
  .work-card:hover .play-btn svg path { fill: #090909; }
  .work-thumb.playing .thumb-overlay { display: none; }
  .work-thumb.playing iframe { pointer-events: all; }

  .work-info { padding: 1.25rem 1.5rem 1.5rem; }
  .work-tag { display: inline-block; font-size: 0.72rem; font-weight: 500; letter-spacing: 0.08em; text-transform: uppercase; color: var(--accent); background: var(--accent-dim); border-radius: 100px; padding: 0.25rem 0.7rem; margin-bottom: 0.6rem; }
  .work-title { font-family: 'Syne', sans-serif; font-weight: 600; font-size: 1.1rem; }
  .work-meta { font-size: 0.82rem; color: var(--muted); margin-top: 0.3rem; }

  .reviews-section { background: var(--bg2); }
  .reviews-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.25rem; margin-top: 3rem; }
  .review-card { background: var(--card); border: 1px solid var(--border); border-radius: 18px; padding: 1.75rem; transition: border-color 0.3s; }
  .review-card:hover { border-color: var(--border2); }
  .stars { color: var(--accent); font-size: 0.9rem; margin-bottom: 1rem; letter-spacing: 2px; }
  .review-text { font-size: 0.92rem; color: var(--muted); font-weight: 300; line-height: 1.8; font-style: italic; margin-bottom: 1.5rem; }
  .reviewer { display: flex; align-items: center; gap: 0.75rem; }
  .reviewer-avatar { width: 38px; height: 38px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-family: 'Syne', sans-serif; font-weight: 700; font-size: 0.85rem; color: #090909; background: var(--accent); flex-shrink: 0; }
  .reviewer-name { font-family: 'Syne', sans-serif; font-size: 0.9rem; font-weight: 600; }
  .reviewer-role { font-size: 0.78rem; color: var(--muted); }

  .pricing-section { background: var(--bg); }
  .pricing-subtitle { color: var(--muted); margin-top: 1rem; font-size: 1rem; font-weight: 300; }
  .pricing-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.25rem; margin-top: 3rem; }
  .pricing-card { background: var(--card); border: 1px solid var(--border); border-radius: 22px; padding: 2.25rem 2rem; position: relative; transition: border-color 0.3s, transform 0.3s; display: flex; flex-direction: column; }
  .pricing-card:hover { transform: translateY(-4px); }
  .pricing-card.featured { border-color: rgba(212,244,90,0.35); background: linear-gradient(160deg, #161f00 0%, #111600 100%); }
  .featured-badge { position: absolute; top: -14px; left: 50%; transform: translateX(-50%); background: var(--accent); color: #090909; font-size: 0.72rem; font-weight: 700; letter-spacing: 0.08em; text-transform: uppercase; padding: 0.3rem 1rem; border-radius: 100px; white-space: nowrap; }
  .plan-name { font-family: 'Syne', sans-serif; font-weight: 700; font-size: 1.1rem; margin-bottom: 0.5rem; }
  .plan-tagline { font-size: 0.82rem; color: var(--muted); margin-bottom: 1.75rem; font-weight: 300; }
  .plan-price { font-family: 'Syne', sans-serif; font-size: 3.5rem; font-weight: 800; line-height: 1; letter-spacing: -0.03em; margin-bottom: 0.3rem; }
  .plan-price span { font-size: 1.5rem; font-weight: 500; vertical-align: super; color: var(--muted); }
  .plan-duration { font-size: 0.8rem; color: var(--muted); margin-bottom: 2rem; padding-bottom: 1.75rem; border-bottom: 1px solid var(--border); }
  .plan-features { list-style: none; flex: 1; }
  .plan-features li { font-size: 0.88rem; color: var(--muted); padding: 0.55rem 0; display: flex; align-items: center; gap: 0.75rem; border-bottom: 1px solid var(--border); font-weight: 300; }
  .plan-features li:last-child { border-bottom: none; }
  .check { width: 18px; height: 18px; border-radius: 50%; background: var(--accent-dim); border: 1px solid rgba(212,244,90,0.25); display: flex; align-items: center; justify-content: center; flex-shrink: 0; font-size: 0.65rem; color: var(--accent); }
  .plan-cta { margin-top: 2rem; display: block; text-align: center; padding: 0.85rem; border-radius: 100px; font-size: 0.9rem; font-weight: 500; font-family: 'DM Sans', sans-serif; cursor: pointer; text-decoration: none; transition: all 0.2s; }
  .plan-cta-outline { border: 1px solid var(--border2); color: var(--text); background: transparent; }
  .plan-cta-outline:hover { border-color: rgba(255,255,255,0.35); }
  .plan-cta-filled { background: var(--accent); color: #090909; border: none; }
  .plan-cta-filled:hover { background: var(--accent2); }

  .contact-section { background: var(--bg2); }
  .contact-inner { display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; align-items: start; }
  .contact-left p { color: var(--muted); margin-top: 1.25rem; font-size: 1.05rem; font-weight: 300; margin-bottom: 2rem; }
  .contact-links { display: flex; flex-direction: column; gap: 1rem; }
  .contact-link { display: flex; align-items: center; gap: 1rem; text-decoration: none; color: var(--text); background: var(--card); border: 1px solid var(--border); border-radius: 14px; padding: 1rem 1.25rem; transition: border-color 0.3s, transform 0.2s; }
  .contact-link:hover { border-color: rgba(212,244,90,0.3); transform: translateX(5px); }
  .contact-link-icon { width: 40px; height: 40px; border-radius: 10px; background: var(--accent-dim); border: 1px solid rgba(212,244,90,0.2); display: flex; align-items: center; justify-content: center; font-size: 1rem; flex-shrink: 0; }
  .contact-link-info strong { display: block; font-weight: 500; margin-bottom: 0.1rem; font-size: 0.85rem; font-family: 'Syne', sans-serif; }
  .contact-link-info span { font-size: 0.8rem; color: var(--muted); }
  .contact-form { display: flex; flex-direction: column; gap: 1rem; }
  .form-group { display: flex; flex-direction: column; gap: 0.4rem; }
  .form-label { font-size: 0.8rem; color: var(--muted); font-weight: 400; }
  .form-input, .form-textarea { background: var(--card); border: 1px solid var(--border); color: var(--text); border-radius: 12px; padding: 0.85rem 1.1rem; font-family: 'DM Sans', sans-serif; font-size: 0.92rem; font-weight: 300; outline: none; transition: border-color 0.2s; resize: none; }
  .form-input::placeholder, .form-textarea::placeholder { color: var(--muted); }
  .form-input:focus, .form-textarea:focus { border-color: rgba(212,244,90,0.4); }
  .form-textarea { height: 130px; }
  .form-submit { background: var(--accent); color: #090909; border: none; padding: 0.9rem 2rem; border-radius: 100px; font-family: 'DM Sans', sans-serif; font-size: 0.95rem; font-weight: 500; cursor: pointer; transition: background 0.2s; margin-top: 0.5rem; }
  .form-submit:hover { background: var(--accent2); }

  footer { background: var(--bg); border-top: 1px solid var(--border); padding: 2rem 5%; display: flex; justify-content: space-between; align-items: center; }
  footer p { font-size: 0.82rem; color: var(--muted); }

  .reveal { opacity: 0; transform: translateY(30px); transition: opacity 0.7s ease, transform 0.7s ease; }
  .reveal.visible { opacity: 1; transform: none; }
  ::-webkit-scrollbar { width: 6px; }
  ::-webkit-scrollbar-track { background: var(--bg); }
  ::-webkit-scrollbar-thumb { background: #2a2a2a; border-radius: 3px; }
</style>
</head>
<body>

<nav>
  <a href="#" class="logo">Aryan<span>.</span></a>
  <ul>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#works">Work</a></li>
    <li><a href="#reviews">Reviews</a></li>
    <li><a href="#pricing">Pricing</a></li>
    <li><a href="#contact" class="nav-cta">Hire Me</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero" id="home">
  <div class="hero-grid-bg"></div>
  <div class="hero-glow"></div>
  <div class="hero-tag">Available for freelance work</div>
  <h1>I turn <em>complex SaaS</em><br>into clean motion.</h1>
  <p>Motion designer specializing in SaaS explanation videos, app walkthroughs, and talking head content that converts viewers into customers.</p>
  <div class="hero-actions">
    <a href="#works" class="btn-primary">View My Work</a>
    <a href="#pricing" class="btn-secondary">See Pricing →</a>
  </div>
  <div class="hero-stats">
    <div><div class="stat-num">50<span>+</span></div><div class="stat-label">Projects Delivered</div></div>
    <div><div class="stat-num">30<span>+</span></div><div class="stat-label">Happy Clients</div></div>
    <div><div class="stat-num">3<span>yr</span></div><div class="stat-label">Experience</div></div>
  </div>
</section>

<!-- SKILLS -->
<section class="skills-section" id="skills">
  <div class="skills-inner">
    <div class="skills-text reveal">
      <div class="section-label">What I Do</div>
      <h2 class="section-title">Crafted motion for the digital product era.</h2>
      <p>I specialize in breaking down complex software into visually engaging stories — turning features into feelings, and walkthroughs into conversions.</p>
      <br>
      <p>Every frame is intentional. Every transition earns its place. I design motion that makes your product <em>feel</em> inevitable.</p>
    </div>
    <div class="skills-cards reveal">
      <div class="skill-card">
        <div class="skill-icon">✦</div>
        <div>
          <div class="skill-name">Motion Graphics</div>
          <div class="skill-desc">Dynamic animated visuals, kinetic typography, logo reveals & brand motion</div>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-icon">◈</div>
        <div>
          <div class="skill-name">Talking Head Videos</div>
          <div class="skill-desc">Polished talking head edits with motion overlays, captions & B-roll</div>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-icon">⬡</div>
        <div>
          <div class="skill-name">SaaS / App Explanations</div>
          <div class="skill-desc">Product walkthroughs, feature explainers & onboarding animations that convert</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- WORKS -->
<section id="works">
  <div class="works-header reveal">
    <div>
      <div class="section-label">Portfolio</div>
      <h2 class="section-title">Selected Work</h2>
    </div>
    <a href="#contact" class="btn-secondary">Work With Me →</a>
  </div>

  <div class="works-grid">

    <!-- Card 1: YouTube Short gLR-Wagfm6M -->
    <div class="work-card reveal">
      <div class="work-thumb vertical" id="thumb-1">
        <iframe src="<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Motion Designer Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700;800&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

  :root {
    --bg: #090909;
    --bg2: #111111;
    --bg3: #161616;
    --card: #141414;
    --border: rgba(255,255,255,0.07);
    --border2: rgba(255,255,255,0.13);
    --text: #f0ede8;
    --muted: #888580;
    --accent: #D4F45A;
    --accent2: #B8E040;
    --accent-dim: rgba(212,244,90,0.12);
    --accent-glow: rgba(212,244,90,0.06);
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    font-size: 16px;
    line-height: 1.7;
    overflow-x: hidden;
  }

  /* NAV */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 1.25rem 5%;
    background: rgba(9,9,9,0.88);
    backdrop-filter: blur(18px);
    border-bottom: 1px solid var(--border);
  }

  .logo {
    font-family: 'Syne', sans-serif;
    font-weight: 800;
    font-size: 1.2rem;
    letter-spacing: -0.02em;
    color: var(--text);
    text-decoration: none;
  }

  .logo span { color: var(--accent); }

  nav ul {
    display: flex;
    gap: 2.5rem;
    list-style: none;
  }

  nav ul a {
    text-decoration: none;
    color: var(--muted);
    font-size: 0.88rem;
    font-weight: 400;
    letter-spacing: 0.02em;
    transition: color 0.2s;
  }

  nav ul a:hover { color: var(--text); }

  .nav-cta {
    background: var(--accent);
    color: #090909 !important;
    padding: 0.5rem 1.25rem;
    border-radius: 100px;
    font-weight: 500 !important;
    transition: background 0.2s !important;
  }

  .nav-cta:hover { background: var(--accent2) !important; color: #090909 !important; }

  /* HERO */
  .hero {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 8rem 5% 5rem;
    position: relative;
    overflow: hidden;
  }

  .hero-grid-bg {
    position: absolute;
    inset: 0;
    background-image:
      linear-gradient(rgba(255,255,255,0.025) 1px, transparent 1px),
      linear-gradient(90deg, rgba(255,255,255,0.025) 1px, transparent 1px);
    background-size: 60px 60px;
    mask-image: radial-gradient(ellipse 80% 60% at 50% 40%, black 30%, transparent 100%);
  }

  .hero-glow {
    position: absolute;
    top: 20%;
    left: 50%;
    transform: translateX(-50%);
    width: 700px;
    height: 400px;
    background: radial-gradient(ellipse, rgba(212,244,90,0.08) 0%, transparent 70%);
    pointer-events: none;
  }

  .hero-tag {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    background: var(--accent-dim);
    border: 1px solid rgba(212,244,90,0.25);
    color: var(--accent);
    font-size: 0.8rem;
    font-weight: 500;
    padding: 0.35rem 0.9rem;
    border-radius: 100px;
    margin-bottom: 2rem;
    width: fit-content;
    animation: fadeUp 0.8s ease both;
  }

  .hero-tag::before {
    content: '';
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: var(--accent);
    animation: pulse 2s infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.4; }
  }

  .hero h1 {
    font-family: 'Syne', sans-serif;
    font-weight: 800;
    font-size: clamp(3rem, 7vw, 6.5rem);
    line-height: 1.0;
    letter-spacing: -0.03em;
    max-width: 900px;
    animation: fadeUp 0.8s 0.1s ease both;
  }

  .hero h1 em {
    font-style: normal;
    color: var(--accent);
  }

  .hero p {
    font-size: 1.1rem;
    color: var(--muted);
    max-width: 520px;
    margin-top: 1.5rem;
    font-weight: 300;
    animation: fadeUp 0.8s 0.2s ease both;
  }

  .hero-actions {
    display: flex;
    gap: 1rem;
    margin-top: 2.5rem;
    animation: fadeUp 0.8s 0.3s ease both;
  }

  .btn-primary {
    background: var(--accent);
    color: #090909;
    border: none;
    padding: 0.85rem 2rem;
    border-radius: 100px;
    font-family: 'DM Sans', sans-serif;
    font-size: 0.95rem;
    font-weight: 500;
    cursor: pointer;
    text-decoration: none;
    display: inline-block;
    transition: background 0.2s, transform 0.15s;
  }

  .btn-primary:hover { background: var(--accent2); transform: translateY(-1px); }

  .btn-secondary {
    background: transparent;
    color: var(--text);
    border: 1px solid var(--border2);
    padding: 0.85rem 2rem;
    border-radius: 100px;
    font-family: 'DM Sans', sans-serif;
    font-size: 0.95rem;
    font-weight: 400;
    cursor: pointer;
    text-decoration: none;
    display: inline-block;
    transition: border-color 0.2s, transform 0.15s;
  }

  .btn-secondary:hover { border-color: rgba(255,255,255,0.35); transform: translateY(-1px); }

  .hero-stats {
    display: flex;
    gap: 3rem;
    margin-top: 5rem;
    padding-top: 2.5rem;
    border-top: 1px solid var(--border);
    animation: fadeUp 0.8s 0.4s ease both;
  }

  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 2rem;
    font-weight: 700;
    color: var(--text);
  }

  .stat-num span { color: var(--accent); }

  .stat-label {
    font-size: 0.82rem;
    color: var(--muted);
    margin-top: 0.15rem;
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(28px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* SECTION */
  section { padding: 7rem 5%; }

  .section-label {
    font-size: 0.75rem;
    font-weight: 500;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 1rem;
  }

  .section-title {
    font-family: 'Syne', sans-serif;
    font-weight: 700;
    font-size: clamp(2rem, 4vw, 3.2rem);
    line-height: 1.1;
    letter-spacing: -0.02em;
    max-width: 600px;
  }

  /* SKILLS */
  .skills-section { background: var(--bg2); }

  .skills-inner {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 5rem;
    align-items: center;
  }

  .skills-text p {
    color: var(--muted);
    margin-top: 1.25rem;
    font-size: 1.05rem;
    font-weight: 300;
  }

  .skills-cards {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .skill-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 1.5rem;
    display: flex;
    align-items: center;
    gap: 1.25rem;
    transition: border-color 0.3s, transform 0.3s;
  }

  .skill-card:hover { border-color: rgba(212,244,90,0.3); transform: translateX(6px); }

  .skill-icon {
    width: 48px;
    height: 48px;
    border-radius: 12px;
    background: var(--accent-dim);
    border: 1px solid rgba(212,244,90,0.2);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.3rem;
    flex-shrink: 0;
  }

  .skill-name {
    font-family: 'Syne', sans-serif;
    font-weight: 600;
    font-size: 1rem;
    margin-bottom: 0.2rem;
  }

  .skill-desc {
    font-size: 0.83rem;
    color: var(--muted);
    font-weight: 300;
  }

  /* WORKS */
  .works-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    margin-bottom: 3rem;
  }

  .works-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 1.5rem;
  }

  .work-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 20px;
    overflow: hidden;
    cursor: pointer;
    transition: border-color 0.3s, transform 0.3s;
    position: relative;
  }

  .work-card:hover { border-color: rgba(212,244,90,0.25); transform: translateY(-4px); }

  .work-thumb {
    height: 220px;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    overflow: hidden;
  }

  .work-thumb svg { width: 100%; height: 100%; }

  .play-btn {
    position: absolute;
    width: 54px;
    height: 54px;
    border-radius: 50%;
    background: rgba(9,9,9,0.75);
    border: 1.5px solid rgba(255,255,255,0.2);
    display: flex;
    align-items: center;
    justify-content: center;
    backdrop-filter: blur(8px);
    transition: background 0.2s, transform 0.2s;
  }

  .work-card:hover .play-btn { background: var(--accent); transform: scale(1.08); }
  .work-card:hover .play-btn svg path { fill: #090909; }

  .work-info { padding: 1.25rem 1.5rem 1.5rem; }

  .work-tag {
    display: inline-block;
    font-size: 0.72rem;
    font-weight: 500;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--accent);
    background: var(--accent-dim);
    border-radius: 100px;
    padding: 0.25rem 0.7rem;
    margin-bottom: 0.6rem;
  }

  .work-title {
    font-family: 'Syne', sans-serif;
    font-weight: 600;
    font-size: 1.1rem;
  }

  .work-meta {
    font-size: 0.82rem;
    color: var(--muted);
    margin-top: 0.3rem;
  }

  /* WORK THUMB ILLUSTRATIONS */
  .thumb-a { background: linear-gradient(135deg, #0f1a2e 0%, #0a1220 100%); }
  .thumb-b { background: linear-gradient(135deg, #1a0f1a 0%, #120a12 100%); }
  .thumb-c { background: linear-gradient(135deg, #0d1f0d 0%, #091409 100%); }
  .thumb-d { background: linear-gradient(135deg, #1f150a 0%, #140d06 100%); }

  /* REVIEWS */
  .reviews-section { background: var(--bg2); }

  .reviews-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.25rem;
    margin-top: 3rem;
  }

  .review-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 18px;
    padding: 1.75rem;
    transition: border-color 0.3s;
  }

  .review-card:hover { border-color: var(--border2); }

  .stars { color: var(--accent); font-size: 0.9rem; margin-bottom: 1rem; letter-spacing: 2px; }

  .review-text {
    font-size: 0.92rem;
    color: var(--muted);
    font-weight: 300;
    line-height: 1.8;
    font-style: italic;
    margin-bottom: 1.5rem;
  }

  .reviewer {
    display: flex;
    align-items: center;
    gap: 0.75rem;
  }

  .reviewer-avatar {
    width: 38px;
    height: 38px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Syne', sans-serif;
    font-weight: 700;
    font-size: 0.85rem;
    color: #090909;
    background: var(--accent);
    flex-shrink: 0;
  }

  .reviewer-name {
    font-family: 'Syne', sans-serif;
    font-size: 0.9rem;
    font-weight: 600;
  }

  .reviewer-role {
    font-size: 0.78rem;
    color: var(--muted);
  }

  /* PRICING */
  .pricing-section { background: var(--bg); }

  .pricing-subtitle {
    color: var(--muted);
    margin-top: 1rem;
    font-size: 1rem;
    font-weight: 300;
  }

  .pricing-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.25rem;
    margin-top: 3rem;
  }

  .pricing-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 22px;
    padding: 2.25rem 2rem;
    position: relative;
    transition: border-color 0.3s, transform 0.3s;
    display: flex;
    flex-direction: column;
  }

  .pricing-card:hover { transform: translateY(-4px); }

  .pricing-card.featured {
    border-color: rgba(212,244,90,0.35);
    background: linear-gradient(160deg, #161f00 0%, #111600 100%);
  }

  .featured-badge {
    position: absolute;
    top: -14px;
    left: 50%;
    transform: translateX(-50%);
    background: var(--accent);
    color: #090909;
    font-size: 0.72rem;
    font-weight: 700;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    padding: 0.3rem 1rem;
    border-radius: 100px;
    white-space: nowrap;
  }

  .plan-name {
    font-family: 'Syne', sans-serif;
    font-weight: 700;
    font-size: 1.1rem;
    margin-bottom: 0.5rem;
  }

  .plan-tagline {
    font-size: 0.82rem;
    color: var(--muted);
    margin-bottom: 1.75rem;
    font-weight: 300;
  }

  .plan-price {
    font-family: 'Syne', sans-serif;
    font-size: 3.5rem;
    font-weight: 800;
    line-height: 1;
    letter-spacing: -0.03em;
    margin-bottom: 0.3rem;
  }

  .plan-price span {
    font-size: 1.5rem;
    font-weight: 500;
    vertical-align: super;
    color: var(--muted);
  }

  .plan-duration {
    font-size: 0.8rem;
    color: var(--muted);
    margin-bottom: 2rem;
    padding-bottom: 1.75rem;
    border-bottom: 1px solid var(--border);
  }

  .plan-features {
    list-style: none;
    flex: 1;
  }

  .plan-features li {
    font-size: 0.88rem;
    color: var(--muted);
    padding: 0.55rem 0;
    display: flex;
    align-items: center;
    gap: 0.75rem;
    border-bottom: 1px solid var(--border);
    font-weight: 300;
  }

  .plan-features li:last-child { border-bottom: none; }

  .check {
    width: 18px;
    height: 18px;
    border-radius: 50%;
    background: var(--accent-dim);
    border: 1px solid rgba(212,244,90,0.25);
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
    font-size: 0.65rem;
    color: var(--accent);
  }

  .plan-cta {
    margin-top: 2rem;
    display: block;
    text-align: center;
    padding: 0.85rem;
    border-radius: 100px;
    font-size: 0.9rem;
    font-weight: 500;
    font-family: 'DM Sans', sans-serif;
    cursor: pointer;
    text-decoration: none;
    transition: all 0.2s;
  }

  .plan-cta-outline {
    border: 1px solid var(--border2);
    color: var(--text);
    background: transparent;
  }

  .plan-cta-outline:hover { border-color: rgba(255,255,255,0.35); }

  .plan-cta-filled {
    background: var(--accent);
    color: #090909;
    border: none;
  }

  .plan-cta-filled:hover { background: var(--accent2); }

  /* CONTACT */
  .contact-section { background: var(--bg2); }

  .contact-inner {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 5rem;
    align-items: start;
  }

  .contact-left p {
    color: var(--muted);
    margin-top: 1.25rem;
    font-size: 1.05rem;
    font-weight: 300;
    margin-bottom: 2rem;
  }

  .contact-links {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .contact-link {
    display: flex;
    align-items: center;
    gap: 1rem;
    text-decoration: none;
    color: var(--text);
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 1rem 1.25rem;
    transition: border-color 0.3s, transform 0.2s;
    font-size: 0.92rem;
  }

  .contact-link:hover { border-color: rgba(212,244,90,0.3); transform: translateX(5px); }

  .contact-link-icon {
    width: 40px;
    height: 40px;
    border-radius: 10px;
    background: var(--accent-dim);
    border: 1px solid rgba(212,244,90,0.2);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1rem;
    flex-shrink: 0;
  }

  .contact-link-info strong {
    display: block;
    font-weight: 500;
    margin-bottom: 0.1rem;
    font-size: 0.85rem;
    font-family: 'Syne', sans-serif;
  }

  .contact-link-info span {
    font-size: 0.8rem;
    color: var(--muted);
  }

  .contact-form {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .form-group { display: flex; flex-direction: column; gap: 0.4rem; }

  .form-label {
    font-size: 0.8rem;
    color: var(--muted);
    font-weight: 400;
    letter-spacing: 0.03em;
  }

  .form-input, .form-textarea {
    background: var(--card);
    border: 1px solid var(--border);
    color: var(--text);
    border-radius: 12px;
    padding: 0.85rem 1.1rem;
    font-family: 'DM Sans', sans-serif;
    font-size: 0.92rem;
    font-weight: 300;
    outline: none;
    transition: border-color 0.2s;
    resize: none;
  }

  .form-input::placeholder, .form-textarea::placeholder { color: var(--muted); }
  .form-input:focus, .form-textarea:focus { border-color: rgba(212,244,90,0.4); }

  .form-textarea { height: 130px; }

  .form-submit {
    background: var(--accent);
    color: #090909;
    border: none;
    padding: 0.9rem 2rem;
    border-radius: 100px;
    font-family: 'DM Sans', sans-serif;
    font-size: 0.95rem;
    font-weight: 500;
    cursor: pointer;
    transition: background 0.2s;
    margin-top: 0.5rem;
  }

  .form-submit:hover { background: var(--accent2); }

  /* FOOTER */
  footer {
    background: var(--bg);
    border-top: 1px solid var(--border);
    padding: 2rem 5%;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  footer p { font-size: 0.82rem; color: var(--muted); }
  footer .logo { font-size: 1rem; }

  /* SCROLL ANIMATIONS */
  .reveal {
    opacity: 0;
    transform: translateY(30px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }

  .reveal.visible {
    opacity: 1;
    transform: none;
  }

  /* DIVIDER LINE */
  .divider {
    width: 100%;
    height: 1px;
    background: var(--border);
  }

  /* SCROLLBAR */
  ::-webkit-scrollbar { width: 6px; }
  ::-webkit-scrollbar-track { background: var(--bg); }
  ::-webkit-scrollbar-thumb { background: #2a2a2a; border-radius: 3px; }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#" class="logo">Aryan<span>.</span></a>
  <ul>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#works">Work</a></li>
    <li><a href="#reviews">Reviews</a></li>
    <li><a href="#pricing">Pricing</a></li>
    <li><a href="#contact" class="nav-cta">Hire Me</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero" id="home">
  <div class="hero-grid-bg"></div>
  <div class="hero-glow"></div>

  <div class="hero-tag">Available for freelance work</div>

  <h1>I turn <em>complex SaaS</em><br>into clean motion.</h1>

  <p>Motion designer specializing in SaaS explanation videos, app walkthroughs, and talking head content that converts viewers into customers.</p>

  <div class="hero-actions">
    <a href="#works" class="btn-primary">View My Work</a>
    <a href="#pricing" class="btn-secondary">See Pricing →</a>
  </div>

  <div class="hero-stats">
    <div>
      <div class="stat-num">50<span>+</span></div>
      <div class="stat-label">Projects Delivered</div>
    </div>
    <div>
      <div class="stat-num">30<span>+</span></div>
      <div class="stat-label">Happy Clients</div>
    </div>
    <div>
      <div class="stat-num">3<span>yr</span></div>
      <div class="stat-label">Experience</div>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section class="skills-section" id="skills">
  <div class="skills-inner">
    <div class="skills-text reveal">
      <div class="section-label">What I Do</div>
      <h2 class="section-title">Crafted motion for the digital product era.</h2>
      <p>I specialize in breaking down complex software into visually engaging stories — turning features into feelings, and walkthroughs into conversions.</p>
      <br>
      <p>Every frame is intentional. Every transition earns its place. I design motion that makes your product <em>feel</em> inevitable.</p>
    </div>
    <div class="skills-cards reveal">
      <div class="skill-card">
        <div class="skill-icon">✦</div>
        <div>
          <div class="skill-name">Motion Graphics</div>
          <div class="skill-desc">Dynamic animated visuals, kinetic typography, logo reveals & brand motion</div>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-icon">◈</div>
        <div>
          <div class="skill-name">Talking Head Videos</div>
          <div class="skill-desc">Polished talking head edits with motion overlays, captions & B-roll</div>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-icon">⬡</div>
        <div>
          <div class="skill-name">SaaS / App Explanations</div>
          <div class="skill-desc">Product walkthroughs, feature explainers & onboarding animations that convert</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- WORKS -->
<section id="works">
  <div class="works-header reveal">
    <div>
      <div class="section-label">Portfolio</div>
      <h2 class="section-title">Selected Work</h2>
    </div>
    <a href="#contact" class="btn-secondary">See All Work →</a>
  </div>

  <div class="works-grid">
    <!-- Card 1 -->
    <div class="work-card reveal">
      <div class="work-thumb thumb-a">
        <svg viewBox="0 0 500 220" xmlns="http://www.w3.org/2000/svg">
          <!-- animated UI mock -->
          <rect x="60" y="40" width="380" height="140" rx="12" fill="#0a1628" stroke="#1e3a5f" stroke-width="1"/>
          <rect x="75" y="55" width="60" height="8" rx="4" fill="#1e3a5f"/>
          <rect x="75" y="70" width="40" height="6" rx="3" fill="#152840"/>
          <!-- dashboard bars -->
          <rect x="75" y="95" width="16" height="50" rx="4" fill="#1a4a8a" opacity="0.9"/>
          <rect x="97" y="110" width="16" height="35" rx="4" fill="#1a4a8a" opacity="0.7"/>
          <rect x="119" y="100" width="16" height="45" rx="4" fill="#D4F45A" opacity="0.9"/>
          <rect x="141" y="120" width="16" height="25" rx="4" fill="#1a4a8a" opacity="0.6"/>
          <rect x="163" y="108" width="16" height="37" rx="4" fill="#1a4a8a" opacity="0.7"/>
          <!-- right side card -->
          <rect x="210" y="90" width="210" height="35" rx="8" fill="#12233d"/>
          <circle cx="228" cy="107" r="9" fill="#1a4a8a"/>
          <rect x="244" y="101" width="80" height="6" rx="3" fill="#1e3a5f"/>
          <rect x="244" y="112" width="55" height="5" rx="2.5" fill="#152840"/>
          <rect x="330" y="100" width="40" height="14" rx="7" fill="#D4F45A" opacity="0.9"/>
          <rect x="210" y="133" width="100" height="30" rx="8" fill="#12233d"/>
          <rect x="318" y="133" width="102" height="30" rx="8" fill="#12233d"/>
          <!-- floating accent -->
          <circle cx="415" cy="68" r="18" fill="#D4F45A" opacity="0.15"/>
          <text x="415" y="73" text-anchor="middle" fill="#D4F45A" font-size="11" font-family="monospace">↗</text>
        </svg>
        <div class="play-btn">
          <svg width="16" height="16" viewBox="0 0 16 16" fill="

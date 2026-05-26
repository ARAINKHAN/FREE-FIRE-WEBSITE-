<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>FR NINE GUILD – Free Fire</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Rajdhani:wght@400;600;700&family=Exo+2:wght@300;400;700&display=swap" rel="stylesheet">
<style>
  :root {
    --blue: #0047FF;
    --red: #FF1A1A;
    --white: #FFFFFF;
    --dark: #0a0a0f;
    --card-bg: #f5f5f5;
    --border: #e0e0e0;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: #ffffff;
    color: #111;
    font-family: 'Rajdhani', sans-serif;
    overflow-x: hidden;
  }

  /* ── HERO ── */
  .hero {
    position: relative;
    min-height: 100vh;
    background: #0a0a0f;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    overflow: hidden;
  }

  /* animated grid lines */
  .hero::before {
    content: '';
    position: absolute;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,71,255,.07) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,71,255,.07) 1px, transparent 1px);
    background-size: 60px 60px;
    animation: gridScroll 20s linear infinite;
  }

  @keyframes gridScroll {
    0%   { background-position: 0 0; }
    100% { background-position: 60px 60px; }
  }

  /* glow blobs */
  .blob {
    position: absolute;
    border-radius: 50%;
    filter: blur(120px);
    opacity: .35;
    animation: pulse 6s ease-in-out infinite alternate;
  }
  .blob-blue  { width:500px; height:500px; background:var(--blue); top:-100px; left:-100px; }
  .blob-red   { width:400px; height:400px; background:var(--red);  bottom:-80px; right:-80px; animation-delay:-3s; }

  @keyframes pulse { from{opacity:.25;} to{opacity:.45;} }

  .hero-content { position: relative; z-index: 2; text-align: center; padding: 2rem; }

  /* GUILD NAME */
  .guild-name {
    font-family: 'Orbitron', sans-serif;
    font-weight: 900;
    font-size: clamp(3rem, 10vw, 7rem);
    letter-spacing: .05em;
    line-height: 1;
    text-transform: uppercase;
    display: flex;
    gap: .3em;
    justify-content: center;
    flex-wrap: wrap;
    filter: drop-shadow(0 0 30px rgba(0,71,255,.6));
    animation: nameReveal .8s cubic-bezier(.16,1,.3,1) both;
  }
  @keyframes nameReveal {
    from { opacity:0; transform: translateY(40px) scale(.95); }
    to   { opacity:1; transform: translateY(0)   scale(1);    }
  }
  .fr    { color: var(--blue); text-shadow: 0 0 40px rgba(0,71,255,.9), 0 0 80px rgba(0,71,255,.4); }
  .nine  { color: var(--white); text-shadow: 0 0 20px rgba(255,255,255,.6); }
  .guild { color: var(--red);  text-shadow: 0 0 40px rgba(255,26,26,.9), 0 0 80px rgba(255,26,26,.4); }

  .hero-sub {
    margin-top: 1.5rem;
    font-family: 'Exo 2', sans-serif;
    font-size: clamp(1rem, 2.5vw, 1.4rem);
    color: rgba(255,255,255,.6);
    letter-spacing: .2em;
    text-transform: uppercase;
    animation: nameReveal .8s .2s cubic-bezier(.16,1,.3,1) both;
  }

  .hero-badges {
    margin-top: 2.5rem;
    display: flex;
    gap: 1rem;
    justify-content: center;
    flex-wrap: wrap;
    animation: nameReveal .8s .4s cubic-bezier(.16,1,.3,1) both;
  }

  .badge {
    padding: .4rem 1.2rem;
    border-radius: 2px;
    font-family: 'Orbitron', sans-serif;
    font-size: .7rem;
    font-weight: 700;
    letter-spacing: .15em;
    text-transform: uppercase;
    border: 2px solid;
  }
  .badge-blue  { color:var(--blue);  border-color:var(--blue);  background:rgba(0,71,255,.1); }
  .badge-red   { color:var(--red);   border-color:var(--red);   background:rgba(255,26,26,.1); }
  .badge-white { color:var(--white); border-color:var(--white); background:rgba(255,255,255,.05); }

  .scroll-hint {
    position: absolute;
    bottom: 2rem;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: .5rem;
    color: rgba(255,255,255,.4);
    font-family: 'Exo 2', sans-serif;
    font-size: .75rem;
    letter-spacing: .15em;
    text-transform: uppercase;
    z-index: 2;
  }
  .scroll-arrow {
    width: 24px; height: 24px;
    border-right: 2px solid rgba(255,255,255,.3);
    border-bottom: 2px solid rgba(255,255,255,.3);
    transform: rotate(45deg);
    animation: scrollBounce 1.5s ease-in-out infinite;
  }
  @keyframes scrollBounce { 0%,100%{transform:rotate(45deg) translateY(0);} 50%{transform:rotate(45deg) translateY(6px);} }

  /* ── SECTION WRAPPER ── */
  section { padding: 5rem 2rem; }
  .container { max-width: 1100px; margin: 0 auto; }

  .section-tag {
    font-family: 'Orbitron', sans-serif;
    font-size: .7rem;
    letter-spacing: .25em;
    text-transform: uppercase;
    color: var(--blue);
    margin-bottom: .75rem;
  }

  .section-title {
    font-family: 'Orbitron', sans-serif;
    font-size: clamp(1.8rem, 4vw, 3rem);
    font-weight: 900;
    line-height: 1.1;
    color: #111;
  }
  .section-title span.red  { color: var(--red); }
  .section-title span.blue { color: var(--blue); }

  .divider {
    width: 60px; height: 4px;
    background: linear-gradient(90deg, var(--blue), var(--red));
    margin: 1.5rem 0;
    border-radius: 2px;
  }

  /* ── STATS BAR ── */
  .stats-bar {
    background: var(--dark);
    padding: 2rem;
    display: flex;
    justify-content: center;
    gap: 3rem;
    flex-wrap: wrap;
  }
  .stat-item { text-align: center; }
  .stat-num {
    font-family: 'Orbitron', sans-serif;
    font-size: 2.5rem;
    font-weight: 900;
    background: linear-gradient(135deg, var(--blue), var(--red));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }
  .stat-label {
    font-family: 'Exo 2', sans-serif;
    font-size: .8rem;
    letter-spacing: .15em;
    text-transform: uppercase;
    color: rgba(255,255,255,.5);
    margin-top: .25rem;
  }

  /* ── ABOUT ── */
  .about { background: #fff; }
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    align-items: center;
  }
  @media(max-width:700px){ .about-grid{ grid-template-columns:1fr; } }

  .about-text p {
    font-family: 'Exo 2', sans-serif;
    font-size: 1.05rem;
    line-height: 1.8;
    color: #444;
    margin-bottom: 1rem;
  }

  .feature-list { list-style: none; margin-top: 1.5rem; }
  .feature-list li {
    font-family: 'Exo 2', sans-serif;
    font-size: 1rem;
    color: #333;
    padding: .6rem 0;
    border-bottom: 1px solid #eee;
    display: flex;
    align-items: center;
    gap: .75rem;
  }
  .feature-list li::before {
    content: '▶';
    font-size: .6rem;
    color: var(--blue);
  }

  .about-visual {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .shield {
    width: 220px; height: 260px;
    clip-path: polygon(50% 0%, 100% 20%, 100% 60%, 50% 100%, 0% 60%, 0% 20%);
    background: linear-gradient(135deg, var(--blue) 0%, var(--dark) 50%, var(--red) 100%);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    animation: shieldGlow 3s ease-in-out infinite alternate;
    box-shadow: 0 0 60px rgba(0,71,255,.4), 0 0 120px rgba(255,26,26,.2);
  }
  @keyframes shieldGlow {
    from { box-shadow: 0 0 40px rgba(0,71,255,.3); }
    to   { box-shadow: 0 0 80px rgba(255,26,26,.5); }
  }
  .shield-fr   { font-family:'Orbitron',sans-serif; font-size:2rem; font-weight:900; color:var(--blue); text-shadow:0 0 20px var(--blue); }
  .shield-nine { font-family:'Orbitron',sans-serif; font-size:2rem; font-weight:900; color:#fff; }
  .shield-tag  { font-family:'Exo 2',sans-serif; font-size:.65rem; letter-spacing:.2em; color:var(--red); margin-top:.25rem; text-transform:uppercase; }

  /* ── MEMBERS ── */
  .members { background: #f8f8f8; }
  .members-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(230px, 1fr));
    gap: 1.5rem;
    margin-top: 2.5rem;
  }
  .member-card {
    background: #fff;
    border: 1px solid var(--border);
    border-top: 3px solid var(--blue);
    padding: 1.5rem;
    position: relative;
    transition: transform .2s, box-shadow .2s;
  }
  .member-card:hover { transform: translateY(-4px); box-shadow: 0 12px 40px rgba(0,71,255,.12); }
  .member-card.sponsor { border-top-color: var(--red); }
  .member-card.sponsor:hover { box-shadow: 0 12px 40px rgba(255,26,26,.15); }

  .member-role {
    font-family: 'Orbitron', sans-serif;
    font-size: .6rem;
    letter-spacing: .2em;
    text-transform: uppercase;
    color: var(--blue);
    margin-bottom: .5rem;
  }
  .member-card.sponsor .member-role { color: var(--red); }

  .member-name {
    font-family: 'Orbitron', sans-serif;
    font-size: 1rem;
    font-weight: 700;
    color: #111;
  }

  .member-detail {
    font-family: 'Exo 2', sans-serif;
    font-size: .85rem;
    color: #666;
    margin-top: .4rem;
  }

  .member-pts {
    position: absolute;
    top: 1.5rem;
    right: 1.5rem;
    font-family: 'Orbitron', sans-serif;
    font-size: .85rem;
    font-weight: 700;
    color: var(--blue);
  }
  .member-card.sponsor .member-pts { color: var(--red); }

  /* ── CONTACT ── */
  .contact { background: var(--dark); color: #fff; }
  .contact .section-title { color: #fff; }
  .contact .section-tag { color: rgba(255,255,255,.5); }
  .contact .divider { background: linear-gradient(90deg, var(--red), var(--blue)); }

  .contact-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 3rem;
    margin-top: 2.5rem;
    align-items: start;
  }
  @media(max-width:650px){ .contact-grid{ grid-template-columns:1fr; } }

  .contact-info { display: flex; flex-direction: column; gap: 1.5rem; }
  .contact-item {
    display: flex;
    align-items: flex-start;
    gap: 1rem;
    padding: 1.25rem;
    background: rgba(255,255,255,.04);
    border: 1px solid rgba(255,255,255,.08);
    border-left: 3px solid var(--blue);
    transition: border-color .2s;
  }
  .contact-item:hover { border-left-color: var(--red); }
  .contact-icon { font-size: 1.5rem; flex-shrink:0; }
  .contact-label { font-family:'Exo 2',sans-serif; font-size:.75rem; letter-spacing:.15em; text-transform:uppercase; color:rgba(255,255,255,.4); }
  .contact-value { font-family:'Rajdhani',sans-serif; font-size:1.1rem; color:#fff; font-weight:600; margin-top:.15rem; word-break:break-all; }
  .contact-value a { color:inherit; text-decoration:none; }
  .contact-value a:hover { color: var(--blue); }

  /* join form */
  .join-form { display: flex; flex-direction: column; gap: 1rem; }
  .join-form input, .join-form textarea {
    background: rgba(255,255,255,.06);
    border: 1px solid rgba(255,255,255,.12);
    color: #fff;
    font-family: 'Exo 2', sans-serif;
    font-size: 1rem;
    padding: .85rem 1rem;
    outline: none;
    transition: border-color .2s;
  }
  .join-form input:focus, .join-form textarea:focus { border-color: var(--blue); }
  .join-form textarea { height: 120px; resize: vertical; }

  .btn {
    padding: .9rem 2.5rem;
    font-family: 'Orbitron', sans-serif;
    font-size: .85rem;
    font-weight: 700;
    letter-spacing: .12em;
    text-transform: uppercase;
    cursor: pointer;
    border: none;
    position: relative;
    overflow: hidden;
    transition: transform .15s;
    clip-path: polygon(0 0, calc(100% - 12px) 0, 100% 12px, 100% 100%, 12px 100%, 0 calc(100% - 12px));
  }
  .btn:active { transform: scale(.97); }

  .btn-primary {
    background: linear-gradient(135deg, var(--blue), #0033cc);
    color: #fff;
    box-shadow: 0 4px 20px rgba(0,71,255,.4);
  }
  .btn-primary:hover { box-shadow: 0 8px 30px rgba(0,71,255,.6); }

  /* ── FOOTER ── */
  footer {
    background: #050508;
    text-align: center;
    padding: 2rem;
    border-top: 1px solid rgba(255,255,255,.06);
  }
  .footer-logo {
    font-family: 'Orbitron', sans-serif;
    font-size: 1.2rem;
    font-weight: 900;
    margin-bottom: .5rem;
  }
  footer p {
    font-family: 'Exo 2', sans-serif;
    font-size: .8rem;
    color: rgba(255,255,255,.3);
  }

  /* ── NAV ── */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 1rem 2rem;
    background: rgba(10,10,15,.85);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid rgba(255,255,255,.06);
  }
  .nav-logo {
    font-family: 'Orbitron', sans-serif;
    font-size: 1.1rem;
    font-weight: 900;
  }
  .nav-links {
    display: flex;
    gap: 2rem;
    list-style: none;
  }
  .nav-links a {
    font-family: 'Exo 2', sans-serif;
    font-size: .9rem;
    letter-spacing: .08em;
    color: rgba(255,255,255,.6);
    text-decoration: none;
    text-transform: uppercase;
    transition: color .2s;
  }
  .nav-links a:hover { color: #fff; }
  @media(max-width:600px){ .nav-links{ display:none; } }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">
    <span class="fr">FR</span><span class="nine" style="color:#fff"> NINE </span><span class="guild" style="color:var(--red)">GUILD</span>
  </div>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#members">Members</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<div class="hero">
  <div class="blob blob-blue"></div>
  <div class="blob blob-red"></div>
  <div class="hero-content">
    <div class="guild-name">
      <span class="fr">FR</span>
      <span class="nine">NINE</span>
      <span class="guild">GUILD</span>
    </div>
    <p class="hero-sub">Free Fire · France Server · Competitive</p>
    <div class="hero-badges">
      <span class="badge badge-blue">Battle Royale</span>
      <span class="badge badge-white">Clash Squad</span>
      <span class="badge badge-red">Heroic+</span>
    </div>
  </div>
  <div class="scroll-hint">
    <span>Scroll</span>
    <div class="scroll-arrow"></div>
  </div>
</div>

<!-- STATS BAR -->
<div class="stats-bar">
  <div class="stat-item">
    <div class="stat-num">7</div>
    <div class="stat-label">Members</div>
  </div>
  <div class="stat-item">
    <div class="stat-num">Lv.4</div>
    <div class="stat-label">Guild Level</div>
  </div>
  <div class="stat-item">
    <div class="stat-num">4980</div>
    <div class="stat-label">Activity Points</div>
  </div>
  <div class="stat-item">
    <div class="stat-num">Heroic</div>
    <div class="stat-label">Rank</div>
  </div>
  <div class="stat-item">
    <div class="stat-num">France</div>
    <div class="stat-label">Region</div>
  </div>
</div>

<!-- ABOUT -->
<section class="about" id="about">
  <div class="container">
    <div class="about-grid">
      <div class="about-text">
        <div class="section-tag">// Who We Are</div>
        <h2 class="section-title">Elite <span class="blue">French</span> <span class="red">Warriors</span></h2>
        <div class="divider"></div>
        <p>FR-NINE is a competitive Free Fire guild based on the France server, built for players who want to push their limits and dominate every season. Whether you're a Battle Royale specialist or a Clash Squad ace, there's a place for you here.</p>
        <p>We value teamwork, loyalty, and consistent activity. Our goal is to climb every leaderboard, earn every reward, and build a lasting community of elite French-speaking players.</p>
        <ul class="feature-list">
          <li>Heroic & above players welcome</li>
          <li>Active Guild War participation</li>
          <li>Weekly activity rewards</li>
          <li>Francophone community (FR/EN)</li>
          <li>All game modes: BR & Clash Squad</li>
        </ul>
      </div>
      <div class="about-visual">
        <div class="shield">
          <div class="shield-fr">FR</div>
          <div class="shield-nine">NINE</div>
          <div class="shield-tag">Guild</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- MEMBERS -->
<section class="members" id="members">
  <div class="container">
    <div class="section-tag">// Roster</div>
    <h2 class="section-title">Our <span class="blue">Members</span></h2>
    <div class="divider"></div>
    <div class="members-grid">

      <div class="member-card sponsor">
        <div class="member-role">⭐ Sponsor / Leader</div>
        <div class="member-name">K9-KIYONI</div>
        <div class="member-detail">Lv.66 · Clash Squad · Heroic</div>
        <div class="member-pts">2460 pts</div>
      </div>

      <div class="member-card">
        <div class="member-role">🔥 Top Performer</div>
        <div class="member-name">A9-ARAIN</div>
        <div class="member-detail">Lv.75 · Battle Royale · Heroic 29</div>
        <div class="member-pts">Active</div>
      </div>

      <div class="member-card">
        <div class="member-role">🎯 Rifler</div>
        <div class="member-name">@Isaías_Mk</div>
        <div class="member-detail">Clash Squad Specialist</div>
        <div class="member-pts">640 pts</div>
      </div>

      <div class="member-card">
        <div class="member-role">🏆 Veteran</div>
        <div class="member-name">L9-LEGEND</div>
        <div class="member-detail">Lv.56 · 5 Years Old · CS Heroic</div>
        <div class="member-pts">1320 pts</div>
      </div>

      <div class="member-card">
        <div class="member-role">🥷 Rifler</div>
        <div class="member-name">NinjÆ.FF</div>
        <div class="member-detail">Lv.54 · Old Player · BR Heroic</div>
        <div class="member-pts">0 pts</div>
      </div>

      <div class="member-card" style="border-top-color:#aaa; opacity:.7;">
        <div class="member-role" style="color:#999;">+ Open Slots</div>
        <div class="member-name" style="color:#bbb;">28 Spots Available</div>
        <div class="member-detail">Join us and claim your spot!</div>
        <div class="member-pts" style="color:#aaa;">35 max</div>
      </div>

    </div>
  </div>
</section>

<!-- CONTACT -->
<section class="contact" id="contact">
  <div class="container">
    <div class="section-tag">// Reach Us</div>
    <h2 class="section-title">Join the <span class="red">Guild</span></h2>
    <div class="divider"></div>

    <div class="contact-grid">
      <div class="contact-info">

        <div class="contact-item">
          <div class="contact-icon">📞</div>
          <div>
            <div class="contact-label">Phone / WhatsApp</div>
            <div class="contact-value">
              <a href="tel:0784769179">0784769179</a>
            </div>
          </div>
        </div>

        <div class="contact-item">
          <div class="contact-icon">✉️</div>
          <div>
            <div class="contact-label">Email</div>
            <div class="contact-value">
              <a href="mailto:Ajmalarain62@gmail.com">Ajmalarain62@gmail.com</a>
            </div>
          </div>
        </div>

        <div class="contact-item">
          <div class="contact-icon">🎮</div>
          <div>
            <div class="contact-label">Guild ID</div>
            <div class="contact-value">3096811130</div>
          </div>
        </div>

        <div class="contact-item">
          <div class="contact-icon">🌍</div>
          <div>
            <div class="contact-label">Server</div>
            <div class="contact-value">France · FR-NINE</div>
          </div>
        </div>

      </div>

      <div>
        <p style="font-family:'Exo 2',sans-serif;color:rgba(255,255,255,.55);margin-bottom:1.5rem;line-height:1.7;">
          Want to join FR-NINE? Drop your IGN and UID below and we'll get back to you. Heroic rank or above preferred. French speakers prioritized — but all skilled players are welcome!
        </p>
        <div class="join-form">
          <input type="text"     placeholder="In-Game Name (IGN)" />
          <input type="text"     placeholder="Your UID" />
          <input type="text"     placeholder="Current Rank" />
          <textarea             placeholder="Tell us about your playstyle..."></textarea>
          <button class="btn btn-primary">Send Application</button>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">
    <span style="color:var(--blue)">FR</span>
    <span style="color:#fff"> NINE </span>
    <span style="color:var(--red)">GUILD</span>
  </div>
  <p>Free Fire · France Server · Guild ID: 3096811130</p>
  <p style="margin-top:.5rem;">Contact: 0784769179 · Ajmalarain62@gmail.com</p>
  <p style="margin-top:1rem;font-size:.7rem;color:rgba(255,255,255,.2);">© 2026 FR-NINE Guild. All rights reserved.</p>
</footer>

</body>
</html>

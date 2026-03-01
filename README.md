<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Douae Moeniss — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;700;800&family=DM+Mono:ital,wght@0,400;0,500;1,400&family=Instrument+Serif:ital@0;1&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0a0f;
    --surface: #111118;
    --border: rgba(255,255,255,0.07);
    --accent: #c8f05a;
    --accent2: #5af0c8;
    --accent3: #f05a8c;
    --text: #e8e8f0;
    --muted: #6b6b80;
    --card: #13131c;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Mono', monospace;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(200,240,90,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(200,240,90,0.03) 1px, transparent 1px);
    background-size: 60px 60px;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 860px;
    margin: 0 auto;
    padding: 60px 24px;
    position: relative;
    z-index: 1;
  }

  /* ── HEADER ── */
  .header {
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 32px;
    align-items: start;
    margin-bottom: 64px;
  }

  .header-left {}

  .badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    font-size: 11px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--accent);
    border: 1px solid rgba(200,240,90,0.3);
    padding: 5px 12px;
    border-radius: 2px;
    margin-bottom: 20px;
    animation: fadeUp 0.6s ease both;
  }

  .badge::before {
    content: '';
    width: 6px; height: 6px;
    background: var(--accent);
    border-radius: 50%;
    animation: pulse 2s infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.5; transform: scale(0.8); }
  }

  h1 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(42px, 7vw, 72px);
    font-weight: 800;
    line-height: 1;
    letter-spacing: -0.03em;
    animation: fadeUp 0.7s 0.1s ease both;
  }

  h1 .first { color: var(--text); }
  h1 .last {
    color: transparent;
    -webkit-text-stroke: 1px rgba(255,255,255,0.3);
  }

  .subtitle {
    font-family: 'Instrument Serif', serif;
    font-style: italic;
    font-size: 18px;
    color: var(--muted);
    margin-top: 12px;
    animation: fadeUp 0.7s 0.2s ease both;
  }

  .tagline {
    font-size: 12px;
    color: var(--muted);
    margin-top: 16px;
    line-height: 1.7;
    max-width: 420px;
    animation: fadeUp 0.7s 0.3s ease both;
  }

  .tagline span { color: var(--accent2); }

  .header-right {
    text-align: right;
    animation: fadeUp 0.7s 0.2s ease both;
  }

  .location-badge {
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 0.08em;
    margin-bottom: 8px;
  }

  .status {
    font-size: 11px;
    background: rgba(200,240,90,0.08);
    border: 1px solid rgba(200,240,90,0.2);
    color: var(--accent);
    padding: 6px 14px;
    border-radius: 2px;
    letter-spacing: 0.05em;
  }

  /* ── DIVIDER ── */
  .divider {
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--border), transparent);
    margin: 48px 0;
  }

  /* ── SECTION LABEL ── */
  .section-label {
    font-size: 10px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 24px;
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* ── SKILLS ── */
  .skills-section { margin-bottom: 64px; animation: fadeUp 0.7s 0.4s ease both; }

  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
    gap: 16px;
  }

  .skill-group {
    background: var(--card);
    border: 1px solid var(--border);
    padding: 20px;
    border-radius: 4px;
    transition: border-color 0.3s, transform 0.3s;
  }

  .skill-group:hover {
    border-color: rgba(200,240,90,0.2);
    transform: translateY(-2px);
  }

  .skill-group-label {
    font-size: 9px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 12px;
  }

  .skill-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .tag {
    font-size: 11px;
    color: var(--text);
    background: rgba(255,255,255,0.04);
    border: 1px solid var(--border);
    padding: 3px 8px;
    border-radius: 2px;
    transition: all 0.2s;
  }

  .tag:hover {
    background: rgba(200,240,90,0.08);
    border-color: rgba(200,240,90,0.3);
    color: var(--accent);
  }

  /* ── STATS ── */
  .stats-section { margin-bottom: 64px; animation: fadeUp 0.7s 0.5s ease both; }

  .stats-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  .stats-img-wrap {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 4px;
    overflow: hidden;
    padding: 16px;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: border-color 0.3s;
  }

  .stats-img-wrap:hover { border-color: rgba(90,240,200,0.2); }

  .stats-img-wrap img {
    width: 100%;
    border-radius: 2px;
    filter: brightness(0.9);
  }

  /* ── CONTACT ── */
  .contact-section { animation: fadeUp 0.7s 0.6s ease both; }

  .contact-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 12px;
  }

  .contact-card {
    background: var(--card);
    border: 1px solid var(--border);
    padding: 18px 20px;
    border-radius: 4px;
    display: flex;
    align-items: center;
    gap: 12px;
    text-decoration: none;
    color: var(--text);
    transition: all 0.3s;
    font-size: 12px;
  }

  .contact-card:hover {
    border-color: rgba(90,240,200,0.3);
    background: rgba(90,240,200,0.04);
    transform: translateX(4px);
  }

  .contact-icon {
    font-size: 18px;
    flex-shrink: 0;
  }

  .contact-label {
    font-size: 9px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 3px;
  }

  .contact-value {
    font-size: 12px;
    color: var(--text);
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }

  /* ── FOOTER ── */
  .footer {
    margin-top: 64px;
    padding-top: 32px;
    border-top: 1px solid var(--border);
    display: flex;
    align-items: center;
    justify-content: space-between;
    animation: fadeUp 0.7s 0.7s ease both;
  }

  .footer-text {
    font-size: 11px;
    color: var(--muted);
    font-family: 'Instrument Serif', serif;
    font-style: italic;
  }

  .footer-cta {
    font-size: 11px;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--accent);
    border: 1px solid rgba(200,240,90,0.3);
    padding: 8px 18px;
    border-radius: 2px;
    text-decoration: none;
    transition: all 0.3s;
  }

  .footer-cta:hover {
    background: rgba(200,240,90,0.1);
    letter-spacing: 0.18em;
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(16px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  /* ── MARKDOWN COPY SECTION ── */
  .readme-section {
    margin-top: 64px;
    animation: fadeUp 0.7s 0.8s ease both;
  }

  .readme-code {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 4px;
    overflow: hidden;
  }

  .readme-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 12px 18px;
    border-bottom: 1px solid var(--border);
    font-size: 11px;
    color: var(--muted);
  }

  .copy-btn {
    background: rgba(200,240,90,0.08);
    border: 1px solid rgba(200,240,90,0.2);
    color: var(--accent);
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    padding: 5px 12px;
    border-radius: 2px;
    cursor: pointer;
    transition: all 0.2s;
  }

  .copy-btn:hover { background: rgba(200,240,90,0.15); }

  .readme-body {
    padding: 24px 18px;
    max-height: 360px;
    overflow-y: auto;
    font-size: 12px;
    line-height: 1.8;
    color: var(--muted);
    scrollbar-width: thin;
    scrollbar-color: var(--border) transparent;
  }

  .readme-body .k  { color: var(--accent2); }
  .readme-body .s  { color: var(--accent); }
  .readme-body .c  { color: var(--muted); }
  .readme-body .h  { color: var(--accent3); }

  /* Responsive */
  @media (max-width: 600px) {
    .header { grid-template-columns: 1fr; }
    .header-right { text-align: left; }
    .stats-grid { grid-template-columns: 1fr; }
    .footer { flex-direction: column; gap: 16px; }
  }
</style>
</head>
<body>
<div class="container">

  <!-- HEADER -->
  <header class="header">
    <div class="header-left">
      <div class="badge">Available for PFA 2025</div>
      <h1>
        <span class="first">Douae</span><br>
        <span class="last">Moeniss</span>
      </h1>
      <p class="subtitle">Computer Engineering Student</p>
      <p class="tagline">
        ENSA Tétouan · Full-Stack Developer<br>
        Passionate about <span>web architecture</span>, scalable systems & <span>AI integration</span>
      </p>
    </div>
    <div class="header-right">
      <p class="location-badge">📍 Tétouan, Morocco</p>
      <div class="status">Open to opportunities</div>
    </div>
  </header>

  <!-- SKILLS -->
  <section class="skills-section">
    <div class="section-label">Technical Arsenal</div>
    <div class="skills-grid">
      <div class="skill-group">
        <div class="skill-group-label">Languages</div>
        <div class="skill-tags">
          <span class="tag">C#</span><span class="tag">Java</span><span class="tag">Python</span>
          <span class="tag">JavaScript</span><span class="tag">TypeScript</span><span class="tag">PHP</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-label">Backend</div>
        <div class="skill-tags">
          <span class="tag">Spring Boot</span><span class="tag">ASP.NET</span><span class="tag">Laravel</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-label">Frontend</div>
        <div class="skill-tags">
          <span class="tag">Angular</span><span class="tag">React</span><span class="tag">Vue.js</span><span class="tag">Livewire</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-label">Infra & Tools</div>
        <div class="skill-tags">
          <span class="tag">Docker</span><span class="tag">Git</span><span class="tag">REST APIs</span>
          <span class="tag">MySQL</span><span class="tag">SQL Server</span>
        </div>
      </div>
    </div>
  </section>

  <div class="divider"></div>

  <!-- STATS -->
  <section class="stats-section">
    <div class="section-label">GitHub Stats</div>
    <div class="stats-grid">
      <div class="stats-img-wrap">
        <img src="https://github-readme-stats.vercel.app/api?douaem1=douae-moeniss&show_icons=true&theme=dark&bg_color=13131c&border_color=ffffff12&title_color=c8f05a&icon_color=5af0c8&text_color=e8e8f0&hide_border=false" alt="GitHub Stats">
      </div>
      <div class="stats-img-wrap">
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?douaem1=douae-moeniss&layout=compact&theme=dark&bg_color=13131c&border_color=ffffff12&title_color=c8f05a&text_color=e8e8f0&hide_border=false" alt="Top Languages">
      </div>
    </div>
  </section>

  <div class="divider"></div>

  <!-- CONTACT -->
  <section class="contact-section">
    <div class="section-label">Get in touch</div>
    <div class="contact-grid">
      <a class="contact-card" href="mailto:douae.moeniss@gmail.com">
        <span class="contact-icon">✉️</span>
        <div>
          <div class="contact-label">Email</div>
          <div class="contact-value">douae.moeniss@gmail.com</div>
        </div>
      </a>
      <a class="contact-card" href="https://www.linkedin.com/in/douae-moeniss-4b4417237/" target="_blank">
        <span class="contact-icon">🔗</span>
        <div>
          <div class="contact-label">LinkedIn</div>
          <div class="contact-value">douae-moeniss</div>
        </div>
      </a>
      <div class="contact-card">
        <span class="contact-icon">📍</span>
        <div>
          <div class="contact-label">Location</div>
          <div class="contact-value">Tétouan, Morocco</div>
        </div>
      </div>
    </div>
  </section>

  <div class="divider"></div>

  <!-- README CODE -->
  <section class="readme-section">
    <div class="section-label">README.md — Copy & Paste</div>
    <div class="readme-code">
      <div class="readme-header">
        <span>README.md</span>
        <button class="copy-btn" onclick="copyReadme()">Copy</button>
      </div>
      <pre class="readme-body" id="readme-content">
<span class="h">&lt;div align="center"&gt;</span>

<span class="h">&lt;img src="https://capsule-render.vercel.app/api?type=waving&color=c8f05a&height=120&section=header&text=Douae%20Moeniss&fontSize=42&fontColor=0a0a0f&fontAlignY=38&animation=fadeIn" /&gt;</span>

<span class="k">### Computer Engineering Student · Full-Stack Developer · ENSA Tétouan</span>

<span class="s">![](https://img.shields.io/badge/Available-PFA%202025-c8f05a?style=flat-square&labelColor=0a0a0f)</span>
<span class="s">![](https://img.shields.io/badge/Location-Tétouan%2C%20Morocco-5af0c8?style=flat-square&labelColor=0a0a0f)</span>

<span class="h">&lt;/div&gt;</span>

---

<span class="k">## 🧠 About Me</span>

Computer Engineering student at **ENSA Tétouan**, passionate about designing scalable web applications, building intelligent systems, and contributing to innovative technology-driven projects.

---

<span class="k">## ⚙️ Tech Stack</span>

<span class="h">&lt;div align="center"&gt;</span>

<span class="s">![C#](https://img.shields.io/badge/C%23-239120?style=flat-square&logo=c-sharp&logoColor=white)</span>
<span class="s">![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)</span>
<span class="s">![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)</span>
<span class="s">![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)</span>
<span class="s">![PHP](https://img.shields.io/badge/PHP-777BB4?style=flat-square&logo=php&logoColor=white)</span>
<span class="s">![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=spring-boot&logoColor=white)</span>
<span class="s">![ASP.NET](https://img.shields.io/badge/ASP.NET-512BD4?style=flat-square&logo=dotnet&logoColor=white)</span>
<span class="s">![Laravel](https://img.shields.io/badge/Laravel-FF2D20?style=flat-square&logo=laravel&logoColor=white)</span>
<span class="s">![Angular](https://img.shields.io/badge/Angular-DD0031?style=flat-square&logo=angular&logoColor=white)</span>
<span class="s">![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black)</span>
<span class="s">![Vue.js](https://img.shields.io/badge/Vue.js-4FC08D?style=flat-square&logo=vue.js&logoColor=white)</span>
<span class="s">![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)</span>
<span class="s">![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)</span>

<span class="h">&lt;/div&gt;</span>

---

<span class="k">## 📊 GitHub Statistics</span>

<span class="h">&lt;div align="center"&gt;</span>
<span class="h">&lt;img src="https://github-readme-stats.vercel.app/api?douaem1=YOUR_douaem1&show_icons=true&theme=dark&bg_color=0d1117&border_color=c8f05a&title_color=c8f05a&icon_color=5af0c8&text_color=e8e8f0" height="165"/&gt;</span>
<span class="h">&lt;img src="https://github-readme-stats.vercel.app/api/top-langs/?douaem1=YOUR_douaem1&layout=compact&theme=dark&bg_color=0d1117&border_color=c8f05a&title_color=c8f05a&text_color=e8e8f0" height="165"/&gt;</span>
<span class="h">&lt;/div&gt;</span>

---

<span class="k">## 📫 Contact</span>

<span class="h">&lt;div align="center"&gt;</span>

<span class="s">[![Email](https://img.shields.io/badge/douae.moeniss%40gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:douae.moeniss@gmail.com)</span>
<span class="s">[![LinkedIn](https://img.shields.io/badge/LinkedIn-Douae_Moeniss-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/douae-moeniss-4b4417237/)</span>

<span class="c">*Open to PFA opportunities and collaborative tech projects.*</span>

<span class="h">&lt;img src="https://capsule-render.vercel.app/api?type=waving&color=c8f05a&height=80&section=footer" /&gt;</span>

<span class="h">&lt;/div&gt;</span>
      </pre>
    </div>
  </section>

  <!-- FOOTER -->
  <footer class="footer">
    <p class="footer-text">Seeking PFA 2025 · Open to collaboration</p>
    <a class="footer-cta" href="mailto:douae.moeniss@gmail.com">Let's build something →</a>
  </footer>

</div>

<script>
function copyReadme() {
  const content = `<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=c8f05a&height=120&section=header&text=Douae%20Moeniss&fontSize=42&fontColor=0a0a0f&fontAlignY=38&animation=fadeIn" />

### Computer Engineering Student · Full-Stack Developer · ENSA Tétouan

![](https://img.shields.io/badge/Available-PFA%202025-c8f05a?style=flat-square&labelColor=0a0a0f)
![](https://img.shields.io/badge/Location-Tétouan%2C%20Morocco-5af0c8?style=flat-square&labelColor=0a0a0f)

</div>

---

## 🧠 About Me

Computer Engineering student at **ENSA Tétouan**, passionate about designing scalable web applications, building intelligent systems, and contributing to innovative technology-driven projects.

---

## ⚙️ Tech Stack

<div align="center">

![C#](https://img.shields.io/badge/C%23-239120?style=flat-square&logo=c-sharp&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![PHP](https://img.shields.io/badge/PHP-777BB4?style=flat-square&logo=php&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=spring-boot&logoColor=white)
![ASP.NET](https://img.shields.io/badge/ASP.NET-512BD4?style=flat-square&logo=dotnet&logoColor=white)
![Laravel](https://img.shields.io/badge/Laravel-FF2D20?style=flat-square&logo=laravel&logoColor=white)
![Angular](https://img.shields.io/badge/Angular-DD0031?style=flat-square&logo=angular&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black)
![Vue.js](https://img.shields.io/badge/Vue.js-4FC08D?style=flat-square&logo=vue.js&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)

</div>

---

## 📊 GitHub Statistics

<div align="center">
<img src="https://github-readme-stats.vercel.app/api?douaem1=douaem1&show_icons=true&theme=dark&bg_color=0d1117&border_color=c8f05a&title_color=c8f05a&icon_color=5af0c8&text_color=e8e8f0" height="165"/>
<img src="https://github-readme-stats.vercel.app/api/top-langs/?douaem1=YOUR_douaem1&layout=compact&theme=dark&bg_color=0d1117&border_color=c8f05a&title_color=c8f05a&text_color=e8e8f0" height="165"/>
</div>

---

## 📫 Contact

<div align="center">

[![Email](https://img.shields.io/badge/douae.moeniss%40gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:douae.moeniss@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Douae_Moeniss-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/douae-moeniss-4b4417237/)

*Open to PFA opportunities and collaborative tech projects.*

<img src="https://capsule-render.vercel.app/api?type=waving&color=c8f05a&height=80&section=footer" />

</div>`;

  navigator.clipboard.writeText(content).then(() => {
    const btn = document.querySelector('.copy-btn');
    btn.textContent = 'Copied ✓';
    btn.style.color = '#5af0c8';
    btn.style.borderColor = 'rgba(90,240,200,0.4)';
    setTimeout(() => {
      btn.textContent = 'Copy';
      btn.style.color = '';
      btn.style.borderColor = '';
    }, 2500);
  });
}
</script>
</body>
</html>

	
<style>
@import url('https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Rajdhani:wght@400;500;600&family=Orbitron:wght@400;700&display=swap');

:root {
  --c0: #050d1a;
  --c1: #0a1628;
  --c2: #0e2040;
  --c3: #00d4ff;
  --c4: #7b2fff;
  --c5: #00ff9d;
  --c6: #ff6b35;
  --ct: #e2f0ff;
  --cm: #8ab4d4;
  --cd: #3a5a7a;
}

* { box-sizing: border-box; margin: 0; padding: 0; }

body, .root {
  background: var(--c0);
  color: var(--ct);
  font-family: 'Rajdhani', sans-serif;
  min-height: 100vh;
}

.root {
  max-width: 860px;
  margin: 0 auto;
  padding: 24px 20px;
  position: relative;
}

.grid-bg {
  position: fixed; top: 0; left: 0; width: 100%; height: 100%;
  background-image:
    linear-gradient(rgba(0,212,255,0.04) 1px, transparent 1px),
    linear-gradient(90deg, rgba(0,212,255,0.04) 1px, transparent 1px);
  background-size: 40px 40px;
  pointer-events: none;
  z-index: 0;
}

.content { position: relative; z-index: 1; }

/* HEADER */
.header {
  display: flex;
  align-items: flex-start;
  gap: 28px;
  padding: 28px;
  background: linear-gradient(135deg, var(--c1) 0%, #0a1e38 100%);
  border: 1px solid rgba(0,212,255,0.2);
  border-radius: 16px;
  margin-bottom: 16px;
  position: relative;
  overflow: hidden;
}

.header::before {
  content: '';
  position: absolute;
  top: -1px; left: 0;
  width: 60%; height: 2px;
  background: linear-gradient(90deg, var(--c3), var(--c4), transparent);
}

.header::after {
  content: '';
  position: absolute;
  bottom: 0; right: 0;
  width: 200px; height: 200px;
  background: radial-gradient(circle, rgba(123,47,255,0.12) 0%, transparent 70%);
  pointer-events: none;
}

.avatar-wrap {
  position: relative;
  flex-shrink: 0;
}

.avatar {
  width: 88px; height: 88px;
  border-radius: 50%;
  background: linear-gradient(135deg, #0e2040, #1a3060);
  border: 2px solid rgba(0,212,255,0.4);
  display: flex; align-items: center; justify-content: center;
  font-family: 'Orbitron', monospace;
  font-size: 28px; font-weight: 700;
  color: var(--c3);
  letter-spacing: 2px;
  position: relative;
}

.avatar-ring {
  position: absolute;
  top: -6px; left: -6px;
  width: 100px; height: 100px;
  border-radius: 50%;
  border: 1px solid rgba(0,212,255,0.2);
  animation: spin 8s linear infinite;
}

.avatar-ring::after {
  content: '';
  position: absolute;
  top: -2px; left: 40px;
  width: 6px; height: 6px;
  border-radius: 50%;
  background: var(--c3);
  box-shadow: 0 0 8px var(--c3);
}

.status-dot {
  position: absolute;
  bottom: 2px; right: 2px;
  width: 14px; height: 14px;
  border-radius: 50%;
  background: var(--c5);
  border: 2px solid var(--c1);
  box-shadow: 0 0 8px var(--c5);
}

.header-info { flex: 1; }

.name {
  font-family: 'Orbitron', monospace;
  font-size: 26px;
  font-weight: 700;
  color: #fff;
  letter-spacing: 1px;
  margin-bottom: 4px;
}

.name span { color: var(--c3); }

.role {
  font-family: 'Share Tech Mono', monospace;
  font-size: 13px;
  color: var(--c3);
  margin-bottom: 12px;
  letter-spacing: 1px;
}

.role::before { content: '> '; color: var(--c4); }

.tagline {
  font-size: 15px;
  color: var(--cm);
  line-height: 1.5;
  max-width: 480px;
  margin-bottom: 14px;
}

.badges {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.badge {
  display: flex;
  align-items: center;
  gap: 6px;
  padding: 4px 12px;
  border-radius: 20px;
  font-family: 'Share Tech Mono', monospace;
  font-size: 11px;
  letter-spacing: 0.5px;
  border: 1px solid;
}

.badge-blue { background: rgba(0,212,255,0.08); border-color: rgba(0,212,255,0.3); color: var(--c3); }
.badge-purple { background: rgba(123,47,255,0.08); border-color: rgba(123,47,255,0.3); color: #a78bfa; }
.badge-green { background: rgba(0,255,157,0.08); border-color: rgba(0,255,157,0.3); color: var(--c5); }

.dot { width: 6px; height: 6px; border-radius: 50%; }
.dot-blue { background: var(--c3); box-shadow: 0 0 4px var(--c3); }
.dot-purple { background: #a78bfa; box-shadow: 0 0 4px #a78bfa; }
.dot-green { background: var(--c5); box-shadow: 0 0 4px var(--c5); }

/* STATS ROW */
.stats-row {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 12px;
  margin-bottom: 16px;
}

.stat-card {
  background: var(--c1);
  border: 1px solid rgba(0,212,255,0.12);
  border-radius: 12px;
  padding: 16px 14px;
  text-align: center;
  position: relative;
  overflow: hidden;
}

.stat-card::before {
  content: '';
  position: absolute;
  top: 0; left: 50%; transform: translateX(-50%);
  width: 40%; height: 1px;
  background: var(--accent, var(--c3));
  opacity: 0.6;
}

.stat-num {
  font-family: 'Orbitron', monospace;
  font-size: 22px;
  font-weight: 700;
  color: var(--accent, var(--c3));
  margin-bottom: 4px;
}

.stat-label {
  font-family: 'Share Tech Mono', monospace;
  font-size: 10px;
  color: var(--cm);
  letter-spacing: 1px;
  text-transform: uppercase;
}

/* SKILLS */
.skills-section {
  background: var(--c1);
  border: 1px solid rgba(0,212,255,0.12);
  border-radius: 16px;
  padding: 22px;
  margin-bottom: 16px;
}

.section-title {
  font-family: 'Share Tech Mono', monospace;
  font-size: 11px;
  color: var(--c3);
  letter-spacing: 2px;
  text-transform: uppercase;
  margin-bottom: 18px;
  display: flex;
  align-items: center;
  gap: 10px;
}

.section-title::before {
  content: '//';
  color: var(--c4);
}

.section-title::after {
  content: '';
  flex: 1;
  height: 1px;
  background: linear-gradient(90deg, rgba(0,212,255,0.2), transparent);
}

.skills-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
}

.skill-item {
  display: flex;
  flex-direction: column;
  gap: 6px;
}

.skill-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.skill-name {
  font-size: 13px;
  color: var(--ct);
  font-weight: 500;
}

.skill-pct {
  font-family: 'Share Tech Mono', monospace;
  font-size: 11px;
  color: var(--skill-color, var(--c3));
}

.skill-bar {
  height: 4px;
  background: rgba(255,255,255,0.06);
  border-radius: 2px;
  overflow: hidden;
}

.skill-fill {
  height: 100%;
  border-radius: 2px;
  background: var(--skill-color, var(--c3));
  box-shadow: 0 0 6px var(--skill-color, var(--c3));
  width: var(--w, 80%);
  animation: fillBar 1.2s ease-out forwards;
  transform-origin: left;
}

@keyframes fillBar {
  from { width: 0%; }
  to { width: var(--w, 80%); }
}

/* PROJECTS */
.projects-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
  margin-bottom: 16px;
}

.project-card {
  background: var(--c1);
  border: 1px solid rgba(0,212,255,0.10);
  border-radius: 14px;
  padding: 18px;
  position: relative;
  overflow: hidden;
  cursor: pointer;
  transition: border-color 0.2s, transform 0.2s;
}

.project-card:hover {
  border-color: rgba(0,212,255,0.35);
  transform: translateY(-2px);
}

.project-card::after {
  content: '';
  position: absolute;
  top: 0; right: 0;
  width: 60px; height: 60px;
  background: radial-gradient(circle, var(--pc, rgba(0,212,255,0.1)) 0%, transparent 70%);
}

.project-tag {
  font-family: 'Share Tech Mono', monospace;
  font-size: 10px;
  color: var(--pc-text, var(--c3));
  letter-spacing: 1px;
  text-transform: uppercase;
  margin-bottom: 8px;
}

.project-name {
  font-size: 15px;
  font-weight: 600;
  color: #fff;
  margin-bottom: 6px;
}

.project-desc {
  font-size: 12px;
  color: var(--cm);
  line-height: 1.5;
  margin-bottom: 12px;
}

.project-meta {
  display: flex;
  gap: 12px;
}

.meta-item {
  font-family: 'Share Tech Mono', monospace;
  font-size: 10px;
  color: var(--cd);
  display: flex;
  align-items: center;
  gap: 4px;
}

.meta-item span { color: var(--cm); }

/* CONNECT */
.connect-row {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
  margin-bottom: 16px;
}

.connect-btn {
  background: var(--c1);
  border: 1px solid rgba(0,212,255,0.12);
  border-radius: 10px;
  padding: 12px 10px;
  text-align: center;
  cursor: pointer;
  transition: all 0.2s;
  text-decoration: none;
}

.connect-btn:hover {
  background: rgba(0,212,255,0.06);
  border-color: rgba(0,212,255,0.3);
}

.connect-icon {
  font-family: 'Share Tech Mono', monospace;
  font-size: 16px;
  margin-bottom: 5px;
  color: var(--ci, var(--c3));
}

.connect-label {
  font-family: 'Share Tech Mono', monospace;
  font-size: 10px;
  color: var(--cm);
  letter-spacing: 0.5px;
}

/* FOOTER / QUOTE */
.footer-quote {
  background: linear-gradient(135deg, rgba(123,47,255,0.08), rgba(0,212,255,0.06));
  border: 1px solid rgba(123,47,255,0.2);
  border-radius: 12px;
  padding: 18px 22px;
  text-align: center;
}

.quote-text {
  font-family: 'Share Tech Mono', monospace;
  font-size: 13px;
  color: var(--cm);
  letter-spacing: 0.5px;
  line-height: 1.6;
}

.quote-text .hl { color: var(--c3); }
.quote-text .hl2 { color: #a78bfa; }

@keyframes spin { to { transform: rotate(360deg); } }

@keyframes pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.4; }
}

.blink { animation: pulse 1.8s ease-in-out infinite; }

/* CONTRIB GRAPH */
.contrib-section {
  background: var(--c1);
  border: 1px solid rgba(0,212,255,0.12);
  border-radius: 16px;
  padding: 22px;
  margin-bottom: 16px;
}

.contrib-grid {
  display: flex;
  gap: 3px;
  flex-wrap: wrap;
  margin-top: 4px;
}

.contrib-week {
  display: flex;
  flex-direction: column;
  gap: 3px;
}

.contrib-day {
  width: 11px;
  height: 11px;
  border-radius: 2px;
  background: var(--cb, rgba(0,212,255,0.06));
}
</style>

<div class="grid-bg"></div>
<div class="root content">

  <!-- HEADER -->
  <div class="header">
    <div class="avatar-wrap">
      <div class="avatar">AP
        <div class="status-dot"></div>
      </div>
      <div class="avatar-ring"></div>
    </div>
    <div class="header-info">
      <div class="name">Aman <span>Patel</span></div>
      <div class="role">AI/ML Engineer &amp; Data Scientist</div>
      <div class="tagline">Building intelligent systems at the intersection of machine learning, deep learning, and real-world impact. Turning data into decisions.</div>
      <div class="badges">
        <div class="badge badge-blue"><div class="dot dot-blue"></div>Open to Work</div>
        <div class="badge badge-purple"><div class="dot dot-purple"></div>ML Research</div>
        <div class="badge badge-green"><div class="dot dot-green"></div>India 🇮🇳</div>
      </div>
    </div>
  </div>

  <!-- STATS -->
  <!-- Replace YOUR_USERNAME with your GitHub username -->
  ![GitHub Stats](https://github-readme-stats.vercel.app/api
    ?username=amanpatel26
    &show_icons=true
    &count_private=true
    &theme=tokyonight
    &hide_border=true
    &bg_color=050d1a
    &title_color=00d4ff
    &icon_color=7b2fff)

  <!-- SKILLS -->
  ![Top Languages](https://github-readme-stats.vercel.app/api/top-langs
    ?username=AmanPatel
    &layout=compact
    &langs_count=8
    &theme=tokyonight
    &hide_border=true
    &bg_color=050d1a
    &title_color=00d4ff)

  <!-- PROJECTS -->
  <div align="center">
  
  ![Stats](https://github-readme-stats.vercel.app/api?username=AmanPatel&show_icons=true&theme=tokyonight&hide_border=true&bg_color=050d1a&title_color=00d4ff&icon_color=7b2fff&count_private=true)
  ![Langs](https://github-readme-stats.vercel.app/api/top-langs?username=AmanPatel&layout=compact&theme=tokyonight&hide_border=true&bg_color=050d1a&title_color=00d4ff)
  
  </div>

  <!-- CONTRIBUTION GRAPH -->
  <div class="contrib-section">
    <div class="section-title">Activity Matrix</div>
    <div class="contrib-grid" id="cgrid"></div>
  </div>

  <!-- CONNECT -->
  <div class="connect-row">
    <div class="connect-btn" style="--ci: var(--c3)">
      <div class="connect-icon">[GH]</div>
      <div class="connect-label">GitHub</div>
    </div>
    <div class="connect-btn" style="--ci: #0a66c2">
      <div class="connect-icon">[in]</div>
      <div class="connect-label">LinkedIn</div>
    </div>
    <div class="connect-btn" style="--ci: #a78bfa">
      <div class="connect-icon">[@]</div>
      <div class="connect-label">Email</div>
    </div>
    <div class="connect-btn" style="--ci: var(--c6)">
      <div class="connect-icon">[kb]</div>
      <div class="connect-label">Kaggle</div>
    </div>
  </div>

  <!-- QUOTE -->
  <div class="footer-quote">
    <div class="quote-text">
      <span class="hl2">"</span> The goal is to turn <span class="hl">data</span> into information, information into <span class="hl2">insight</span>, and insight into <span class="hl">intelligence</span>. <span class="hl2">"</span>
    </div>
  </div>

</div>

<script>
const grid = document.getElementById('cgrid');
const levels = [0, 0.06, 0.14, 0.3, 0.55, 0.85];
const colors = ['rgba(0,212,255,', 'rgba(0,255,157,', 'rgba(123,47,255,'];
for (let w = 0; w < 52; w++) {
  const week = document.createElement('div');
  week.className = 'contrib-week';
  for (let d = 0; d < 7; d++) {
    const day = document.createElement('div');
    day.className = 'contrib-day';
    const r = Math.random();
    const colorSet = colors[Math.floor(Math.random() * colors.length)];
    if (r > 0.55) {
      const intensity = levels[Math.floor(Math.random() * 3) + 3];
      day.style.cssText = `background: ${colorSet}${intensity}); box-shadow: 0 0 3px ${colorSet}${intensity * 0.5})`;
    } else if (r > 0.3) {
      day.style.background = `rgba(0,212,255,0.10)`;
    }
    week.appendChild(day);
  }
  grid.appendChild(week);
}
</script>

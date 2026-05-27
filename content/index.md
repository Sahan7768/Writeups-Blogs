---
title: "SAHAN · Cyber Security Hub"
---

<link href="https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Rajdhani:wght@400;600;700&display=swap" rel="stylesheet"/>

<style>
.page-hero-wrapper {
  background: #0a0e0a;
  color: #c8ffc8;
  font-family: 'Share Tech Mono', monospace;
  border-radius: 8px;
  overflow: hidden;
  position: relative;
  padding: 2.5rem 2rem 3rem;
  margin-bottom: 2rem;
}

.page-hero-wrapper::before {
  content: '';
  position: absolute;
  inset: 0;
  background: repeating-linear-gradient(
    0deg,
    transparent,
    transparent 2px,
    rgba(0,255,0,0.015) 2px,
    rgba(0,255,0,0.015) 4px
  );
  pointer-events: none;
  z-index: 0;
}

.page-hero-wrapper::after {
  content: '';
  position: absolute;
  inset: 0;
  background-image:
    linear-gradient(rgba(0,200,0,0.04) 1px, transparent 1px),
    linear-gradient(90deg, rgba(0,200,0,0.04) 1px, transparent 1px);
  background-size: 40px 40px;
  pointer-events: none;
  z-index: 0;
}

.cyber-inner {
  position: relative;
  z-index: 1;
}

.topbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid rgba(0,255,80,0.2);
  padding-bottom: 0.75rem;
  margin-bottom: 2.5rem;
  font-size: 11px;
  color: rgba(100,255,100,0.5);
  letter-spacing: 0.12em;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.status-dot {
  display: inline-block;
  width: 7px; height: 7px;
  border-radius: 50%;
  background: #00ff50;
  box-shadow: 0 0 6px #00ff50;
  animation: pulse 2s infinite;
  vertical-align: middle;
  margin-right: 5px;
}

@keyframes pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.3; }
}

.hero-grid {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 1.5rem;
  flex-wrap: wrap;
  margin-bottom: 2.5rem;
}

.hero-label {
  font-size: 11px;
  letter-spacing: 0.2em;
  color: rgba(0,255,80,0.5);
  margin-bottom: 0.5rem;
  text-transform: uppercase;
}

.hero-name {
  font-family: 'Rajdhani', sans-serif;
  font-size: clamp(3rem, 8vw, 5.2rem);
  font-weight: 700;
  line-height: 0.9;
  color: #00ff50;
  letter-spacing: -0.02em;
  text-shadow: 0 0 40px rgba(0,255,80,0.3);
  animation: flicker 8s infinite;
  margin: 0;
}

@keyframes flicker {
  0%, 95%, 97%, 100% { opacity: 1; }
  96% { opacity: 0.85; }
}

.hero-tagline {
  font-family: 'Rajdhani', sans-serif;
  font-size: 1rem;
  color: rgba(180,255,180,0.65);
  margin-top: 0.9rem;
  letter-spacing: 0.05em;
  line-height: 1.7;
}

.hero-tagline span { color: #00ff80; }

.hex-wrap {
  flex-shrink: 0;
  width: 140px;
  height: 162px;
  position: relative;
}

.hex-wrap svg { position: absolute; top: 0; left: 0; }

.hex-center {
  position: absolute;
  top: 50%; left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
  line-height: 1;
}

.hex-initial {
  font-family: 'Rajdhani', sans-serif;
  font-size: 4rem;
  font-weight: 700;
  color: #00ff50;
  text-shadow: 0 0 30px rgba(0,255,80,0.5);
  display: block;
}

.hex-sub {
  font-size: 9px;
  letter-spacing: 0.25em;
  color: rgba(0,255,80,0.5);
  text-transform: uppercase;
}

/* ABOUT */
.about-block {
  background: rgba(0,255,80,0.03);
  border: 1px solid rgba(0,255,80,0.12);
  border-left: 3px solid rgba(0,255,80,0.6);
  padding: 1.25rem 1.5rem;
  margin-bottom: 2.5rem;
  position: relative;
}

.about-block::before {
  content: '// ABOUT';
  position: absolute;
  top: -9px; left: 12px;
  font-size: 10px;
  letter-spacing: 0.15em;
  color: rgba(0,255,80,0.5);
  background: #0a0e0a;
  padding: 0 6px;
}

.about-block p {
  font-size: 13px;
  line-height: 1.9;
  color: rgba(180,255,180,0.75);
  margin: 0;
}

.about-block p strong { color: #00ff80; font-weight: 400; }

/* SECTION LABEL */
.sec-label {
  font-size: 10px;
  letter-spacing: 0.25em;
  color: rgba(0,255,80,0.45);
  text-transform: uppercase;
  margin-bottom: 1rem;
}

/* TOOLS */
.tools-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
  gap: 12px;
  margin-bottom: 2.5rem;
}

.tool-card {
  background: rgba(0,20,0,0.8);
  border: 1px solid rgba(0,255,80,0.12);
  padding: 1rem;
  position: relative;
  transition: border-color 0.2s, background 0.2s;
}

.tool-card:hover {
  border-color: rgba(0,255,80,0.5);
  background: rgba(0,255,80,0.05);
}

.tool-corner {
  position: absolute;
  top: 6px; right: 8px;
  width: 8px; height: 8px;
  border-top: 1px solid rgba(0,255,80,0.3);
  border-right: 1px solid rgba(0,255,80,0.3);
}

.tool-icon { font-size: 22px; display: block; margin-bottom: 0.5rem; }

.tool-name {
  font-family: 'Rajdhani', sans-serif;
  font-size: 1.05rem;
  font-weight: 600;
  color: #00ff80;
  letter-spacing: 0.05em;
}

.tool-desc {
  font-size: 10px;
  color: rgba(100,200,100,0.5);
  margin-top: 2px;
  letter-spacing: 0.04em;
}

/* PLATFORMS */
.platforms-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
  margin-bottom: 2.5rem;
}

.platform-card {
  border: 1px solid rgba(0,255,80,0.15);
  padding: 1rem 1.25rem;
  background: rgba(0,10,0,0.6);
}

.p-label {
  font-size: 10px;
  letter-spacing: 0.2em;
  color: rgba(0,255,80,0.4);
  text-transform: uppercase;
  margin-bottom: 0.3rem;
}

.p-title {
  font-family: 'Rajdhani', sans-serif;
  font-size: 1.3rem;
  font-weight: 600;
  color: #c8ffc8;
  letter-spacing: 0.05em;
}

.p-status {
  margin-top: 0.5rem;
  font-size: 10px;
  color: rgba(0,255,80,0.5);
  display: flex;
  align-items: center;
  gap: 5px;
}

.p-status-dot {
  width: 5px; height: 5px;
  border-radius: 50%;
  background: #00ff50;
  display: inline-block;
  flex-shrink: 0;
}

/* BLOG LINK */
.blog-row {
  border: 1px solid rgba(0,255,80,0.12);
  padding: 1.25rem 1.5rem;
  background: rgba(0,15,0,0.5);
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
  margin-bottom: 2.5rem;
  cursor: pointer;
  transition: border-color 0.2s;
  text-decoration: none;
}

.blog-row:hover { border-color: rgba(0,255,80,0.4); }

.blog-inner-label {
  font-size: 10px;
  letter-spacing: 0.2em;
  color: rgba(0,255,80,0.4);
  text-transform: uppercase;
  margin-bottom: 0.3rem;
}

.blog-title {
  font-family: 'Rajdhani', sans-serif;
  font-size: 1.1rem;
  font-weight: 600;
  color: #c8ffc8;
}

.blog-arrow {
  font-size: 1.4rem;
  color: rgba(0,255,80,0.4);
  flex-shrink: 0;
  transition: transform 0.2s, color 0.2s;
}

.blog-row:hover .blog-arrow {
  transform: translateX(4px);
  color: #00ff80;
}

/* CURSOR BLINK */
.cursor {
  display: inline-block;
  width: 9px; height: 14px;
  background: #00ff50;
  animation: blink 1s step-end infinite;
  vertical-align: middle;
  margin-left: 3px;
}

@keyframes blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0; }
}

/* FOOTER */
.cyber-footer {
  border-top: 1px solid rgba(0,255,80,0.1);
  padding-top: 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 10px;
  color: rgba(0,200,0,0.3);
  letter-spacing: 0.12em;
  flex-wrap: wrap;
  gap: 0.5rem;
}

/* fade in */
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(16px); }
  to   { opacity: 1; transform: translateY(0); }
}

.hero-grid    { animation: fadeUp 0.5s ease both; }
.about-block  { animation: fadeUp 0.5s 0.1s ease both; }
.tools-grid   { animation: fadeUp 0.5s 0.2s ease both; }
.platforms-grid { animation: fadeUp 0.5s 0.3s ease both; }
.blog-row     { animation: fadeUp 0.5s 0.4s ease both; }
</style>

<div class="page-hero-wrapper">
<div class="cyber-inner">

<div class="topbar">
  <span>SAHAN://CYBER_HUB v1.0</span>
  <span><span class="status-dot"></span>SECURE SESSION ACTIVE</span>
  <span id="cyber-clock">--:--:--</span>
</div>

<div class="hero-grid">
  <div>
    <div class="hero-label">// IDENTITY CONFIRMED</div>
    <div class="hero-name">SAHAN</div>
    <div class="hero-tagline">
      <span>CS Undergraduate</span> · Eastern University, Trincomalee<br/>
      Pursuing the path of <span>Cybersecurity</span> — one lab at a time.
    </div>
  </div>
  <div class="hex-wrap">
    <svg width="140" height="162" viewBox="0 0 140 162">
      <polygon points="70,4 136,38 136,124 70,158 4,124 4,38"
        fill="none" stroke="rgba(0,255,80,0.35)" stroke-width="1"/>
      <polygon points="70,18 122,47 122,115 70,144 18,115 18,47"
        fill="rgba(0,255,80,0.04)" stroke="rgba(0,255,80,0.15)" stroke-width="0.5"/>
      <line x1="70" y1="4"   x2="70"  y2="14"  stroke="#00ff50" stroke-width="2"/>
      <line x1="136" y1="38" x2="127" y2="43"  stroke="#00ff50" stroke-width="2"/>
      <line x1="136" y1="124" x2="127" y2="119" stroke="#00ff50" stroke-width="2"/>
      <line x1="70" y1="158" x2="70"  y2="148" stroke="#00ff50" stroke-width="2"/>
      <line x1="4"  y1="124" x2="13"  y2="119" stroke="#00ff50" stroke-width="2"/>
      <line x1="4"  y1="38"  x2="13"  y2="43"  stroke="#00ff50" stroke-width="2"/>
    </svg>
    <div class="hex-center">
      <span class="hex-initial">S</span>
      <span class="hex-sub">SEC&nbsp;OPS</span>
    </div>
  </div>
</div>

<div class="about-block">
  <p>
    I'm a <strong>computer science undergraduate</strong> at Eastern University's Trincomalee Campus,
    walking the <strong>cybersecurity path</strong> to build a professional career in offensive security.
    I sharpen my skills daily on <strong>TryHackMe</strong> and <strong>HackTheBox</strong> —
    every flag captured becomes a <strong>writeup</strong> published here as a blog.
  </p>
</div>

<div class="sec-label">// ARSENAL</div>
<div class="tools-grid">
  <div class="tool-card">
    <div class="tool-corner"></div>
    <span class="tool-icon">🦈</span>
    <div class="tool-name">Wireshark</div>
    <div class="tool-desc">Packet analysis &amp; network forensics</div>
  </div>
  <div class="tool-card">
    <div class="tool-corner"></div>
    <span class="tool-icon">🗺️</span>
    <div class="tool-name">Nmap</div>
    <div class="tool-desc">Network scanning &amp; enumeration</div>
  </div>
  <div class="tool-card">
    <div class="tool-corner"></div>
    <span class="tool-icon">⚔️</span>
    <div class="tool-name">Metasploit</div>
    <div class="tool-desc">Exploitation framework</div>
  </div>
</div>

<div class="sec-label">// ACTIVE TRAINING PLATFORMS</div>
<div class="platforms-grid">
  <div class="platform-card">
    <div class="p-label">Platform 01</div>
    <div class="p-title">TryHackMe</div>
    <div class="p-status"><span class="p-status-dot"></span> Learning paths · CTF rooms</div>
  </div>
  <div class="platform-card">
    <div class="p-label">Platform 02</div>
    <div class="p-title">HackTheBox</div>
    <div class="p-status"><span class="p-status-dot"></span> Machine writeups · Labs</div>
  </div>
</div>

<div class="blog-row">
  <div>
    <div class="blog-inner-label">// LATEST WRITEUP</div>
    <div class="blog-title">Browse all CTF walkthroughs &amp; lab writeups <span class="cursor"></span></div>
  </div>
  <div class="blog-arrow">⟶</div>
</div>

<div class="cyber-footer">
  <span>SAHAN · EASTERN UNIVERSITY · TRINCOMALEE</span>
  <span>CYBERSECURITY · [UNDERGRADUATE]</span>
</div>

</div>
</div>

<script>
(function(){
  function tick(){
    var n=new Date(), pad=function(x){return String(x).padStart(2,'0');};
    var el=document.getElementById('cyber-clock');
    if(el) el.textContent=pad(n.getHours())+':'+pad(n.getMinutes())+':'+pad(n.getSeconds());
  }
  tick(); setInterval(tick,1000);
})();
</script>

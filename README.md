
<style>
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body { font-family: var(--font-mono); }
  .root { padding: 1.5rem 0; }
  .terminal { background: #0d1117; border-radius: var(--border-radius-lg); border: 0.5px solid #30363d; overflow: hidden; }
  .topbar { background: #161b22; padding: 12px 16px; display: flex; align-items: center; gap: 8px; border-bottom: 0.5px solid #30363d; }
  .dot { width: 12px; height: 12px; border-radius: 50%; }
  .dot-r { background: #ff5f57; }
  .dot-y { background: #febc2e; }
  .dot-g { background: #28c840; }
  .title-bar { color: #8b949e; font-size: 13px; margin-left: auto; margin-right: auto; font-family: var(--font-mono); }
  .body { padding: 20px 24px; min-height: 320px; }
  .prompt { display: flex; gap: 8px; align-items: flex-start; margin-bottom: 6px; }
  .ps1-user { color: #79c0ff; font-size: 13px; font-family: var(--font-mono); }
  .ps1-at { color: #8b949e; font-size: 13px; }
  .ps1-host { color: #7ee787; font-size: 13px; font-family: var(--font-mono); }
  .ps1-path { color: #d2a8ff; font-size: 13px; font-family: var(--font-mono); }
  .ps1-dollar { color: #8b949e; font-size: 13px; }
  .cmd { color: #e6edf3; font-size: 13px; font-family: var(--font-mono); }
  .output { margin: 4px 0 18px 0; padding-left: 0; }
  .line { font-size: 13px; font-family: var(--font-mono); line-height: 1.7; color: #c9d1d9; }
  .key { color: #79c0ff; }
  .val { color: #a5d6ff; }
  .str { color: #a5d6ff; }
  .arr-item { color: #7ee787; }
  .comment { color: #8b949e; }
  .bracket { color: #e6edf3; }
  .fn-color { color: #ffa657; }
  .ret { color: #f0883e; }
  .tab1 { padding-left: 20px; }
  .tab2 { padding-left: 40px; }
  .section-tabs { display: flex; gap: 2px; margin-bottom: 1px; flex-wrap: wrap; }
  .tab { background: #161b22; border: 0.5px solid #30363d; border-bottom: none; padding: 6px 14px; font-size: 12px; font-family: var(--font-mono); color: #8b949e; cursor: pointer; border-radius: 6px 6px 0 0; transition: background 0.15s, color 0.15s; }
  .tab.active { background: #0d1117; color: #79c0ff; border-color: #30363d; }
  .tab:hover:not(.active) { background: #21262d; color: #c9d1d9; }
  .panel { display: none; }
  .panel.active { display: block; }
  .badge-row { display: flex; flex-wrap: wrap; gap: 6px; margin: 4px 0 12px 0; }
  .badge { display: inline-block; padding: 3px 10px; border-radius: 4px; font-size: 11px; font-family: var(--font-mono); font-weight: 500; background: #21262d; color: #7ee787; border: 0.5px solid #3fb950; }
  .badge.blue { color: #79c0ff; border-color: #388bfd; }
  .badge.purple { color: #d2a8ff; border-color: #8957e5; }
  .badge.orange { color: #ffa657; border-color: #d29922; }
  .badge.pink { color: #ff7b72; border-color: #da3633; }
  .proj-card { background: #161b22; border: 0.5px solid #30363d; border-radius: 8px; padding: 12px 14px; margin-bottom: 10px; }
  .proj-name { color: #79c0ff; font-size: 13px; font-family: var(--font-mono); font-weight: 500; }
  .proj-desc { color: #8b949e; font-size: 12px; margin: 4px 0 6px; line-height: 1.5; }
  .proj-stack { display: flex; flex-wrap: wrap; gap: 4px; }
  .stack-tag { font-size: 10px; font-family: var(--font-mono); padding: 2px 7px; border-radius: 3px; background: #0d1117; border: 0.5px solid #30363d; color: #7ee787; }
  .cert-row { display: flex; align-items: center; gap: 10px; padding: 7px 0; border-bottom: 0.5px solid #21262d; }
  .cert-icon { color: #ffa657; font-size: 16px; flex-shrink: 0; }
  .cert-name { color: #c9d1d9; font-size: 12px; }
  .cert-org { color: #8b949e; font-size: 11px; }
  .cursor { display: inline-block; width: 8px; height: 14px; background: #79c0ff; animation: blink 1s step-end infinite; vertical-align: middle; margin-left: 2px; }
  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }
  .copy-btn { margin-left: auto; background: transparent; border: 0.5px solid #30363d; color: #8b949e; font-size: 11px; padding: 3px 10px; border-radius: 4px; cursor: pointer; font-family: var(--font-mono); transition: background 0.15s, color 0.15s; }
  .copy-btn:hover { background: #21262d; color: #c9d1d9; }
  .stat-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 8px; margin: 8px 0 12px; }
  .stat-box { background: #161b22; border: 0.5px solid #30363d; border-radius: 8px; padding: 10px 12px; text-align: center; }
  .stat-val { color: #7ee787; font-size: 18px; font-weight: 500; font-family: var(--font-mono); }
  .stat-lbl { color: #8b949e; font-size: 11px; margin-top: 2px; }
</style>

<div class="root">
  <h2 class="sr-only">Interactive GitHub profile card for Raihan K Rasily, MEAN Stack Developer</h2>
  <div class="terminal">
    <div class="topbar">
      <div class="dot dot-r"></div>
      <div class="dot dot-y"></div>
      <div class="dot dot-g"></div>
      <span class="title-bar">raihan@dev ~ profile.sh</span>
    </div>

    <div style="background:#0d1117; padding: 0 24px 0;">
      <div style="padding-top:16px; display:flex; align-items:center; gap:8px; flex-wrap:wrap;">
        <span class="ps1-user">raihan</span><span class="ps1-at">@</span><span class="ps1-host">github</span><span class="ps1-at">:</span><span class="ps1-path">~/profile</span><span class="ps1-dollar"> $</span>
        <span class="cmd">node about.js</span>
      </div>
      <div class="output" style="margin-top:10px;">
        <div class="line"><span class="bracket">{</span></div>
        <div class="line tab1"><span class="key">name</span><span class="comment">:</span> <span class="str">"Raihan K Rasily"</span><span class="comment">,</span></div>
        <div class="line tab1"><span class="key">role</span><span class="comment">:</span> <span class="str">"MEAN Stack Developer @ CarvingSoft Technologies"</span><span class="comment">,</span></div>
        <div class="line tab1"><span class="key">location</span><span class="comment">:</span> <span class="str">"Kerala, India 🌴"</span><span class="comment">,</span></div>
        <div class="line tab1"><span class="key">experience</span><span class="comment">:</span> <span class="str">"1+ year Full Stack Development"</span><span class="comment">,</span></div>
        <div class="line tab1"><span class="key">stack</span><span class="comment">:</span> <span class="bracket">[</span><span class="arr-item">"MongoDB"</span><span class="comment">, </span><span class="arr-item">"Express.js"</span><span class="comment">, </span><span class="arr-item">"Angular"</span><span class="comment">, </span><span class="arr-item">"Node.js"</span><span class="comment">, </span><span class="arr-item">"React"</span><span class="bracket">]</span><span class="comment">,</span></div>
        <div class="line tab1"><span class="key">funFact</span><span class="comment">:</span> <span class="str">"I debug with console.log and I'm not ashamed 😄"</span><span class="comment">,</span></div>
        <div class="line tab1"><span class="fn-color">motto</span><span class="bracket">()</span> <span class="comment">→</span> <span class="ret">"Ship fast. Refactor smart. Learn always."</span></div>
        <div class="line"><span class="bracket">}</span></div>
      </div>
    </div>

    <div style="padding: 0 24px 0; background:#0d1117;">
      <div style="display:flex; align-items:center; gap:8px; margin-bottom:12px; flex-wrap:wrap;">
        <span class="ps1-user">raihan</span><span class="ps1-at">@</span><span class="ps1-host">github</span><span class="ps1-at">:</span><span class="ps1-path">~/profile</span><span class="ps1-dollar"> $</span>
        <span class="cmd">cat details.json</span>
        <button class="copy-btn" onclick="copyReadme()" id="copybtn"><i class="ti ti-copy" aria-hidden="true"></i> copy readme</button>
      </div>

      <div class="section-tabs">
        <div class="tab active" onclick="switchTab('skills')">skills.json</div>
        <div class="tab" onclick="switchTab('projects')">projects.json</div>
        <div class="tab" onclick="switchTab('certs')">certs.json</div>
        <div class="tab" onclick="switchTab('learning')">learning.json</div>
      </div>
    </div>

    <div style="background:#0d1117; padding: 0 24px 16px; border-top: 0.5px solid #30363d;">

      <div class="panel active" id="panel-skills">
        <div style="height:12px;"></div>
        <div class="line comment" style="margin-bottom:8px;">// languages</div>
        <div class="badge-row">
          <span class="badge pink">JavaScript</span>
          <span class="badge pink">TypeScript</span>
          <span class="badge pink">Python</span>
          <span class="badge pink">PHP</span>
          <span class="badge pink">Java</span>
          <span class="badge pink">C++</span>
          <span class="badge pink">SQL</span>
        </div>
        <div class="line comment" style="margin-bottom:8px; margin-top:4px;">// frontend</div>
        <div class="badge-row">
          <span class="badge blue">Angular</span>
          <span class="badge blue">React.js</span>
          <span class="badge blue">RxJS</span>
          <span class="badge blue">Tailwind CSS</span>
          <span class="badge blue">Bootstrap</span>
          <span class="badge blue">HTML5</span>
          <span class="badge blue">CSS3</span>
        </div>
        <div class="line comment" style="margin-bottom:8px; margin-top:4px;">// backend</div>
        <div class="badge-row">
          <span class="badge">Node.js</span>
          <span class="badge">Express.js</span>
          <span class="badge">Socket.IO</span>
          <span class="badge">JWT Auth</span>
          <span class="badge">RBAC</span>
          <span class="badge">REST APIs</span>
        </div>
        <div class="line comment" style="margin-bottom:8px; margin-top:4px;">// databases & tools</div>
        <div class="badge-row">
          <span class="badge orange">MongoDB</span>
          <span class="badge orange">MySQL</span>
          <span class="badge purple">Git</span>
          <span class="badge purple">GitHub</span>
          <span class="badge purple">Postman</span>
          <span class="badge purple">Linux</span>
          <span class="badge purple">NGINX</span>
          <span class="badge purple">Netlify</span>
        </div>
      </div>

      <div class="panel" id="panel-projects">
        <div style="height:12px;"></div>
        <div class="proj-card">
          <div class="proj-name">🎫 TickTrix</div>
          <div class="proj-desc">Multi-tenant SaaS service ticket management — branch isolation, real-time tracking, GST invoicing, subscription tiers (Basic/Pro)</div>
          <div class="proj-stack">
            <span class="stack-tag">MongoDB</span><span class="stack-tag">Express</span><span class="stack-tag">Angular</span><span class="stack-tag">Node.js</span><span class="stack-tag">Socket.IO</span><span class="stack-tag">RxJS</span><span class="stack-tag">JWT</span>
          </div>
        </div>
        <div class="proj-card">
          <div class="proj-name">🍽️ Zerano</div>
          <div class="proj-desc">Restaurant POS — order & table management, KOT system, live kitchen updates, attendance & RBAC</div>
          <div class="proj-stack">
            <span class="stack-tag">MongoDB</span><span class="stack-tag">Express</span><span class="stack-tag">Angular</span><span class="stack-tag">Node.js</span><span class="stack-tag">Socket.IO</span>
          </div>
        </div>
        <div class="proj-card">
          <div class="proj-name">⚡ SlotMySocket</div>
          <div class="proj-desc">EV charging slot management — station discovery, real-time availability & slot reservation</div>
          <div class="proj-stack">
            <span class="stack-tag">React</span><span class="stack-tag">Node.js</span><span class="stack-tag">Express</span><span class="stack-tag">MongoDB</span>
          </div>
        </div>
        <div class="proj-card">
          <div class="proj-name">📍 FlexPoint</div>
          <div class="proj-desc">Location-based flex/hoarding management — shop discovery, ad management, location search</div>
          <div class="proj-stack">
            <span class="stack-tag">Angular</span><span class="stack-tag">Node.js</span><span class="stack-tag">Express</span><span class="stack-tag">MySQL</span>
          </div>
        </div>
        <div class="proj-card">
          <div class="proj-name">🚗 DriveMate</div>
          <div class="proj-desc">Car rental platform — vehicle management, driver allocation, booking & rental operations</div>
          <div class="proj-stack">
            <span class="stack-tag">PHP</span><span class="stack-tag">MySQL</span><span class="stack-tag">HTML</span><span class="stack-tag">CSS</span>
          </div>
        </div>
      </div>

      <div class="panel" id="panel-certs">
        <div style="height:12px;"></div>
        <div class="cert-row">
          <i class="ti ti-certificate cert-icon" aria-hidden="true"></i>
          <div><div class="cert-name">Joy of Using Python</div><div class="cert-org">NPTEL</div></div>
        </div>
        <div class="cert-row">
          <i class="ti ti-certificate cert-icon" aria-hidden="true"></i>
          <div><div class="cert-name">Software Testing</div><div class="cert-org">NPTEL</div></div>
        </div>
        <div class="cert-row">
          <i class="ti ti-certificate cert-icon" aria-hidden="true"></i>
          <div><div class="cert-name">Introduction to SQL</div><div class="cert-org">Simplilearn</div></div>
        </div>
        <div class="cert-row">
          <i class="ti ti-certificate cert-icon" aria-hidden="true"></i>
          <div><div class="cert-name">Introduction to Cybercrime</div><div class="cert-org">Simplilearn</div></div>
        </div>
        <div class="cert-row" style="border:none;">
          <i class="ti ti-certificate cert-icon" aria-hidden="true"></i>
          <div><div class="cert-name">Introduction to AI</div><div class="cert-org">Simplilearn</div></div>
        </div>
        <div style="margin-top:16px;" class="line comment">// currently learning</div>
        <div class="badge-row" style="margin-top:8px;">
          <span class="badge orange">AWS</span>
          <span class="badge orange">Docker</span>
          <span class="badge orange">CI/CD</span>
          <span class="badge orange">System Design</span>
          <span class="badge orange">Advanced TypeScript</span>
        </div>
      </div>

      <div class="panel" id="panel-learning">
        <div style="height:12px;"></div>
        <div class="line comment" style="margin-bottom:10px;">// active learning roadmap</div>
        <div class="line tab1" style="margin-bottom:6px;"><span class="key">cloud</span> <span class="comment">→</span> <span class="arr-item">AWS (EC2, S3, Lambda)</span> <span class="comment">|</span> <span class="arr-item">GCP Fundamentals</span></div>
        <div class="line tab1" style="margin-bottom:6px;"><span class="key">devops</span> <span class="comment">→</span> <span class="arr-item">Docker</span> <span class="comment">|</span> <span class="arr-item">GitHub Actions</span> <span class="comment">|</span> <span class="arr-item">CI/CD Pipelines</span></div>
        <div class="line tab1" style="margin-bottom:6px;"><span class="key">architecture</span> <span class="comment">→</span> <span class="arr-item">Microservices</span> <span class="comment">|</span> <span class="arr-item">Caching</span> <span class="comment">|</span> <span class="arr-item">Load Balancing</span></div>
        <div class="line tab1" style="margin-bottom:6px;"><span class="key">typescript</span> <span class="comment">→</span> <span class="arr-item">Advanced Generics</span> <span class="comment">|</span> <span class="arr-item">Decorators</span> <span class="comment">|</span> <span class="arr-item">Utility Types</span></div>
        <div class="line tab1" style="margin-bottom:6px;"><span class="key">security</span> <span class="comment">→</span> <span class="arr-item">OAuth 2.0</span> <span class="comment">|</span> <span class="arr-item">HTTPS/TLS</span> <span class="comment">|</span> <span class="arr-item">API Rate Limiting</span></div>
        <div style="margin-top:16px;" class="line comment">// stat snapshot</div>
        <div class="stat-grid" style="margin-top:10px;">
          <div class="stat-box"><div class="stat-val">5+</div><div class="stat-lbl">projects shipped</div></div>
          <div class="stat-box"><div class="stat-val">1+</div><div class="stat-lbl">years experience</div></div>
          <div class="stat-box"><div class="stat-val">5</div><div class="stat-lbl">certifications</div></div>
        </div>
      </div>

      <div style="display:flex; align-items:center; gap:8px; margin-top:16px; flex-wrap:wrap;">
        <span class="ps1-user">raihan</span><span class="ps1-at">@</span><span class="ps1-host">github</span><span class="ps1-at">:</span><span class="ps1-path">~/profile</span><span class="ps1-dollar"> $</span>
        <span class="cursor"></span>
      </div>
    </div>
  </div>
</div>

<script>
function switchTab(name) {
  document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
  document.querySelectorAll('.panel').forEach(p => p.classList.remove('active'));
  event.target.classList.add('active');
  document.getElementById('panel-' + name).classList.add('active');
}

function copyReadme() {
  const text = `# Hi there, I'm Raihan K Rasily 👋\n\n**MEAN Stack Developer | Turning ideas into production-ready apps**\n\n- 💼 MEAN Stack Developer @ CarvingSoft Technologies\n- 📍 Kerala, India\n- 🛠️ Stack: MongoDB · Express.js · Angular · Node.js · React · Socket.IO\n- 🚀 Building: TickTrix · Zerano · SlotMySocket\n- 🌱 Learning: AWS · Docker · System Design · CI/CD\n- 💬 Fun fact: I debug with console.log and I'm not ashamed 😄\n\n> "Ship fast. Refactor smart. Learn always."\n\n[![GitHub](https://img.shields.io/badge/GitHub-raihan--k--rasily-181717?style=flat-square&logo=github)](https://github.com/raihan-k-rasily)`;
  navigator.clipboard.writeText(text).then(() => {
    const btn = document.getElementById('copybtn');
    btn.textContent = ' copied!';
    setTimeout(() => { btn.innerHTML = '<i class="ti ti-copy"></i> copy readme'; }, 2000);
  });
}
</script>

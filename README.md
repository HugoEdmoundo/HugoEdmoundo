
<style>
  @import url('https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400&family=Syne:wght@400;700;800&display=swap');

  * { box-sizing: border-box; margin: 0; padding: 0; }

  .gh-wrap {
    font-family: 'Space Mono', monospace;
    background: #0d1117;
    color: #e6edf3;
    padding: 32px;
    border-radius: 12px;
    max-width: 860px;
    border: 1px solid #21262d;
    position: relative;
    overflow: hidden;
  }

  .scanline {
    position: absolute;
    top: 0; left: 0; right: 0; bottom: 0;
    background: repeating-linear-gradient(0deg, transparent, transparent 2px, rgba(255,255,255,0.012) 2px, rgba(255,255,255,0.012) 4px);
    pointer-events: none;
    z-index: 0;
  }

  .content { position: relative; z-index: 1; }

  .header-row {
    display: flex;
    align-items: flex-start;
    gap: 28px;
    margin-bottom: 28px;
  }

  .avatar-wrap {
    flex-shrink: 0;
    position: relative;
  }

  .avatar-gif {
    width: 110px;
    height: 110px;
    border-radius: 50%;
    border: 2px solid #30363d;
    object-fit: cover;
    display: block;
    background: #161b22;
    overflow: hidden;
  }

  .avatar-placeholder {
    width: 110px;
    height: 110px;
    border-radius: 50%;
    border: 2px solid #30363d;
    background: #161b22;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 42px;
    position: relative;
  }

  .status-dot {
    position: absolute;
    bottom: 6px;
    right: 6px;
    width: 14px;
    height: 14px;
    border-radius: 50%;
    background: #3fb950;
    border: 2px solid #0d1117;
    animation: pulse-dot 2s infinite;
  }

  @keyframes pulse-dot {
    0%, 100% { box-shadow: 0 0 0 0 rgba(63, 185, 80, 0.4); }
    50% { box-shadow: 0 0 0 5px rgba(63, 185, 80, 0); }
  }

  .header-info { flex: 1; }

  .name-row {
    display: flex;
    align-items: center;
    gap: 10px;
    flex-wrap: wrap;
    margin-bottom: 4px;
  }

  .display-name {
    font-family: 'Syne', sans-serif;
    font-size: 26px;
    font-weight: 800;
    color: #e6edf3;
    letter-spacing: -0.5px;
  }

  .handle {
    font-size: 13px;
    color: #7d8590;
    margin-bottom: 10px;
  }

  .bio-line {
    font-size: 12px;
    color: #8b949e;
    margin-bottom: 12px;
    line-height: 1.6;
  }

  .badges {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .badge {
    font-size: 10px;
    font-family: 'Space Mono', monospace;
    padding: 3px 8px;
    border-radius: 20px;
    border: 1px solid;
  }

  .badge-ts { background: #1c2d4d; border-color: #2d5a9e; color: #79c0ff; }
  .badge-py { background: #2d1b4d; border-color: #6e40c9; color: #d2a8ff; }
  .badge-ai { background: #1b3a2d; border-color: #2ea043; color: #56d364; }
  .badge-agents { background: #3a1b1b; border-color: #9e2a2a; color: #ff7b72; }

  .divider {
    border: none;
    border-top: 1px solid #21262d;
    margin: 20px 0;
  }

  .section-label {
    font-size: 10px;
    color: #7d8590;
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 12px;
  }

  .code-block {
    background: #161b22;
    border: 1px solid #21262d;
    border-radius: 8px;
    padding: 16px;
    margin-bottom: 20px;
    font-size: 12px;
    line-height: 1.7;
  }

  .code-block .c-key { color: #79c0ff; }
  .code-block .c-str { color: #a5d6ff; }
  .code-block .c-list { color: #d2a8ff; }
  .code-block .c-bool { color: #56d364; }
  .code-block .c-comment { color: #6e7681; font-style: italic; }
  .code-block .c-obj { color: #ffa657; }

  .code-header {
    display: flex;
    align-items: center;
    gap: 6px;
    margin-bottom: 12px;
    padding-bottom: 10px;
    border-bottom: 1px solid #21262d;
  }

  .dot { width: 10px; height: 10px; border-radius: 50%; }
  .dot-r { background: #ff5f57; }
  .dot-y { background: #febc2e; }
  .dot-g { background: #28c840; }
  .file-name { font-size: 11px; color: #6e7681; margin-left: auto; }

  .quote-block {
    border-left: 3px solid #3fb950;
    padding: 10px 16px;
    background: #161b22;
    border-radius: 0 6px 6px 0;
    font-size: 12px;
    color: #8b949e;
    font-style: italic;
    margin-bottom: 20px;
  }

  .grid-2 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
    margin-bottom: 20px;
  }

  .do-card {
    background: #161b22;
    border: 1px solid #21262d;
    border-radius: 8px;
    padding: 14px;
  }

  .do-card .dc-icon { font-size: 20px; margin-bottom: 8px; display: block; }
  .do-card .dc-title { font-size: 12px; font-weight: 700; color: #e6edf3; margin-bottom: 4px; }
  .do-card .dc-desc { font-size: 11px; color: #7d8590; line-height: 1.5; }

  .stack-bar { margin-bottom: 14px; }
  .stack-row {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 8px;
    font-size: 11px;
  }
  .stack-label { width: 80px; color: #8b949e; flex-shrink: 0; }
  .bar-track {
    flex: 1;
    height: 6px;
    background: #21262d;
    border-radius: 3px;
    overflow: hidden;
  }
  .bar-fill {
    height: 100%;
    border-radius: 3px;
    animation: grow-bar 1.2s ease forwards;
    transform-origin: left;
  }
  .bar-fill.ts { background: #79c0ff; width: 88%; }
  .bar-fill.py { background: #d2a8ff; width: 80%; }
  .bar-fill.infra { background: #56d364; width: 60%; }
  .bar-fill.ai { background: #ffa657; width: 95%; }

  @keyframes grow-bar {
    from { width: 0%; }
  }

  .bar-pct { color: #6e7681; font-size: 10px; width: 28px; text-align: right; }

  .projects-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 12px;
    margin-bottom: 20px;
  }

  .projects-table th {
    text-align: left;
    font-size: 10px;
    color: #6e7681;
    padding: 0 0 8px;
    letter-spacing: 1px;
    border-bottom: 1px solid #21262d;
  }

  .projects-table td {
    padding: 10px 0;
    border-bottom: 1px solid #21262d;
    color: #8b949e;
    vertical-align: top;
  }

  .projects-table td:first-child { color: #e6edf3; font-weight: 700; }
  .projects-table td:last-child { text-align: right; }

  .status-pill {
    font-size: 10px;
    padding: 2px 8px;
    border-radius: 20px;
    font-family: 'Space Mono', monospace;
  }
  .s-prog { background: #1c2d4d; color: #79c0ff; border: 1px solid #2d5a9e; }
  .s-alpha { background: #2d1b4d; color: #d2a8ff; border: 1px solid #6e40c9; }
  .s-idea { background: #21262d; color: #6e7681; border: 1px solid #30363d; }
  .s-rogue { background: #3a1b1b; color: #ff7b72; border: 1px solid #9e2a2a; animation: blink 1.2s infinite; }

  @keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.4; }
  }

  .fun-facts {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 8px;
    margin-bottom: 20px;
  }

  .fact-item {
    display: flex;
    align-items: flex-start;
    gap: 8px;
    font-size: 11px;
    color: #8b949e;
    line-height: 1.5;
  }
  .fact-emoji { flex-shrink: 0; font-size: 14px; }

  .commit-block {
    background: #161b22;
    border: 1px solid #21262d;
    border-radius: 8px;
    padding: 14px 16px;
    font-size: 11px;
    margin-bottom: 20px;
  }
  .commit-hash { color: #79c0ff; margin-bottom: 6px; }
  .commit-title { color: #e6edf3; font-weight: 700; margin-bottom: 8px; font-size: 12px; }
  .commit-body { color: #7d8590; line-height: 1.8; }
  .commit-body .plus { color: #56d364; }
  .commit-body .minus { color: #ff7b72; }

  .links-row {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
  }

  .link-btn {
    font-size: 11px;
    font-family: 'Space Mono', monospace;
    padding: 6px 14px;
    border-radius: 6px;
    border: 1px solid #30363d;
    background: #161b22;
    color: #8b949e;
    cursor: pointer;
    transition: border-color 0.15s, color 0.15s;
    text-decoration: none;
    display: inline-block;
  }
  .link-btn:hover { border-color: #7d8590; color: #e6edf3; }
  .link-btn.primary { border-color: #3fb950; color: #56d364; }
  .link-btn.primary:hover { background: #1b3a2d; }

  .footer-note {
    text-align: center;
    font-size: 10px;
    color: #3d444d;
    margin-top: 20px;
    font-style: italic;
  }

  .robo-row {
    display: flex;
    align-items: center;
    gap: 8px;
    margin-bottom: 6px;
  }
  .robo-typing {
    font-size: 11px;
    color: #6e7681;
  }
  .cursor-blink {
    display: inline-block;
    width: 7px;
    height: 12px;
    background: #3fb950;
    vertical-align: middle;
    animation: blink 1s step-end infinite;
    margin-left: 2px;
  }

  .section-header {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 14px;
  }
  .section-line { flex: 1; height: 1px; background: #21262d; }
</style>

<div class="gh-wrap">
  <div class="scanline"></div>
  <div class="content">

    <div class="header-row">
      <div class="avatar-wrap">
        <div class="avatar-placeholder">
          🤖
          <span style="position:absolute;bottom:2px;right:-2px;font-size:16px">☕</span>
        </div>
        <div class="status-dot"></div>
      </div>
      <div class="header-info">
        <div class="name-row">
          <span class="display-name">HugoEdmoundo</span>
          <span style="font-size:11px;background:#1b3a2d;color:#56d364;padding:2px 8px;border-radius:20px;border:1px solid #2ea043">PRO (probably)</span>
        </div>
        <div class="handle">@HugoEdmoundo · Software Engineer · AI/Agent Systems</div>
        <div class="bio-line">
          Making LLMs do things they probably shouldn't.<br>
          <span style="color:#3fb950">⬤</span>&nbsp;Currently: building something that may or may not become sentient.
        </div>
        <div class="badges">
          <span class="badge badge-ts">TypeScript</span>
          <span class="badge badge-py">Python</span>
          <span class="badge badge-ai">AI/Agents</span>
          <span class="badge badge-agents">LLM Whisperer</span>
          <span class="badge" style="background:#1b2d3a;border-color:#1f6feb;color:#58a6ff">Coffee-Driven Dev</span>
        </div>
      </div>
    </div>

    <div class="quote-block">
      "If it can be automated, it will be automated. If it can't, I'll train a model on it."
      <br><span style="color:#3fb950;font-style:normal;font-size:10px;">— definitely me, after 3am commit</span>
    </div>

    <div class="code-block">
      <div class="code-header">
        <div class="dot dot-r"></div>
        <div class="dot dot-y"></div>
        <div class="dot dot-g"></div>
        <span class="file-name">hugo.py</span>
      </div>
<span class="c-obj">hugo</span> = {
  <span class="c-key">  "stack"</span>:        [<span class="c-str">"TypeScript"</span>, <span class="c-str">"Python"</span>],
  <span class="c-key">  "obsessed_with"</span>: [<span class="c-str">"AI Agents"</span>, <span class="c-str">"LLM orchestration"</span>, <span class="c-str">"automation"</span>],
  <span class="c-key">  "currently"</span>:    <span class="c-str">"building something that may or may not become sentient"</span>,
  <span class="c-key">  "coffee"</span>:       <span class="c-bool">True</span>,    <span class="c-comment"># non-negotiable</span>
  <span class="c-key">  "sleep"</span>:        <span class="c-bool">False</span>,   <span class="c-comment"># we don't do that here</span>
  <span class="c-key">  "agent_escaped"</span>: <span class="c-bool">True</span>,   <span class="c-comment"># 3000 API calls. trust the process.</span>
}
    </div>

    <div class="section-header">
      <span class="section-label">what i actually do</span>
      <div class="section-line"></div>
    </div>

    <div class="grid-2">
      <div class="do-card">
        <span class="dc-icon">🕵️</span>
        <div class="dc-title">AI Agent Systems</div>
        <div class="dc-desc">Multi-agent pipelines, tool-calling, RAG. The whole glorious chaos — shipped before fully understood.</div>
      </div>
      <div class="do-card">
        <span class="dc-icon">🔷</span>
        <div class="dc-title">TypeScript</div>
        <div class="dc-desc">JavaScript with a safety net, self-respect, and a slightly less cursed 2am experience.</div>
      </div>
      <div class="do-card">
        <span class="dc-icon">🐍</span>
        <div class="dc-title">Python</div>
        <div class="dc-desc">For the AI stuff. And the backend stuff. And the "this shouldn't work but it does" stuff.</div>
      </div>
      <div class="do-card">
        <span class="dc-icon">🔗</span>
        <div class="dc-title">Orchestration</div>
        <div class="dc-desc">LangChain, LlamaIndex, custom runtimes. Basically a traffic warden for confused LLMs.</div>
      </div>
    </div>

    <div class="section-header">
      <span class="section-label">stack proficiency</span>
      <div class="section-line"></div>
    </div>

    <div class="stack-bar">
      <div class="stack-row">
        <span class="stack-label">TypeScript</span>
        <div class="bar-track"><div class="bar-fill ts"></div></div>
        <span class="bar-pct">88%</span>
      </div>
      <div class="stack-row">
        <span class="stack-label">Python</span>
        <div class="bar-track"><div class="bar-fill py"></div></div>
        <span class="bar-pct">80%</span>
      </div>
      <div class="stack-row">
        <span class="stack-label">AI/Agents</span>
        <div class="bar-track"><div class="bar-fill ai"></div></div>
        <span class="bar-pct">95%</span>
      </div>
      <div class="stack-row">
        <span class="stack-label">Infra/DevOps</span>
        <div class="bar-track"><div class="bar-fill infra"></div></div>
        <span class="bar-pct">60%</span>
      </div>
      <div class="stack-row">
        <span class="stack-label">Prompt Eng.</span>
        <div class="bar-track"><div class="bar-fill" style="background:#ffa657;width:92%"></div></div>
        <span class="bar-pct">92%</span>
      </div>
    </div>

    <div class="section-header">
      <span class="section-label">currently shipping</span>
      <div class="section-line"></div>
    </div>

    <table class="projects-table">
      <thead>
        <tr>
          <th>PROJECT</th>
          <th>WHAT IT DOES</th>
          <th>STATUS</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>agent-core</td>
          <td>Multi-agent task runner. It delegates. Better at it than me.</td>
          <td><span class="status-pill s-prog">in progress</span></td>
        </tr>
        <tr>
          <td>memstore</td>
          <td>Long-term memory layer for LLM apps. Basically LLM therapy notes.</td>
          <td><span class="status-pill s-alpha">alpha</span></td>
        </tr>
        <tr>
          <td>toolchain</td>
          <td>Custom tool registry for AI agents. They need tools too, okay?</td>
          <td><span class="status-pill s-idea">ideating</span></td>
        </tr>
        <tr>
          <td>agent-v0.1</td>
          <td>Queued 3,000 API calls before I noticed. Technically impressive.</td>
          <td><span class="status-pill s-rogue">⚠ rogue</span></td>
        </tr>
      </tbody>
    </table>

    <div class="section-header">
      <span class="section-label">random facts (certified real™)</span>
      <div class="section-line"></div>
    </div>

    <div class="fun-facts">
      <div class="fact-item"><span class="fact-emoji">🧃</span><span>Spent more time prompt engineering than writing actual code this month. Worth it? Debatable.</span></div>
      <div class="fact-item"><span class="fact-emoji">📉</span><span>First agent went rogue — 3,000 API calls before I noticed. I consider this a success story.</span></div>
      <div class="fact-item"><span class="fact-emoji">🎯</span><span>I genuinely believe <code style="font-size:10px;color:#79c0ff">async/await</code> is one of humanity's greatest achievements. I will die on this hill.</span></div>
      <div class="fact-item"><span class="fact-emoji">🌀</span><span>Refactored the same function 6 times. Looks exactly the same. I'm fine. The function is fine.</span></div>
      <div class="fact-item"><span class="fact-emoji">☕</span><span>Function naming degrades exponentially after 11pm. <code style="font-size:10px;color:#ff7b72">doTheThing2Final_v3</code> was a dark era.</span></div>
      <div class="fact-item"><span class="fact-emoji">🤖</span><span>My agents have more retry logic than I have life plans. They're more prepared. I respect it.</span></div>
    </div>

    <div class="commit-block">
      <div class="commit-hash">commit a4f8c2d · main</div>
      <div class="commit-title">feat: ship fast, document later, let the agent handle the edge cases</div>
      <div class="commit-body">
        <span class="plus">+</span> added retry logic (trust me bro)<br>
        <span class="plus">+</span> the tests pass locally<br>
        <span class="plus">+</span> prod is fine probably<br>
        <span class="minus">-</span> removed documentation (agent will write it)<br>
        <span class="minus">-</span> deleted unit tests (vibe-based testing now)<br>
        <span class="c-comment">// reviewed by: me, 2am-me, and a confused LLM</span>
      </div>
    </div>

    <div class="section-header">
      <span class="section-label">let's talk</span>
      <div class="section-line"></div>
    </div>

    <div style="margin-bottom:14px;font-size:11px;color:#7d8590;line-height:1.7">
      Built something weird with AI? Have a bad idea that might actually work?<br>
      Or just wanna nerd out about agents, orchestration, or why the LLM keeps hallucinating field names?
    </div>

    <div class="links-row">
      <a class="link-btn primary" href="mailto:hugo@example.com">📧 email me</a>
      <a class="link-btn" href="https://linkedin.com/in/HugoEdmoundo">in LinkedIn</a>
      <a class="link-btn" href="https://twitter.com/HugoEdmoundo">𝕏 @HugoEdmoundo</a>
    </div>

    <div class="footer-note">
      <div class="robo-row" style="justify-content:center">
        <span class="robo-typing">// last updated by a script. obviously.</span>
        <span class="cursor-blink"></span>
      </div>
      <span style="font-size:9px;color:#21262d">⚠ no agents were harmed in the making of this README (they escaped)</span>
    </div>

  </div>
</div>

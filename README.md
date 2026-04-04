<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>stewiecancode_sa — GitHub README</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link href="https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Orbitron:wght@400;700;900&family=Rajdhani:wght@300;400;600&display=swap" rel="stylesheet" />
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --neon-green: #00ff88;
      --neon-cyan: #00d4ff;
      --neon-purple: #bf5fff;
      --neon-pink: #ff2d78;
      --bg-dark: #0a0b0f;
      --bg-card: #0f1117;
      --bg-card2: #13151e;
      --border-glow: rgba(0,212,255,0.3);
      --text-dim: #5a6a7a;
      --text-muted: #8896a8;
    }

    html, body {
      background: var(--bg-dark);
      min-height: 100vh;
    }

    .readme-wrap {
      background: var(--bg-dark);
      min-height: 100vh;
      font-family: 'Rajdhani', sans-serif;
      color: #c8d8e8;
      padding: 0 0 60px;
      position: relative;
      overflow-x: hidden;
    }

    .readme-wrap::before {
      content: '';
      position: fixed;
      inset: 0;
      background: repeating-linear-gradient(0deg, transparent, transparent 2px, rgba(0,0,0,0.07) 2px, rgba(0,0,0,0.07) 4px);
      pointer-events: none;
      z-index: 0;
    }

    .content { position: relative; z-index: 1; max-width: 860px; margin: 0 auto; }

    .hero {
      text-align: center;
      padding: 56px 24px 36px;
      position: relative;
    }

    .hero-grid-bg {
      position: absolute;
      inset: 0;
      background-image:
        linear-gradient(rgba(0,212,255,0.04) 1px, transparent 1px),
        linear-gradient(90deg, rgba(0,212,255,0.04) 1px, transparent 1px);
      background-size: 32px 32px;
    }

    .glitch-name {
      font-family: 'Orbitron', monospace;
      font-size: clamp(28px, 6vw, 56px);
      font-weight: 900;
      color: var(--neon-cyan);
      letter-spacing: 4px;
      text-shadow: 0 0 20px rgba(0,212,255,0.6), 0 0 60px rgba(0,212,255,0.2);
      animation: flicker 4s infinite;
      position: relative;
    }

    @keyframes flicker {
      0%,94%,96%,98%,100% { opacity: 1; }
      95%,97%,99% { opacity: 0.82; }
    }

    .hero-sub {
      font-family: 'Share Tech Mono', monospace;
      font-size: 13px;
      color: var(--neon-green);
      letter-spacing: 3px;
      margin-top: 10px;
    }

    .hero-tag {
      display: inline-block;
      background: rgba(191,95,255,0.12);
      border: 1px solid rgba(191,95,255,0.4);
      color: var(--neon-purple);
      font-family: 'Share Tech Mono', monospace;
      font-size: 11px;
      padding: 4px 14px;
      border-radius: 2px;
      margin: 12px 4px 0;
      letter-spacing: 2px;
    }

    .section-title {
      font-family: 'Orbitron', monospace;
      font-size: 13px;
      font-weight: 700;
      color: var(--neon-cyan);
      letter-spacing: 4px;
      text-transform: uppercase;
      border-left: 3px solid var(--neon-cyan);
      padding-left: 12px;
      margin-bottom: 20px;
    }

    .about-card {
      margin: 32px 20px;
      background: var(--bg-card);
      border: 1px solid var(--border-glow);
      border-radius: 4px;
      padding: 24px;
      position: relative;
    }

    .about-card::before {
      content: '';
      position: absolute;
      top: -1px; left: 20px; width: 80px; height: 2px;
      background: var(--neon-cyan);
    }

    .terminal-line {
      font-family: 'Share Tech Mono', monospace;
      font-size: 13px;
      color: #8896a8;
      margin-bottom: 8px;
      line-height: 1.7;
    }

    .terminal-line .prompt { color: var(--neon-green); }
    .terminal-line .highlight { color: var(--neon-cyan); }
    .terminal-line .str { color: var(--neon-pink); }

    .skills-section { margin: 32px 20px; }

    .skills-grid { display: flex; flex-wrap: wrap; gap: 8px; }

    .skill-badge {
      font-family: 'Share Tech Mono', monospace;
      font-size: 11px;
      padding: 6px 14px;
      border-radius: 2px;
      letter-spacing: 1px;
      border: 1px solid;
      transition: transform 0.15s, box-shadow 0.15s;
      cursor: default;
    }

    .skill-badge:hover { transform: translateY(-2px); box-shadow: 0 4px 16px currentColor; }

    .sk-js   { color: #f0db4f; border-color: rgba(240,219,79,0.4);  background: rgba(240,219,79,0.07);  }
    .sk-cs   { color: #9b4f96; border-color: rgba(155,79,150,0.4);  background: rgba(155,79,150,0.07);  }
    .sk-ts   { color: #3178c6; border-color: rgba(49,120,198,0.4);  background: rgba(49,120,198,0.07);  }
    .sk-react{ color: #61dafb; border-color: rgba(97,218,251,0.4);  background: rgba(97,218,251,0.07);  }
    .sk-node { color: #6da55f; border-color: rgba(109,165,95,0.4);  background: rgba(109,165,95,0.07);  }
    .sk-net  { color: #9b59d0; border-color: rgba(155,89,208,0.4);  background: rgba(155,89,208,0.07);  }
    .sk-css  { color: #1572b6; border-color: rgba(21,114,182,0.4);  background: rgba(21,114,182,0.07);  }
    .sk-sql  { color: #cc2927; border-color: rgba(204,41,39,0.4);   background: rgba(204,41,39,0.07);   }
    .sk-aws  { color: #ff9900; border-color: rgba(255,153,0,0.4);   background: rgba(255,153,0,0.07);   }
    .sk-fire { color: #ff6d00; border-color: rgba(255,109,0,0.4);   background: rgba(255,109,0,0.07);   }
    .sk-tw   { color: #38b2ac; border-color: rgba(56,178,172,0.4);  background: rgba(56,178,172,0.07);  }
    .sk-supa { color: #3ecf8e; border-color: rgba(62,207,142,0.4);  background: rgba(62,207,142,0.07);  }
    .sk-pbi  { color: #f2c811; border-color: rgba(242,200,17,0.4);  background: rgba(242,200,17,0.07);  }
    .sk-gh   { color: #e8e8e8; border-color: rgba(232,232,232,0.3); background: rgba(232,232,232,0.05); }

    /* ---- GAMES ---- */
    .games-row {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 16px;
      margin: 0 20px;
    }

    @media (max-width: 600px) { .games-row { grid-template-columns: 1fr; } }

    .game-card, .type-game-wrap {
      background: var(--bg-card);
      border: 1px solid rgba(0,255,136,0.2);
      border-radius: 4px;
      padding: 20px;
      position: relative;
    }

    .type-game-wrap { border-color: rgba(0,212,255,0.2); }

    .game-card::before {
      content: ''; position: absolute;
      top: -1px; left: 20px; width: 80px; height: 2px;
      background: var(--neon-green);
    }

    .type-game-wrap::before {
      content: ''; position: absolute;
      top: -1px; left: 20px; width: 80px; height: 2px;
      background: var(--neon-cyan);
    }

    .game-title {
      font-family: 'Share Tech Mono', monospace;
      font-size: 11px;
      letter-spacing: 3px;
      color: var(--neon-green);
      margin-bottom: 12px;
    }

    #snakeCanvas {
      display: block;
      margin: 0 auto;
      border: 1px solid rgba(0,255,136,0.3);
      background: #050708;
      image-rendering: pixelated;
    }

    .game-controls {
      display: flex;
      gap: 12px;
      justify-content: center;
      margin-top: 12px;
      flex-wrap: wrap;
      align-items: center;
    }

    .btn-game {
      font-family: 'Share Tech Mono', monospace;
      font-size: 12px;
      letter-spacing: 2px;
      padding: 8px 20px;
      border-radius: 2px;
      cursor: pointer;
      border: 1px solid var(--neon-green);
      background: rgba(0,255,136,0.08);
      color: var(--neon-green);
      transition: background 0.15s, box-shadow 0.15s;
    }

    .btn-game:hover { background: rgba(0,255,136,0.18); box-shadow: 0 0 12px rgba(0,255,136,0.3); }

    .score-display {
      font-family: 'Share Tech Mono', monospace;
      font-size: 13px;
      color: var(--neon-green);
      letter-spacing: 2px;
    }

    .d-pad {
      display: grid;
      grid-template-areas: '. up .' 'left . right' '. down .';
      gap: 4px;
      margin-top: 12px;
    }

    .d-btn {
      font-family: 'Share Tech Mono', monospace;
      font-size: 14px;
      width: 36px; height: 36px;
      border: 1px solid rgba(0,255,136,0.4);
      background: rgba(0,255,136,0.06);
      color: var(--neon-green);
      cursor: pointer;
      border-radius: 2px;
      display: flex; align-items: center; justify-content: center;
      transition: background 0.1s;
      user-select: none;
    }

    .d-btn:active { background: rgba(0,255,136,0.2); }
    .d-up    { grid-area: up;    }
    .d-left  { grid-area: left;  }
    .d-right { grid-area: right; }
    .d-down  { grid-area: down;  }

    /* Memory */
    .memory-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 8px;
      max-width: 280px;
      margin: 12px auto;
    }

    .mem-card {
      aspect-ratio: 1;
      border: 1px solid rgba(191,95,255,0.3);
      border-radius: 4px;
      background: #0a0b14;
      cursor: pointer;
      display: flex; align-items: center; justify-content: center;
      font-size: 20px;
      transition: transform 0.1s, border-color 0.15s;
    }

    .mem-card:hover { border-color: rgba(191,95,255,0.6); }
    .mem-card.flipped { border-color: var(--neon-purple); background: rgba(191,95,255,0.1); }
    .mem-card.matched  { border-color: var(--neon-green);  background: rgba(0,255,136,0.08); cursor: default; }

    .mem-status {
      font-family: 'Share Tech Mono', monospace;
      font-size: 12px;
      color: var(--neon-purple);
      text-align: center;
      margin-top: 8px;
      letter-spacing: 2px;
      min-height: 20px;
    }

    /* Typing */
    .word-display {
      font-family: 'Share Tech Mono', monospace;
      font-size: 22px;
      text-align: center;
      color: var(--neon-cyan);
      letter-spacing: 6px;
      padding: 16px;
      border: 1px dashed rgba(0,212,255,0.2);
      border-radius: 2px;
      margin-bottom: 12px;
      min-height: 60px;
      display: flex; align-items: center; justify-content: center;
      background: #070810;
      flex-wrap: wrap;
    }

    .word-display .hit  { color: var(--neon-green); }
    .word-display .miss { color: var(--neon-pink);  }

    .type-input {
      font-family: 'Share Tech Mono', monospace;
      font-size: 16px;
      width: 100%;
      padding: 10px 14px;
      background: #070810;
      border: 1px solid rgba(0,212,255,0.3);
      border-radius: 2px;
      color: var(--neon-cyan);
      outline: none;
      letter-spacing: 3px;
    }

    .type-input:focus { border-color: var(--neon-cyan); box-shadow: 0 0 8px rgba(0,212,255,0.2); }

    .stat-item {
      font-family: 'Share Tech Mono', monospace;
      font-size: 12px;
      color: var(--text-muted);
      letter-spacing: 1px;
    }

    .stat-item span { color: var(--neon-cyan); font-size: 16px; }

    /* Stats section */
    .stats-section { margin: 32px 20px; }

    .stats-cards {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
      gap: 12px;
      margin-bottom: 16px;
    }

    .stat-card {
      background: var(--bg-card);
      border: 1px solid rgba(0,212,255,0.15);
      border-radius: 4px;
      padding: 16px;
      text-align: center;
      transition: border-color 0.2s;
    }

    .stat-card:hover { border-color: rgba(0,212,255,0.4); }

    .stat-num {
      font-family: 'Orbitron', monospace;
      font-size: 24px;
      font-weight: 900;
      color: var(--neon-cyan);
      display: block;
      text-shadow: 0 0 12px rgba(0,212,255,0.4);
    }

    .stat-label-s {
      font-family: 'Share Tech Mono', monospace;
      font-size: 10px;
      color: var(--text-muted);
      letter-spacing: 2px;
      margin-top: 4px;
      display: block;
    }

    /* Connect */
    .connect-section { margin: 32px 20px 0; text-align: center; }

    .connect-links {
      display: flex;
      gap: 12px;
      justify-content: center;
      flex-wrap: wrap;
      margin-top: 16px;
    }

    .connect-btn {
      font-family: 'Share Tech Mono', monospace;
      font-size: 11px;
      letter-spacing: 2px;
      padding: 8px 18px;
      border-radius: 2px;
      cursor: pointer;
      border: 1px solid;
      text-decoration: none;
      transition: transform 0.15s, box-shadow 0.15s;
      display: inline-block;
    }

    .connect-btn:hover { transform: translateY(-2px); }

    .c-li { color: #0077b5; border-color: rgba(0,119,181,0.5);  background: rgba(0,119,181,0.08);  }
    .c-gh { color: #e8e8e8; border-color: rgba(232,232,232,0.3);background: rgba(232,232,232,0.05);}
    .c-ig { color: #e4405f; border-color: rgba(228,64,95,0.4);  background: rgba(228,64,95,0.07);  }
    .c-tt { color: #e8e8e8; border-color: rgba(232,232,232,0.25);background:rgba(232,232,232,0.04);}
    .c-em { color: var(--neon-pink); border-color: rgba(255,45,120,0.4); background: rgba(255,45,120,0.07); }

    .footer-txt {
      font-family: 'Share Tech Mono', monospace;
      font-size: 11px;
      color: var(--text-dim);
      letter-spacing: 2px;
      margin-top: 32px;
      padding-top: 20px;
      border-top: 1px solid rgba(255,255,255,0.05);
    }

    .pulse-dot {
      display: inline-block;
      width: 7px; height: 7px;
      border-radius: 50%;
      background: var(--neon-green);
      margin-right: 6px;
      animation: pulse 1.5s infinite;
      vertical-align: middle;
    }

    @keyframes pulse {
      0%,100% { opacity: 1; transform: scale(1); }
      50%      { opacity: 0.4; transform: scale(0.7); }
    }

    .orb {
      position: fixed;
      border-radius: 50%;
      filter: blur(80px);
      opacity: 0.06;
      pointer-events: none;
      z-index: 0;
    }

    .orb1 { width: 340px; height: 340px; background: #00d4ff; top: -60px; right: -60px; animation: orbFloat 8s ease-in-out infinite; }
    .orb2 { width: 280px; height: 280px; background: #bf5fff; bottom: 80px; left: -80px;  animation: orbFloat 10s ease-in-out infinite reverse; }

    @keyframes orbFloat {
      0%,100% { transform: translateY(0); }
      50%      { transform: translateY(30px); }
    }

    .game-section { margin: 16px 20px 0; }
  </style>
</head>
<body>
<div class="readme-wrap">
  <div class="orb orb1"></div>
  <div class="orb orb2"></div>

  <div class="content">

    <!-- HERO -->
    <div class="hero">
      <div class="hero-grid-bg"></div>
      <div style="position:relative">
        <div class="glitch-name">STEWIECANCODE</div>
        <div class="hero-sub">// TSHIRELETSO SELEMELA · SOUTH AFRICA</div>
        <div style="margin-top:14px">
          <span class="hero-tag">FULL STACK</span>
          <span class="hero-tag">NQF L4 CS &amp; IT</span>
          <span class="hero-tag">BUILDER</span>
        </div>
        <div style="font-family:'Rajdhani',sans-serif;font-size:15px;color:#8896a8;margin-top:16px;line-height:1.6;">
          <span class="pulse-dot"></span>Open to collabs · building cool things · based in 🇿🇦
        </div>
      </div>
    </div>

    <!-- ABOUT -->
    <div class="about-card">
      <div class="section-title">ABOUT.SH</div>
      <div class="terminal-line"><span class="prompt">$ </span><span class="highlight">whoami</span></div>
      <div class="terminal-line" style="padding-left:16px;color:#a0b0c0">→ Graduate · CS &amp; IT · Passionate dev who loves shipping products</div>
      <div class="terminal-line" style="margin-top:8px"><span class="prompt">$ </span><span class="highlight">cat skills.json</span></div>
      <div class="terminal-line" style="padding-left:16px">{ <span class="str">"frontend"</span>: [<span class="str">"React"</span>, <span class="str">"HTML/CSS"</span>, <span class="str">"Tailwind"</span>],</div>
      <div class="terminal-line" style="padding-left:16px">  <span class="str">"backend"</span>: [<span class="str">"Node.js"</span>, <span class="str">"ASP.NET"</span>, <span class="str">"Express"</span>],</div>
      <div class="terminal-line" style="padding-left:16px">  <span class="str">"databases"</span>: [<span class="str">"MSSQL"</span>, <span class="str">"MySQL"</span>, <span class="str">"Firebase"</span>, <span class="str">"Supabase"</span>] }</div>
      <div class="terminal-line" style="margin-top:8px"><span class="prompt">$ </span><span class="highlight">echo $VIBE</span></div>
      <div class="terminal-line" style="padding-left:16px;color:#a0b0c0">→ Code · Coffee · Create · Repeat ☕</div>
    </div>

    <!-- TECH STACK -->
    <div class="skills-section">
      <div class="section-title">TECH.STACK</div>
      <div class="skills-grid">
        <span class="skill-badge sk-js">JavaScript</span>
        <span class="skill-badge sk-ts">TypeScript</span>
        <span class="skill-badge sk-cs">C#</span>
        <span class="skill-badge sk-react">React</span>
        <span class="skill-badge sk-react">React Native</span>
        <span class="skill-badge sk-node">Node.js</span>
        <span class="skill-badge sk-net">.NET / Blazor</span>
        <span class="skill-badge sk-css">HTML / CSS</span>
        <span class="skill-badge sk-tw">Tailwind CSS</span>
        <span class="skill-badge sk-sql">MSSQL</span>
        <span class="skill-badge sk-sql">MySQL</span>
        <span class="skill-badge sk-fire">Firebase</span>
        <span class="skill-badge sk-supa">Supabase</span>
        <span class="skill-badge sk-aws">AWS</span>
        <span class="skill-badge sk-aws">DynamoDB</span>
        <span class="skill-badge sk-pbi">Power BI</span>
        <span class="skill-badge sk-gh">GitHub</span>
        <span class="skill-badge sk-net">Xamarin</span>
      </div>
    </div>

    <!-- GAMES HEADER -->
    <div style="margin:32px 20px 16px">
      <div class="section-title">MINI.GAMES</div>
    </div>

    <!-- SNAKE + MEMORY -->
    <div class="games-row">

      <!-- SNAKE -->
      <div class="game-card">
        <div class="game-title">▶ SNAKE.EXE</div>
        <canvas id="snakeCanvas" width="200" height="200"></canvas>
        <div class="game-controls">
          <span class="score-display" id="snakeScore">SCORE: 0</span>
          <button class="btn-game" onclick="snakeStart()">START</button>
        </div>
        <div style="display:flex;justify-content:center">
          <div class="d-pad">
            <button class="d-btn d-up"    onpointerdown="snakeDir(0,-1)">▲</button>
            <button class="d-btn d-left"  onpointerdown="snakeDir(-1,0)">◀</button>
            <button class="d-btn d-right" onpointerdown="snakeDir(1,0)">▶</button>
            <button class="d-btn d-down"  onpointerdown="snakeDir(0,1)">▼</button>
          </div>
        </div>
      </div>

      <!-- MEMORY -->
      <div class="type-game-wrap" style="border-color:rgba(191,95,255,0.25)">
        <div class="game-title" style="color:var(--neon-purple)">▶ MEMORY.EXE</div>
        <div class="mem-status" id="memStatus">CLICK A CARD TO START</div>
        <div class="memory-grid" id="memoryGrid"></div>
        <div style="text-align:center;margin-top:10px;display:flex;align-items:center;justify-content:center;gap:12px">
          <button class="btn-game" style="border-color:var(--neon-purple);color:var(--neon-purple);background:rgba(191,95,255,0.08)" onclick="initMemory()">RESET</button>
          <span style="font-family:'Share Tech Mono',monospace;font-size:12px;color:var(--neon-purple);letter-spacing:1px">MOVES: <span id="memMoves">0</span></span>
        </div>
      </div>

    </div>

    <!-- TYPING GAME -->
    <div class="game-section">
      <div class="type-game-wrap">
        <div class="game-title">▶ TYPING.EXE — TYPE THE CODE WORD</div>
        <div class="word-display" id="typingWordDisplay">PRESS START</div>
        <input type="text" class="type-input" id="typingInput" placeholder="type here..." autocomplete="off" spellcheck="false" disabled />
        <div style="display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:8px;margin-top:10px">
          <div style="display:flex;gap:20px;flex-wrap:wrap">
            <div class="stat-item">WPM: <span id="wpmVal">0</span></div>
            <div class="stat-item">ACC: <span id="accVal">-</span></div>
            <div class="stat-item">SCORE: <span id="typeScore">0</span></div>
          </div>
          <button class="btn-game" onclick="startTypingGame()">START</button>
        </div>
      </div>
    </div>

    <!-- GITHUB STATS -->
    <div class="stats-section">
      <div class="section-title">STATS.LOG</div>
      <div class="stats-cards">
        <div class="stat-card"><span class="stat-num">JS</span><span class="stat-label-s">TOP LANGUAGE</span></div>
        <div class="stat-card"><span class="stat-num" style="font-size:18px">C# + JS</span><span class="stat-label-s">POWER COMBO</span></div>
        <div class="stat-card"><span class="stat-num">4+</span><span class="stat-label-s">DATABASES</span></div>
        <div class="stat-card"><span class="stat-num">8+</span><span class="stat-label-s">FRAMEWORKS</span></div>
      </div>
      <div style="display:flex;flex-wrap:wrap;gap:10px;justify-content:center">
        <img src="https://github-readme-stats.vercel.app/api?username=tshire-13&theme=chartreuse-dark&hide_border=true&include_all_commits=true&count_private=true&bg_color=0a0b0f&title_color=00d4ff&text_color=8896a8&icon_color=00ff88"
             alt="GitHub Stats" style="border-radius:4px;max-width:100%;border:1px solid rgba(0,212,255,0.15)" onerror="this.style.display='none'" />
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=tshire-13&theme=chartreuse-dark&hide_border=true&layout=compact&bg_color=0a0b0f&title_color=00d4ff&text_color=8896a8"
             alt="Top Languages" style="border-radius:4px;max-width:100%;border:1px solid rgba(0,212,255,0.15)" onerror="this.style.display='none'" />
      </div>
    </div>

    <!-- CONNECT -->
    <div class="connect-section">
      <div class="section-title" style="text-align:left">CONNECT.SH</div>
      <div class="connect-links">
        <a class="connect-btn c-li" href="https://www.linkedin.com/in/tshireletso-selemela-00a283253/" target="_blank">LINKEDIN</a>
        <a class="connect-btn c-gh" href="https://github.com/tshire-13" target="_blank">GITHUB</a>
        <a class="connect-btn c-ig" href="https://instagram.com/stewiecancode_sa" target="_blank">INSTAGRAM</a>
        <a class="connect-btn c-tt" href="https://tiktok.com/@stewiecancode_sa" target="_blank">TIKTOK</a>
        <a class="connect-btn c-em" href="mailto:tshireletsoselemela17@gmail.com">EMAIL</a>
      </div>
      <div class="footer-txt">
        <span class="pulse-dot"></span>PROUDLY BUILT IN 🇿🇦 · © STEWIECANCODE_SA · tshire-13
      </div>
    </div>

  </div><!-- /content -->
</div><!-- /readme-wrap -->

<script>
// ============= SNAKE =============
const sCanvas = document.getElementById('snakeCanvas');
const sCtx = sCanvas.getContext('2d');
const GRID = 10, COLS = 20, ROWS = 20;
let snake, dir, nextDir, food, score, sLoop, gameRunning = false;

function snakeStart() {
  snake = [{x:10,y:10},{x:9,y:10},{x:8,y:10}];
  dir = {x:1,y:0}; nextDir = {x:1,y:0};
  score = 0;
  document.getElementById('snakeScore').textContent = 'SCORE: 0';
  gameRunning = true;
  placeFood();
  if (sLoop) clearInterval(sLoop);
  sLoop = setInterval(snakeTick, 120);
}

function placeFood() {
  let pos;
  do { pos = {x:Math.floor(Math.random()*COLS), y:Math.floor(Math.random()*ROWS)}; }
  while (snake.some(s => s.x===pos.x && s.y===pos.y));
  food = pos;
}

function snakeDir(x,y) {
  if (!(x===-dir.x&&y===0) && !(y===-dir.y&&x===0)) nextDir={x,y};
}

function snakeTick() {
  dir = nextDir;
  const head = {x: snake[0].x+dir.x, y: snake[0].y+dir.y};
  if (head.x<0||head.x>=COLS||head.y<0||head.y>=ROWS||snake.some(s=>s.x===head.x&&s.y===head.y)) {
    clearInterval(sLoop); gameRunning=false;
    drawSnake();
    sCtx.fillStyle='rgba(255,45,120,0.85)'; sCtx.fillRect(0,80,200,40);
    sCtx.fillStyle='#fff'; sCtx.font='bold 13px monospace'; sCtx.textAlign='center';
    sCtx.fillText('GAME OVER  SCORE: '+score, 100, 105);
    return;
  }
  snake.unshift(head);
  if (head.x===food.x && head.y===food.y) { score++; document.getElementById('snakeScore').textContent='SCORE: '+score; placeFood(); }
  else snake.pop();
  drawSnake();
}

function drawSnake() {
  sCtx.fillStyle='#050708'; sCtx.fillRect(0,0,200,200);
  sCtx.fillStyle='#ff2d78'; sCtx.shadowBlur=8; sCtx.shadowColor='#ff2d78';
  sCtx.fillRect(food.x*GRID+1, food.y*GRID+1, GRID-2, GRID-2);
  sCtx.shadowBlur=0;
  snake.forEach((s,i) => {
    sCtx.fillStyle = i===0 ? '#00ff88' : `hsl(${150+i*4},80%,${Math.max(30,55-i*1.2)}%)`;
    if (i===0) { sCtx.shadowBlur=6; sCtx.shadowColor='#00ff88'; }
    sCtx.fillRect(s.x*GRID+1, s.y*GRID+1, GRID-2, GRID-2);
    sCtx.shadowBlur=0;
  });
}

sCtx.fillStyle='#050708'; sCtx.fillRect(0,0,200,200);
sCtx.fillStyle='rgba(0,212,255,0.4)'; sCtx.font='12px monospace'; sCtx.textAlign='center';
sCtx.fillText('PRESS START', 100, 105);

document.addEventListener('keydown', e => {
  if (!gameRunning) return;
  if (e.key==='ArrowUp')    { e.preventDefault(); snakeDir(0,-1); }
  if (e.key==='ArrowDown')  { e.preventDefault(); snakeDir(0,1);  }
  if (e.key==='ArrowLeft')  { e.preventDefault(); snakeDir(-1,0); }
  if (e.key==='ArrowRight') { e.preventDefault(); snakeDir(1,0);  }
});

// ============= MEMORY =============
const emojis = ['⚡','🔥','💎','🚀','⚙️','🎮','🌐','🛸'];
let memCards=[], flipped=[], matched=[], memMovesCount=0, canFlip=true;

function initMemory() {
  const pairs = [...emojis,...emojis];
  for (let i=pairs.length-1; i>0; i--) { const j=Math.floor(Math.random()*(i+1)); [pairs[i],pairs[j]]=[pairs[j],pairs[i]]; }
  memCards=pairs; flipped=[]; matched=[]; memMovesCount=0; canFlip=true;
  document.getElementById('memMoves').textContent='0';
  document.getElementById('memStatus').textContent='MATCH THE PAIRS';
  const grid=document.getElementById('memoryGrid');
  grid.innerHTML='';
  pairs.forEach((emoji,i) => {
    const card=document.createElement('div');
    card.className='mem-card';
    card.dataset.idx=i; card.dataset.emoji=emoji;
    card.textContent='?';
    card.style.color='rgba(191,95,255,0.5)'; card.style.fontSize='16px'; card.style.fontFamily='monospace';
    card.addEventListener('click', () => flipCard(card,i,emoji));
    grid.appendChild(card);
  });
}

function flipCard(card,i,emoji) {
  if (!canFlip||flipped.includes(i)||matched.includes(i)) return;
  card.textContent=emoji; card.classList.add('flipped');
  flipped.push(i);
  if (flipped.length===2) {
    canFlip=false; memMovesCount++;
    document.getElementById('memMoves').textContent=memMovesCount;
    const [a,b]=flipped;
    if (memCards[a]===memCards[b]) {
      matched.push(a,b);
      document.querySelectorAll('#memoryGrid .mem-card').forEach(c=>{ if(matched.includes(+c.dataset.idx)) c.classList.add('matched'); });
      flipped=[]; canFlip=true;
      if (matched.length===16) document.getElementById('memStatus').textContent='🎉 YOU WIN! MOVES: '+memMovesCount;
      else document.getElementById('memStatus').textContent='✓ MATCH!';
    } else {
      document.getElementById('memStatus').textContent='✗ TRY AGAIN';
      setTimeout(() => {
        document.querySelectorAll('#memoryGrid .mem-card').forEach(c => {
          if (flipped.includes(+c.dataset.idx)) { c.textContent='?'; c.style.color='rgba(191,95,255,0.5)'; c.classList.remove('flipped'); }
        });
        flipped=[]; canFlip=true;
        document.getElementById('memStatus').textContent='MATCH THE PAIRS';
      }, 800);
    }
  }
}

initMemory();

// ============= TYPING =============
const codeWords = ['JAVASCRIPT','TYPESCRIPT','REACT','NODEJS','CSHARP','DOTNET','FIREBASE','SUPABASE','TAILWIND','BLAZOR','EXPRESS','GITHUB','MONGODB','DYNAMODB','FULLSTACK','DEVMODE','AWESOME'];
let typingWord='', typingStart=0, typingScore=0, typingActive=false, totalTyped=0, correctTyped=0;

function startTypingGame() {
  typingScore=0; totalTyped=0; correctTyped=0;
  document.getElementById('wpmVal').textContent='0';
  document.getElementById('accVal').textContent='-';
  document.getElementById('typeScore').textContent='0';
  nextTypingWord();
  const inp=document.getElementById('typingInput');
  inp.disabled=false; inp.value=''; inp.focus();
  typingActive=true;
  inp.oninput=checkTyping;
}

function nextTypingWord() {
  typingWord=codeWords[Math.floor(Math.random()*codeWords.length)];
  renderTypingWord(''); typingStart=Date.now();
  document.getElementById('typingInput').value='';
}

function renderTypingWord(input) {
  const disp=document.getElementById('typingWordDisplay');
  let html='';
  for (let i=0; i<typingWord.length; i++) {
    if (i<input.length) {
      html+=`<span class="${input[i]===typingWord[i]?'hit':'miss'}">${typingWord[i]}</span>`;
    } else {
      html+=`<span style="opacity:0.5">${typingWord[i]}</span>`;
    }
  }
  disp.innerHTML=html;
}

function checkTyping(e) {
  const val=e.target.value.toUpperCase();
  totalTyped++;
  if (val[val.length-1]===typingWord[val.length-1]) correctTyped++;
  renderTypingWord(val);
  document.getElementById('accVal').textContent=totalTyped>0?Math.round(correctTyped/totalTyped*100)+'%':'-';
  if (val===typingWord) {
    const elapsed=(Date.now()-typingStart)/60000;
    document.getElementById('wpmVal').textContent=Math.round((typingWord.length/5)/elapsed);
    typingScore++;
    document.getElementById('typeScore').textContent=typingScore;
    setTimeout(nextTypingWord,200);
  }
}
</script>
</body>
</html>

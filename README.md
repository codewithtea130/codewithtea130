<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 400" width="800" height="400">
  <defs>
    <style>
      @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }
      @keyframes fadeIn { from{opacity:0;transform:translateY(6px)} to{opacity:1;transform:translateY(0)} }
      @keyframes pulse { 0%,100%{r:18;opacity:0.18} 50%{r:26;opacity:0.06} }
      @keyframes pulse2 { 0%,100%{r:30;opacity:0.10} 50%{r:40;opacity:0.03} }
      @keyframes scanline { 0%{transform:translateY(-8px);opacity:0.18} 100%{transform:translateY(400px);opacity:0} }
      @keyframes glow { 0%,100%{opacity:0.7} 50%{opacity:1} }
      @keyframes typeLine1 { 0%,8%{width:0} 22%,100%{width:220px} }
      @keyframes typeLine2 { 0%,24%{width:0} 38%,100%{width:180px} }
      @keyframes typeLine3 { 0%,40%{width:0} 54%,100%{width:200px} }
      @keyframes typeLine4 { 0%,56%{width:0} 70%,100%{width:160px} }
      @keyframes typeLine5 { 0%,72%{width:0} 86%,100%{width:190px} }
      @keyframes showLine1 { 0%,7%{opacity:0} 8%,100%{opacity:1} }
      @keyframes showLine2 { 0%,23%{opacity:0} 24%,100%{opacity:1} }
      @keyframes showLine3 { 0%,39%{opacity:0} 40%,100%{opacity:1} }
      @keyframes showLine4 { 0%,55%{opacity:0} 56%,100%{opacity:1} }
      @keyframes showLine5 { 0%,71%{opacity:0} 72%,100%{opacity:1} }
      @keyframes showPrompt { 0%,85%{opacity:0} 86%,100%{opacity:1} }
      @keyframes radarSpin { from{transform:rotate(0deg)} to{transform:rotate(360deg)} }
      @keyframes dotAppear1 { 0%,30%{opacity:0;r:0} 32%,100%{opacity:1;r:3} }
      @keyframes dotAppear2 { 0%,45%{opacity:0;r:0} 47%,100%{opacity:1;r:3} }
      @keyframes dotAppear3 { 0%,60%{opacity:0;r:0} 62%,100%{opacity:1;r:3} }
      @keyframes dotAppear4 { 0%,75%{opacity:0;r:0} 77%,100%{opacity:1;r:3} }

      .cursor { animation: blink 1s step-end infinite; }
      .scanline { animation: scanline 4s linear infinite; }
      .glowtext { animation: glow 2.5s ease-in-out infinite; }

      .tl1 { animation: typeLine1 12s ease-out infinite; overflow:hidden; display:inline-block; white-space:nowrap; }
      .tl2 { animation: typeLine2 12s ease-out infinite; overflow:hidden; display:inline-block; white-space:nowrap; }
      .tl3 { animation: typeLine3 12s ease-out infinite; overflow:hidden; display:inline-block; white-space:nowrap; }
      .tl4 { animation: typeLine4 12s ease-out infinite; overflow:hidden; display:inline-block; white-space:nowrap; }
      .tl5 { animation: typeLine5 12s ease-out infinite; overflow:hidden; display:inline-block; white-space:nowrap; }

      .sl1 { animation: showLine1 12s ease-out infinite; }
      .sl2 { animation: showLine2 12s ease-out infinite; }
      .sl3 { animation: showLine3 12s ease-out infinite; }
      .sl4 { animation: showLine4 12s ease-out infinite; }
      .sl5 { animation: showLine5 12s ease-out infinite; }
      .sp  { animation: showPrompt 12s ease-out infinite; }

      .da1 { animation: dotAppear1 12s ease-out infinite; }
      .da2 { animation: dotAppear2 12s ease-out infinite; }
      .da3 { animation: dotAppear3 12s ease-out infinite; }
      .da4 { animation: dotAppear4 12s ease-out infinite; }
    </style>

    <!-- glow filter -->
    <filter id="gf" x="-20%" y="-20%" width="140%" height="140%">
      <feGaussianBlur stdDeviation="2.5" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
    <filter id="softglow" x="-50%" y="-50%" width="200%" height="200%">
      <feGaussianBlur stdDeviation="4" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>

    <!-- radar sweep gradient -->
    <radialGradient id="radarBg" cx="50%" cy="50%" r="50%">
      <stop offset="0%" stop-color="#58a6ff" stop-opacity="0.04"/>
      <stop offset="100%" stop-color="#58a6ff" stop-opacity="0"/>
    </radialGradient>
    <linearGradient id="sweep" x1="0" y1="0" x2="1" y2="0">
      <stop offset="0%" stop-color="#58a6ff" stop-opacity="0"/>
      <stop offset="100%" stop-color="#58a6ff" stop-opacity="0.35"/>
    </linearGradient>
  </defs>

  <!-- background -->
  <rect width="800" height="400" fill="#0d1117" rx="12"/>

  <!-- subtle grid lines -->
  <line x1="0" y1="133" x2="800" y2="133" stroke="#ffffff" stroke-opacity="0.022" stroke-width="1"/>
  <line x1="0" y1="266" x2="800" y2="266" stroke="#ffffff" stroke-opacity="0.022" stroke-width="1"/>
  <line x1="266" y1="0" x2="266" y2="400" stroke="#ffffff" stroke-opacity="0.022" stroke-width="1"/>
  <line x1="532" y1="0" x2="532" y2="400" stroke="#ffffff" stroke-opacity="0.022" stroke-width="1"/>

  <!-- scanline sweep -->
  <rect class="scanline" x="0" y="0" width="800" height="8" fill="#58a6ff" fill-opacity="0.025" rx="0"/>

  <!-- ── LEFT: TERMINAL PANEL ── -->
  <rect x="28" y="28" width="440" height="344" rx="8" fill="#010409" stroke="#21262d" stroke-width="1"/>

  <!-- terminal top bar -->
  <rect x="28" y="28" width="440" height="36" rx="8" fill="#161b22"/>
  <rect x="28" y="52" width="440" height="12" fill="#161b22"/>
  <!-- traffic lights -->
  <circle cx="52" cy="46" r="5.5" fill="#ff5f57"/>
  <circle cx="70" cy="46" r="5.5" fill="#febc2e"/>
  <circle cx="88" cy="46" r="5.5" fill="#28c840"/>
  <!-- terminal title -->
  <text x="400" y="51" font-family="'JetBrains Mono',monospace" font-size="11" fill="#484f58" text-anchor="middle">tanmaya — python3</text>

  <!-- prompt line -->
  <text x="48" y="96" font-family="'JetBrains Mono',monospace" font-size="12" fill="#3fb950">tanmaya@codewithtea</text>
  <text x="196" y="96" font-family="'JetBrains Mono',monospace" font-size="12" fill="#484f58">:</text>
  <text x="202" y="96" font-family="'JetBrains Mono',monospace" font-size="12" fill="#58a6ff">~/projects</text>
  <text x="275" y="96" font-family="'JetBrains Mono',monospace" font-size="12" fill="#e6edf3">$ </text>
  <text x="291" y="96" font-family="'JetBrains Mono',monospace" font-size="12" fill="#e6edf3">python3 stack.py</text>

  <!-- output lines with typewriter animation -->
  <!-- line 1 -->
  <g class="sl1">
    <text x="48" y="124" font-family="'JetBrains Mono',monospace" font-size="12" fill="#484f58">›</text>
    <text x="60" y="124" font-family="'JetBrains Mono',monospace" font-size="12" fill="#8b949e">Loading</text>
    <text x="60" y="124" font-family="'JetBrains Mono',monospace" font-size="12" fill="#8b949e" class="tl1">  Python  ·  FastAPI  ·  Django</text>
  </g>

  <!-- line 2 -->
  <g class="sl2">
    <text x="48" y="150" font-family="'JetBrains Mono',monospace" font-size="12" fill="#484f58">›</text>
    <text x="60" y="150" font-family="'JetBrains Mono',monospace" font-size="12" fill="#8b949e">Loading</text>
    <text x="60" y="150" font-family="'JetBrains Mono',monospace" font-size="12" fill="#8b949e" class="tl2">  React  ·  Next.js  ·  Node</text>
  </g>

  <!-- line 3 -->
  <g class="sl3">
    <text x="48" y="176" font-family="'JetBrains Mono',monospace" font-size="12" fill="#484f58">›</text>
    <text x="60" y="176" font-family="'JetBrains Mono',monospace" font-size="12" fill="#8b949e">Loading</text>
    <text x="60" y="176" font-family="'JetBrains Mono',monospace" font-size="12" fill="#8b949e" class="tl3">  GSAP  ·  Three.js  ·  WebGL</text>
  </g>

  <!-- line 4 -->
  <g class="sl4">
    <text x="48" y="202" font-family="'JetBrains Mono',monospace" font-size="12" fill="#484f58">›</text>
    <text x="60" y="202" font-family="'JetBrains Mono',monospace" font-size="12" fill="#8b949e">Loading</text>
    <text x="60" y="202" font-family="'JetBrains Mono',monospace" font-size="12" fill="#8b949e" class="tl4">  PyTorch  ·  LangChain</text>
  </g>

  <!-- line 5 -->
  <g class="sl5">
    <text x="48" y="228" font-family="'JetBrains Mono',monospace" font-size="12" fill="#484f58">›</text>
    <text x="60" y="228" font-family="'JetBrains Mono',monospace" font-size="12" fill="#8b949e">Loading</text>
    <text x="60" y="228" font-family="'JetBrains Mono',monospace" font-size="12" fill="#8b949e" class="tl5">  Docker  ·  AWS  ·  GitHub CI</text>
  </g>

  <!-- success line -->
  <g class="sp">
    <text x="48" y="262" font-family="'JetBrains Mono',monospace" font-size="12" fill="#3fb950" filter="url(#gf)">✓ Stack initialized. Ready to ship.</text>
    <!-- next prompt -->
    <text x="48" y="292" font-family="'JetBrains Mono',monospace" font-size="12" fill="#3fb950">tanmaya@codewithtea</text>
    <text x="196" y="292" font-family="'JetBrains Mono',monospace" font-size="12" fill="#484f58">:</text>
    <text x="202" y="292" font-family="'JetBrains Mono',monospace" font-size="12" fill="#58a6ff">~/projects</text>
    <text x="275" y="292" font-family="'JetBrains Mono',monospace" font-size="12" fill="#e6edf3">$ </text>
    <rect class="cursor" x="291" y="280" width="8" height="14" fill="#58a6ff" opacity="0.9"/>
  </g>

  <!-- ── RIGHT: RADAR PANEL ── -->
  <rect x="492" y="28" width="280" height="344" rx="8" fill="#010409" stroke="#21262d" stroke-width="1"/>

  <!-- radar panel title -->
  <text x="632" y="60" font-family="'JetBrains Mono',monospace" font-size="10" fill="#484f58" text-anchor="middle">SKILL RADAR</text>
  <line x1="520" y1="68" x2="744" y2="68" stroke="#21262d" stroke-width="1"/>

  <!-- radar background -->
  <circle cx="632" cy="198" r="90" fill="url(#radarBg)"/>

  <!-- radar rings -->
  <circle cx="632" cy="198" r="72" fill="none" stroke="#21262d" stroke-width="0.8"/>
  <circle cx="632" cy="198" r="50" fill="none" stroke="#21262d" stroke-width="0.8"/>
  <circle cx="632" cy="198" r="28" fill="none" stroke="#21262d" stroke-width="0.8"/>

  <!-- radar crosshairs -->
  <line x1="632" y1="116" x2="632" y2="280" stroke="#21262d" stroke-width="0.8"/>
  <line x1="550" y1="198" x2="714" y2="198" stroke="#21262d" stroke-width="0.8"/>
  <line x1="574" y1="140" x2="690" y2="256" stroke="#21262d" stroke-width="0.8"/>
  <line x1="690" y1="140" x2="574" y2="256" stroke="#21262d" stroke-width="0.8"/>

  <!-- radar sweep (rotating) -->
  <g style="transform-origin:632px 198px; animation:radarSpin 4s linear infinite">
    <path d="M632,198 L632,126 A72,72 0 0,1 694,234 Z" fill="url(#sweep)" opacity="0.6"/>
  </g>

  <!-- skill dots with labels -->
  <!-- Python: top (strongest) -->
  <circle class="da1" cx="632" cy="130" r="3" fill="#3776AB" filter="url(#softglow)"/>
  <text x="632" y="122" font-family="'JetBrains Mono',monospace" font-size="9" fill="#3776AB" text-anchor="middle" class="da1">Python</text>

  <!-- MERN: right -->
  <circle class="da2" cx="700" cy="198" r="3" fill="#339933" filter="url(#softglow)"/>
  <text x="716" y="202" font-family="'JetBrains Mono',monospace" font-size="9" fill="#339933" text-anchor="start" class="da2">MERN</text>

  <!-- Animations: bottom-right -->
  <circle class="da3" cx="678" cy="256" r="3" fill="#88CE02" filter="url(#softglow)"/>
  <text x="688" y="268" font-family="'JetBrains Mono',monospace" font-size="9" fill="#88CE02" text-anchor="middle" class="da3">GSAP·3D</text>

  <!-- AI/ML: bottom-left -->
  <circle class="da4" cx="582" cy="256" r="3" fill="#EE4C2C" filter="url(#softglow)"/>
  <text x="572" y="268" font-family="'JetBrains Mono',monospace" font-size="9" fill="#EE4C2C" text-anchor="middle" class="da4">AI / ML</text>

  <!-- DevOps: left -->
  <circle cx="564" cy="198" r="3" fill="#2496ED" filter="url(#softglow)" style="animation:dotAppear4 12s ease-out infinite"/>
  <text x="548" y="202" font-family="'JetBrains Mono',monospace" font-size="9" fill="#2496ED" text-anchor="end" style="animation:dotAppear4 12s ease-out infinite">DevOps</text>

  <!-- radar center dot -->
  <circle cx="632" cy="198" r="3" fill="#58a6ff" opacity="0.8"/>
  <circle cx="632" cy="198" r="6" fill="none" stroke="#58a6ff" stroke-width="0.8" opacity="0.3"/>

  <!-- pulse rings on center -->
  <circle cx="632" cy="198" fill="none" stroke="#58a6ff" stroke-width="0.8">
    <animate attributeName="r" values="8;28;8" dur="3s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0.3;0;0.3" dur="3s" repeatCount="indefinite"/>
  </circle>

  <!-- bottom bar on radar -->
  <line x1="520" y1="312" x2="744" y2="312" stroke="#21262d" stroke-width="1"/>
  <text x="632" y="330" font-family="'JetBrains Mono',monospace" font-size="9" fill="#484f58" text-anchor="middle">codewithtea · tanmaya</text>
  <text x="632" y="346" font-family="'JetBrains Mono',monospace" font-size="9" fill="#3fb950" text-anchor="middle" filter="url(#gf)">● online</text>

  <!-- outer border glow -->
  <rect x="1" y="1" width="798" height="398" rx="12" fill="none" stroke="#58a6ff" stroke-width="0.5" stroke-opacity="0.15"/>
</svg>

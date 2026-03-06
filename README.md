<svg viewBox="0 0 860 200" xmlns="http://www.w3.org/2000/svg" width="860" height="200">
  <defs>
    <style>
      .bg { fill: #010409; }
      .grid { stroke: #00ffe0; stroke-width: 0.4; opacity: 0.08; }

      /* Floating particles */
      .p { fill: #00ffe0; }
      .p1 { animation: rise1 6s ease-in infinite; }
      .p2 { animation: rise2 8s ease-in infinite 1s; }
      .p3 { animation: rise3 7s ease-in infinite 2s; }
      .p4 { animation: rise4 9s ease-in infinite 0.5s; }
      .p5 { animation: rise5 6.5s ease-in infinite 3s; }
      .p6 { animation: rise6 7.5s ease-in infinite 1.5s; }

      @keyframes rise1 { 0%{transform:translate(120px,180px);opacity:.8} 100%{transform:translate(110px,10px);opacity:0} }
      @keyframes rise2 { 0%{transform:translate(300px,190px);opacity:.6} 100%{transform:translate(310px,5px);opacity:0} }
      @keyframes rise3 { 0%{transform:translate(500px,185px);opacity:.7} 100%{transform:translate(495px,8px);opacity:0} }
      @keyframes rise4 { 0%{transform:translate(680px,180px);opacity:.8} 100%{transform:translate(690px,12px);opacity:0} }
      @keyframes rise5 { 0%{transform:translate(200px,190px);opacity:.5} 100%{transform:translate(195px,6px);opacity:0} }
      @keyframes rise6 { 0%{transform:translate(760px,185px);opacity:.7} 100%{transform:translate(768px,9px);opacity:0} }

      /* Scanning line */
      .scan { animation: scanline 3.5s linear infinite; opacity: 0.15; }
      @keyframes scanline {
        0%  { transform: translateY(0px); opacity: 0; }
        10% { opacity: 0.15; }
        90% { opacity: 0.15; }
        100%{ transform: translateY(200px); opacity: 0; }
      }

      /* Name text */
      .name {
        font-family: 'Segoe UI', Arial, sans-serif;
        font-size: 58px;
        font-weight: 900;
        fill: url(#nameGrad);
        filter: url(#glow);
        animation: fadeUp 1s ease both;
      }
      @keyframes fadeUp {
        from { opacity:0; transform: translateY(20px); }
        to   { opacity:1; transform: translateY(0); }
      }

      /* Subtitle */
      .sub {
        font-family: 'Courier New', monospace;
        font-size: 14px;
        fill: #94a3b8;
        letter-spacing: 3px;
        animation: fadeUp 1s 0.4s ease both;
        opacity: 0;
        animation-fill-mode: forwards;
      }

      /* Tag line */
      .tag {
        font-family: 'Courier New', monospace;
        font-size: 12px;
        fill: #00ffe0;
        letter-spacing: 2px;
        animation: fadeUp 1s 0.8s ease both;
        opacity: 0;
        animation-fill-mode: forwards;
      }

      /* Underline */
      .uline {
        stroke: url(#lineGrad);
        stroke-width: 1.5;
        animation: expandLine 0.8s 0.3s ease both;
        opacity: 0;
        animation-fill-mode: forwards;
      }
      @keyframes expandLine {
        from { stroke-dasharray: 0 600; opacity: 0; }
        to   { stroke-dasharray: 600 0; opacity: 1; }
      }

      /* Corner brackets */
      .corner { stroke: #00ffe0; stroke-width: 1.5; fill: none; opacity: 0.5; }

      /* Gradient pulse on name */
      .nameGradStop1 { animation: colorCycle1 4s ease infinite; }
      .nameGradStop2 { animation: colorCycle2 4s ease infinite; }
      @keyframes colorCycle1 {
        0%,100% { stop-color: #00ffe0; }
        50%      { stop-color: #818cf8; }
      }
      @keyframes colorCycle2 {
        0%,100% { stop-color: #818cf8; }
        50%      { stop-color: #f472b6; }
      }
    </style>

    <linearGradient id="nameGrad" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" class="nameGradStop1"/>
      <stop offset="100%" class="nameGradStop2"/>
    </linearGradient>

    <linearGradient id="lineGrad" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" stop-color="transparent"/>
      <stop offset="50%" stop-color="#00ffe0"/>
      <stop offset="100%" stop-color="transparent"/>
    </linearGradient>

    <filter id="glow" x="-20%" y="-20%" width="140%" height="140%">
      <feGaussianBlur stdDeviation="4" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
  </defs>

  <!-- Background -->
  <rect width="860" height="200" class="bg" rx="12"/>

  <!-- Grid -->
  <line x1="0" y1="40"  x2="860" y2="40"  class="grid"/>
  <line x1="0" y1="80"  x2="860" y2="80"  class="grid"/>
  <line x1="0" y1="120" x2="860" y2="120" class="grid"/>
  <line x1="0" y1="160" x2="860" y2="160" class="grid"/>
  <line x1="100" y1="0" x2="100" y2="200" class="grid"/>
  <line x1="200" y1="0" x2="200" y2="200" class="grid"/>
  <line x1="300" y1="0" x2="300" y2="200" class="grid"/>
  <line x1="430" y1="0" x2="430" y2="200" class="grid"/>
  <line x1="560" y1="0" x2="560" y2="200" class="grid"/>
  <line x1="660" y1="0" x2="660" y2="200" class="grid"/>
  <line x1="760" y1="0" x2="760" y2="200" class="grid"/>

  <!-- Scanning line -->
  <rect x="0" y="0" width="860" height="2" fill="#00ffe0" class="scan"/>

  <!-- Particles -->
  <circle r="2.5" class="p p1" cx="0" cy="0"/>
  <circle r="2"   class="p p2" cx="0" cy="0"/>
  <circle r="2.5" class="p p3" cx="0" cy="0" fill="#818cf8"/>
  <circle r="2"   class="p p4" cx="0" cy="0" fill="#f472b6"/>
  <circle r="1.5" class="p p5" cx="0" cy="0"/>
  <circle r="2"   class="p p6" cx="0" cy="0" fill="#818cf8"/>

  <!-- Corner brackets -->
  <polyline points="18,18 18,42 42,42" class="corner"/>
  <polyline points="842,18 842,42 818,42" class="corner"/>
  <polyline points="18,182 18,158 42,158" class="corner"/>
  <polyline points="842,182 842,158 818,158" class="corner"/>

  <!-- Name -->
  <text x="430" y="100" text-anchor="middle" class="name">Prem Kumar</text>

  <!-- Underline -->
  <line x1="130" y1="116" x2="730" y2="116" class="uline" stroke-dasharray="0 600"/>

  <!-- Subtitle -->
  <text x="430" y="142" text-anchor="middle" class="sub">FULL STACK DEV · AI ENGINEER · OPEN SOURCE</text>

  <!-- Tag -->
  <text x="430" y="168" text-anchor="middle" class="tag">⚡ Building the future, one commit at a time ⚡</text>
</svg>

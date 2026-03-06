<svg width="900" height="200" viewBox="0 0 900 200" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <style>
      @keyframes fadeSlideUp {
        0%   { opacity:0; transform:translateY(22px); }
        100% { opacity:1; transform:translateY(0); }
      }
      @keyframes colorShift {
        0%,100% { fill:#a78bfa; }
        25%      { fill:#60a5fa; }
        50%      { fill:#34d399; }
        75%      { fill:#f472b6; }
      }
      @keyframes pulse {
        0%,100% { opacity:1; transform:scale(1); }
        50%      { opacity:0.6; transform:scale(1.15); }
      }
      @keyframes blink {
        0%,49% { opacity:1; }
        50%,100%{ opacity:0; }
      }
      @keyframes rise {
        0%   { transform:translate(var(--x),190px); opacity:0.9; }
        100% { transform:translate(var(--x),-10px);  opacity:0; }
      }
      @keyframes scanDown {
        0%   { transform:translateY(-4px); opacity:0; }
        8%   { opacity:0.18; }
        92%  { opacity:0.18; }
        100% { transform:translateY(204px); opacity:0; }
      }
      @keyframes drawLine {
        from { stroke-dashoffset: 800; }
        to   { stroke-dashoffset: 0; }
      }
      @keyframes glowPulse {
        0%,100% { filter: drop-shadow(0 0 6px #a78bfa); }
        50%      { filter: drop-shadow(0 0 18px #a78bfa) drop-shadow(0 0 30px #60a5fa); }
      }

      .bg  { fill: #0d1117; }
      .grid{ stroke:#a78bfa; stroke-width:0.3; opacity:0.07; }

      .name {
        font: 900 60px/1 'Segoe UI', Arial, sans-serif;
        fill: #a78bfa;
        animation: fadeSlideUp 0.9s ease both, colorShift 6s ease-in-out 1s infinite, glowPulse 3s ease-in-out infinite;
      }
      .sub {
        font: 600 15px/1 'Courier New', monospace;
        letter-spacing: 3.5px;
        fill: #8b949e;
        animation: fadeSlideUp 0.9s 0.5s ease both;
        opacity:0; animation-fill-mode:forwards;
      }
      .tag {
        font: 400 12px/1 'Courier New', monospace;
        letter-spacing: 2px;
        fill: #60a5fa;
        animation: fadeSlideUp 0.9s 0.9s ease both;
        opacity:0; animation-fill-mode:forwards;
      }
      .cursor {
        animation: blink 1s 1.3s step-end infinite;
        fill:#a78bfa; opacity:0; animation-fill-mode:forwards;
      }
      .divider {
        stroke:#a78bfa; stroke-width:1.5; fill:none; opacity:0.5;
        stroke-dasharray:800; stroke-dashoffset:800;
        animation: drawLine 1s 0.4s ease forwards;
      }
      .corner { stroke:#a78bfa; stroke-width:1.5; fill:none; opacity:0.4; }
      .dot { animation: pulse 2s ease-in-out infinite; fill:#34d399; }

      .p1{--x:80px;  animation:rise 5s 0.0s ease-in infinite; fill:#a78bfa; opacity:0;}
      .p2{--x:200px; animation:rise 6s 1.0s ease-in infinite; fill:#60a5fa; opacity:0;}
      .p3{--x:360px; animation:rise 4.5s 0.5s ease-in infinite; fill:#34d399; opacity:0;}
      .p4{--x:520px; animation:rise 7s 1.8s ease-in infinite; fill:#f472b6; opacity:0;}
      .p5{--x:690px; animation:rise 5.5s 0.3s ease-in infinite; fill:#a78bfa; opacity:0;}
      .p6{--x:810px; animation:rise 6.5s 2.5s ease-in infinite; fill:#60a5fa; opacity:0;}
      .p7{--x:140px; animation:rise 4s 3.0s ease-in infinite;   fill:#f472b6; opacity:0;}
      .p8{--x:620px; animation:rise 7.5s 1.2s ease-in infinite; fill:#34d399; opacity:0;}

      .scan { fill:#a78bfa; animation:scanDown 4s 0.5s linear infinite; opacity:0; }
    </style>
  </defs>

  <!-- BG -->
  <rect width="900" height="200" class="bg" rx="12"/>

  <!-- Grid -->
  <line x1="0"   y1="50"  x2="900" y2="50"  class="grid"/>
  <line x1="0"   y1="100" x2="900" y2="100" class="grid"/>
  <line x1="0"   y1="150" x2="900" y2="150" class="grid"/>
  <line x1="112" y1="0"   x2="112" y2="200" class="grid"/>
  <line x1="225" y1="0"   x2="225" y2="200" class="grid"/>
  <line x1="337" y1="0"   x2="337" y2="200" class="grid"/>
  <line x1="450" y1="0"   x2="450" y2="200" class="grid"/>
  <line x1="562" y1="0"   x2="562" y2="200" class="grid"/>
  <line x1="675" y1="0"   x2="675" y2="200" class="grid"/>
  <line x1="787" y1="0"   x2="787" y2="200" class="grid"/>

  <!-- Scan line -->
  <rect x="0" y="0" width="900" height="2" class="scan"/>

  <!-- Particles -->
  <circle r="2.5" class="p1" cx="0" cy="0"/>
  <circle r="2"   class="p2" cx="0" cy="0"/>
  <circle r="3"   class="p3" cx="0" cy="0"/>
  <circle r="2"   class="p4" cx="0" cy="0"/>
  <circle r="2.5" class="p5" cx="0" cy="0"/>
  <circle r="2"   class="p6" cx="0" cy="0"/>
  <circle r="1.5" class="p7" cx="0" cy="0"/>
  <circle r="2"   class="p8" cx="0" cy="0"/>

  <!-- Corner brackets -->
  <polyline points="16,16 16,42 42,42"     class="corner"/>
  <polyline points="884,16 884,42 858,42"  class="corner"/>
  <polyline points="16,184 16,158 42,158"  class="corner"/>
  <polyline points="884,184 884,158 858,158" class="corner"/>

  <!-- Status dot -->
  <circle cx="840" cy="30" r="5" class="dot"/>
  <text x="852" y="34" font="10px 'Courier New'" font-size="10" fill="#34d399" font-family="'Courier New',monospace" letter-spacing="1">ONLINE</text>

  <!-- Name -->
  <text x="450" y="98" text-anchor="middle" class="name">Prem Kumar</text>

  <!-- Cursor -->
  <rect x="680" y="62" width="3" height="46" class="cursor"/>

  <!-- Divider -->
  <line x1="100" y1="116" x2="800" y2="116" class="divider"/>

  <!-- Subtitle -->
  <text x="450" y="144" text-anchor="middle" class="sub">FULL STACK DEV  ·  AI ENGINEER  ·  OPEN SOURCE</text>

  <!-- Tag -->
  <text x="450" y="170" text-anchor="middle" class="tag">⚡ building the future, one commit at a time ⚡</text>
</svg>

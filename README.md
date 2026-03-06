<svg width="860" height="190" viewBox="0 0 860 190" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <style>
      @keyframes fadeIn {
        from { opacity: 0; transform: translateY(16px); }
        to   { opacity: 1; transform: translateY(0); }
      }
      @keyframes gradient {
        0%,100% { fill: #6366f1; }
        33%      { fill: #8b5cf6; }
        66%      { fill: #06b6d4; }
      }
      @keyframes blink {
        0%,100% { opacity: 1; }
        50%      { opacity: 0; }
      }
      @keyframes rise {
        0%   { transform: translateY(0px);   opacity: 0.7; }
        100% { transform: translateY(-160px); opacity: 0; }
      }
      @keyframes scanline {
        0%   { transform: translateY(-2px); opacity: 0; }
        5%   { opacity: 0.2; }
        95%  { opacity: 0.2; }
        100% { transform: translateY(192px); opacity: 0; }
      }
      @keyframes expand {
        from { stroke-dashoffset: 700; }
        to   { stroke-dashoffset: 0; }
      }

      .bg   { fill: #0d1117; }
      .name {
        font: 900 56px/1 'Segoe UI', Arial, sans-serif;
        animation: fadeIn 0.8s ease both, gradient 4s ease-in-out 0.8s infinite;
        fill: #6366f1;
      }
      .sub {
        font: 500 15px/1 'Courier New', monospace;
        fill: #8b949e;
        letter-spacing: 3px;
        animation: fadeIn 0.8s 0.4s ease both;
        opacity: 0;
        animation-fill-mode: forwards;
      }
      .cursor {
        fill: #6366f1;
        animation: blink 1s step-end 1.2s infinite;
        opacity: 0;
        animation-fill-mode: forwards;
      }
      .line {
        stroke: #6366f1;
        stroke-width: 1.5;
        fill: none;
        stroke-dasharray: 700;
        stroke-dashoffset: 700;
        animation: expand 1s 0.3s ease forwards;
        opacity: 0.4;
      }
      .p1 { fill: #6366f1; animation: rise 4s 0.0s ease-in infinite; opacity: 0; }
      .p2 { fill: #8b5cf6; animation: rise 5s 0.8s ease-in infinite; opacity: 0; }
      .p3 { fill: #06b6d4; animation: rise 4.5s 1.6s ease-in infinite; opacity: 0; }
      .p4 { fill: #6366f1; animation: rise 3.5s 2.4s ease-in infinite; opacity: 0; }
      .p5 { fill: #8b5cf6; animation: rise 5.5s 0.4s ease-in infinite; opacity: 0; }
      .p6 { fill: #06b6d4; animation: rise 4s 3.0s ease-in infinite; opacity: 0; }
      .scan {
        fill: #6366f1;
        animation: scanline 3s 1s linear infinite;
        opacity: 0;
      }
      .corner { stroke: #6366f1; stroke-width: 1.5; fill: none; opacity: 0.35; }
      .grid   { stroke: #6366f1; stroke-width: 0.3; opacity: 0.06; }
    </style>
  </defs>

  <!-- Background -->
  <rect width="860" height="190" class="bg" rx="10"/>

  <!-- Grid -->
  <line x1="0"   y1="47"  x2="860" y2="47"  class="grid"/>
  <line x1="0"   y1="95"  x2="860" y2="95"  class="grid"/>
  <line x1="0"   y1="143" x2="860" y2="143" class="grid"/>
  <line x1="143" y1="0"   x2="143" y2="190" class="grid"/>
  <line x1="286" y1="0"   x2="286" y2="190" class="grid"/>
  <line x1="430" y1="0"   x2="430" y2="190" class="grid"/>
  <line x1="573" y1="0"   x2="573" y2="190" class="grid"/>
  <line x1="716" y1="0"   x2="716" y2="190" class="grid"/>

  <!-- Scan line -->
  <rect x="0" y="0" width="860" height="2" class="scan"/>

  <!-- Particles -->
  <circle cx="90"  cy="170" r="2.5" class="p1"/>
  <circle cx="220" cy="175" r="2"   class="p2"/>
  <circle cx="380" cy="170" r="3"   class="p3"/>
  <circle cx="530" cy="175" r="2"   class="p4"/>
  <circle cx="670" cy="170" r="2.5" class="p5"/>
  <circle cx="790" cy="172" r="2"   class="p6"/>

  <!-- Corner brackets -->
  <polyline points="16,16 16,38 38,38"   class="corner"/>
  <polyline points="844,16 844,38 822,38" class="corner"/>
  <polyline points="16,174 16,152 38,152"   class="corner"/>
  <polyline points="844,174 844,152 822,152" class="corner"/>

  <!-- Name -->
  <text x="430" y="96" text-anchor="middle" class="name">Prem Kumar</text>

  <!-- Cursor blink after name -->
  <rect x="658" y="68" width="3" height="40" class="cursor"/>

  <!-- Divider line -->
  <line x1="130" y1="112" x2="730" y2="112" class="line"/>

  <!-- Subtitle -->
  <text x="430" y="138" text-anchor="middle" class="sub">FULL STACK DEV  ·  AI ENGINEER  ·  OPEN SOURCE</text>
</svg>

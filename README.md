<svg width="900" height="280" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <linearGradient id="bg" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#0d0d1a"/>
      <stop offset="50%" style="stop-color:#0a1628"/>
      <stop offset="100%" style="stop-color:#0d0d1a"/>
    </linearGradient>
    <linearGradient id="textGrad" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" style="stop-color:#38bdf8">
        <animate attributeName="stop-color" values="#38bdf8;#818cf8;#f472b6;#38bdf8" dur="4s" repeatCount="indefinite"/>
      </stop>
      <stop offset="100%" style="stop-color:#818cf8">
        <animate attributeName="stop-color" values="#818cf8;#f472b6;#38bdf8;#818cf8" dur="4s" repeatCount="indefinite"/>
      </stop>
    </linearGradient>
    <linearGradient id="lineGrad" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" style="stop-color:transparent"/>
      <stop offset="50%" style="stop-color:#38bdf8"/>
      <stop offset="100%" style="stop-color:transparent"/>
    </linearGradient>
    <filter id="glow">
      <feGaussianBlur stdDeviation="3" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
    <filter id="textGlow">
      <feGaussianBlur stdDeviation="6" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
  </defs>

  <!-- Background -->
  <rect width="900" height="280" fill="url(#bg)"/>

  <!-- Animated grid lines -->
  <g opacity="0.07">
    <line x1="0" y1="56" x2="900" y2="56" stroke="#38bdf8" stroke-width="0.5"/>
    <line x1="0" y1="112" x2="900" y2="112" stroke="#38bdf8" stroke-width="0.5"/>
    <line x1="0" y1="168" x2="900" y2="168" stroke="#38bdf8" stroke-width="0.5"/>
    <line x1="0" y1="224" x2="900" y2="224" stroke="#38bdf8" stroke-width="0.5"/>
    <line x1="112" y1="0" x2="112" y2="280" stroke="#38bdf8" stroke-width="0.5"/>
    <line x1="225" y1="0" x2="225" y2="280" stroke="#38bdf8" stroke-width="0.5"/>
    <line x1="337" y1="0" x2="337" y2="280" stroke="#38bdf8" stroke-width="0.5"/>
    <line x1="450" y1="0" x2="450" y2="280" stroke="#38bdf8" stroke-width="0.5"/>
    <line x1="562" y1="0" x2="562" y2="280" stroke="#38bdf8" stroke-width="0.5"/>
    <line x1="675" y1="0" x2="675" y2="280" stroke="#38bdf8" stroke-width="0.5"/>
    <line x1="787" y1="0" x2="787" y2="280" stroke="#38bdf8" stroke-width="0.5"/>
  </g>

  <!-- Floating orbs -->
  <circle cx="80" cy="60" r="60" fill="#38bdf8" opacity="0.04">
    <animate attributeName="cy" values="60;90;60" dur="7s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0.04;0.08;0.04" dur="7s" repeatCount="indefinite"/>
  </circle>
  <circle cx="820" cy="200" r="80" fill="#818cf8" opacity="0.05">
    <animate attributeName="cy" values="200;170;200" dur="9s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0.05;0.09;0.05" dur="9s" repeatCount="indefinite"/>
  </circle>
  <circle cx="450" cy="30" r="50" fill="#f472b6" opacity="0.03">
    <animate attributeName="r" values="50;70;50" dur="6s" repeatCount="indefinite"/>
  </circle>

  <!-- Animated particles -->
  <circle cx="150" cy="220" r="2" fill="#38bdf8" opacity="0.6">
    <animate attributeName="cy" values="220;40;220" dur="5s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0.6;0;0.6" dur="5s" repeatCount="indefinite"/>
  </circle>
  <circle cx="300" cy="180" r="1.5" fill="#818cf8" opacity="0.5">
    <animate attributeName="cy" values="180;20;180" dur="6.5s" repeatCount="indefinite" begin="1s"/>
    <animate attributeName="opacity" values="0.5;0;0.5" dur="6.5s" repeatCount="indefinite" begin="1s"/>
  </circle>
  <circle cx="500" cy="240" r="2" fill="#f472b6" opacity="0.5">
    <animate attributeName="cy" values="240;30;240" dur="7s" repeatCount="indefinite" begin="2s"/>
    <animate attributeName="opacity" values="0.5;0;0.5" dur="7s" repeatCount="indefinite" begin="2s"/>
  </circle>
  <circle cx="650" cy="200" r="1.5" fill="#38bdf8" opacity="0.6">
    <animate attributeName="cy" values="200;50;200" dur="5.5s" repeatCount="indefinite" begin="0.5s"/>
    <animate attributeName="opacity" values="0.6;0;0.6" dur="5.5s" repeatCount="indefinite" begin="0.5s"/>
  </circle>
  <circle cx="780" cy="160" r="2" fill="#818cf8" opacity="0.5">
    <animate attributeName="cy" values="160;10;160" dur="8s" repeatCount="indefinite" begin="3s"/>
    <animate attributeName="opacity" values="0.5;0;0.5" dur="8s" repeatCount="indefinite" begin="3s"/>
  </circle>
  <circle cx="60" cy="140" r="1.5" fill="#f472b6" opacity="0.4">
    <animate attributeName="cy" values="140;10;140" dur="6s" repeatCount="indefinite" begin="1.5s"/>
    <animate attributeName="opacity" values="0.4;0;0.4" dur="6s" repeatCount="indefinite" begin="1.5s"/>
  </circle>
  <circle cx="840" cy="100" r="2" fill="#38bdf8" opacity="0.5">
    <animate attributeName="cy" values="100;260;100" dur="9s" repeatCount="indefinite" begin="4s"/>
    <animate attributeName="opacity" values="0.5;0;0.5" dur="9s" repeatCount="indefinite" begin="4s"/>
  </circle>

  <!-- Main name text with gradient + glow -->
  <text x="450" y="125" text-anchor="middle" font-family="'Segoe UI', Arial, sans-serif" font-size="68" font-weight="900" fill="url(#textGrad)" filter="url(#textGlow)" letter-spacing="2">
    Prem Kumar
    <animate attributeName="opacity" values="0;1" dur="1s" fill="freeze"/>
  </text>

  <!-- Subtitle -->
  <text x="450" y="168" text-anchor="middle" font-family="'Courier New', monospace" font-size="17" fill="#94a3b8" letter-spacing="4">
    FULL STACK DEV  ·  AI ENGINEER  ·  OPEN SOURCE
    <animate attributeName="opacity" values="0;0;1" dur="1.8s" fill="freeze"/>
  </text>

  <!-- Animated underline -->
  <line x1="150" y1="185" x2="750" y2="185" stroke="url(#lineGrad)" stroke-width="1.5">
    <animate attributeName="x1" values="450;150;150" dur="1.2s" fill="freeze"/>
    <animate attributeName="x2" values="450;750;750" dur="1.2s" fill="freeze"/>
  </line>

  <!-- Bottom tagline -->
  <text x="450" y="228" text-anchor="middle" font-family="'Courier New', monospace" font-size="13" fill="#38bdf8" letter-spacing="2" opacity="0.8">
    ⚡ Building the future, one commit at a time ⚡
    <animate attributeName="opacity" values="0;0;0;0.8" dur="2.5s" fill="freeze"/>
  </text>

  <!-- Corner decorations -->
  <g fill="none" stroke="#38bdf8" stroke-width="1.5" opacity="0.4">
    <polyline points="20,20 20,50 50,50"/>
    <polyline points="880,20 880,50 850,50"/>
    <polyline points="20,260 20,230 50,230"/>
    <polyline points="880,260 880,230 850,230"/>
  </g>

  <!-- Scanning line animation -->
  <rect x="0" y="0" width="900" height="2" fill="url(#lineGrad)" opacity="0.3">
    <animate attributeName="y" values="0;278;0" dur="4s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0.3;0.1;0.3" dur="4s" repeatCount="indefinite"/>
  </rect>
</svg>

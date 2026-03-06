<svg xmlns="http://www.w3.org/2000/svg" width="900" height="80" viewBox="0 0 900 80">
  <defs>
    <style>
      .text-1, .text-2, .text-3, .text-4 {
        font: 700 22px 'Courier New', monospace;
        fill: #a78bfa;
        text-anchor: middle;
        animation-duration: 12s;
        animation-timing-function: ease-in-out;
        animation-iteration-count: infinite;
      }
      .text-1 { animation-name: t1; }
      .text-2 { animation-name: t2; }
      .text-3 { animation-name: t3; }
      .text-4 { animation-name: t4; }

      @keyframes t1 {
        0%,20%  { opacity:1; transform:translateY(0); }
        25%,95% { opacity:0; transform:translateY(-10px); }
        100%    { opacity:1; transform:translateY(0); }
      }
      @keyframes t2 {
        0%,20%  { opacity:0; transform:translateY(10px); }
        25%,45% { opacity:1; transform:translateY(0); }
        50%,100%{ opacity:0; transform:translateY(-10px); }
      }
      @keyframes t3 {
        0%,45%  { opacity:0; transform:translateY(10px); }
        50%,70% { opacity:1; transform:translateY(0); }
        75%,100%{ opacity:0; transform:translateY(-10px); }
      }
      @keyframes t4 {
        0%,70%  { opacity:0; transform:translateY(10px); }
        75%,95% { opacity:1; transform:translateY(0); }
        100%    { opacity:0; transform:translateY(-10px); }
      }
    </style>
  </defs>
  <rect width="900" height="80" fill="#0d1117" rx="8"/>
  <text x="450" y="47" class="text-1">🚀 Full Stack Developer &amp; AI Engineer</text>
  <text x="450" y="47" class="text-2">🤖 Building AI-Powered Apps</text>
  <text x="450" y="47" class="text-3">☁️ Cloud · DevOps · Open Source</text>
  <text x="450" y="47" class="text-4">💡 Always Learning · Always Shipping</text>
</svg>

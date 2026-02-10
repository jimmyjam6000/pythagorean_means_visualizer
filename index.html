<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Pythagorean Means (radius = 1)</title>
  <style>
    :root { --bg:#0b0f14; --fg:#e9eef5; --muted:#a9b4c0; --panel:#121926; --stroke:#cfd8e3; }
    body { margin:0; font-family: system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, sans-serif; background:var(--bg); color:var(--fg); }
    .wrap { display:grid; grid-template-columns: 1.2fr 0.8fr; gap:16px; padding:16px; max-width:1100px; margin:0 auto; }
    .card { background:var(--panel); border:1px solid rgba(255,255,255,0.08); border-radius:16px; padding:14px; }
    h1 { font-size:18px; margin:0 0 8px; }
    .row { display:flex; align-items:center; gap:10px; flex-wrap:wrap; }
    label { font-size:14px; color:var(--muted); }
    input[type="range"] { width: 340px; }
    .mono { font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace; }
    .kv { display:grid; grid-template-columns: 1fr auto; gap:6px 10px; margin-top:10px; }
    .kv div { font-size:14px; }
    .eq { color:var(--muted); line-height:1.5; font-size:13px; }
    .hint { color:var(--muted); font-size:13px; margin-top:8px; }
    svg { width:100%; height:auto; display:block; }
    .badge { padding:2px 8px; border-radius:999px; font-size:12px; border:1px solid rgba(255,255,255,0.12); color:var(--muted); }
  </style>
</head>
<body>
  <div class="wrap">
    <div class="card">
      <div class="row" style="justify-content:space-between;">
        <h1>Pythagorean Means in a Circle (radius = 1 ⇒ AM(a,b)=1)</h1>
        <span class="badge mono">a + b = 2</span>
      </div>

      <!-- VIEWBOX is in math-coordinates: x,y in roughly [-1.25, 1.75] x [-0.25, 1.75] -->
      <svg id="viz" viewBox="-1.25 -1.65 3.0 3.45" aria-label="Pythagorean means visualization">
        <!-- axes (subtle) -->
        <line x1="-1.2" y1="0" x2="1.6" y2="0" stroke="rgba(255,255,255,0.08)" stroke-width="0.01" />
        <line x1="0" y1="-1.55" x2="0" y2="1.65" stroke="rgba(255,255,255,0.08)" stroke-width="0.01" />

        <!-- circle radius 1 centered at origin -->
        <circle cx="0" cy="0" r="1" fill="none" stroke="rgba(233,238,245,0.85)" stroke-width="0.02" />

        <!-- diameter -->
        <line x1="-1" y1="0" x2="1" y2="0" stroke="rgba(233,238,245,0.85)" stroke-width="0.03" />

        <!-- dynamic groups -->
        <g id="dynamic"></g>

        <!-- legend text -->
        <text x="-1.18" y="1.55" fill="rgba(233,238,245,0.9)" font-size="0.09" class="mono">
          a (left) + b (right) = 2
        </text>
      </svg>

      <div class="row" style="margin-top:10px;">
        <label for="bRange">Move b:</label>
        <input id="bRange" type="range" min="0.05" max="1.95" step="0.001" value="1.00" />
        <span class="mono" id="bLabel"></span>
      </div>

      <div class="hint">
        The geometric mean segment uses the classic semicircle fact:
        for a point splitting the diameter into lengths <span class="mono">a</span> and <span class="mono">b</span>,
        the perpendicular to the circle has length <span class="mono">GM = √(ab)</span>.
      </div>
    </div>

    <div class="card">
      <h1>Values & formulas</h1>

      <div class="kv mono">
        <div>a</div><div id="aVal"></div>
        <div>b</div><div id="bVal"></div>
        <div>AM</div><div id="amVal"></div>
        <div>GM</div><div id="gmVal"></div>
        <div>HM</div><div id="hmVal"></div>
        <div>QM</div><div id="qmVal"></div>
      </div>

      <hr style="border:none;border-top:1px solid rgba(255,255,255,0.10); margin:12px 0;" />

      <div class="eq mono" id="eqBlock"></div>

      <div class="hint">
        Note: since <span class="mono">a + b = 2</span>, we get <span class="mono">AM = (a+b)/2 = 1</span> always,
        and <span class="mono">HM = 2ab/(a+b) = ab</span>.
      </div>
    </div>
  </div>

<script>
(function(){
  const svgNS = "http://www.w3.org/2000/svg";
  const dyn = document.getElementById("dynamic");
  const bRange = document.getElementById("bRange");

  const bLabel = document.getElementById("bLabel");
  const aVal = document.getElementById("aVal");
  const bVal = document.getElementById("bVal");
  const amVal = document.getElementById("amVal");
  const gmVal = document.getElementById("gmVal");
  const hmVal = document.getElementById("hmVal");
  const qmVal = document.getElementById("qmVal");
  const eqBlock = document.getElementById("eqBlock");

  function el(name, attrs = {}) {
    const n = document.createElementNS(svgNS, name);
    for (const [k,v] of Object.entries(attrs)) n.setAttribute(k, v);
    return n;
  }

  function fmt(x) {
    return (Math.round(x * 1000) / 1000).toFixed(3);
  }

  function clear(node) {
    while (node.firstChild) node.removeChild(node.firstChild);
  }

  function update() {
    const b = parseFloat(bRange.value);
    const a = 2 - b;

    const AM = (a + b) / 2;             // = 1
    const GM = Math.sqrt(a * b);
    const HM = (2 * a * b) / (a + b);   // = ab because a+b=2
    const QM = Math.sqrt((a*a + b*b) / 2);

    // geometry: diameter endpoints at x=-1 and x=+1. Split point M at x = -1 + a = 1 - b
    const xM = 1 - b;
    const yGM = Math.sqrt(Math.max(0, 1 - xM*xM)); // equals sqrt(ab) when a+b=2, radius=1

    // update labels
    bLabel.textContent = `b = ${fmt(b)} (a = ${fmt(a)})`;
    aVal.textContent = fmt(a);
    bVal.textContent = fmt(b);
    amVal.textContent = fmt(AM);
    gmVal.textContent = fmt(GM);
    hmVal.textContent = fmt(HM);
    qmVal.textContent = fmt(QM);

    eqBlock.innerHTML =
      `AM(a,b) = (a + b)/2 = 1\n` +
      `GM(a,b) = √(ab) = ${fmt(GM)}\n` +
      `HM(a,b) = 2ab/(a + b) = ab = ${fmt(HM)}\n` +
      `QM(a,b) = √((a² + b²)/2) = ${fmt(QM)}\n`;

    // redraw dynamic SVG pieces
    clear(dyn);

    // split point M
    dyn.appendChild(el("circle", { cx: xM, cy: 0, r: 0.03, fill: "rgba(233,238,245,0.95)" }));
    dyn.appendChild(el("text", {
      x: xM + 0.03, y: -0.06, fill: "rgba(233,238,245,0.9)", "font-size": "0.09"
    })).textContent = "M";

    // segment a (left) along diameter: from -1 to xM
    dyn.appendChild(el("line", {
      x1: -1, y1: 0, x2: xM, y2: 0,
      stroke: "rgba(190, 120, 255, 0.95)", "stroke-width": "0.05", "stroke-linecap":"round"
    }));
    dyn.appendChild(el("text", {
      x: (-1 + xM)/2, y: 0.12, fill: "rgba(190, 120, 255, 0.95)", "font-size":"0.10", class:"mono"
    })).textContent = `a=${fmt(a)}`;

    // segment b (right) along diameter: from xM to +1
    dyn.appendChild(el("line", {
      x1: xM, y1: 0, x2: 1, y2: 0,
      stroke: "rgba(80, 220, 255, 0.95)", "stroke-width": "0.05", "stroke-linecap":"round"
    }));
    dyn.appendChild(el("text", {
      x: (xM + 1)/2, y: 0.12, fill: "rgba(80, 220, 255, 0.95)", "font-size":"0.10", class:"mono"
    })).textContent = `b=${fmt(b)}`;

    // geometric mean: perpendicular from M to circle (upward)
    dyn.appendChild(el("line", {
      x1: xM, y1: 0, x2: xM, y2: yGM,
      stroke: "rgba(120, 255, 170, 0.95)", "stroke-width":"0.04", "stroke-linecap":"round"
    }));
    dyn.appendChild(el("circle", { cx: xM, cy: yGM, r: 0.028, fill: "rgba(120, 255, 170, 0.95)" }));
    dyn.appendChild(el("text", {
      x: xM + 0.05, y: yGM - 0.03, fill:"rgba(120, 255, 170, 0.95)", "font-size":"0.10", class:"mono"
    })).textContent = `GM=√(ab)=${fmt(GM)}`;

    // arithmetic mean: radius 1 (fixed) drawn as vertical segment from origin
    dyn.appendChild(el("line", {
      x1: 0, y1: 0, x2: 0, y2: 1,
      stroke: "rgba(255, 210, 90, 0.95)", "stroke-width":"0.035", "stroke-linecap":"round"
    }));
    dyn.appendChild(el("text", {
      x: 0.05, y: 1.03, fill:"rgba(255, 210, 90, 0.95)", "font-size":"0.10", class:"mono"
    })).textContent = "AM=1";

    // harmonic mean: draw on +x axis from origin to (HM, 0)
    dyn.appendChild(el("line", {
      x1: 0, y1: 0, x2: HM, y2: 0,
      stroke: "rgba(255, 140, 140, 0.95)", "stroke-width":"0.035", "stroke-linecap":"round"
    }));
    dyn.appendChild(el("text", {
      x: Math.min(HM + 0.05, 1.25), y: -0.08,
      fill:"rgba(255, 140, 140, 0.95)", "font-size":"0.10", class:"mono"
    })).textContent = `HM=${fmt(HM)}`;

    // quadratic mean: vertical segment from origin up to QM (can exceed circle)
    dyn.appendChild(el("line", {
      x1: -0.15, y1: 0, x2: -0.15, y2: QM,
      stroke: "rgba(160, 200, 255, 0.95)", "stroke-width":"0.03", "stroke-linecap":"round",
      "stroke-dasharray":"0.05 0.05"
    }));
    dyn.appendChild(el("text", {
      x: -0.62, y: QM + 0.02,
      fill:"rgba(160, 200, 255, 0.95)", "font-size":"0.10", class:"mono"
    })).textContent = `QM=${fmt(QM)}`;

    // helper: show where circle height equals GM (so user sees equality GM == yGM)
    dyn.appendChild(el("text", {
      x: -1.18, y: -1.45,
      fill:"rgba(233,238,245,0.65)", "font-size":"0.085", class:"mono"
    })).textContent = `Check: y(M)=√(1−x_M²)=√(b(2−b))=√(ab)=GM`;
  }

  bRange.addEventListener("input", update, { passive: true });
  update();
})();
</script>
</body>
</html>

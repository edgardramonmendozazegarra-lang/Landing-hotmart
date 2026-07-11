<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Manual de Fotografía: Click Perfecto</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,400;0,9..144,600;0,9..144,700;0,9..144,900;1,9..144,500&family=Work+Sans:wght@400;500;600;700&family=IBM+Plex+Mono:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#14120f;
    --panel:#1d1a15;
    --panel-2:#242019;
    --paper:#f3eee3;
    --ink:#211d17;
    --amber:#e8a33d;
    --amber-dark:#c97f1e;
    --rust:#c1442e;
    --grey:#948d80;
    --grey-dim:#5c574c;
    --line: rgba(243,238,227,0.14);
  }
  *{box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    margin:0;
    background:var(--bg);
    color:var(--paper);
    font-family:'Work Sans', sans-serif;
    font-size:16px;
    line-height:1.6;
    -webkit-font-smoothing:antialiased;
  }
  h1,h2,h3{
    font-family:'Fraunces', serif;
    font-weight:700;
    margin:0;
    letter-spacing:-0.01em;
  }
  .mono{
    font-family:'IBM Plex Mono', monospace;
    letter-spacing:0.04em;
  }
  a{color:inherit;}
  img{max-width:100%;display:block;}
  .wrap{max-width:1080px;margin:0 auto;padding:0 24px;}
  section{position:relative;}

  /* ---------- viewfinder corner brackets, signature motif ---------- */
  .frame{position:relative;}
  .frame::before,.frame::after,.frame span::before,.frame span::after{
    content:"";
    position:absolute;
    width:22px;height:22px;
    border-color:var(--amber);
    border-style:solid;
    opacity:0.55;
  }
  .frame::before{top:-1px;left:-1px;border-width:2px 0 0 2px;}
  .frame::after{top:-1px;right:-1px;border-width:2px 2px 0 0;}
  .frame span::before{bottom:-1px;left:-1px;border-width:0 0 2px 2px;position:absolute;}
  .frame span::after{bottom:-1px;right:-1px;border-width:0 2px 2px 0;position:absolute;}

  /* ---------- sticky top bar ---------- */
  .topbar{
    position:sticky;top:0;z-index:50;
    background:rgba(20,18,15,0.86);
    backdrop-filter:blur(10px);
    border-bottom:1px solid var(--line);
  }
  .topbar-inner{
    max-width:1080px;margin:0 auto;padding:12px 24px;
    display:flex;align-items:center;justify-content:space-between;gap:16px;
  }
  .topbar-title{font-size:0.95rem;letter-spacing:0.02em;color:var(--paper);opacity:0.9;}
  .topbar-title b{color:var(--amber);}
  .btn-small{
    display:inline-flex;align-items:center;gap:8px;
    background:var(--amber);color:#1a1200;
    font-family:'Work Sans',sans-serif;font-weight:700;font-size:0.85rem;
    padding:10px 18px;border-radius:3px;text-decoration:none;
    white-space:nowrap;
    transition:transform .15s ease, background .15s ease;
  }
  .btn-small:hover{background:var(--amber-dark);transform:translateY(-1px);}
  .btn-small:focus-visible{outline:2px solid var(--paper);outline-offset:2px;}

  /* ---------- big CTA button ---------- */
  .btn-big{
    display:inline-flex;align-items:center;gap:14px;
    background:var(--amber);color:#1a1200;
    font-family:'Work Sans',sans-serif;font-weight:700;
    font-size:1.15rem;
    padding:20px 38px;
    border-radius:4px;
    text-decoration:none;
    box-shadow:0 12px 32px -8px rgba(232,163,61,0.45);
    transition:transform .18s ease, box-shadow .18s ease, background .18s ease;
  }
  .btn-big:hover{transform:translateY(-2px);background:var(--amber-dark);box-shadow:0 16px 36px -6px rgba(232,163,61,0.55);}
  .btn-big:focus-visible{outline:3px solid var(--paper);outline-offset:3px;}
  .btn-big .arrow{transition:transform .18s ease;}
  .btn-big:hover .arrow{transform:translateX(4px);}
  .btn-note{font-size:0.8rem;color:var(--grey);margin-top:10px;}

  /* ---------- hero ---------- */
  .hero{
    padding:96px 0 110px;
    overflow:hidden;
    background:
      radial-gradient(circle at 18% 20%, rgba(232,163,61,0.16), transparent 42%),
      radial-gradient(circle at 82% 70%, rgba(193,68,46,0.14), transparent 45%),
      var(--bg);
  }
  .bokeh{position:absolute;inset:0;pointer-events:none;z-index:0;}
  .bokeh span{
    position:absolute;border-radius:50%;
    filter:blur(2px);
    opacity:0.5;
  }
  .eyebrow{
    display:inline-flex;align-items:center;gap:10px;
    font-size:0.72rem;letter-spacing:0.16em;text-transform:uppercase;
    color:var(--amber);margin-bottom:22px;
  }
  .eyebrow::before{content:"";width:26px;height:1px;background:var(--amber);}
  .hero-grid{
    position:relative;z-index:1;
    display:grid;grid-template-columns:1.15fr 0.85fr;gap:56px;align-items:center;
  }
  .hero h1{font-size:clamp(2.3rem,4.4vw,3.6rem);line-height:1.05;color:var(--paper);}
  .hero h1 em{font-style:italic;color:var(--amber);}
  .hero p.lead{font-size:1.12rem;color:#d9d2c2;max-width:46ch;margin:22px 0 34px;}

  /* book cover mock */
  .cover-stage{display:flex;justify-content:center;position:relative;}
  .cover{
    width:290px;aspect-ratio:3/4.2;
    background:linear-gradient(155deg,#211d16,#171410 60%);
    border:1px solid rgba(243,238,227,0.16);
    border-radius:6px;
    padding:26px 24px;
    position:relative;
    box-shadow:0 40px 70px -20px rgba(0,0,0,0.7), 0 0 0 1px rgba(0,0,0,0.4);
    transform:rotate(2.2deg);
  }
  .cover-eyebrow{font-size:0.62rem;letter-spacing:0.2em;color:var(--grey);text-transform:uppercase;}
  .cover h3{font-size:1.55rem;color:var(--paper);margin-top:14px;line-height:1.15;}
  .cover h3 em{color:var(--amber);font-style:italic;display:block;font-size:1.7rem;margin-top:4px;}
  .aperture{
    position:absolute;bottom:26px;right:24px;width:64px;height:64px;
  }
  .cover-foot{position:absolute;bottom:26px;left:24px;font-size:0.68rem;color:var(--grey);}

  /* ---------- generic section padding ---------- */
  .section{padding:88px 0;}
  .section-tight{padding:64px 0;}
  .kicker{
    font-size:0.72rem;letter-spacing:0.16em;text-transform:uppercase;color:var(--amber);
    margin-bottom:14px;display:block;
  }
  .section h2{font-size:clamp(1.8rem,3vw,2.5rem);color:var(--paper);max-width:20ch;}
  .section p.sub{color:#c9c1b1;max-width:56ch;margin-top:16px;font-size:1.02rem;}

  /* ---------- pain section ---------- */
  .pain{background:var(--panel);}
  .pain-grid{
    margin-top:48px;
    display:grid;grid-template-columns:repeat(2,1fr);gap:1px;
    background:var(--line);
    border:1px solid var(--line);
  }
  .pain-item{
    background:var(--panel);
    padding:30px 28px;
    display:flex;gap:16px;
  }
  .pain-item svg{flex:none;width:26px;height:26px;stroke:var(--rust);margin-top:2px;}
  .pain-item p{margin:0;color:#d9d2c2;font-size:0.98rem;}
  .pain-item b{color:var(--paper);display:block;margin-bottom:4px;font-size:1.02rem;}

  /* ---------- solution ---------- */
  .solution{background:var(--bg);}
  .solution-grid{
    margin-top:48px;
    display:grid;grid-template-columns:1fr 1fr;gap:60px;align-items:start;
  }
  .feat-list{list-style:none;margin:0;padding:0;display:flex;flex-direction:column;gap:22px;}
  .feat-list li{display:flex;gap:16px;align-items:flex-start;}
  .feat-num{
    font-family:'IBM Plex Mono',monospace;
    color:var(--amber);font-size:0.85rem;
    border:1px solid var(--line);border-radius:50%;
    width:30px;height:30px;flex:none;
    display:flex;align-items:center;justify-content:center;
  }
  .feat-list b{color:var(--paper);display:block;margin-bottom:2px;}
  .feat-list span{color:#bdb5a4;font-size:0.95rem;}

  .spec-card{
    background:var(--panel-2);border:1px solid var(--line);border-radius:6px;
    padding:26px 28px;margin-top:8px;
  }
  .spec-row{
    display:flex;justify-content:space-between;
    padding:12px 0;border-bottom:1px dashed var(--line);
    font-size:0.92rem;
  }
  .spec-row:last-child{border-bottom:none;}
  .spec-row .k{color:var(--grey);}
  .spec-row .v{font-family:'IBM Plex Mono',monospace;color:var(--paper);}

  /* ---------- angles / for you if ---------- */
  .angles{background:var(--panel);}
  .angles-grid{margin-top:48px;display:grid;grid-template-columns:1fr 1fr;gap:1px;background:var(--line);border:1px solid var(--line);}
  .angle-card{background:var(--panel);padding:36px 32px;}
  .angle-card .tag{font-family:'IBM Plex Mono',monospace;font-size:0.7rem;letter-spacing:0.08em;color:var(--amber);text-transform:uppercase;}
  .angle-card p{color:#d9d2c2;font-size:1rem;margin-top:14px;}

  /* ---------- social proof placeholders ---------- */
  .proof{background:var(--bg);}
  .proof-grid{margin-top:44px;display:grid;grid-template-columns:repeat(3,1fr);gap:22px;}
  .proof-card{
    border:1px dashed var(--line);border-radius:6px;padding:26px 22px;
    background:var(--panel-2);min-height:170px;display:flex;flex-direction:column;justify-content:space-between;
  }
  .proof-card p{color:var(--grey);font-style:italic;font-size:0.92rem;margin:0;}
  .proof-card .who{margin-top:16px;font-size:0.78rem;color:var(--grey-dim);font-family:'IBM Plex Mono',monospace;}

  /* ---------- pricing ---------- */
  .pricing{
    background:linear-gradient(180deg, var(--panel), #17140f);
    border-top:1px solid var(--line);border-bottom:1px solid var(--line);
  }
  .price-grid{
    margin-top:48px;
    display:grid;grid-template-columns:1fr 1fr;gap:48px;align-items:center;
  }
  .value-stack{background:var(--panel-2);border:1px solid var(--line);border-radius:6px;padding:30px 30px 24px;}
  .value-row{display:flex;justify-content:space-between;align-items:baseline;padding:11px 0;border-bottom:1px solid var(--line);font-size:0.95rem;}
  .value-row:last-of-type{border-bottom:none;}
  .value-row .v{font-family:'IBM Plex Mono',monospace;color:var(--paper);}
  .value-total{display:flex;justify-content:space-between;padding-top:16px;margin-top:6px;border-top:1px solid var(--line);}
  .value-total .k{color:var(--grey);}
  .value-total .v{font-family:'IBM Plex Mono',monospace;color:var(--grey);text-decoration:line-through;}

  .price-panel{text-align:center;}
  .dial-wrap{display:flex;justify-content:center;margin-bottom:12px;}
  .price-tag{
    font-family:'IBM Plex Mono',monospace;
    font-size:0.78rem;color:var(--amber);letter-spacing:0.1em;text-transform:uppercase;
  }
  .price-big{
    font-family:'Fraunces',serif;font-weight:900;
    font-size:5rem;color:var(--paper);line-height:1;margin:10px 0 4px;
  }
  .price-big sup{font-size:2rem;top:-2.4rem;}
  .price-old{color:var(--grey);text-decoration:line-through;font-family:'IBM Plex Mono',monospace;font-size:1rem;}
  .urgency{
    margin-top:20px;display:inline-flex;align-items:center;gap:10px;
    background:rgba(193,68,46,0.14);border:1px solid rgba(193,68,46,0.4);
    color:#f0a793;padding:9px 16px;border-radius:4px;font-size:0.85rem;
  }
  .urgency .dot{width:7px;height:7px;border-radius:50%;background:var(--rust);animation:pulse 1.4s infinite;}
  @keyframes pulse{0%,100%{opacity:1;}50%{opacity:.25;}}
  .timer{font-family:'IBM Plex Mono',monospace;color:var(--paper);}

  .guarantee{
    margin-top:34px;display:flex;gap:14px;align-items:flex-start;
    border-top:1px solid var(--line);padding-top:26px;text-align:left;
  }
  .guarantee svg{flex:none;width:30px;height:30px;stroke:var(--amber);}
  .guarantee p{margin:0;color:#c9c1b1;font-size:0.9rem;}
  .guarantee b{color:var(--paper);display:block;margin-bottom:2px;}

  /* ---------- final cta ---------- */
  .final{
    text-align:center;padding:110px 0 100px;
    background:
      radial-gradient(circle at 50% 0%, rgba(232,163,61,0.14), transparent 55%),
      var(--bg);
  }
  .final h2{font-size:clamp(2rem,3.6vw,2.9rem);max-width:22ch;margin:0 auto 18px;}
  .final p{color:#c9c1b1;max-width:48ch;margin:0 auto 38px;}

  footer{padding:34px 0;text-align:center;color:var(--grey-dim);font-size:0.78rem;border-top:1px solid var(--line);}

  @media (max-width:820px){
    .hero-grid{grid-template-columns:1fr;}
    .cover-stage{order:-1;margin-bottom:8px;}
    .cover{width:230px;}
    .solution-grid,.price-grid,.angles-grid{grid-template-columns:1fr;}
    .pain-grid,.proof-grid{grid-template-columns:1fr;}
    .topbar-title{font-size:0.8rem;}
  }
  @media (prefers-reduced-motion:reduce){
    *{animation:none !important;transition:none !important;}
  }
</style>
</head>
<body>

<div class="topbar">
  <div class="topbar-inner">
    <div class="topbar-title">Manual de Fotografía: <b>Click Perfecto</b></div>
    <a class="btn-small" href="https://pay.hotmart.com/B106673888R" target="_blank" rel="noopener">Comprar · $9</a>
  </div>
</div>

<!-- ============ HERO ============ -->
<section class="hero">
  <div class="bokeh" aria-hidden="true">
    <span style="width:180px;height:180px;background:var(--amber);top:10%;left:6%;"></span>
    <span style="width:120px;height:120px;background:var(--rust);top:60%;left:14%;opacity:0.3;"></span>
    <span style="width:90px;height:90px;background:var(--amber);top:20%;left:82%;opacity:0.35;"></span>
    <span style="width:150px;height:150px;background:var(--rust);top:70%;left:78%;opacity:0.22;"></span>
  </div>
  <div class="wrap hero-grid">
    <div>
      <span class="eyebrow">Manual de fotografía · Edición digital</span>
      <h1>Deja el modo automático.<br>Domina el <em>Click Perfecto.</em></h1>
      <p class="lead">Sin manuales técnicos aburridos ni teoría de ingeniería óptica. Solo los ajustes exactos que necesitas tocar para que tus fotos dejen de verse "amateur" y empiecen a dejar a todos con la boca abierta — desde tu primer disparo en manual.</p>
      <a class="btn-big" href="https://pay.hotmart.com/B106673888R" target="_blank" rel="noopener">
        Quiero mi manual por $9 <span class="arrow">→</span>
      </a>
      <div class="btn-note">Descarga inmediata en PDF · Acceso de por vida · Pago 100% seguro vía Hotmart</div>
    </div>
    <div class="cover-stage">
      <div class="cover frame"><span></span>
        <div class="cover-eyebrow">Manual práctico</div>
        <h3>Click<em>Perfecto</em></h3>
        <svg class="aperture" viewBox="0 0 100 100" aria-hidden="true">
          <g fill="none" stroke="#e8a33d" stroke-width="2" opacity="0.9">
            <polygon points="50,8 82,28 82,72 50,92 18,72 18,28" opacity="0.35"/>
            <polygon points="50,20 72,33 72,67 50,80 28,67 28,33" opacity="0.7"/>
            <circle cx="50" cy="50" r="12" fill="#e8a33d" opacity="0.9" stroke="none"/>
          </g>
        </svg>
        <div class="cover-foot mono">f/9 · ISO 400 · 1/125s</div>
      </div>
    </div>
  </div>
</section>

<!-- ============ PAIN / AGITACIÓN ============ -->
<section class="pain section">
  <div class="wrap">
    <span class="kicker">La frustración de hoy</span>
    <h2>Tienes una cámara capaz de mucho más de lo que le estás pidiendo.</h2>
    <p class="sub">Si algo de esto te suena familiar, no es que te falte "ojo" — es que nadie te ha explicado los tres ajustes que realmente importan, en un lenguaje que se entiende.</p>
    <div class="pain-grid">
      <div class="pain-item">
        <svg viewBox="0 0 24 24" fill="none" stroke-width="1.6"><path d="M3 17l6-6 4 4 8-8"/><circle cx="12" cy="12" r="10" stroke-dasharray="2 3"/></svg>
        <p><b>Fotos que salen borrosas o "planas"</b>Aunque enfocaste bien, la imagen no transmite nada. Le falta profundidad, luz, intención.</p>
      </div>
      <div class="pain-item">
        <svg viewBox="0 0 24 24" fill="none" stroke-width="1.6"><rect x="7" y="2" width="10" height="20" rx="2"/><line x1="11" y1="18" x2="13" y2="18"/></svg>
        <p><b>Tu celular te "gana" a la cámara</b>Sientes que pagaste por un equipo profesional que apenas sabes usar en modo automático.</p>
      </div>
      <div class="pain-item">
        <svg viewBox="0 0 24 24" fill="none" stroke-width="1.6"><circle cx="12" cy="12" r="9"/><path d="M9.5 9a2.5 2.5 0 015 .5c0 1.7-2.5 2-2.5 4"/><line x1="12" y1="17" x2="12" y2="17.2"/></svg>
        <p><b>Miedo a tocar el modo manual</b>ISO, apertura, velocidad... suena a examen de física. Prefieres no arriesgarte a "arruinar" la toma.</p>
      </div>
      <div class="pain-item">
        <svg viewBox="0 0 24 24" fill="none" stroke-width="1.6"><path d="M2 12h4M18 12h4M12 2v4M12 18v4"/><circle cx="12" cy="12" r="5"/></svg>
        <p><b>Ves fotos ajenas espectaculares</b>Y no logras identificar qué hicieron distinto. La diferencia nunca fue el equipo — fue el criterio.</p>
      </div>
    </div>
  </div>
</section>

<!-- ============ SOLUCIÓN ============ -->
<section class="solution section">
  <div class="wrap solution-grid">
    <div>
      <span class="kicker">La solución simplificada</span>
      <h2>Un manual, no un curso. Se lee en una tarde, se aplica de por vida.</h2>
      <p class="sub" style="margin-bottom:34px;">Click Perfecto está escrito para alguien que quiere resultados ya, no una carrera de fotografía. Cada capítulo te deja con un ajuste concreto para probar con tu propia cámara, hoy mismo.</p>
      <ul class="feat-list">
        <li><span class="feat-num">1</span><div><b>El triángulo de exposición sin fórmulas</b><span>ISO, apertura y velocidad explicados con ejemplos, no con física.</span></div></li>
        <li><span class="feat-num">2</span><div><b>Errores invisibles que arruinan tus fotos</b><span>Y la corrección exacta para cada uno, en menos de 2 minutos.</span></div></li>
        <li><span class="feat-num">3</span><div><b>Compatible con cualquier equipo</b><span>DSLR, mirrorless o el celular que ya tienes en el bolsillo.</span></div></li>
      </ul>
    </div>
    <div class="spec-card frame"><span></span>
      <div class="spec-row"><span class="k">Formato</span><span class="v">PDF descargable</span></div>
      <div class="spec-row"><span class="k">Extensión</span><span class="v">46 páginas</span></div>
      <div class="spec-row"><span class="k">Lectura</span><span class="v">Celular · tablet · PC</span></div>
      <div class="spec-row"><span class="k">Acceso</span><span class="v">De por vida</span></div>
      <div class="spec-row"><span class="k">Entrega</span><span class="v">Inmediata al pagar</span></div>
    </div>
  </div>
</section>

<!-- ============ ÁNGULOS: PARA QUIÉN ============ -->
<section class="angles section-tight">
  <div class="wrap">
    <span class="kicker">¿Es esto para ti?</span>
    <h2>Click Perfecto se adapta a lo que buscas capturar.</h2>
    <div class="angles-grid">
      <div class="angle-card">
        <span class="tag">Control técnico</span>
        <p>Deja de adivinar las configuraciones de tu cámara. Toma el control total del modo manual, domina la nitidez perfecta y logra un aspecto profesional desde el primer disparo.</p>
      </div>
      <div class="angle-card">
        <span class="tag">Momentos e historias</span>
        <p>No dejes que los momentos importantes salgan borrosos o sin vida. Aprende a componer imágenes que transmiten emociones reales y a dominar la luz natural, de forma fácil.</p>
      </div>
    </div>
  </div>
</section>

<!-- ============ PRUEBA SOCIAL ============ -->
<section class="proof section">
  <div class="wrap">
    <span class="kicker">Prueba social</span>
    <h2>Lo que dicen quienes ya lo están aplicando.</h2>
    <p class="sub">Espacio reservado para tus propias capturas de pantalla o testimonios reales (Instagram, WhatsApp, reseñas). Reemplaza estas tarjetas con ejemplos verídicos antes de publicar — la prueba social funciona mejor cuando es 100% auténtica.</p>
    <div class="proof-grid">
      <div class="proof-card"><p>"[Espacio para una captura real: antes / después de un alumno]"</p><div class="who">— agrega nombre y usuario real</div></div>
      <div class="proof-card"><p>"[Espacio para un testimonio real sobre un resultado logrado con el manual]"</p><div class="who">— agrega nombre y usuario real</div></div>
      <div class="proof-card"><p>"[Espacio para una reseña real de Hotmart o redes sociales]"</p><div class="who">— agrega nombre y usuario real</div></div>
    </div>
  </div>
</section>

<!-- ============ PRICING ============ -->
<section class="pricing section">
  <div class="wrap">
    <span class="kicker">Tu ajuste perfecto</span>
    <h2>Todo lo que necesitas para dejar de disparar a ciegas.</h2>
    <div class="price-grid">
      <div class="value-stack">
        <div class="value-row"><span>Manual completo "Click Perfecto" (46 págs.)</span><span class="v">$37</span></div>
        <div class="value-row"><span>Acceso de por vida</span><span class="v">$12</span></div>
        <div class="value-total"><span class="k">Valor total</span><span class="v">$49</span></div>
      </div>
      <div class="price-panel">
        <div class="dial-wrap">
          <svg width="88" height="88" viewBox="0 0 100 100" aria-hidden="true">
            <circle cx="50" cy="50" r="46" fill="none" stroke="#3a352b" stroke-width="1.5"/>
            <g fill="none" stroke="#e8a33d" stroke-width="2">
              <polygon points="50,8 82,28 82,72 50,92 18,72 18,28" opacity="0.3"/>
              <polygon points="50,20 72,33 72,67 50,80 28,67 28,33" opacity="0.75"/>
            </g>
            <circle cx="50" cy="50" r="10" fill="#e8a33d"/>
          </svg>
        </div>
        <div class="price-tag">Precio de lanzamiento</div>
        <div class="price-big">$9</div>
        <div class="price-old">Precio regular $27</div>

        <div class="urgency">
          <span class="dot"></span>
          Sube a $27 en <span class="timer" id="countdown">15:00</span>
        </div>

        <div style="margin-top:30px;">
          <a class="btn-big" href="https://pay.hotmart.com/B106673888R" target="_blank" rel="noopener">
            Llevarme el manual · $9 <span class="arrow">→</span>
          </a>
        </div>

        <div class="guarantee">
          <svg viewBox="0 0 24 24" fill="none" stroke-width="1.6"><path d="M12 2l8 4v6c0 5-3.5 8.5-8 10-4.5-1.5-8-5-8-10V6l8-4z"/><path d="M9 12l2 2 4-4"/></svg>
          <p><b>Garantía de 7 días</b>Si sientes que no era lo que esperabas, escribe y te devolvemos tu dinero. Sin preguntas incómodas.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ============ FINAL CTA ============ -->
<section class="final">
  <div class="wrap">
    <span class="kicker" style="justify-content:center;display:flex;">Última llamada</span>
    <h2>Tu cámara ya sabe hacer fotos increíbles. Falta que tú lo sepas también.</h2>
    <p>Click Perfecto por $9, acceso inmediato, para siempre.</p>
    <a class="btn-big" href="https://pay.hotmart.com/B106673888R" target="_blank" rel="noopener">
      Quiero mi Click Perfecto <span class="arrow">→</span>
    </a>
    <div class="btn-note">Pago seguro procesado por Hotmart · Descarga en PDF al instante</div>
  </div>
</section>

<footer>
  Manual de Fotografía: Click Perfecto — Producto digital de entrega inmediata.
</footer>

<script>
  (function(){
    var totalSeconds = 15 * 60; // countdown only in-memory, resets on reload
    var el = document.getElementById('countdown');
    function tick(){
      if(totalSeconds <= 0){ el.textContent = "00:00"; return; }
      totalSeconds--;
      var m = Math.floor(totalSeconds/60);
      var s = totalSeconds%60;
      el.textContent = (m<10?'0':'')+m+':'+(s<10?'0':'')+s;
    }
    setInterval(tick, 1000);
  })();
</script>

</body>
</html>

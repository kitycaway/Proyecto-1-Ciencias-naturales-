# Proyecto-1-Ciencias-naturales-
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Ciencias Naturales y Exactas II</title>
  <link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800;900&family=Comfortaa:wght@400;600;700&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --green-dark:   #3a7d5c;
      --green-mid:    #6ab68a;
      --green-light:  #a8d8b8;
      --green-pale:   #d4f0e0;
      --green-bg:     #edf7f1;
      --mint:         #c6ead8;
      --sage:         #8fbfa8;
      --accent:       #f7c59f;
      --accent2:      #f9e4b7;
      --text-dark:    #2b4a39;
      --text-mid:     #4a7a62;
      --white:        #ffffff;
      --card-shadow:  0 4px 24px rgba(58,125,92,0.13);
    }
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; }
    body {
      font-family: 'Nunito', sans-serif;
      background: var(--green-bg);
      color: var(--text-dark);
      min-height: 100vh;
    }

    /* ── HEADER ── */
    header {
      background: linear-gradient(135deg, var(--green-dark) 0%, var(--green-mid) 60%, var(--mint) 100%);
      padding: 48px 24px 56px;
      text-align: center;
      position: relative;
      overflow: hidden;
    }
    header::before {
      content: '';
      position: absolute; inset: 0;
      background: radial-gradient(ellipse at 20% 50%, rgba(255,255,255,0.12) 0%, transparent 60%),
                  radial-gradient(ellipse at 80% 20%, rgba(255,255,255,0.08) 0%, transparent 50%);
    }
    .header-icon { font-size: 3.2rem; margin-bottom: 10px; display: block; animation: float 3s ease-in-out infinite; }
    @keyframes float { 0%,100%{transform:translateY(0)} 50%{transform:translateY(-8px)} }
    header h1 {
      font-family: 'Comfortaa', cursive;
      font-size: clamp(1.6rem, 5vw, 2.8rem);
      color: var(--white);
      font-weight: 700;
      letter-spacing: -0.5px;
      position: relative;
      text-shadow: 0 2px 12px rgba(0,0,0,0.18);
    }
    header p {
      margin-top: 10px;
      color: var(--green-pale);
      font-size: 1.05rem;
      position: relative;
    }

    /* ── NAV ── */
    nav {
      background: var(--white);
      box-shadow: 0 2px 12px rgba(58,125,92,0.10);
      position: sticky; top: 0; z-index: 100;
      display: flex; flex-wrap: wrap; justify-content: center; gap: 6px;
      padding: 12px 16px;
    }
    nav a {
      text-decoration: none;
      background: var(--green-pale);
      color: var(--green-dark);
      font-weight: 700;
      font-size: 0.85rem;
      padding: 7px 16px;
      border-radius: 50px;
      transition: background 0.2s, color 0.2s, transform 0.15s;
      border: 2px solid transparent;
    }
    nav a:hover {
      background: var(--green-dark);
      color: var(--white);
      transform: translateY(-2px);
    }

    /* ── MAIN ── */
    main { max-width: 960px; margin: 0 auto; padding: 36px 16px 60px; }

    /* ── SECTION ── */
    .section {
      margin-bottom: 48px;
      animation: fadeUp 0.5s ease both;
    }
    @keyframes fadeUp { from{opacity:0;transform:translateY(20px)} to{opacity:1;transform:translateY(0)} }
    .section-header {
      display: flex; align-items: center; gap: 14px;
      background: linear-gradient(90deg, var(--green-dark), var(--green-mid));
      color: var(--white);
      padding: 16px 24px;
      border-radius: 18px 18px 0 0;
      margin-bottom: 0;
    }
    .section-number {
      background: rgba(255,255,255,0.22);
      border-radius: 50%;
      width: 38px; height: 38px;
      display: flex; align-items: center; justify-content: center;
      font-weight: 900; font-size: 1rem;
      flex-shrink: 0;
    }
    .section-header h2 { font-size: 1.05rem; font-weight: 700; line-height: 1.3; }
    .section-body {
      background: var(--white);
      border-radius: 0 0 18px 18px;
      padding: 20px;
      box-shadow: var(--card-shadow);
    }
    .section-desc {
      font-size: 0.92rem;
      color: var(--text-mid);
      margin-bottom: 18px;
      padding: 10px 14px;
      background: var(--green-pale);
      border-left: 4px solid var(--green-mid);
      border-radius: 0 10px 10px 0;
      line-height: 1.6;
    }

    /* ── GRID DE VIDEOS ── */
    .videos-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
      gap: 16px;
    }
    .video-card {
      border-radius: 14px;
      overflow: hidden;
      border: 2px solid var(--green-pale);
      background: var(--green-bg);
      transition: transform 0.2s, box-shadow 0.2s, border-color 0.2s;
    }
    .video-card:hover {
      transform: translateY(-4px);
      box-shadow: 0 8px 28px rgba(58,125,92,0.18);
      border-color: var(--green-mid);
    }
    .video-thumb {
      position: relative;
      width: 100%;
      padding-top: 56.25%;
      background: var(--green-pale);
    }
    .video-thumb iframe {
      position: absolute; inset: 0;
      width: 100%; height: 100%;
      border: none;
    }
    .video-info {
      padding: 10px 12px;
    }
    .video-label {
      font-size: 0.75rem;
      font-weight: 800;
      color: var(--green-dark);
      background: var(--green-pale);
      display: inline-block;
      padding: 2px 10px;
      border-radius: 50px;
      margin-bottom: 5px;
    }
    .video-title {
      font-size: 0.85rem;
      color: var(--text-dark);
      font-weight: 600;
      line-height: 1.4;
    }
    .video-link {
      display: inline-flex; align-items: center; gap: 5px;
      margin-top: 7px;
      font-size: 0.78rem;
      font-weight: 700;
      color: var(--green-dark);
      text-decoration: none;
      background: var(--green-pale);
      padding: 4px 11px;
      border-radius: 50px;
      transition: background 0.2s, color 0.2s;
    }
    .video-link:hover { background: var(--green-dark); color: var(--white); }

    /* ── FOOTER ── */
    footer {
      text-align: center;
      padding: 28px 16px;
      background: var(--green-dark);
      color: var(--green-pale);
      font-size: 0.85rem;
    }
    footer span { color: var(--accent); font-weight: 700; }

    /* ── ACCESIBILIDAD ── */
    :focus-visible { outline: 3px solid var(--green-mid); outline-offset: 3px; }
  </style>
</head>
<body>

<header>
  <span class="header-icon" aria-hidden="true">🌿</span>
  <h1>Ciencias Naturales y Exactas II</h1>
  <p>Energía, Fuerza, Calor y Termodinámica — Recursos de Aprendizaje</p>
</header>

<nav aria-label="Propósitos formativos">
  <a href="#pf1">⚡ Energía</a>
  <a href="#pf2">🏃 Fuerza y Movimiento</a>
  <a href="#pf3">🌡️ Calor y Temperatura</a>
  <a href="#pf4">🔥 Transferencia de Calor</a>
  <a href="#pf5">⚙️ Termodinámica</a>
</nav>

<main>

  <!-- PF1 -->
  <section class="section" id="pf1">
    <div class="section-header">
      <div class="section-number" aria-hidden="true">1</div>
      <h2>Propósito Formativo 1 — Energía y sus Transformaciones</h2>
    </div>
    <div class="section-body">
      <p class="section-desc">
        Comprende, a partir del análisis de fenómenos naturales cotidianos, que la energía puede transformarse y transferirse sin destruirse. Temas: tipos de energía, energías renovables y no renovables, conservación de la energía y magnitudes fundamentales.
      </p>
      <div class="videos-grid">

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/NAPAMIpGB-s?start=35"
              title="¿Qué es la energía? – Tipos de energía – Energías renovables y no renovables"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen
              loading="lazy"
              alt="Video educativo sobre tipos de energía y energías renovables y no renovables"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 1.1</span>
            <p class="video-title">¿Qué es la energía? – Tipos de energía – Renovables y No Renovables</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=NAPAMIpGB-s&t=35s" target="_blank" rel="noopener" aria-label="Ver video 1.1 en YouTube: Tipos de energía">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/b2khuHTzkeU?start=217"
              title="La Energía y sus Transformaciones – Renovables vs No Renovables"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video sobre transformaciones de energía y diferencia entre renovables y no renovables"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 1.2</span>
            <p class="video-title">🔋 La Energía y sus Transformaciones 🌀 Renovables vs No Renovables ⚡</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=b2khuHTzkeU&t=217s" target="_blank" rel="noopener" aria-label="Ver video 1.2 en YouTube: Transformaciones de energía">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/khTgRuS2yeM"
              title="Principio de Conservación de la Energía"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video explicativo del principio de conservación de la energía en 2 minutos"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 1.3</span>
            <p class="video-title">✅ Principio de Conservación de la Energía (en 2 minutos)</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=khTgRuS2yeM" target="_blank" rel="noopener" aria-label="Ver video 1.3: Principio de Conservación de la Energía">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/o8ReM0JgLRI"
              title="Magnitudes Fundamentales – Física"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video sobre magnitudes fundamentales en Física, fácil y rápido"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 1.4</span>
            <p class="video-title">📏 Magnitudes Fundamentales 💡 Fácil y Rápido – Física</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=o8ReM0JgLRI" target="_blank" rel="noopener" aria-label="Ver video 1.4: Magnitudes Fundamentales">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/gaYnhERIgpw"
              title="CNEyT II – Definición de Energía"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video de CNEyT II sobre la definición de energía"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 1.5</span>
            <p class="video-title">CNEyT II — Definición de Energía</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=gaYnhERIgpw" target="_blank" rel="noopener" aria-label="Ver video 1.5: Definición de Energía CNEyT">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/ETPPqhSdJYU"
              title="CNEyT II – La Ley de la Conservación de la Energía"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video de CNEyT II explicando la Ley de Conservación de la Energía"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 1.6</span>
            <p class="video-title">CNEyT II — La Ley de la Conservación de la Energía</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=ETPPqhSdJYU" target="_blank" rel="noopener" aria-label="Ver video 1.6: Ley de Conservación de la Energía">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/AhXB_YgJcIw"
              title="CNEyT II – Medidas de Energía"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video de CNEyT II sobre las medidas de energía y sus unidades"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 1.7</span>
            <p class="video-title">CNEyT II — Medidas de Energía</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=AhXB_YgJcIw" target="_blank" rel="noopener" aria-label="Ver video 1.7: Medidas de Energía CNEyT">▶ Ver en YouTube</a>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- PF2 -->
  <section class="section" id="pf2">
    <div class="section-header">
      <div class="section-number">2</div>
      <h2>Propósito Formativo 2 — Fuerza, Movimiento y Energía Mecánica</h2>
    </div>
    <div class="section-body">
      <p class="section-desc">
        Analiza el cambio de posición de un cuerpo al interactuar con otro, para comprender los conceptos de fuerza, movimiento y su relación con la energía mecánica. Incluye cinemática, velocidad, trayectorias y sistemas de referencia.
      </p>
      <div class="videos-grid">

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/bv89Bs187aU"
              title="Fuerza y Movimiento"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video educativo sobre fuerza y movimiento en física"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 2.1</span>
            <p class="video-title">Fuerza y Movimiento</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=bv89Bs187aU" target="_blank" rel="noopener" aria-label="Ver video 2.1: Fuerza y Movimiento">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/h3Hvb3Xadq8"
              title="CNEyT II – Concepto de Fuerza"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video de CNEyT II explicando el concepto de fuerza en física"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 2.2</span>
            <p class="video-title">CNEyT II — Concepto de Fuerza</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=h3Hvb3Xadq8" target="_blank" rel="noopener" aria-label="Ver video 2.2: Concepto de Fuerza CNEyT">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/62zygT_0QA4"
              title="CNEyT II – Posición, Movimiento y Velocidad"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video de CNEyT II sobre conceptos de posición, movimiento y velocidad"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 2.3</span>
            <p class="video-title">CNEyT II — Conceptos de Posición, Movimiento y Velocidad</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=62zygT_0QA4" target="_blank" rel="noopener" aria-label="Ver video 2.3: Posición, Movimiento y Velocidad">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/MgfyjHAvJWg"
              title="CNEyT II – La Energía Mecánica y Cinética"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video de CNEyT II sobre energía mecánica y cinética"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 2.4</span>
            <p class="video-title">CNEyT II — La Energía Mecánica y Cinética</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=MgfyjHAvJWg" target="_blank" rel="noopener" aria-label="Ver video 2.4: Energía Mecánica y Cinética">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/BE6TxBjwYj4"
              title="Física – La Cinemática: móvil, trayectorias y sistemas de referencia"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video sobre cinemática, trayectorias y sistemas de referencia inercial y no inercial"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 2.5</span>
            <p class="video-title">Física — La Cinemática: móvil, trayectorias y sistemas de referencia</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=BE6TxBjwYj4" target="_blank" rel="noopener" aria-label="Ver video 2.5: La Cinemática">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/ojJdAzwdJVQ"
              title="Física – Movimiento Relativo y Sistemas de Referencia"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video sobre movimiento relativo y sistemas de referencia en física"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 2.6</span>
            <p class="video-title">Física — Movimiento Relativo y Sistemas de Referencia</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=ojJdAzwdJVQ" target="_blank" rel="noopener" aria-label="Ver video 2.6: Movimiento Relativo">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/RCtpSqn9p64"
              title="La velocidad como factor de riesgo en la conducción"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video sobre cómo la velocidad es un factor de riesgo en la conducción vehicular"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 2.7</span>
            <p class="video-title">La velocidad como factor de riesgo en la conducción</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=RCtpSqn9p64" target="_blank" rel="noopener" aria-label="Ver video 2.7: Velocidad como factor de riesgo">▶ Ver en YouTube</a>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- PF3 -->
  <section class="section" id="pf3">
    <div class="section-header">
      <div class="section-number">3</div>
      <h2>Propósito Formativo 3 — Calor, Temperatura y Equilibrio Térmico</h2>
    </div>
    <div class="section-body">
      <p class="section-desc">
        Analiza el intercambio de calor entre cuerpos y con el entorno, para comprender su concepto, el de temperatura y su diferencia. Incluye transferencia de calor, equilibrio térmico y escalas termométricas.
      </p>
      <div class="videos-grid">

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/YxSkljBNvoI"
              title="Calor y Temperatura: diferencias, transferencia, cómo se miden"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video sobre diferencias entre calor y temperatura, su transferencia y formas de medirlos"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 3.1</span>
            <p class="video-title">Calor y Temperatura: diferencias, transferencia, cómo se miden, ejemplos</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=YxSkljBNvoI" target="_blank" rel="noopener" aria-label="Ver video 3.1: Calor y Temperatura">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/On0qZBpYTgk"
              title="La Transferencia del Calor"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video educativo sobre los mecanismos de transferencia del calor"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 3.2</span>
            <p class="video-title">La Transferencia del Calor</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=On0qZBpYTgk" target="_blank" rel="noopener" aria-label="Ver video 3.2: Transferencia del Calor">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/uKL5dhWxlZs"
              title="El calor y el equilibrio térmico – Experimento"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video con experimento demostrativo sobre calor y equilibrio térmico"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 3.3</span>
            <p class="video-title">El calor y el equilibrio térmico — Experimento</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=uKL5dhWxlZs" target="_blank" rel="noopener" aria-label="Ver video 3.3: Equilibrio Térmico">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/sJLJGeTEhJs"
              title="Cómo afecta el plástico al cambio climático"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video sobre el impacto del plástico en el cambio climático"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 3.4</span>
            <p class="video-title">Cómo afecta el plástico al cambio climático</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=sJLJGeTEhJs" target="_blank" rel="noopener" aria-label="Ver video 3.4: Plástico y Cambio Climático">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/E2iEWYGShEU"
              title="CNEyT II – Calor y Temperatura"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video de CNEyT II sobre calor y temperatura y sus diferencias"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 3.5</span>
            <p class="video-title">CNEyT II — Calor y Temperatura</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=E2iEWYGShEU" target="_blank" rel="noopener" aria-label="Ver video 3.5: Calor y Temperatura CNEyT">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/kEUhxL485zg"
              title="CNEyT II – Escalas Termométricas y Equilibrio Térmico"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video de CNEyT II sobre escalas termométricas y equilibrio térmico"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 3.6</span>
            <p class="video-title">CNEyT II — Escalas Termométricas y Equilibrio Térmico</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=kEUhxL485zg" target="_blank" rel="noopener" aria-label="Ver video 3.6: Escalas Termométricas">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/DdIhKXMs1t0"
              title="CNEyT II – Conducción y Convección"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video de CNEyT II explicando conducción y convección del calor"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 3.7</span>
            <p class="video-title">CNEyT II — Conducción y Convección</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=DdIhKXMs1t0" target="_blank" rel="noopener" aria-label="Ver video 3.7: Conducción y Convección">▶ Ver en YouTube</a>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- PF4 -->
  <section class="section" id="pf4">
    <div class="section-header">
      <div class="section-number">4</div>
      <h2>Propósito Formativo 4 — Energía, Materia y Formas de Propagación del Calor</h2>
    </div>
    <div class="section-body">
      <p class="section-desc">
        Analiza la interacción entre la energía y la estructura de la materia para comprender las formas de propagación de calor: conducción, convección y radiación. Incluye escalas termométricas, calor específico y calorimetría.
      </p>
      <div class="videos-grid">

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/DQEiMBryObs"
              title="Procesos de Transferencia de Calor – Conducción, Convección y Radiación"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video sobre los tres procesos de transferencia de calor: conducción, convección y radiación"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 4.1</span>
            <p class="video-title">Procesos de Transferencia de Calor — Conducción, Convección y Radiación</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=DQEiMBryObs" target="_blank" rel="noopener" aria-label="Ver video 4.1: Transferencia de Calor">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/XbT_xwSS3GA"
              title="CNEyT II – Transferencia de Calor por Radiación y Conductividad"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video de CNEyT II sobre transferencia de calor por radiación y conductividad térmica"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 4.2</span>
            <p class="video-title">CNEyT II — Transferencia de Calor por Radiación y Conductividad</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=XbT_xwSS3GA" target="_blank" rel="noopener" aria-label="Ver video 4.2: Radiación y Conductividad">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/_BfPj_ZHHT4"
              title="Escalas Termométricas"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video educativo sobre las distintas escalas termométricas: Celsius, Fahrenheit y Kelvin"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 4.3</span>
            <p class="video-title">Escalas Termométricas</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=_BfPj_ZHHT4" target="_blank" rel="noopener" aria-label="Ver video 4.3: Escalas Termométricas">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/vUSU8VUW0_8"
              title="Química – Calor específico y capacidad calorífica"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video de química sobre calor específico y capacidad calorífica de las sustancias"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 4.4</span>
            <p class="video-title">Química — Calor específico y capacidad calorífica</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=vUSU8VUW0_8" target="_blank" rel="noopener" aria-label="Ver video 4.4: Calor Específico">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/poTE1tmsfJ8"
              title="Calorimetría – Calor cedido y calor ganado"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video sobre calorimetría, calor cedido y calor ganado en sistemas térmicos"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 4.5</span>
            <p class="video-title">Calorimetría — Calor cedido y calor ganado</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=poTE1tmsfJ8" target="_blank" rel="noopener" aria-label="Ver video 4.5: Calorimetría">▶ Ver en YouTube</a>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- PF5 -->
  <section class="section" id="pf5">
    <div class="section-header">
      <div class="section-number">5</div>
      <h2>Propósito Formativo 5 — Trabajo Mecánico y Termodinámica</h2>
    </div>
    <div class="section-body">
      <p class="section-desc">
        Analiza el vínculo entre trabajo mecánico y calor, para comprender el concepto de termodinámica. Incluye potencia, trabajo, conversiones de energía y el Principio Cero de la Termodinámica.
      </p>
      <div class="videos-grid">

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/wMZuBmO9qH0"
              title="CNEyT II – Trabajo Mecánico y Concepto de Termodinámica"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video de CNEyT II sobre trabajo mecánico y el concepto de termodinámica"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 5.1</span>
            <p class="video-title">CNEyT II — Trabajo Mecánico y Concepto de Termodinámica</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=wMZuBmO9qH0" target="_blank" rel="noopener" aria-label="Ver video 5.1: Trabajo Mecánico y Termodinámica">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/tB5-NPxqueQ"
              title="Potencia, trabajo y energía – Khan Academy"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video de Khan Academy sobre potencia, trabajo y energía en física"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 5.2</span>
            <p class="video-title">Potencia, trabajo y energía — Khan Academy</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=tB5-NPxqueQ" target="_blank" rel="noopener" aria-label="Ver video 5.2: Potencia, trabajo y energía Khan Academy">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/RUDPDjzWKao"
              title="Entiende el concepto de termodinámica"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video explicativo sobre el concepto de termodinámica y sus principios"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 5.3</span>
            <p class="video-title">Entiende el concepto de termodinámica</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=RUDPDjzWKao" target="_blank" rel="noopener" aria-label="Ver video 5.3: Concepto de Termodinámica">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/EiXGmR59qCg"
              title="Trabajo mecánico y sus aplicaciones"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video sobre trabajo mecánico y sus aplicaciones en la vida cotidiana"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 5.4</span>
            <p class="video-title">Trabajo mecánico y sus aplicaciones</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=EiXGmR59qCg" target="_blank" rel="noopener" aria-label="Ver video 5.4: Trabajo Mecánico y Aplicaciones">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/_ghFNoGkeWo"
              title="CNEyT II – El vínculo entre el trabajo mecánico y la termodinámica"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video de CNEyT II sobre el vínculo entre trabajo mecánico y termodinámica"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 5.5</span>
            <p class="video-title">CNEyT II — El vínculo entre el trabajo mecánico y la termodinámica</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=_ghFNoGkeWo" target="_blank" rel="noopener" aria-label="Ver video 5.5: Vínculo Trabajo y Termodinámica">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/fiaXjOkmuRg"
              title="Conversiones de unidades de energía: Equivalencias físicas"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video sobre conversiones de unidades de energía y equivalencias físicas"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 5.6</span>
            <p class="video-title">Conversiones de unidades de energía — Equivalencias físicas</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=fiaXjOkmuRg" target="_blank" rel="noopener" aria-label="Ver video 5.6: Conversiones de Energía">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/Aj-28ej6QKw"
              title="CNEyT – Principio Cero de Termodinámica"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video de CNEyT sobre el Principio Cero de la Termodinámica"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 5.7</span>
            <p class="video-title">CNEyT — Principio Cero de Termodinámica</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=Aj-28ej6QKw" target="_blank" rel="noopener" aria-label="Ver video 5.7: Principio Cero Termodinámica">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/cQVheWILkfA"
              title="Ley cero de la termodinámica"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video explicativo sobre la Ley Cero de la Termodinámica"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 5.8</span>
            <p class="video-title">Ley cero de la termodinámica</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=cQVheWILkfA" target="_blank" rel="noopener" aria-label="Ver video 5.8: Ley Cero de la Termodinámica">▶ Ver en YouTube</a>
          </div>
        </div>

        <div class="video-card">
          <div class="video-thumb">
            <iframe src="https://www.youtube.com/embed/q4BvqPRGfE4"
              title="Ley 0 de la Termodinámica – Experimento demostrativo"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"
              alt="Video con experimento demostrativo de la Ley 0 de la Termodinámica"></iframe>
          </div>
          <div class="video-info">
            <span class="video-label">Video 5.9</span>
            <p class="video-title">Ley 0 de la Termodinámica — Experimento demostrativo</p>
            <a class="video-link" href="https://www.youtube.com/watch?v=q4BvqPRGfE4" target="_blank" rel="noopener" aria-label="Ver video 5.9: Experimento Ley 0 Termodinámica">▶ Ver en YouTube</a>
          </div>
        </div>

      </div>
    </div>
  </section>

</main>

<footer>
  <p>🌿 Ciencias Naturales y Exactas II &nbsp;|&nbsp; <span>Recursos Educativos</span> &nbsp;|&nbsp; Todos los derechos de los videos corresponden a sus respectivos autores en YouTube.</p>
  <p style="margin-top:6px; font-size:0.78rem; opacity:0.7;">Los enlaces y videos incluidos en este sitio se usan con fines educativos, respetando las pautas de uso justo.</p>
</footer>

</body>
</html>

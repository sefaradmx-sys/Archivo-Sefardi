<!DOCTYPE html>
<html lang="es">
  <!-- Usa el head corregido de arriba -->
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Sefarad MX — Genealogía y memoria</title>
    <meta name="description" content="Sefarad MX: genealogía, historia y memoria en México con raíces sefardíes." />
    <meta name="theme-color" content="#1e1916" />
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@500;700&family=Crimson+Text:ital@0;1&family=Inter:wght@400;600&display=swap" rel="stylesheet">
    <style>
      /* Copia aquí los estilos del head corregido y el resto del CSS que te pasé antes */
    </style>
  </head>
  <body>
    <header>
      <nav class="nav">
        <a class="brand" href="#">
          <span class="brand-mark" aria-hidden="true"></span>
          <span class="brand-title">Sefarad MX</span>
        </a>
        <div class="nav-links">
          <a href="#familias">Familias</a>
          <a href="#linea-del-tiempo">Línea del tiempo</a>
          <a href="#archivo">Archivo</a>
          <a href="#contacto">Contacto</a>
        </div>
      </nav>
    </header>

    <section class="hero">
      <div class="hero-wrap">
        <div>
          <h1>Genealogía, memoria y rutas de linaje en México</h1>
          <p>Conecta apellidos, historias y testimonios para reconstruir rutas de migración y linajes con raíces sefardíes.</p>
        </div>
        <div class="hero-media" aria-hidden="true"></div>
      </div>
    </section>

    <main class="grid" id="familias"></main>

    <section class="grid">
      <article class="panel" id="linea-del-tiempo">
        <h3>Línea del tiempo</h3>
        <div class="timeline" id="timeline"></div>
      </article>
      <aside class="panel-map">
        <h3>Rutas de migración</h3>
        <div class="map-ghost">Mapa interactivo próximamente.</div>
      </aside>
    </section>

    <section class="grid" id="archivo">
      <article class="panel" style="grid-column: span 12;">
        <h3>Archivo y documentos</h3>
        <p style="color:var(--muted)">Comparte actas, partidas, cartas y fotografías para precisar fechas y vínculos.</p>
        <div class="timeline" id="docs"></div>
      </article>
    </section>

    <footer id="contacto">
      <div class="footer-wrap">
        <div>
          <h5>Sobre Sefarad MX</h5>
          <p>Proyecto comunitario de investigación y difusión genealógica.</p>
        </div>
        <div>
          <h5>Contacto</h5>
          <p>contacto@sefarad.mx</p>
        </div>
        <div>
          <h5>Transparencia</h5>
          <p>Publicación responsable con fuente y contexto.</p>
        </div>
      </div>
    </footer>

    <script>
      // Datos de ejemplo
      const familias = [
        { id:"garcia-lampazos", apellido:"García", origen:"Sevilla, España", llegadaMX:"1579", ruta:"sefardi", localidades:["Lampazos de Naranjo, NL","Monterrey, NL"], destinos:["Nuevo León","Coahuila"], notas:"Rutas a la frontera noreste." },
        { id:"salinas-coahuila", apellido:"Salinas", origen:"Toledo, España", llegadaMX:"1604", ruta:"converso", localidades:["Parras, COAH","Saltillo, COAH"], destinos:["Coahuila","Durango"], notas:"Oficios y comercio regional." }
      ];
      const eventos = [
        { year:1492, text:"Dispersión sefardí." },
        { year:1575, text:"Fundaciones en el Noreste." },
        { year:1600, text:"Registros parroquiales." }
      ];
      const docsSimulados = [
        { tipo:"Partida", año:"1601", resumen:"Bautismo en Lampazos" },
        { tipo:"Acta", año:"1621", resumen:"Matrimonio en Parras" }
      ];

      const grid = document.getElementById('familias');
      const timeline = document.getElementById('timeline');
      const docs = document.getElementById('docs');

      function renderCards(items){
        grid.innerHTML = items.map(f => `
          <article class="card" aria-label="Familia ${f.apellido}">
            <div class="thumb" aria-hidden="true"></div>
            <div class="body">
              <span class="tag">Ruta: ${f.ruta.charAt(0).toUpperCase()+f.ruta.slice(1)}</span>
              <div class="title">${f.apellido}</div>
              <div class="meta">Origen: ${f.origen} • Llegada: ${f.llegadaMX}</div>
              <div class="meta">Localidades: ${f.localidades.join(", ")}</div>
              <p style="margin-top:8px; color:var(--muted)">${f.notas}</p>
            </div>
          </article>
        `).join('');
      }
      function renderTimeline(){
        timeline.innerHTML = eventos.map(e=>`
          <div class="event">
            <div class="year">${e.year}</div>
            <div class="desc">${e.text}</div>
          </div>
        `).join('');
      }
      function renderDocs(){
        docs.innerHTML = docsSimulados.map(d=>`
          <div class="event">
            <div class="year">${d.año}</div>
            <div class="desc"><strong>${d.tipo}:</strong> ${d.resumen}</div>
          </div>
        `).join('');
      }

      renderCards(familias);
      renderTimeline();
      renderDocs();
    </script>
  </body>
</html>      background: linear-gradient(180deg, rgba(28,25,22,.85), rgba(28,25,22,.6));
      border-bottom: 1px solid rgba(255,255,255,.08);
    }
    .nav{
      max-width: 1200px; margin:0 auto; padding: 14px 20px;
      display:flex; align-items:center; justify-content:space-between;
    }
    .brand{
      display:flex; align-items:center; gap:14px;
      text-decoration:none; color:var(--paper);
    }
    .brand-mark{
      width:44px; height:44px; border-radius:50%;
      background:
        radial-gradient(closest-side, #b6874c 35%, #8b5e34 60%, #3b2a21 100%);
      box-shadow: inset 0 0 0 2px rgba(255,255,255,.08), var(--shadow);
      position:relative;
    }
    .brand-mark:after{
      content:"✶"; position:absolute; inset:0; display:flex; align-items:center; justify-content:center;
      color:#f4e7d1; font-size:20px; text-shadow:0 1px 0 #2f2721;
    }
    .brand-title{
      font-family: "Playfair Display", serif;
      font-weight:700; letter-spacing:.4px; font-size: 1.25rem;
    }
    .nav-links a{
      color:var(--muted); text-decoration:none; margin-left:18px; font-weight:600;
    }
    .nav-links a:hover{color:var(--paper)}

    .hero{
      position:relative; overflow:hidden;
      padding: 64px 20px 40px;
      border-bottom: 1px solid rgba(255,255,255,.08);
    }
    .hero-wrap{
      max-width: 1200px; margin:0 auto; display:grid; grid-template-columns:1.1fr .9fr; gap:30px;
    }
    .hero h1{
      font-family:"Playfair Display", serif; font-weight:700; font-size: clamp(2.2rem, 4.2vw, 3.6rem);
      line-height:1.15; margin:0 0 16px;
    }
    .hero p{
      font-family:"Crimson Text", serif; font-size:1.1rem; color:var(--muted); margin:0 0 24px;
    }
    .hero-card{
      background: linear-gradient(145deg, rgba(231,223,207,.08), rgba(231,223,207,.02));
      border: 1px solid rgba(255,255,255,.10);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      padding: 18px; display:flex; align-items:center; gap:16px;
    }
    .hero-card .emblem{
      width:56px; height:56px; border-radius:12px; background: radial-gradient(closest-side, #f1e5cf, #c9b99b, #6a4a2f);
      display:grid; place-items:center; color:#3b2a21; font-size:22px; box-shadow: inset 0 0 0 2px rgba(0,0,0,.12);
    }

    .hero-media{
      position:relative; min-height: 320px; border-radius: var(--radius);
      background:
        linear-gradient(180deg, rgba(182,135,76,.25), transparent),
        url('https://images.unsplash.com/photo-1519681393784-d120267933ba?q=80&w=1200&auto=format&fit=crop') center/cover;
      box-shadow: var(--shadow);
      border:1px solid rgba(255,255,255,.10);
    }
    .hero-media:after{
      content:"Mapa de rutas y linajes • Sefarad MX"; position:absolute; right:16px; bottom:14px; font-size:.9rem; color:#e7dfcf;
      background: rgba(0,0,0,.25); padding:6px 10px; border-radius:10px; border:1px solid rgba(255,255,255,.12);
    }

    .toolbar{
      max-width: 1200px; margin: 22px auto 26px; padding: 0 20px;
      display:flex; flex-wrap:wrap; gap:10px; align-items:center;
    }
    .input{
      flex:1; min-width: 260px; display:flex; align-items:center; gap:10px;
      background: var(--bg-alt); border:1px solid rgba(255,255,255,.10); border-radius: 12px; padding: 8px 12px;
    }
    .input input{
      flex:1; background: transparent; border:0; color: var(--paper); padding:10px; outline:none;
    }
    .btn{
      appearance:none; border:0; background: linear-gradient(180deg, #c79a5f, #8b5e34);
      color:#fff; font-weight:600; padding:12px 16px; border-radius:12px; box-shadow: var(--shadow);
      cursor:pointer;
    }
    .btn:hover{filter:brightness(1.05)}
    .filter{
      display:flex; gap:8px; flex-wrap:wrap;
    }
    .chip{
      border:1px solid rgba(255,255,255,.10); color: var(--muted);
      background: var(--bg-alt); padding:8px 12px; border-radius: 999px; cursor:pointer;
    }
    .chip.active{ color:#fff; border-color: #c79a5f; box-shadow: var(--ring) }

    .grid{
      max-width: 1200px; margin: 0 auto; padding: 0 20px 40px;
      display:grid; grid-template-columns: repeat(12, 1fr); gap: 18px;
    }
    .card{
      grid-column: span 4;
      background: linear-gradient(160deg, rgba(231,223,207,.08), rgba(231,223,207,.02));
      border: 1px solid rgba(255,255,255,.10);
      border-radius: var(--radius);
      overflow:hidden; box-shadow: var(--shadow);
      transition: transform .25s ease, box-shadow .25s ease;
    }
    .card:hover{ transform: translateY(-3px); box-shadow: 0 26px 50px rgba(0,0,0,.45) }
    .card .thumb{ height: 160px; background: #332820 url('https://images.unsplash.com/photo-1520975922284-66b3b0532c8c?q=80&w=1200&auto=format&fit=crop') center/cover }
    .card .body{ padding: 16px }
    .tag{
      display:inline-block; font-size:.8rem; color:#e7dfcf; background: rgba(182,135,76,.25);
      border:1px solid rgba(182,135,76,.35); padding:4px 8px; border-radius:999px; margin-bottom:8px;
    }
    .title{
      font-family:"Playfair Display", serif; font-weight:700; font-size: 1.15rem; margin: 6px 0 6px;
    }
    .meta{ color: var(--muted); font-size:.95rem }
    .more{
      margin-top:12px; display:flex; gap:10px; flex-wrap:wrap;
    }
    .more .btn-secondary{
      background: transparent; color:#e7dfcf; border: 1px solid rgba(255,255,255,.12); padding:10px 12px; border-radius: 10px;
      cursor:pointer;
    }
    .more .btn-secondary:hover{ border-color: #c79a5f; color:#fff }

    /* Panel de línea del tiempo */
    .panel{
      grid-column: span 8;
      background: linear-gradient(160deg, rgba(231,223,207,.06), rgba(231,223,207,.02));
      border: 1px solid rgba(255,255,255,.10); border-radius: var(--radius); padding: 18px; box-shadow: var(--shadow);
    }
    .panel h3{ margin:0 0 12px; font-family:"Playfair Display", serif }
    .timeline{
      display:flex; gap:16px; overflow-x:auto; padding-bottom:8px;
      scroll-snap-type: x mandatory;
    }
    .event{
      min-width: 220px; scroll-snap-align:center;
      background: var(--bg-alt);
      border: 1px solid rgba(255,255,255,.08); border-radius: 10px; padding: 12px;
    }
    .event .year{ font-weight:700; color:#e7dfcf }
    .event .desc{ color: var(--muted) }

    /* Panel del mapa */
    .panel-map{
      grid-column: span 4;
      background: linear-gradient(160deg, rgba(231,223,207,.06), rgba(231,223,207,.02));
      border: 1px solid rgba(255,255,255,.10); border-radius: var(--radius); padding: 18px; box-shadow: var(--shadow);
      min-height: 240px; position:relative;
    }
    .map-ghost{
      position:absolute; inset:0; display:grid; place-items:center;
      color:var(--muted); font-style:italic;
      border: 1px dashed rgba(255,255,255,.12); border-radius: 12px;
    }

    /* Modal */
    dialog{
      border:0; border-radius: 14px; padding: 0; max-width: 780px; width: calc(100% - 24px);
      background: linear-gradient(160deg, rgba(231,223,207,.10), rgba(231,223,207,.03));
      color: var(--paper);
      box-shadow: 0 50px 120px rgba(0,0,0,.60);
    }
    dialog::backdrop{ backdrop-filter: blur(5px); background: rgba(0,0,0,.45) }
    .modal{
      display:grid; grid-template-columns: 1.1fr .9fr; gap:0;
    }
    .modal .left{
      padding: 20px 18px;
    }
    .modal .right{
      background: url('https://images.unsplash.com/photo-1544551763-7ef0389c11ff?q=80&w=1200&auto=format&fit=crop') center/cover;
      min-height: 260px;
    }
    .modal h4{
      margin:0 0 8px; font-family:"Playfair Display", serif; font-size: 1.4rem;
    }
    .modal .muted{ color: var(--muted); margin-bottom: 14px }
    .modal .list{
      display:grid; grid-template-columns: 1fr 1fr; gap: 10px;
    }
    .modal .list .item{
      background: var(--bg-alt); border: 1px solid rgba(255,255,255,.08);
      border-radius: 10px; padding: 10px;
    }
    .modal .actions{
      display:flex; justify-content:flex-end; gap:8px; margin-top: 14px;
    }
    .close-btn{
      background: transparent; color: #e7dfcf; border:1px solid rgba(255,255,255,.14);
      padding:10px 12px; border-radius: 10px; cursor:pointer;
    }
    .primary-btn{ background: linear-gradient(180deg, #c79a5f, #8b5e34); color:#fff; border:0; padding:10px 12px; border-radius: 10px; cursor:pointer }

    /* Footer */
    footer{
      margin-top: 30px; padding: 24px 20px 50px; border-top: 1px solid rgba(255,255,255,.08);
    }
    .footer-wrap{ max-width: 1200px; margin:0 auto; display:grid; grid-template-columns: 2fr 1fr 1fr; gap: 22px }
    footer h5{ margin:0 0 10px; font-family:"Playfair Display", serif; font-size:1.1rem }
    footer p, footer a{ color: var(--muted) }
    footer a{ text-decoration:none }
    footer a:hover{ color:#fff }

    /* Responsivo */
    @media (max-width: 980px){
      .hero-wrap{ grid-template-columns: 1fr }
      .grid{ grid-template-columns: repeat(6,1fr) }
      .card{ grid-column: span 6 }
      .panel{ grid-column: span 6 }
      .panel-map{ grid-column: span 6 }
      .modal{ grid-template-columns: 1fr }
      .modal .right{ min-height: 180px }
      .footer-wrap{ grid-template-columns: 1fr 1fr }
    }
    @media (max-width: 640px){
      .grid{ grid-template-columns: repeat(4,1fr) }
      .card{ grid-column: span 4 }
      .panel{ grid-column: span 4 }
      .panel-map{ grid-column: span 4 }
      .footer-wrap{ grid-template-columns: 1fr }
    }
  </style>
</head>

<body class="grain">
  <a class="skip" href="#contenido" style="position:absolute;left:-9999px;top:auto;width:1px;height:1px;overflow:hidden;">Saltar al contenido</a>

  <!-- NAV -->
  <header role="banner" aria-label="Encabezado principal">
    <nav class="nav" aria-label="Navegación">
      <a class="brand" href="#" aria-label="Página de inicio Sefarad MX">
        <span class="brand-mark" aria-hidden="true"></span>
        <span class="brand-title">Sefarad MX</span>
      </a>
      <div class="nav-links" role="navigation">
        <a href="#familias">Familias</a>
        <a href="#linea-del-tiempo">Línea del tiempo</a>
        <a href="#archivo">Archivo</a>
        <a href="#contacto">Contacto</a>
      </div>
    </nav>
  </header>

  <!-- HERO -->
  <section class="hero" id="contenido" aria-label="Introducción y misión">
    <div class="hero-wrap">
      <div>
        <h1>Genealogía, memoria y rutas de linaje en México</h1>
        <p>
          Sefarad MX es un espacio vivo de investigación y comunidad. Aquí conectamos apellidos, historias y
          testimonios para reconstruir rutas de migración, linajes y tradición en México con raíces sefardíes.
        </p>

        <div class="hero-card" role="note" aria-label="Manifiesto Sefarad MX">
          <div class="emblem">⚜</div>
          <div>
            <strong>Propósito:</strong> dignificar cada nombre, cada documento, cada viaje. Esta página permite
            explorar familias, tiempos y territorios con una estética histórica y herramientas modernas.
          </div>
        </div>
      </div>

      <div class="hero-media" aria-hidden="true"></div>
    </div>
  </section>

  <!-- TOOLBAR -->
  <section class="toolbar" aria-label="Búsqueda y filtros">
    <div class="input" role="search">
      <span aria-hidden="true">🔎</span>
      <input id="q" type="search" placeholder="Buscar apellido, localidad o ruta…" aria-label="Buscar en familias" />
    </div>
    <button class="btn" id="btnLimpiar" aria-label="Limpiar búsqueda">Limpiar</button>
    <div class="filter" role="group" aria-label="Filtrar por ruta">
      <button class="chip active" data-route="todas" aria-pressed="true">Todas</button>
      <button class="chip" data-route="sefardi">Sefardí</button>
      <button class="chip" data-route="converso">Converso</button>
      <button class="chip" data-route="mixta">Mixta</button>
    </div>
  </section>

  <!-- GRID PRINCIPAL -->
  <main class="grid" id="familias" aria-label="Familias destacadas">
    <!-- Tarjetas generadas dinámicamente -->
  </main>

  <!-- PANEL LÍNEA DEL TIEMPO + MAPA -->
  <section class="grid">
    <article class="panel" id="linea-del-tiempo" aria-label="Línea del tiempo de migración">
      <h3>Línea del tiempo</h3>
      <div class="timeline" id="timeline" aria-live="polite">
        <!-- Eventos generados dinámicamente -->
      </div>
    </article>

    <aside class="panel-map" aria-label="Mapa de rutas">
      <h3 style="margin:0 0 12px; font-family:'Playfair Display',serif">Rutas de migración</h3>
      <div class="map-ghost">
        Mapa interactivo próximamente. Por ahora, los destinos se muestran en cada familia.
      </div>
    </aside>
  </section>

  <!-- ARCHIVO -->
  <section class="grid" id="archivo" aria-label="Archivo y documentos">
    <article class="panel" style="grid-column: span 12;">
      <h3>Archivo y documentos</h3>
      <p style="color:var(--muted)">
        Convocatoria abierta: comparte actas, partidas, cartas y fotografías. Cada documento ayuda a precisar fechas,
        rutas y vínculos familiares.
      </p>
      <div class="timeline" id="docs">
        <!-- Documentos simulados -->
      </div>
    </article>
  </section>

  <!-- CONTACTO -->
  <footer id="contacto" role="contentinfo" aria-label="Pie de página">
    <div class="footer-wrap">
      <div>
        <h5>Sobre Sefarad MX</h5>
        <p>
          Proyecto comunitario sin fines de lucro para la investigación y difusión genealógica. Priorizamos accesibilidad,
          fuente primaria y cuidado de la memoria.
        </p>
      </div>
      <div>
        <h5>Contacto</h5>
        <p>Escríbenos: contacto@sefarad.mx</p>
        <p>Sugerencias y correcciones son bienvenidas.</p>
      </div>
      <div>
        <h5>Transparencia</h5>
        <p>Fuente, autoría y contexto acompañan cada ficha. Los datos se publican de forma responsable.</p>
      </div>
    </div>
  </footer>

  <!-- MODAL -->
  <dialog id="modal">
    <div class="modal">
      <div class="left">
        <h4 id="modalTitle">Familia</h4>
        <p class="muted" id="modalSubtitle">Linaje y rutas</p>
        <div class="list" id="modalList">
          <!-- Items -->
        </div>
        <div class="actions">
          <button class="close-btn" id="cerrar">Cerrar</button>
          <button class="primary-btn" id="verMas">Ver más</button>
        </div>
      </div>
      <div class="right" aria-hidden="true"></div>
    </div>
  </dialog>

  <script>
    // Datos simulados (puedes reemplazar con JSON externo en GitHub)
    const familias = [
      {
        id: "garcia-lampazos",
        apellido: "García",
        origen: "Sevilla, España",
        llegadaMX: "1579",
        ruta: "sefardi",
        localidades: ["Lampazos de Naranjo, NL", "Monterrey, NL"],
        destinos: ["Nuevo León", "Coahuila"],
        notas: "Linaje con testimonios de conversión y rutas a la frontera noreste.",
        documentos: [
          { tipo: "Partida", año: "1583", detalle: "Bautismo en Monterrey." },
          { tipo: "Carta", año: "1602", detalle: "Traslado a Lampazos." }
        ]
      },
      {
        id: "salinas-coahuila",
        apellido: "Salinas",
        origen: "Toledo, España",
        llegadaMX: "1604",
        ruta: "converso",
        localidades: ["Parras, COAH", "Saltillo, COAH"],
        destinos: ["Coahuila", "Durango"],
        notas: "Ramas con presencia en oficios y comercio regional.",
        documentos: [
          { tipo: "Acta", año: "1621", detalle: "Matrimonio en Parras." },
          { tipo: "Testamento", año: "1650", detalle: "Inventario de bienes." }
        ]
      },
      {
        id: "naranjo-nl",
        apellido: "Naranjo",
        origen: "Castilla, España",
        llegadaMX: "1595",
        ruta: "mixta",
        localidades: ["Lampazos de Naranjo, NL", "Sabinas, COAH"],
        destinos: ["Nuevo León", "Coahuila"],
        notas: "Relatos orales y registros parroquiales complementarios.",
        documentos: [
          { tipo: "Partida", año: "1601", detalle: "Confirmación en Lampazos." },
          { tipo: "Carta", año: "1630", detalle: "Traslado hacia Sabinas." }
        ]
      },
      {
        id: "trevino-noreste",
        apellido: "Treviño",
        origen: "Navarra, España",
        llegadaMX: "1586",
        ruta: "sefardi",
        localidades: ["Monterrey, NL", "Monclova, COAH"],
        destinos: ["Nuevo León", "Coahuila", "Tamaulipas"],
        notas: "Rutas mestas y vínculos con expediciones del noreste.",
        documentos: [
          { tipo: "Acta", año: "1592", detalle: "Fundación y cargos municipales." },
          { tipo: "Carta", año: "1615", detalle: "Permisos de traslado." }
        ]
      },
      {
        id: "lopez-altiplano",
        apellido: "López",
        origen: "Extremadura, España",
        llegadaMX: "1610",
        ruta: "converso",
        localidades: ["Zacatecas, ZAC", "San Luis Potosí, SLP"],
        destinos: ["Zacatecas", "San Luis Potosí"],
        notas: "Minería y administración local documentada.",
        documentos: [
          { tipo: "Acta", año: "1612", detalle: "Registro minero." },
          { tipo: "Testamento", año: "1648", detalle: "Disposiciones familiares." }
        ]
      }
    ];

    const eventos = [
      { year: 1492, text: "Expulsión y dispersión sefardí; primeras rutas hacia el Mediterráneo y Atlántico." },
      { year: 1521, text: "Conquista y establecimiento colonial: visibilización parcial de conversos." },
      { year: 1575, text: "Fundaciones en el Noreste; migración hacia Nuevo León y Coahuila." },
      { year: 1600, text: "Consolidación de rutas familiares; registros parroquiales." },
      { year: 1700, text: "Ramas mixtas y redes comerciales regionales." }
    ];

    const docsSimulados = [
      { tipo:"Partida", año:"1601", resumen:"Bautismo en Lampazos", link:"#"},
      { tipo:"Carta", año:"1630", resumen:"Traslado a Sabinas", link:"#"},
      { tipo:"Acta", año:"1621", resumen:"Matrimonio en Parras", link:"#"},
      { tipo:"Testamento", año:"1650", resumen:"Inventario de bienes", link:"#"}
    ];

    // Render de tarjetas
    const grid = document.querySelector('main.grid');
    function renderCards(items){
      grid.innerHTML = "";
      if(!items.length){
        grid.innerHTML = `<div class="panel" style="grid-column: span 12;">
          <h3>Sin resultados</h3>
          <p style="color:var(--muted)">No encontramos coincidencias. Prueba con otro apellido o cambia los filtros.</p>
        </div>`;
        return;
      }
      items.forEach(f => {
        const el = document.createElement('article');
        el.className = 'card';
        el.setAttribute('tabindex', '0');
        el.setAttribute('aria-label', `Familia ${f.apellido}, llegada ${f.llegadaMX} desde ${f.origen}`);
        el.innerHTML = `
          <div class="thumb" aria-hidden="true"></div>
          <div class="body">
            <span class="tag">Ruta: ${capitalize(f.ruta)}</span>
            <div class="title">${f.apellido}</div>
            <div class="meta">Origen: ${f.origen} • Llegada: ${f.llegadaMX}</div>
            <div class="meta">Localidades: ${f.localidades.join(", ")}</div>
            <p style="margin-top:8px; color:var(--muted)">${f.notas}</p>
            <div class="more">
              <button class="btn-secondary" data-id="${f.id}" data-action="abrir">Perfil</button>
              <button class="btn-secondary" data-id="${f.id}" data-action="docs">Documentos</button>
            </div>
          </div>
        `;
        grid.appendChild(el);
      });
    }

    // Render timeline
    const timeline = document.getElementById('timeline');
    function renderTimeline(){
      timeline.innerHTML = "";
      eventos.forEach(e=>{
        const div = document.createElement('div');
        div.className = 'event';
        div.innerHTML = `
          <div class="year">${e.year}</div>
          <div class="desc">${e.text}</div>
        `;
        timeline.appendChild(div);
      });
    }

    // Render documentos
    const docs = document.getElementById('docs');
    function renderDocs(){
      docs.innerHTML = "";
      docsSimulados.forEach(d=>{
        const el = document.createElement('div');
        el.className = 'event';
        el.innerHTML = `
          <div class="year">${d.año}</div>
          <div class="desc"><strong>${d.tipo}:</strong> ${d.resumen}</div>
        `;
        docs.appendChild(el);
      });
    }

    // Búsqueda y filtros
    const input = document.getElementById('q');
    const btnLimpiar = document.getElementById('btnLimpiar');
    const chips = Array.from(document.querySelectorAll('.chip'));

    let routeFilter = 'todas';
    let query = '';

    function apply(){
      const normalized = s => (s||"").toLowerCase();
      const q = normalized(query);
      const out = familias.filter(f=>{
        const byRoute = routeFilter==='todas' ? true : f.ruta === routeFilter;
        const inText =
          normalized(f.apellido).includes(q) ||
          normalized(f.origen).includes(q) ||
          normalized(f.localidades.join(' ')).includes(q) ||
          normalized(f.destinos.join(' ')).includes(q) ||
          normalized(f.notas).includes(q);
        return byRoute && inText;
      });
      renderCards(out);
    }

    input.addEventListener('input', (e)=>{ query = e.target.value; apply() });
    btnLimpiar.addEventListener('click', ()=>{ input.value=''; query=''; apply() });
    chips.forEach(c=>{
      c.addEventListener('click', ()=>{
        chips.forEach(x=>x.classList.remove('active'));
        chips.forEach(x=>x.setAttribute('aria-pressed','false'));
        c.classList.add('active');
        c.setAttribute('aria-pressed','true');
        routeFilter = c.dataset.route;
        apply();
      });
    });

    // Modal
    const modal = document.getElementById('modal');
    const modalTitle = document.getElementById('modalTitle');
    const modalSubtitle = document.getElementById('modalSubtitle');
    const modalList = document.getElementById('modalList');
    const cerrar = document.getElementById('cerrar');
    const verMas = document.getElementById('verMas');

    grid.addEventListener('click', (e)=>{
      const btn = e.target.closest('button[data-action]');
      if(!btn) return;
      const id = btn.dataset.id;
      const action = btn.dataset.action;
      const f = familias.find(x=>x.id===id);
      if(!f) return;

      if(action==='abrir'){
        openFamily(f);
      } else if(action==='docs'){
        openDocs(f);
      }
    });

    grid.addEventListener('keyup', (e)=>{
      if(e.key==='Enter'){
        const card = e.target.closest('.card');
        if(!card) return;
        // Abrir el perfil del primer botón
        const btn = card.querySelector('button[data-action="abrir"]');
        if(btn){
          const id = btn.dataset.id;
          const f = familias.find(x=>x.id===id);
          if(f) openFamily(f);
        }
      }
    });

    cerrar.addEventListener('click', ()=> modal.close());
    verMas.addEventListener('click', ()=>{
      // Aquí puedes redirigir a una página detallada (e.g., /familia/garcia-lampazos.html)
      modal.close();
      alert('Próximamente: perfil completo en páginas dedicadas.');
    });

    function openFamily(f){
      modalTitle.textContent = `Familia ${f.apellido}`;
      modalSubtitle.textContent = `${f.origen} → México (${f.llegadaMX}) • Ruta ${capitalize(f.ruta)}`;
      modalList.innerHTML = `
        <div class="item"><strong>Localidades</strong><br>${f.localidades.join(', ')}</div>
        <div class="item"><strong>Destinos</strong><br>${f.destinos.join(', ')}</div>
        <div class="item"><strong>Notas</strong><br>${f.notas}</div>
        <div class="item"><strong>Documentos</strong><br>${f.documentos.map(d=>`${d.tipo} ${d.año}`).join(', ')}</div>
      `;
      modal.showModal();
    }

    function openDocs(f){
      modalTitle.textContent = `Documentos — ${f.apellido}`;
      modalSubtitle.textContent = `Fuentes y registros asociados`;
      modalList.innerHTML = f.documentos.map(d=>`
        <div class="item"><strong>${d.tipo} (${d.año})</strong><br>${d.detalle}</div>
      `).join('');
      modal.showModal();
    }

    function capitalize(s){ return (s||'').charAt(0).toUpperCase() + (s||'').slice(1) }

    // Inicialización
    renderCards(familias);
    renderTimeline();
    renderDocs();
  </script>
</body>
</html>

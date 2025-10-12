<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Archivo Sefardí</title>
  <link rel="stylesheet" href="style.css">
  <script src="https://cdn.jsdelivr.net/npm/marked/marked.min.js"></script>
</head>
<body>
  <div class="layout">
    <aside class="sidebar">
      <h2>Secciones</h2>
      <ul>
        <li><a href="#" onclick="loadMarkdown('historia.md')">Historia</a></li>
        <li><a href="#" onclick="loadMarkdown('testimonios.md')">Testimonios</a></li>
        <li><a href="#" onclick="loadMarkdown('instituciones.md')">Instituciones</a></li>
        <li><a href="#" onclick="loadMarkdown('referencias.md')">Referencias</a></li>
      </ul>
    </aside>

    <main class="content">
      <header>
        <h1>Archivo Sefardí</h1>
        <p>Documentación histórica, comunitaria y ética</p>
      </header>
      <section id="markdown-content">
        <p>Selecciona una sección para comenzar.</p>
      </section>
      <footer>
        <p>Creado por Diego y colaboradores. Proyecto de memoria y justicia.</p>
      </footer>
    </main>
  </div>

  <script src="script.js"></script>
</body>
</html>

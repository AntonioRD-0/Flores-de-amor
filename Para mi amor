<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Girasoles Animados</title>
  <style>
    body {
      background: #ec71b4; /* Fondo completamente rosa */
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }
    h1.nombre {
      font-family: "Segoe UI", sans-serif;
      font-size: 36px;
      color: #8b5a2b;
      margin-bottom: 20px;
    }
    .girasoles-container {
      display: flex;
      gap: 50px;
    }
    svg {
      width: 220px;
      height: 320px;
      animation: girasolBalanceo 4s ease-in-out infinite alternate;
      transform-origin: center bottom;
    }
    @keyframes girasolBalanceo {
      0% { transform: rotate(-5deg); }
      100% { transform: rotate(5deg); }
    }
    .petal {
      fill: #fcd116;
    }
    .center {
      fill: #8b5a2b;
    }
    .stem {
      fill: #3b873e;
    }
    .leaf {
      fill: #2e7d32;
    }
    .ground {
      fill: #a86b35;
    }
  </style>
</head>
<body>
  <h1 class="nombre">Te amo mi niña</h1>
  <div class="girasoles-container">
    <!-- Repetimos 3 girasoles animados -->
    <template id="girasol-template">
      <svg viewBox="0 0 200 300">
        <defs>
          <ellipse id="petal" cx="100" cy="60" rx="15" ry="30" class="petal" />
        </defs>
        <g id="petals"></g>
        <circle class="center" cx="100" cy="100" r="35" />
        <rect x="95" y="135" width="10" height="100" class="stem" />
        <ellipse class="leaf" cx="75" cy="180" rx="30" ry="18" transform="rotate(-30 75 180)" />
        <ellipse class="leaf" cx="125" cy="190" rx="30" ry="18" transform="rotate(30 125 190)" />
        <ellipse class="ground" cx="100" cy="270" rx="60" ry="10" />
      </svg>
    </template>

    <div id="girasol1"></div>
    <div id="girasol2"></div>
    <div id="girasol3"></div>
  </div>

  <script>
    function crearGirasol(contenedorId) {
      const template = document.getElementById('girasol-template');
      const clone = template.content.cloneNode(true);
      const petalsGroup = clone.querySelector('g');
      const svgNS = "http://www.w3.org/2000/svg";
      for (let i = 0; i < 16; i++) {
        const use = document.createElementNS(svgNS, "use");
        use.setAttributeNS("http://www.w3.org/1999/xlink", "xlink:href", "#petal");
        use.setAttribute("transform", `rotate(${i * (360 / 16)} 100 100)`);
        petalsGroup.appendChild(use);
      }
      document.getElementById(contenedorId).appendChild(clone);
    }

    crearGirasol('girasol1');
    crearGirasol('girasol2');
    crearGirasol('girasol3');
  </script>
</body>
</html>

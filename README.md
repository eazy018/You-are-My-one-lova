<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Página Romántica</title>

    <!-- Fuente moderna y legible -->
    <link
      href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;700;800&display=swap"
      rel="stylesheet"
    />

    <style>
      /* 1. Estilos globales y fondo espacial */
      * {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
      }
      html, body {
        width: 100%;
        height: 100%;
        overflow: hidden;
        font-family: 'Poppins', sans-serif;
        background-color: #121212;
        background-image: url('https://images.unsplash.com/photo-1446776811953-b23d57bd21aa?&auto=format&fit=crop&w=1050&q=80');
        background-size: cover;
        background-position: center;
      }

      /* Contenedor principal centrado */
      .container {
        position: relative;
        width: 100%;
        height: 100%;
      }

      /* 2. Corazones animados */
      .heart {
        position: absolute;
        top: -10%;
        color: rgba(255, 77, 109, 0.9); /* rosa #ff4d6d semitransparente */
        font-size: 1.5rem;
        opacity: 0;
        animation-name: fall;
        animation-duration: 6s;
        animation-iteration-count: infinite;
        animation-timing-function: linear;
      }
      @keyframes fall {
        0% {
          transform: translateY(-20px) scale(0.8);
          opacity: 0;
        }
        10% {
          opacity: 1;
        }
        100% {
          transform: translateY(110vh) scale(1.2);
          opacity: 0;
        }
      }
      /* Variaciones en posición horizontal, retrasos y tamaños */
      /* Generamos 12 corazones con distintos delays y posiciones */
      .heart:nth-child(1) {
        left: 10%;
        animation-delay: 0s;
        font-size: 1.2rem;
      }
      .heart:nth-child(2) {
        left: 30%;
        animation-delay: 1s;
        font-size: 1.8rem;
      }
      .heart:nth-child(3) {
        left: 50%;
        animation-delay: 0.7s;
        font-size: 1.5rem;
      }
      .heart:nth-child(4) {
        left: 70%;
        animation-delay: 2s;
        font-size: 1.3rem;
      }
      .heart:nth-child(5) {
        left: 85%;
        animation-delay: 1.5s;
        font-size: 2rem;
      }
      .heart:nth-child(6) {
        left: 20%;
        animation-delay: 2.5s;
        font-size: 1.4rem;
      }
      .heart:nth-child(7) {
        left: 40%;
        animation-delay: 1.2s;
        font-size: 1.7rem;
      }
      .heart:nth-child(8) {
        left: 60%;
        animation-delay: 0.3s;
        font-size: 1.6rem;
      }
      .heart:nth-child(9) {
        left: 75%;
        animation-delay: 2.2s;
        font-size: 1.9rem;
      }
      .heart:nth-child(10) {
        left: 5%;
        animation-delay: 1.8s;
        font-size: 1.1rem;
      }
      .heart:nth-child(11) {
        left: 90%;
        animation-delay: 0.5s;
        font-size: 1.3rem;
      }
      .heart:nth-child(12) {
        left: 50%;
        animation-delay: 3s;
        font-size: 2.2rem;
      }

      /* 3. Texto central “Te Amo” con efecto neón/LED */
      .neon-container {
        position: absolute;
        top: 40%;
        left: 50%;
        transform: translate(-50%, -50%);
        text-align: center;
        z-index: 2;
      }
      .neon-container h1 {
        font-size: 3rem;
        color: #ff4d6d; /* rosa */
        text-shadow:
          0 0 5px #ff4d6d,
          0 0 10px #ff4d6d,
          0 0 20px #ff4d6d,
          0 0 40px #ff4d6d,
          0 0 80px #ff4d6d;
        animation: neon-flicker 1.5s infinite alternate;
        user-select: none;
      }
      @keyframes neon-flicker {
        0%, 100% {
          text-shadow:
            0 0 2px #ff4d6d,
            0 0 5px #ff4d6d,
            0 0 10px #ff4d6d,
            0 0 20px #ff4d6d,
            0 0 30px #ff4d6d;
          opacity: 1;
        }
        50% {
          text-shadow:
            0 0 10px #ff4d6d,
            0 0 20px #ff4d6d,
            0 0 40px #ff4d6d,
            0 0 60px #ff4d6d,
            0 0 80px #ff4d6d;
          opacity: 0.8;
        }
      }

      /* 4. Contenedor de los embeds de Spotify */
      .spotify-wrapper {
        position: absolute;
        top: 60%;
        left: 50%;
        transform: translateX(-50%);
        width: 90%;
        max-width: 400px;
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 1rem;
        z-index: 2;
      }
      .spotify-card {
        width: 100%;
        border: 2px solid rgba(255, 77, 109, 0.6); /* borde rosa semitransparente */
        border-radius: 12px;
        overflow: hidden;
        box-shadow: 0 0 10px rgba(255, 77, 109, 0.4);
        animation: float-slow 6s ease-in-out infinite alternate;
      }
      .spotify-card:nth-child(1) { animation-delay: 0s; }
      .spotify-card:nth-child(2) { animation-delay: 1s; }
      .spotify-card:nth-child(3) { animation-delay: 2s; }
      .spotify-card:nth-child(4) { animation-delay: 3s; }
      .spotify-card:nth-child(5) { animation-delay: 4s; }
      .spotify-card:nth-child(6) { animation-delay: 5s; }
      .spotify-card:nth-child(7) { animation-delay: 6s; }

      /* Animación sutil de flotación */
      @keyframes float-slow {
        0% {
          transform: translateY(0) scale(1);
        }
        100% {
          transform: translateY(10px) scale(1.02);
        }
      }

      /* Estilos del iframe de Spotify */
      .spotify-card iframe {
        width: 100%;
        height: 80px;
        border: none;
      }

      /* 6. Media queries para asegurar buena vista en móvil */
      @media (max-width: 480px) {
        .neon-container h1 {
          font-size: 2.5rem;
        }
        .spotify-wrapper {
          top: 65%;
        }
      }
      @media (min-width: 481px) {
        .neon-container h1 {
          font-size: 4rem;
        }
      }
    </style>
</head>
<body>
  <div class="container">
    <!-- 2. Creamos 12 corazones para que siempre haya algunos en pantalla -->
    <div class="heart">♥</div>
    <div class="heart">♥</div>
    <div class="heart">♥</div>
    <div class="heart">♥</div>
    <div class="heart">♥</div>
    <div class="heart">♥</div>
    <div class="heart">♥</div>
    <div class="heart">♥</div>
    <div class="heart">♥</div>
    <div class="heart">♥</div>
    <div class="heart">♥</div>
    <div class="heart">♥</div>

    <!-- 3. Texto central con efecto neón -->
    <div class="neon-container">
      <h1>Te Amo</h1>
    </div>

    <!-- 4. Embeds reales de Spotify -->
    <div class="spotify-wrapper">
      <!-- Sustituye cada src con tu propio enlace en formato embed de Spotify -->
      <div class="spotify-card">
        <iframe
          src="https://open.spotify.com/embed/track/1MKsphr9WmAkAGameksHDu?si=iHkra0joRy2Vg5bnLm3EpA"
          allow="encrypted-media"
          allowtransparency="true"
          allow="autoplay"
        ></iframe>
      </div>
      <div class="spotify-card">
        <iframe
          src="https://open.spotify.com/embed/track/4vtoaW1PyxXd57hB3RRZvm?si=X9u6RlXvQ9i6rnT5Rapeqg"
          allow="encrypted-media"
          allowtransparency="true"
          allow="autoplay"
        ></iframe>
      </div>
      <div class="spotify-card">
        <iframe
          src="https://open.spotify.com/embed/track/1tREl7Eo7dMS6JZe6wQKT5?si=qJjSyiVeRdmOTivO4ekfqg"
          allow="encrypted-media"
          allowtransparency="true"
          allow="autoplay"
        ></iframe>
      </div>
      <div class="spotify-card">
        <iframe
          src="https://open.spotify.com/embed/track/1BPPFJX2JI7EruBrV9p1xc?si=j6iMKym7R2ew-Zhrxqpdwg"
          allow="encrypted-media"
          allowtransparency="true"
          allow="autoplay"
        ></iframe>
      </div>
      <div class="spotify-card">
        <iframe
          src="https://open.spotify.com/embed/track/7f3y3Wpgy5xetFmyuNyXlF?si=xc5BRlV-R0ywG5g_8lOMXA"
          allow="encrypted-media"
          allowtransparency="true"
          allow="autoplay"
        ></iframe>
      </div>
      <div class="spotify-card">
        <iframe
          src="https://open.spotify.com/embed/track/7DyErSUFARWWozmqCRRPzv?si=jPuF01coT9SRVfM_pzHLnw"
          allow="encrypted-media"
          allowtransparency="true"
          allow="autoplay"
        ></iframe>
      </div>
      <div class="spotify-card">
        <iframe
          src="https://open.spotify.com/embed/track/1LFszPPjedeTRYYb7rt94J?si=PRyFvrcqQxyKXa09nfVd-g"
          allow="encrypted-media"
          allowtransparency="true"
          allow="autoplay"
        ></iframe>
      </div>
    </div>
  </div>

  <!-- 2 (opcional). Si quieres generar más corazones dinámicamente, puedes usar este script.
       En la versión actual ya tenemos 12 corazones estáticos, pero con JS podrías crear más,
       ubicarlos en posiciones aleatorias y que aparezcan/desaparezcan. -->
  <script>
    // (Opcional) Código para generar corazones aleatorios cada cierto tiempo
    // Descomenta si quieres más dinamismo, pero con los 12 ya hay bastante movimiento.

    /*
    const container = document.querySelector('.container');
    function createHeart() {
      const heart = document.createElement('div');
      heart.className = 'heart';
      heart.textContent = '♥';
      heart.style.left = Math.random() * 100 + '%';
      heart.style.fontSize = (Math.random() * 1.5 + 1) + 'rem';
      heart.style.animationDuration = (Math.random() * 4 + 4) + 's';
      container.appendChild(heart);
      // Eliminar el corazón después de que termine la animación
      setTimeout(() => {
        heart.remove();
      }, 8000);
    }
    // Crear un nuevo corazón cada 700ms (puedes ajustar la frecuencia)
    setInterval(createHeart, 700);
    */
  </script>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Atenea & Demyan</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background-color: #fff0f5;
     background-image: url('https://www.transparenttextures.com/patterns/paw-print.png');
      background-repeat: repeat;
      margin: 0;
      padding: 20px;
      text-align: center;
      position: relative;
      overflow-x: hidden;
    }

    h1 {
      color: #ba68c8;
      margin-bottom: 10px;
    }

    .caption {
      font-size: 18px;
      color: #6a1b9a;
      margin-bottom: 30px;
    }

    #imageContainer img {
      width: 90%;
      max-width: 500px;
      border-radius: 20px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.2);
      transition: opacity 0.5s ease-in-out;
    }

    button {
      background-color: #ba68c8;
      border: none;
      color: white;
      padding: 12px 25px;
      font-size: 16px;
      border-radius: 30px;
      cursor: pointer;
      margin-top: 20px;
      transition: background-color 0.3s;
      position: relative;
    }

    button::before {
      content: "🐾";
      color: black;
      font-size: 18px;
      position: absolute;
      left: 10px;
      top: 50%;
      transform: translateY(-50%);
    }

    button:hover {
      background-color: #9c4dcc;
    }

    footer {
      margin-top: 60px;
      color: #6a1b9a;
      font-size: 16px;
      font-weight: bold;
    }

    .corner {
      position: fixed;
      font-size: 12px;
      color: #999;
      opacity: 0.5;
      z-index: 0;
    }

    .top-left { top: 5px; left: 5px; }
    .top-right { top: 5px; right: 5px; }
    .bottom-left { bottom: 5px; left: 5px; }
    .bottom-right { bottom: 5px; right: 5px; }

    .top-name {
      position: absolute;
      top: 0;
      left: 50%;
      transform: translateX(-50%);
      color: #6a1b9a;
      font-weight: bold;
      font-size: 18px;
      margin-top: 5px;
    }

    .purr-paw {
      position: absolute;
      font-size: 24px;
      color: #6a1b9a;
      animation: floatUp 2s ease-out forwards;
      pointer-events: none;
      z-index: 1000;
    }

    @keyframes floatUp {
      0% {
        opacity: 1;
        transform: translateY(0) scale(1);
      }
      100% {
        opacity: 0;
        transform: translateY(-80px) scale(1.5);
      }
    }
  </style>
</head>
<body>

  <!-- Esquinas -444 -->
  <div class="corner top-left">-444</div>
  <div class="corner top-right">-444</div>
  <div class="corner bottom-left">-444</div>
  <div class="corner bottom-right">-444</div>

  <!-- Texto superior -->
  <div class="top-name">Demyan Samuel</div>

  <h1>Atenea & Demyan 🐾</h1>
  <p class="caption">Two tiny souls that warm your heart.</p>

  <div id="imageContainer">
    <img src="fotos/atenea.jpg" alt="Foto inicial" id="mainImage">
  </div>

  <button onclick="showRandomImage()">Ver otra foto</button>

  <footer>
    Perséfone Atena
  </footer>

  <!-- 🎵 Sonido de ronroneo -->
  <audio id="purrSound" src="audio/ronroneo.mp3" preload="auto"></audio>

  <script>
    const images = [
      "fotos/atenea.jpg",
      "fotos/demyan.jpg",
      "fotos/juntos.jpg",
      "fotos/dormidos.jpg",
      "fotos/abrazo.jpg"
      "fotos/dormido1.jpg",
      "fotos/dormido2.jpg",
      "fotos/dormido3.jpg",
      "fotos/dormido4.jpg",
      "fotos/dormido5.jpg",
      "fotos/dormido6.jpg",
      "fotos/dormido7.jpg",
      "fotos/dormido8.jpg",
      "fotos/dormido9.jpg",
      "fotos/dormido10.jpg",
      "fotos/dormido11.jpg",
      "fotos/dormido12.jpg",
      "fotos/dormido13.jpg",          
    ];

    function showRandomImage() {
      const randomIndex = Math.floor(Math.random() * images.length);
      const imageElement = document.getElementById("mainImage");
      const sound = document.getElementById("purrSound");

      imageElement.style.opacity = 0;
      setTimeout(() => {
        imageElement.src = images[randomIndex];
        imageElement.style.opacity = 1;
      }, 200);

      sound.currentTime = 0;
      sound.play();

      createFloatingPaw();
    }

    function createFloatingPaw() {
      const paw = document.createElement("div");
      paw.classList.add("purr-paw");
      paw.innerText = "🐾";

      // Posición aleatoria cerca del centro
      const x = window.innerWidth / 2 + (Math.random() * 100 - 50);
      const y = window.innerHeight / 2 + (Math.random() * 40 - 20);

      paw.style.left = ${x}px;
      paw.style.top = ${y}px;

      document.body.appendChild(paw);

      setTimeout(() => {
        paw.remove();
      }, 2000);
    }
  </script>

</body>
</html>

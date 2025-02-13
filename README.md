<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Tulipán Realista Animado</title>
  <style>
    body {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      background-color: #f8e8e8;
      font-family: Arial, sans-serif;
      text-align: center;
    }
    .tulip-container {
      width: 200px;
      height: 320px;
    }
    .tulip-animate {
      animation: sway 3s infinite ease-in-out;
      transform-origin: bottom center;
    }
    @keyframes sway {
      0% { transform: rotate(0deg); }
      50% { transform: rotate(2deg); }
      100% { transform: rotate(0deg); }
    }
    .poem {
      margin: 20px 0;
      font-size: 16px;
      line-height: 1.5;
      max-width: 80%;
    }
    textarea {
      width: 300px;
      height: 100px;
      border-radius: 10px;
      padding: 10px;
      margin-top: 20px;
    }
  </style>
</head>
<body>
  <h1>Para Ti 💖</h1>
  <svg class="tulip-container" viewBox="0 0 100 160">
    <defs>
      <linearGradient id="tulipGradient" x1="0" y1="0" x2="0" y2="1">
        <stop offset="0%" stop-color="#ff99cc" />
        <stop offset="100%" stop-color="#ff3366" />
      </linearGradient>
    </defs>
    <g class="tulip-animate">
      <path d="M50,10 C30,40 30,70 50,90 C70,70 70,40 50,10 Z" fill="url(#tulipGradient)" stroke="darkred" stroke-width="2" />
      <path d="M50,90 L50,150" stroke="green" stroke-width="4" stroke-linecap="round" />
    </g>
  </svg>
  <div class="poem">
    <p>
      En el jardín de mi alma florece un tulipán,<br>
      testigo silente de un amor sin final.<br>
      Cada pétalo narra un susurro, un tierno latido,<br>
      en versos de pasión y un sueño compartido.
    </p>
  </div>
  <textarea placeholder="Escribe un mensaje..."></textarea>
  <input type="file" accept="audio/*" onchange="playSong(event)">
  <audio id="audio" controls></audio>
  <script>
    function playSong(event) {
      const audio = document.getElementById('audio');
      audio.src = URL.createObjectURL(event.target.files[0]);
      audio.play();
    }
  </script>
</body>
</html>

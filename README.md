# te-amo
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>TE AMO</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background: linear-gradient(to top right, #ffdde1, #ee9ca7);
      overflow: hidden;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      font-family: Arial, sans-serif;
    }
    h1 {
      color: white;
      font-size: 4em;
      text-shadow: 2px 2px 5px rgba(0,0,0,0.3);
      z-index: 2;
    }
    .heart {
      position: absolute;
      width: 20px;
      height: 20px;
      background: red;
      transform: rotate(45deg);
      animation: floatUp linear infinite;
    }
    .heart::before,
    .heart::after {
      content: '';
      position: absolute;
      width: 20px;
      height: 20px;
      background: red;
      border-radius: 50%;
    }
    .heart::before { top: -10px; left: 0; }
    .heart::after { left: -10px; top: 0; }
    @keyframes floatUp {
      0% { transform: translateY(0) rotate(45deg); opacity: 1; }
      100% { transform: translateY(-100vh) rotate(45deg); opacity: 0; }
    }
    audio { display: none; }
  </style>
</head>
<body>
  <h1>TE AMO</h1>
  <audio autoplay loop>
    <source src="musica.mp3" type="audio/mpeg">
    Tu navegador no soporta el audio.
  </audio>
  <script>
    function createHeart() {
      const heart = document.createElement("div");
      heart.classList.add("heart");
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.animationDuration = (Math.random() * 3 + 3) + "s";
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 6000);
    }
    setInterval(createHeart, 300);
  </script>
</body>
</html>

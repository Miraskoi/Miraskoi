<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <title>Анимация текста</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(135deg, #2c3e50, #3498db);
      color: white;
      font-family: 'Segoe UI', sans-serif;
      overflow: hidden;
      animation: bgColor 10s infinite alternate;
    }

    @keyframes bgColor {
      0%   { background: linear-gradient(135deg, #2c3e50, #3498db); }
      100% { background: linear-gradient(135deg, #8e44ad, #e74c3c); }
    }

    h1 {
      font-size: 3em;
      animation: textFade 4s infinite;
    }

    @keyframes textFade {
      0%   { content: "Айгерим л"; opacity: 0; }
      25%  { content: "Айгерим л"; opacity: 1; }
      50%  { content: "Айгерим ч"; opacity: 1; }
      75%  { content: "Айгерим ч"; opacity: 0; }
      100% { content: "Айгерим л"; opacity: 0; }
    }

    /* JS-реализация замены текста */
  </style>
</head>
<body>
  <h1 id="changing-text">Айгерим л</h1>

  <script>
    const phrases = ["Айгерим л", "Айгерим ч"];
    let index = 0;
    const textElement = document.getElementById("changing-text");

    setInterval(() => {
      index = (index + 1) % phrases.length;
      textElement.textContent = phrases[index];
    }, 2000);
  </script>
</body>
</html>

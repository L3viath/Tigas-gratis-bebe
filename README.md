# Tigas-gratis-bebe
Um jogo caça níqueis falso
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Tigas</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #222;
      color: #fff;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      margin: 0;
    }
    h1 {
      margin-bottom: 20px;
    }
    .slot-machine {
      display: flex;
      gap: 20px;
      margin-bottom: 20px;
    }
    .slot {
      width: 80px;
      height: 80px;
      background: #333;
      border: 3px solid #fff;
      border-radius: 10px;
      font-size: 50px;
      display: flex;
      align-items: center;
      justify-content: center;
    }
    button {
      padding: 10px 20px;
      font-size: 18px;
      border: none;
      border-radius: 5px;
      background: #0f0;
      cursor: pointer;
      transition: background 0.3s;
    }
    button:hover {
      background: #0c0;
    }
    .message {
      margin-top: 20px;
      font-size: 20px;
    }
  </style>
</head>
<body>

  <h1>Tigas</h1>

  <div class="slot-machine">
    <div class="slot" id="slot1">🍒</div>
    <div class="slot" id="slot2">🍋</div>
    <div class="slot" id="slot3">🍊</div>
  </div>

  <button onclick="girar()">Girar</button>

  <div class="message" id="message"></div>

  <script>
    const simbolos = ['🍒', '🍋', '🍊', '🍉', '⭐', '💎'];

    function girar() {
      const s1 = simbolos[Math.floor(Math.random() * simbolos.length)];
      const s2 = simbolos[Math.floor(Math.random() * simbolos.length)];
      const s3 = simbolos[Math.floor(Math.random() * simbolos.length)];

      document.getElementById('slot1').textContent = s1;
      document.getElementById('slot2').textContent = s2;
      document.getElementById('slot3').textContent = s3;

      const message = document.getElementById('message');
      if (s1 === s2 && s2 === s3) {
        message.textContent = '🎉 Parabéns! Você ganhou! 🎉';
        message.style.color = 'gold';
      } else {
        message.textContent = 'Tente novamente!';
        message.style.color = '#fff';
      }
    }
  </script>

</body>
</html>

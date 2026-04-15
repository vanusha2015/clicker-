<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <title>Кликер</title>
  <style>
    body {
      font-family: Arial;
      text-align: center;
      background: #111;
      color: white;
    }
    button {
      font-size: 24px;
      padding: 20px 40px;
      margin: 20px;
      cursor: pointer;
    }
    .upgrade {
      background: #444;
      color: white;
      border: none;
      padding: 10px;
      margin: 5px;
    }
  </style>
</head>
<body>

<h1>💰 Кликер-игра</h1>
<p>Монеты: <span id="coins">0</span></p>
<p>За клик: <span id="perClick">1</span></p>

<button onclick="clickCoin()">КЛИКНИ!</button>

<h2>Улучшения</h2>
<button class="upgrade" onclick="buyUpgrade()">+1 за клик (10 монет)</button>

<script>
let coins = 0;
let perClick = 1;
let upgradeCost = 10;

function clickCoin() {
  coins += perClick;
  update();
}

function buyUpgrade() {
  if (coins >= upgradeCost) {
    coins -= upgradeCost;
    perClick++;
    upgradeCost = Math.floor(upgradeCost * 1.5);
    document.querySelector('.upgrade').innerText = "+1 за клик (" + upgradeCost + " монет)";
    update();
  }
}

function update() {
  document.getElementById("coins").innerText = coins;
  document.getElementById("perClick").innerText = perClick;
}
</script>

</body>
</html>

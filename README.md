# color-game<!DOCTYPE html>
<html>
<head>
  <title>Color Guessing Game</title>
  <style>
    body {
      text-align: center;
      font-family: Arial;
    }
    #colorBox {
      width: 200px;
      height: 200px;
      margin: 20px auto;
      border: 2px solid black;
    }
    .colorButton {
      margin: 10px;
      padding: 10px 20px;
      border: none;
      font-size: 16px;
      cursor: pointer;
    }
  </style>
</head>
<body>

<h1>Guess the Color!</h1>
<div id="colorBox"></div>

<button class="colorButton" onclick="checkColor('red')">Red</button>
<button class="colorButton" onclick="checkColor('green')">Green</button>
<button class="colorButton" onclick="checkColor('blue')">Blue</button>

<p id="result"></p>

<script>
  const colors = ['red', 'green', 'blue'];
  let correctColor = '';

  function randomColor() {
    const rand = Math.floor(Math.random() * colors.length);
    correctColor = colors[rand];
    document.getElementById('colorBox').style.backgroundColor = correctColor;
  }

  function checkColor(color) {
    if (color === correctColor) {
      document.getElementById('result').innerText = "🎉 Correct!";
    } else {
      document.getElementById('result').innerText = "❌ Try Again!";
    }
    setTimeout(randomColor, 1000); // change color after 1 sec
  }

  randomColor(); // start game
</script>

</body>
</html>

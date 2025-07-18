<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Simple Calculator</title>
  <style>
    body {
      background: #f2f2f2;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }

    .calculator {
      background: #111;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.5);
    }

    .display {
      width: 100%;
      height: 50px;
      background: #000;
      color: white;
      font-size: 24px;
      border: none;
      text-align: right;
      padding-right: 10px;
      margin-bottom: 10px;
    }

    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 60px);
      gap: 10px;
    }

    button {
      height: 60px;
      font-size: 20px;
      background: #333;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }

    button:hover {
      background: #555;
    }

    .zero {
      grid-column: span 2;
    }
  </style>
</head>
<body>
  <div class="calculator">
    <input type="text" class="display" id="display" disabled />
    <div class="buttons">
      <button onclick="clearDisplay()">C</button>
      <button onclick="appendValue('/')">/</button>
      <button onclick="appendValue('*')">*</button>
      <button onclick="appendValue('-')">-</button>

      <button onclick="appendValue('7')">7</button>
      <button onclick="appendValue('8')">8</button>
      <button onclick="appendValue('9')">9</button>
      <button onclick="appendValue('+')">+</button>

      <button onclick="appendValue('4')">4</button>
      <button onclick="appendValue('5')">5</button>
      <button onclick="appendValue('6')">6</button>
      <button onclick="calculate()">=</button>

      <button onclick="appendValue('1')">1</button>
      <button onclick="appendValue('2')">2</button>
      <button onclick="appendValue('3')">3</button>
      <button onclick="appendValue('.')">.</button>

      <button class="zero" onclick="appendValue('0')">0</button>
    </div>
  </div>

  <script>
    function appendValue(value) {
      document.getElementById('display').value += value;
    }

    function clearDisplay() {
      document.getElementById('display').value = '';
    }

    function calculate() {
      try {
        document.getElementById('display').value = eval(document.getElementById('display').value);
      } catch (e) {
        document.getElementById('display').value = 'Error';
      }
    }
  </script>
</body>
</html>

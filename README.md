<!DOCTYPE html>
<html>
<head>
  <meta http-equiv="CONTENT-TYPE" content="text/html; charset=UTF-8">
  <title>Calculator</title>
</head>
<body>
  <div id="calculator">
    <input id="display" readonly> 
    <div id="keys">
      
      <button onclick="appendToDisplay('+')" class="Operator-btn">+</button>
      <button onclick="appendToDisplay('7')">7</button>
      <button onclick="appendToDisplay('8')">8</button>
      <button onclick="appendToDisplay('9')">9</button>
      <button onclick="appendToDisplay('-')" class="Operator-btn">-</button>
      <button onclick="appendToDisplay('4')">4</button>
      <button onclick="appendToDisplay('5')">5</button>
      <button onclick="appendToDisplay('6')">6</button>
      <button onclick="appendToDisplay('*')" class="Operator-btn">×</button> <!-- Changed × to * -->
      <button onclick="appendToDisplay('1')">1</button>
      <button onclick="appendToDisplay('2')">2</button>
      <button onclick="appendToDisplay('3')">3</button>
      <button onclick="appendToDisplay('/')" class="Operator-btn">÷</button> <!-- Changed ÷ to / -->
      <button onclick="appendToDisplay('0')">0</button>
      <button onclick="appendToDisplay('.')">.</button>
      <button onclick="calculate()">=</button>
      <button onclick="clearDisplay()" class="Operator-btn">C</button> <!-- Fixed case -->
    </div>
  </div>

  <style>
    body {
      margin: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    #calculator {
      font-family: Arial, sans-serif;
      font-size: 10px;
      background-color: black;
      border-radius: 15px;
      max-width: 500px;
      overflow: hidden;
    }
    #display {
      width: 100%;
      padding: 20px;
      font-size: 5rem;
      text-align: left;
      border: none;
      background-color: DarkGrey;
    }
    #keys {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap:1px;
      font-family: 30px;
    }
    button {
      width: 100px;
      height: 100px;
      border-radius: 50px;
      border: none;
      background-color: Grey;
      color: white;
      font-size: 3rem;
      font-weight: bold;
      cursor: pointer;
    }
    .Operator-btn {
      background-color: Orange;
    }
  </style>

  <script>
    const display = document.getElementById("display");

    // Append input to display
    function appendToDisplay(input) {
      display.value += input;
    }

    // Clear display
    function clearDisplay() {
      display.value = "";
    }

    // Calculate the expression
    function calculate() {
      try {
        // Replace × and ÷ with valid operators
        let expression = display.value.replace('×', '*').replace('÷', '/');
        display.value = eval(expression);
      } catch (error) {
        display.value = "Error"; // Show error in case of invalid input
      }
    }
  </script>
</body>
</html>

# HTML (HyperText Markup Language):
    **Definition: HTML is the language used to build the structure of a webpage.**
    **It tells the browser what elements should appear: text boxes, buttons, headings, etc.**
    **In your calculator, HTML creates the display screen and the buttons for numbers and operations.**


# CSS (Cascading Style Sheets):
    **Definition: CSS is used to control the design and appearance of the webpage.**
    **It decides colors, fonts, sizes, spacing, and layout.**
    **In your calculator, CSS makes the background gradient, styles the buttons, adds hover effects, and gives the calculator a modern look.**


# JavaScript (JS):
    **Definition: JavaScript is the programming language of the web.**
    **It adds logic and interactivity to the webpage.**
    **In your calculator, JavaScript makes the buttons work:**
             **When you press a number, it appears on the display.*
             **When you press =, it calculates the result.*
             **When you press C, it clears the display.**
             **When you press ⌫, it deletes the last character.**


# How It Runs Together:
  **The browser first reads the HTML → builds the calculator layout.*
  **Then it applies CSS → makes it look attractive and user-friendly.*
  **Finally, JavaScript runs → gives the calculator its working ability.*
  **When you open the file in a browser (like Chrome, Edge, Firefox), all three combine to show a functional calculator.**
  ##### presentation:
  <!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Unique Calculator</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      background: linear-gradient(135deg, #74ebd5 0%, #ACB6E5 100%);
    }

    .calculator {
      background: #fff;
      padding: 20px;
      border-radius: 15px;
      box-shadow: 0 0 20px rgba(0,0,0,0.3);
      width: 300px;
    }

    #display {
      width: 100%;
      height: 50px;
      font-size: 1.5em;
      text-align: right;
      margin-bottom: 15px;
      padding: 10px;
      border: none;
      border-radius: 8px;
      background: #f0f2f5;
    }

    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
    }

    button {
      padding: 15px;
      font-size: 1.2em;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      background: #007bff;
      color: white;
      transition: background 0.3s;
    }

    button:hover {
      background: #0056b3;
    }

    .equal {
      grid-column: span 2;
      background: #28a745;
    }

    .equal:hover {
      background: #1e7e34;
    }

    .clear {
      background: #dc3545;
    }

    .clear:hover {
      background: #a71d2a;
    }
  </style>
</head>
<body>
  <div class="calculator">
    <input type="text" id="display" disabled>
    <div class="buttons">
      <button onclick="clearDisplay()" class="clear">C</button>
      <button onclick="appendValue('/')">÷</button>
      <button onclick="appendValue('*')">×</button>
      <button onclick="appendValue('-')">−</button>

      <button onclick="appendValue('7')">7</button>
      <button onclick="appendValue('8')">8</button>
      <button onclick="appendValue('9')">9</button>
      <button onclick="appendValue('+')">+</button>

      <button onclick="appendValue('4')">4</button>
      <button onclick="appendValue('5')">5</button>
      <button onclick="appendValue('6')">6</button>
      <button onclick="appendValue('.')">.</button>

      <button onclick="appendValue('1')">1</button>
      <button onclick="appendValue('2')">2</button>
      <button onclick="appendValue('3')">3</button>
      <button onclick="deleteLast()">⌫</button>

      <button onclick="appendValue('0')">0</button>
      <button onclick="calculate()" class="equal">=</button>
    </div>
  </div>

  <script>
    function appendValue(value) {
      document.getElementById("display").value += value;
    }

    function clearDisplay() {
      document.getElementById("display").value = "";
    }

    function deleteLast() {
      let current = document.getElementById("display").value;
      document.getElementById("display").value = current.slice(0, -1);
    }

    function calculate() {
      try {
        let result = eval(document.getElementById("display").value);
        document.getElementById("display").value = result;
      } catch {
        alert("Invalid Expression!");
      }
    }
  </script>
</body>
</html>

# output
http://127.0.0.1:5500/index.HTML

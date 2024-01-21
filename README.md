<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }

        .calculator {
            display: inline-block;
            border: 1px solid black;
            padding: 20px;
            width: 200px;
        }

        .display {
            margin-bottom: 20px;
            height: 20px;
            text-align: right;
        }

        button {
            width: 50px;
            height: 50px;
        }
    </style>
</head>
<body>
    <h1>Simple Calculator</h1>
    <div class="calculator">
        <div class="display" id="display">0</div>
        <button onclick="clearDisplay()">C</button>
        <button onclick="appendNumber(7)">7</button>
        <button onclick="appendNumber(8)">8</button>
        <button onclick="appendNumber(9)">9</button>
        <button onclick="appendOperator('+')">+</button>
        <button onclick="appendNumber(4)">4</button>
        <button onclick="appendNumber(5)">5</button>
        <button onclick="appendNumber(6)">6</button>
        <button onclick="appendOperator('-')">-</button>
        <button onclick="appendNumber(1)">1</button>
        <button onclick="appendNumber(2)">2</button>
        <button onclick="appendNumber(3)">3</button>
        <button onclick="appendOperator('*')">*</button>
        <button onclick="appendNumber(0)">0</button>
        <button onclick="appendOperator('.')">.</button>
        <button onclick="calculateResult()">=</button>
    </div>

    <script>
        function clearDisplay() {
            document.getElementById('display').innerText = '0';
        }

        function appendNumber(number) {
            const display = document.getElementById('display');
            if (display.innerText === '0') {
                display.innerText = number;
            } else {
                display.innerText += number;
            }
        }

        function appendOperator(operator) {
            const display = document.getElementById('display');
            if (['+', '-', '*', '.'].includes(display.innerText.slice(-1))) {
                return;
            }
            display.innerText += operator;
        }

        function calculateResult() {
            const display = document.getElementById('display');
            try {
                display.innerText = eval(display.innerText);
            } catch (error) {
                display.innerText = 'Error';
            }
        }
    </script>
</body>
</html>

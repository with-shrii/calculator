
<html >
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Calculator</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f0f0f0;
            font-family: Arial, sans-serif;
        }
        .calculator {
            border: 2px solid #ccc;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
            background-color: #fff;
            padding: 20px;
            width: 250px;
        }
        #display {
            width: 100%;
            padding: 15px;
            border: 1px solid #ccc;
            border-radius: 5px;
            font-size: 1.5em;
            text-align: right;
            box-sizing: border-box;
            margin-bottom: 10px;
        }
        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 5px;
        }
        button {
            padding: 20px;
            font-size: 1.2em;
            border: none;
            border-radius: 5px;
            background-color: #f1f1f1;
            color: #333;
            cursor: pointer;
            transition: background-color 0.2s;
        }
        button:hover {
            background-color: #ddd;
        }
        button:active {
            background-color: #ccc;
        }
        .operator {
            background-color: #f39c12;
            color: white;
        }
        .operator:hover {
            background-color: #e67e22;
        }
        .equals {
            background-color: #27ae60;
            color: white;
            grid-column: span 4;
        }
        .equals:hover {
            background-color: #2ecc71;
        }
        .clear {
            background-color: #e74c3c;
            color: white;
        }
        .clear:hover {
            background-color: #c0392b;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <input type="text" id="display" disabled>
        <div class="buttons">
            <button class="operator" onclick="appendToDisplay('/')">/</button> 
            <button onclick="appendToDisplay('7')">7</button>
            <button onclick="appendToDisplay('8')">8</button>
            <button onclick="appendToDisplay('9')">9</button>

            <button class="operator" onclick="appendToDisplay('*')">*</button>
            <button onclick="appendToDisplay('4')">4</button>
            <button onclick="appendToDisplay('5')">5</button>
            <button onclick="appendToDisplay('6')">6</button>
            
            <button class="operator" onclick="appendToDisplay('-')">-</button>
            <button onclick="appendToDisplay('1')">1</button>
            <button onclick="appendToDisplay('2')">2</button>
            <button onclick="appendToDisplay('3')">3</button>
            
            
            <button class="operator" onclick="appendToDisplay('+')">+</button>
            <button onclick="appendToDisplay('0')">0</button>
            <button onclick="appendToDisplay('.')">.</button>
            <button class="clear" onclick="clearDisplay()">C</button>
            <button class="equals" onclick="calculateResult()">=</button>
            
        </div>
    </div>

    <script>
        function appendToDisplay(value) {
            document.getElementById('display').value += value;
        }

        function clearDisplay() {
            document.getElementById('display').value = '';
        }

        function calculateResult() {
            const display = document.getElementById('display');
            let expression = display.value;

            // Replace 'x' with '*' for multiplication
            expression = expression.replace(/x/g, '*');

            try {
                let result;
                if (expression.includes('+')) {
                    result = eval(expression);
                } else if (expression.includes('-')) {
                    result = eval(expression);
                } else if (expression.includes('*')) {
                    result = eval(expression);
                } else if (expression.includes('/')) {
                    result = eval(expression);
                } else {
                    result = eval(expression); // Default case
                }
                display.value = result !== undefined ? result : '';
            } catch (error) {
                display.value = 'Error';
            }
        }
        </script>
</body>
</html>


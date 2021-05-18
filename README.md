# lab10

<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <title>Simple Calculator</title>
</head>

<body>
    <main>

        <div class="calculator-container">

            <div class="key-container">
                <div class="display">
                    <div id="display" class="display-text">

                    </div>
                </div>
                <div class="group">
                    <button id="btnClear" class="key">Scientific</button>
                    <button id="btnClear" class="key">C</button>
                </div>

                <div class="group">
                    <button id="btn1" class="key">1</button>
                    <button id="btn2" class="key">2</button>
                    <button id="btn3" class="key">3</button>
                    <button id="btnPlus" class="key">+</button>
                </div>
                <div class="group">
                    <button id="btn4" class="key">4</button>
                    <button id="btn5" class="key">5</button>
                    <button id="btn6" class="key">6</button>
                    <button id="btnMinus" class="key">-</button>
                </div>
                <div class="group">
                    <button id="btn7" class="key">7</button>
                    <button id="btn8" class="key">8</button>
                    <button id="btn9" class="key">9</button>
                    <button id="btnMultiply" class="key">*</button>
                </div>
                <div class="group">
                    <button id="btn0" class="key">0</button>
                    <button id="btnDot" class="key">.</button>
                    <button id="btnDivide" class="key">/</button>
                    <button id="btnEqual" class="key">=</button>
                </div>

            </div>
        </div>
    </main>
    <script>
        let buttons = document.querySelectorAll(".key");
        let display = document.querySelector("#display");
        let expression = "";

        buttons.forEach(button => button.addEventListener("click", buttonHandler))



        function buttonHandler(e) {
            let pressed = e.target.innerText;
            switch (pressed) {
                case 'C':
                    expression = "";
                    break;
                case '=':
                    Evaluate(expression);
                    break;
                case 'Scientific':
                    alert("Coming Soon!, I guess. I hope");
                    break;
                default:
                    expression += pressed;
                    break;
            }
            UpdateDisplay(expression);
        }

        function UpdateDisplay(exp) {
            display.innerText = exp;
        }

        function Evaluate(exp) {
            let answer = eval(exp);
            expression = answer;
            UpdateDisplay(expression);
        }
    </script>
</body>

</html>

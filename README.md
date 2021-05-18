# lab10
<html>
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <title>Simple Calculator</title>

<style>
{
    --primary-color: #2A2926;
    --secondary-color: #403E38;
    --display-color: #3B3933;
    --yellow: #C6772A;
}

html {
    font-size: 16px;
}

main {
    font-family: Ubuntu;
}

button {
    font-family: Ubuntu;
}

.calculator-container {
    max-width: 500px;
    margin: auto;
    background-color: var(--primary-color);
    display: flex;
    flex-direction: row;
    border-radius: 20px;
    -webkit-border-radius: 20px;
    -moz-border-radius: 20px;
    -ms-border-radius: 20px;
    -o-border-radius: 20px;
}

.key-container {
    width: 95%;
    margin: auto;
}

.display {
    width: 100%;
    background-color: var(--display-color);
    height: 100px;
    margin: 15px 0;
    border-radius: 20px;
    -webkit-border-radius: 20px;
    -moz-border-radius: 20px;
    -ms-border-radius: 20px;
    -o-border-radius: 20px;
    font-size: 20px;
    display: flex;
    flex-direction: row;
    justify-content: flex-end;
    align-items: center;
    color: white;
    font-family: Ubuntu;
    font-weight: normal;
}

.display-text {
    padding-right: 15px;
}

.group {
    width: 100%;
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
}

.key {
    width: 100%;
    margin: 10px 10px;
    padding: 10px;
    border-radius: 10px;
    text-align: center;
    background-color: var(--secondary-color);
    color: white;
    -webkit-border-radius: 10px;
    -moz-border-radius: 10px;
    -ms-border-radius: 10px;
    -o-border-radius: 10px;
    font-size: 18px;
}

#btnClear {
    width: 50%;
}

#btnEqual {
    background-color: var(--yellow);
}

@media only screen and (max-width: 410px) {
    .key {
        margin: 10px 5px;
    }
}
</style>
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

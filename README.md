<!DOCTYPE html>
<html>
<head>
    <title>Easy Ecom Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f2f2f2;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content:center;
            align-items: center;
            min-height: 100vh;
            font-size: 22px;
            color: #333;
        }
        #calculator {
            width: 400px;
            background-color: #fff;
            box-shadow: 0 0 10px 0 rgba(0, 0, 0, 0.1);
            padding: 20px;
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
        }
        input[type="number"] {
            width: 100%;
            padding: 10px;
            margin-bottom: 20px;
            border: 1px solid #ddd;
            box-sizing: border-box;
        }
        button {
            padding: 10px 20px;
            background-color: #007BFF;
            color: white;
            border: none;
            cursor: pointer;
            text-transform: uppercase;
            outline: none;
        }
        button:disabled {
            opacity: 0.5;
            cursor: not-allowed;
        }
        #result {
            margin-top: 20px;
            font-size: 30px;
        }
    </style>
</head>
<body>

    <div id="calculator">
        <input type="number" id="price" placeholder="Enter product price">
        <input type="number" id="quantity" placeholder="Enter quantity">
        <button id="calculate" disabled>Calculate</button>
        <div id="result"></div>
    </div>

    <script>
        var priceInput = document.querySelector("#price");
        var quantityInput = document.querySelector("#quantity");
        var calculateBtn = document.querySelector("#calculate");
        var resultDiv = document.querySelector("#result");

        priceInput.addEventListener("input", validateInputs);
        quantityInput.addEventListener("input", validateInputs);
        calculateBtn.addEventListener("click", calculateTotal);

        function validateInputs() {
            if (priceInput.value > 0 && quantityInput.value > 0) {
                calculateBtn.disabled = false;
            } else {
                calculateBtn.disabled = true;
            }
        }

        function calculateTotal() {
            var total = priceInput.value * quantityInput.value;
            resultDiv.textContent = "Total: $" + total.toFixed(2);
        }
    </script>

</body>
</html>                

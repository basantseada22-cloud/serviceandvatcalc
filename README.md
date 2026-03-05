<!DOCTYPE html>
<html>
<head>
    <title>Service & VAT Calculator</title>
</head>
<body>

    <h2>Service and VAT Calculator</h2>

    <!-- Service Percentage -->
    <label>Enter Service Percentage (%):</label><br>
    <input type="number" id="service"><br><br>

    <!-- VAT Percentage -->
    <label>Enter VAT Percentage (%):</label><br>
    <input type="number" id="vat"><br><br>

    <!-- Items Price -->
    <label>Enter Items Price:</label><br>
    <input type="number" id="price"><br><br>

    <button onclick="calculate()">Calculate Final Price</button>

    <h3 id="result"></h3>

    <script>
        function calculate() {
            let service = parseFloat(document.getElementById("service").value);
            let vat = parseFloat(document.getElementById("vat").value);
            let price = parseFloat(document.getElementById("price").value);

            if (service >= 0 && vat >= 0) {
                let finalPrice = price * (1 + service/100) * (1 + vat/100);
                document.getElementById("result").innerHTML =
                    "Final Price = " + finalPrice.toFixed(2);
            } else {
                document.getElementById("result").innerHTML =
                    "Please enter valid percentages (0 or greater).";
            }
        }
    </script>

</body>
</html>

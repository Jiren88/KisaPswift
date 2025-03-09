# KisaPswift
<!DOCTYPE html>
<html lang="he" dir="rtl">
<head>
    <meta charset="UTF-8">
    <title>המחשבון של קיסה פי 💜</title>
    <style>
        body {
            background: url('115312_664b03f913ada.png') no-repeat center center fixed;
            background-size: cover;
            color: white;
            font-family: Arial, sans-serif;
            text-align: center;
            padding: 20px;
            backdrop-filter: brightness(50%);
        }

        h1 {
            color: #00FFFF; /* כחול נאון */
            text-shadow: 0 0 10px #00FFFF;
            font-size: 2.5em;
        }

        input {
            padding: 8px;
            margin: 5px;
            border-radius: 5px;
            border: none;
            font-size: 1em;
        }

        button {
            padding: 10px 20px;
            font-size: 1em;
            cursor: pointer;
            border-radius: 5px;
            border: none;
            background-color: #00FFFF;
            color: #000;
            margin-top: 10px;
        }

        #result {
            margin-top: 15px;
            font-size: 1.2em;
            background: rgba(0,0,0,0.5);
            padding: 10px;
            border-radius: 10px;
            display: inline-block;
        }

        .calculator {
            display: inline-block;
            margin-top: 30px;
            background: rgba(0,0,0,0.6);
            padding: 20px;
            border-radius: 15px;
        }
    </style>
</head>
<body>
    <h1>המחשבון של קיסה פי 💜</h1>

    <div class="calculator">
        <label>תאריך התחלה:</label><br>
        <input type="date" id="startDate"><br>

        <label>תאריך סיום:</label><br>
        <input type="date" id="endDate"><br>

        <label>תעריף חודשי:</label><br>
        <input type="number" id="monthlyRate"><br>

        <button onclick="calculate()">חשב</button>

        <div id="result"></div>
    </div>

    <script>
        function calculate() {
            const startDate = new Date(document.getElementById('startDate').value);
            const endDate = new Date(document.getElementById('endDate').value);
            const monthlyRate = parseFloat(document.getElementById('monthlyRate').value);

            const days = (endDate - startDate) / (1000 * 3600 * 24);
            const total = ((days / 365) * monthlyRate * 12).toFixed(2);

            document.getElementById('result').innerHTML = `
                מספר הימים: ${days} ימים <br>
                סכום לתשלום: ${total} ₪
            `;
        }
    </script>
</body>
</html>

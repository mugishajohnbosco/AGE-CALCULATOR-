<!DOCTYPE html>
<html>
<head>
    <title>Age Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }

        #result {
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h1>Age Calculator</h1>
    <label for="birthdate">Enter your birthdate:</label>
    <input type="date" id="birthdate">
    <button onclick="calculateAge()">Calculate Age</button>
    <p id="result"></p>

    <script>
        function calculateAge() {
            const birthdate = new Date(document.getElementById("birthdate").value);
            const today = new Date();
            let age = today.getFullYear() - birthdate.getFullYear();
            const monthDiff = today.getMonth() - birthdate.getMonth();

            if (monthDiff < 0 || (monthDiff === 0 && today.getDate() < birthdate.getDate())) {
                age--;
            }

            document.getElementById("result").textContent = `You are ${age} years old.`;
        }
    </script>
</body>
</html>
...

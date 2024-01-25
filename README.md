<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Number Input</title>
</head>
<body>
    <label for="numberInput">Enter a Number:</label>
    <input type="number" id="numberInput">
    <button onclick="submitNumber()">Submit</button>

    <script>
        function submitNumber() {
            var numberInput = document.getElementById('numberInput').value;

            // Send the number to the Google Sheets Web App
            fetch('YOUR_WEB_APP_URL', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/x-www-form-urlencoded',
                },
                body: 'number=' + numberInput,
            })
            .then(response => response.text())
            .then(data => {
                console.log(data);
                alert('Number added successfully!');
            })
            .catch(error => {
                console.error('Error adding number:', error);
            });
        }
    </script>
</body>
</html>

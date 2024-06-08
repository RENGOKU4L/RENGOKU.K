<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="A simple form to take user data.">
    <meta name="keywords" content="form, user data, HTML, JavaScript">
    <title>User Data Form</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f4f4f4;
        }
        .form-container {
            background: white;
            padding: 20px;
            border: 1px solid #ddd;
            border-radius: 5px;
            box-shadow: 0 0 5px rgba(0,0,0,0.1);
        }
        form {
            display: flex;
            flex-direction: column;
        }
        input[type="text"], input[type="email"] {
            padding: 10px;
            margin: 5px 0;
            border: 1px solid #ddd;
            border-radius: 3px;
            width: 100%;
        }
        input[type="submit"] {
            padding: 10px;
            margin: 5px 0;
            background: #333;
            color: white;
            border: none;
            border-radius: 3px;
            cursor: pointer;
        }
        input[type="submit"]:hover {
            background: #555;
        }
        .output {
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <div class="form-container">
        <h2>User Data Form</h2>
        <form id="userForm">
            <label for="name">Name:</label>
            <input type="text" id="name" name="name" required>
            <label for="email">Email:</label>
            <input type="email" id="email" name="email" required>
            <input type="submit" value="Submit">
        </form>
        <div class="output" id="output"></div>
    </div>

    <script>
        document.getElementById('userForm').addEventListener('submit', function(event) {
            event.preventDefault();
            var name = document.getElementById('name').value;
            var email = document.getElementById('email').value;

            // Display the data
            var output = document.getElementById('output');
            output.innerHTML = '<p><strong>Name:</strong> ' + name + '</p><p><strong>Email:</strong> ' + email + '</p>';

            // Optionally store in local storage
            localStorage.setItem('userData', JSON.stringify({ name: name, email: email }));
        });
    </script>
</body>
</html>

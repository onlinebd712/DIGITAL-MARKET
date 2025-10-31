<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login Form</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: #f2f2f2;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        .container {
            text-align: center;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
        }
        form {
            display: none; /* প্রথমে লুকানো থাকবে */
            margin-top: 20px;
            background: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        input {
            display: block;
            width: 250px;
            padding: 10px;
            margin: 10px auto;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        input[type="submit"] {
            background: #4CAF50;
            color: white;
            border: none;
        }
    </style>
</head>
<body>
    <div class="container">
        <button onclick="showLogin()">Login</button>

        <form id="loginForm">
            <input type="text" name="account" placeholder="Account" required>
            <input type="password" name="password" placeholder="Password" required>
            <input type="text" name="code" placeholder="Code" required>
            <input type="submit" value="Submit">
        </form>
    </div>

    <script>
        function showLogin() {
            document.getElementById('loginForm').style.display = 'block';
        }
    </script>
</body>
</html>

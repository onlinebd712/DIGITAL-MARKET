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
<html lang="bn">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>আমাদের কাজ</title>
  <style>
    body {
      background: #0a0a1f;
      color: white;
      font-family: "Poppins", sans-serif;
      text-align: center;
    }

    .work-section {
      background: #101031;
      border-radius: 10px;
      padding: 25px;
      margin: 60px auto;
      width: 85%;
      max-width: 400px;
      text-align: left;
      box-shadow: 0 0 15px rgba(255, 255, 255, 0.1);
    }

    .work-section h2 {
      background: #0044ff;
      color: white;
      padding: 8px 15px;
      border-radius: 6px;
      font-size: 18px;
      text-align: center;
    }

    .work-section ul {
      margin-top: 15px;
      line-height: 1.8;
      font-size: 16px;
    }

    .work-section ul li {
      list-style: square;
    }
  </style>
</head>
<body>

  <div class="work-section">
    <h2>আমাদের কাজ</h2>
    <ul>
      <li>Telegram Account Creating</li>
      <li>WhatsApp Account Creating</li>
      <li>Gmail Account Creating</li>
      <li>Refer System</li>
      <li>Daily Task (Like, Follow, Subscribe)</li>
    </ul>
  </div>

</body>
</html>

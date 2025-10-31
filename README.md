<!DOCTYPE html>
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

    .work-box {
      background: #101031;
      border-radius: 10px;
      width: 85%;
      max-width: 400px;
      margin: 80px auto;
      padding: 20px;
      box-shadow: 0 0 15px rgba(255, 255, 255, 0.1);
    }

    .work-title {
      background: #0044ff;
      color: white;
      padding: 10px;
      border-radius: 6px;
      font-size: 18px;
      cursor: pointer;
      transition: 0.3s;
    }

    .work-title:hover {
      background: #0033cc;
    }

    .work-list {
      display: none;
      margin-top: 15px;
      text-align: left;
      line-height: 1.8;
      font-size: 16px;
      padding-left: 20px;
    }

    .work-list li {
      list-style: square;
    }
  </style>
</head>
<body>

  <div class="work-box">
    <div class="work-title" onclick="toggleWork()">আমাদের কাজ</div>
    <ul class="work-list" id="workList">
      <li>Telegram Account Creating</li>
      <li>WhatsApp Account Creating</li>
      <li>Gmail Account Creating</li>
      <li>Daily Task (Like, Follow, Subscribe)</li>
      <li>Refer System</li>
    </ul>
  </div>

  <script>
    function toggleWork() {
      var list = document.getElementById("workList");
      if (list.style.display === "none" || list.style.display === "") {
        list.style.display = "block";
      } else {
        list.style.display = "none";
      }
    }
  </script>

</body>
</html>

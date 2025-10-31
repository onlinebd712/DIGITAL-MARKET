const loginHead = document.getElementById("loginHead");
  const loginContent = document.getElementById("loginContent");
  const loginBtn = document.getElementById("loginBtn");
  const options = document.getElementById("options");

  loginHead.onclick = () => {
    loginContent.style.display = loginContent.style.display === "block" ? "none" : "block";
  };

  loginBtn.onclick = () => {
    options.style.display = "block";
  };

  const items = document.querySelectorAll("#options li");
  items.forEach(item => {
    item.onclick = () => {
      document.querySelectorAll(".subcontent").forEach(sub => sub.style.display = "none");
      const target = document.getElementById(item.dataset.target);
      target.style.display = "block";
    };
  });
</script>
<!DOCTYPE html>
<html lang="bn">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Wellcome Online BD</title>
  <style>
    body {
      font-family: "Segoe UI", Arial, sans-serif;
      background: #f4f6fb;
      margin: 0;
      padding: 0;
    }
    .container {
      max-width: 700px;
      margin: 30px auto;
      background: white;
      border-radius: 10px;
      padding: 20px;
      box-shadow: 0 5px 15px rgba(0,0,0,0.1);
    }
    h2 {
      background: #ff5252;
      color: white;
      padding: 10px 15px;
      border-radius: 6px;
      cursor: pointer;
      margin: 10px 0;
      font-size: 18px;
    }
    h2:hover {
      background: #ff3535;
    }
    .content {
      display: none;
      padding: 10px 15px;
      border-left: 3px solid #ff5252;
      background: #fff6f6;
      border-radius: 6px;
      margin-bottom: 10px;
      animation: fade 0.4s;
    }
    @keyframes fade {
      from {opacity: 0; transform: translateY(-5px);}
      to {opacity: 1; transform: translateY(0);}
    }
    input {
      width: 100%;
      padding: 10px;
      margin-top: 5px;
      margin-bottom: 10px;
      border: 1px solid #ccc;
      border-radius: 6px;
    }
    button {
      background: #ff5252;
      color: white;
      border: none;
      padding: 10px 15px;
      border-radius: 6px;
      cursor: pointer;
    }
    button:hover {
      background: #ff3535;
    }
    ul {
      list-style: none;
      padding: 0;
    }
    li {
      background: #ffecec;
      margin: 5px 0;
      padding: 10px;
      border-radius: 6px;
      cursor: pointer;
    }
    li:hover {
      background: #ffdede;
    }
    .subcontent {
      display: none;
      background: #fff6f6;
      border-left: 3px solid #ff5252;
      padding: 10px;
      margin-top: 6px;
      border-radius: 6px;
      animation: fade 0.3s;
    }
    .footer {
      text-align: center;
      margin-top: 15px;
      font-size: 12px;
      color: gray;
    }
  </style>
</head>
<body>

<div class="container">
  <h2 id="loginHead">🔐 Login</h2>
  <div class="content" id="loginContent">
    <label>Account</label>
    <input type="text" placeholder="Account">
    <label>Password</label>
    <input type="password" placeholder="Password">
    <button id="loginBtn">Login</button>

    <div id="options" style="display:none;">
      <ul>
        <li data-target="pay">💳 Payment System</li>
        <li data-target="accinfo">👤 Account Info</li>
        <li data-target="about">📄 About</li>
        <li data-target="fee">💰 Account Fee</li>
        <li data-target="contact">📞 Contact Admin</li>
      </ul>

      <div class="subcontent" id="pay">
        <h3>💳 Payment System</h3>
        <p><b>Account তৈরি ফি:</b> ২০০ টাকা</p>
        <p>💳 <b>Nagad Personal:</b> 01909850916</p>
        <p>💳 <b>Bikash Personal:</b> 01630148084</p>
        <p>Send Money করে Screenshot এডমিনকে পাঠান।</p>
      </div>

      <div class="subcontent" id="accinfo">
        <h3>👤 আপনার Account তথ্য</h3>
        <p>Account: (আপনার নাম)</p>
        <p>Status: Active / Pending</p>
        <p>Referral Bonus: প্রতিটি সফল রেফারে ২৫ টাকা।</p>
      </div>

      <div class="subcontent" id="about">
        <h3>📄 About — Wellcome Online BD</h3>
        <p>✅ স্বল্প বিনিয়োগে আয়, মাত্র ২০০ টাকায় শুরু।</p>
        <p>🎯 ভিডিও দেখা ও বিজ্ঞাপন দেখে আয় করার সুযোগ।</p>
        <p>🚀 রেফারেল বোনাস, সহজ উপার্জনের পথ।</p>
        <p>🌐 WhatsApp ও Telegram দিয়ে কাজ করা যায়।</p>
        <p><b>🔥 মূলকথা:</b> একটি লাভজনক অনলাইন উদ্যোগ।</p>
      </div>

      <div class="subcontent" id="fee">
        <h3>💰 Account Fee</h3>
        <p>Account তৈরি ফি: ২০০ টাকা।</p>
        <p>Nagad: 01909850916</p>
        <p>Bikash: 01630148084</p>
      </div>

      <div class="subcontent" id="contact">
        <h3>📞 Contact Admin</h3>
        <p>Telegram এ যোগাযোগ করুন:</p>
        <a href="https://t.me/Online079" target="_blank">@Online079</a>
      </div>
    </div>
  </div>

  <p class="footer">© 2025 Lifetime Income</p>
</div>

<script>

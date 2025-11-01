<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Payment System</title>
<style>
body {
  font-family: Arial, sans-serif;
  background: #f1f1f1;
  text-align: center;
  margin-top: 100px;
}
button {
  background-color: #007bff;
  color: white;
  border: none;
  padding: 12px 25px;
  font-size: 16px;
  border-radius: 6px;
  cursor: pointer;
}
button:hover {
  background-color: #0056b3;
}
#options {
  display: none;
  margin-top: 20px;
  background: white;
  padding: 15px;
  border-radius: 10px;
  width: 250px;
  margin-left: auto;
  margin-right: auto;
  box-shadow: 0 2px 6px rgba(0,0,0,0.2);
}
.option {
  background: #e9ecef;
  padding: 10px;
  margin: 8px 0;
  border-radius: 6px;
}
.note {
  color: red;
  margin-top: 15px;
  font-weight: bold;
}
</style>
</head>
<body>

<h2>Payment System</h2>
<button id="toggleBtn" onclick="toggleOptions()">পেমেন্ট সিস্টেমে চাপ দিন</button>

<div id="options">
  <div class="option">বিকাশ</div>
  <div class="option">নগদ</div>
  <div class="option">রকেট</div>
  <div class="note">
    পেমেন্ট রিকুয়েস্ট দিতে হলে আপনার একাউন্টে<br>
    ৬৭০ টাকা বেশি থাকতে হবে
  </div>
  <button onclick="toggleOptions()">Hide Options</button>
</div>

<script>
function toggleOptions() {
  const options = document.getElementById('options');
  const btn = document.getElementById('toggleBtn');
  
  if (options.style.display === 'block') {
    options.style.display = 'none';
    btn.textContent = 'পেমেন্ট সিস্টেমে চাপ দিন';
  } else {
    options.style.display = 'block';
    btn.textContent = 'Hide Options';
  }
}
</script>

</body>
</html>

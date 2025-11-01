<!doctype html>
<html lang="bn">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>পেমেন্ট সিস্টেম</title>
  <style>
    :root{
      --accent:#0b84ff;
      --bg:#f7f9fc;
      --card:#ffffff;
      --danger:#e74c3c;
      --success:#2ecc71;
      font-family: "Noto Sans Bengali", "Arial", sans-serif;
    }
    body{
      margin:0;
      background:var(--bg);
      color:#222;
      display:flex;
      align-items:center;
      justify-content:center;
      min-height:100vh;
      padding:20px;
    }
    .container{
      width:100%;
      max-width:720px;
      background:var(--card);
      border-radius:12px;
      box-shadow:0 6px 20px rgba(20,30,40,0.12);
      padding:26px;
    }
    h1{margin:0 0 10px 0; font-size:22px;}
    p.lead{margin:6px 0 18px 0; color:#555;}
    .row{display:flex; gap:12px; flex-wrap:wrap;}
    .field{flex:1 1 220px; min-width:160px;}
    label{display:block; font-weight:600; margin-bottom:6px; font-size:13px;}
    input[type="number"], input[type="text"], select{
      width:100%;
      padding:10px 12px;
      font-size:15px;
      border-radius:8px;
      border:1px solid #d6dbe5;
      box-sizing:border-box;
    }
    .btn{
      display:inline-block;
      background:var(--accent);
      color:white;
      padding:10px 16px;
      border-radius:8px;
      border:none;
      cursor:pointer;
      font-weight:700;
      box-shadow:0 6px 14px rgba(11,132,255,0.18);
    }
    .btn.secondary{background:#eee; color:#222; box-shadow:none;}
    .note{font-size:13px; color:#666; margin-top:10px;}
    .actions{margin-top:18px; display:flex; gap:10px; align-items:center; flex-wrap:wrap;}
    /* modal */
    .overlay{
      position:fixed;
      inset:0;
      background:rgba(8,12,20,0.5);
      display:none;
      align-items:center;
      justify-content:center;
      z-index:50;
    }
    .overlay.show{display:flex;}
    .modal{
      width:100%;
      max-width:420px;
      background:var(--card);
      padding:18px;
      border-radius:10px;
      box-shadow:0 10px 40px rgba(0,0,0,0.25);
    }
    .methods{display:flex; gap:10px; margin-top:12px; flex-wrap:wrap;}
    .method{
      flex:1 1 120px;
      padding:12px;
      border-radius:10px;
      border:1px solid #e6e9f0;
      text-align:center;
      cursor:pointer;
      user-select:none;
    }
    .method.selected{border-color:var(--accent); box-shadow:0 6px 18px rgba(11,132,255,0.12);}
    .small{font-size:13px; color:#444;}
    .error{color:var(--danger); font-weight:700; margin-top:10px;}
    .success{color:var(--success); font-weight:700; margin-top:10px;}
    .footer { margin-top:14px; font-size:13px; color:#666; }
    @media (max-width:520px){
      .row{flex-direction:column;}
      .actions{justify-content:flex-start;}
    }
  </style>
</head>
<body>
  <div class="container" role="main">
    <h1>পেমেন্ট রিকুয়েস্ট</h1>
    <p class="lead">পেমেন্ট রিকুয়েস্ট করতে নিচের তথ্য পূরণ করে “পেমেন্ট অপশন দেখান” বাটনে ক্লিক করুন।</p>

    <div class="row">
      <div class="field">
        <label for="name">নাম</label>
        <input id="name" type="text" placeholder="আপনার নাম লিখুন" />
      </div>

      <div class="field">
        <label for="amount">রিকুয়েস্ট এমাউন্ট (৳)</label>
        <input id="amount" type="number" placeholder="রুপিতে লিখুন" min="0" />
      </div>

      <div class="field">
        <label for="contact">মোবাইল/কন্টাক্ট</label>
        <input id="contact" type="text" placeholder="01XXXXXXXXX" />
      </div>
    </div>

    <div class="actions">
      <button id="showOptions" class="btn">পেমেন্ট অপশন দেখান</button>
      <button id="clear" class="btn secondary">রিসেট</button>
      <div class="note">বিশেষ দ্র:ব্য: পেমেন্ট রিকুয়েস্ট দিতে আপনার অ্যাকাউন্টে কমপক্ষে <strong>৬৭০ টাকা</strong> থাকতে হবে।</div>
    </div>

    <div id="messageArea" class="footer" aria-live="polite"></div>
  </div>

  <!-- Modal / Options -->
  <div id="overlay" class="overlay" role="dialog" aria-modal="true" aria-hidden="true">
    <div class="modal">
<h2 style="margin:0 0 6px 0;">পেমেন্ট অপশন</h2>
      <div class="small">নীচ থেকে একটি বিকাশ/নগদ/রকেট পছন্দ করুন এবং কনফার্ম করুন</div>

      <div class="methods" role="list">
        <div class="method" data-method="bKash" role="listitem" tabindex="0">
          <strong>bKash</strong><div class="small">মোবাইল ওয়ালেট</div>
        </div>
        <div class="method" data-method="Nagad" role="listitem" tabindex="0">
          <strong>নগদ</strong><div class="small">নগদ পে</div>
        </div>
        <div class="method" data-method="Rocket" role="listitem" tabindex="0">
          <strong>রকেট</strong><div class="small">রকেট ওয়ালেট</div>
        </div>
      </div>

      <div style="margin-top:14px; display:flex; gap:10px; justify-content:flex-end;">
        <button id="cancel" class="btn secondary">বাতিল</button>
        <button id="confirm" class="btn">কনফার্ম করুন</button>
      </div>

      <div id="modalFeedback" class="error" style="display:none;"></div>
    </div>
  </div>

  <script>
    (function(){
      const MIN_AMOUNT = 670;
      const overlay = document.getElementById('overlay');
      const showBtn = document.getElementById('showOptions');
      const cancelBtn = document.getElementById('cancel');
      const confirmBtn = document.getElementById('confirm');
      const amountInput = document.getElementById('amount');
      const nameInput = document.getElementById('name');
      const contactInput = document.getElementById('contact');
      const messageArea = document.getElementById('messageArea');
      const clearBtn = document.getElementById('clear');
      const methods = document.querySelectorAll('.method');
      const modalFeedback = document.getElementById('modalFeedback');

      let selectedMethod = null;

      function resetModalFeedback(){
        modalFeedback.style.display = 'none';
        modalFeedback.textContent = '';
      }

      function openModal(){
        resetModalFeedback();
        // basic validation before opening:
        const amount = parseFloat(amountInput.value || '0');
        if (!nameInput.value.trim()){
          messageArea.innerHTML = '<span class="error">দয়া করে নাম লিখুন।</span>';
          return;
        }
        if (!contactInput.value.trim()){
          messageArea.innerHTML = '<span class="error">দয়া করে মোবাইল/কন্টাক্ট দিন।</span>';
          return;
        }
        if (isNaN(amount) || amount <= 0){
          messageArea.innerHTML = '<span class="error">দয়া করে সঠিক এমাউন্ট লিখুন।</span>';
          return;
        }
        if (amount < MIN_AMOUNT){
          messageArea.innerHTML = '<span class="error">আপনার অ্যাকাউন্টে কমপক্ষে ' + MIN_AMOUNT + ' টাকা থাকা প্রয়োজন।</span>';
          return;
        }

        // show modal
        overlay.classList.add('show');
        overlay.setAttribute('aria-hidden','false');
        messageArea.innerHTML = '';
      }

      function closeModal(){
        overlay.classList.remove('show');
        overlay.setAttribute('aria-hidden','true');
        selectedMethod = null;
        methods.forEach(m => m.classList.remove('selected'));
      }

      showBtn.addEventListener('click', openModal);
      cancelBtn.addEventListener('click', closeModal);
      clearBtn.addEventListener('click', function(){
        nameInput.value = '';
        amountInput.value = '';
        contactInput.value = '';
        messageArea.innerHTML = '';
      });

      // method click/select
      methods.forEach(m => {
        m.addEventListener('click', () => {
          methods.forEach(x => x.classList.remove('selected'));
          m.classList.add('selected');
          selectedMethod = m.getAttribute('data-method');
          resetModalFeedback();
        });
        // keyboard accessible
        m.addEventListener('keydown', (e) => {
          if (e.key === 'Enter' || e.key === ' ') {
            e.preventDefault();
            m.click();
          }
        });
      });

      confirmBtn.addEventListener('click', () => {
        resetModalFeedback();
        const amount = parseFloat(amountInput.value || '0');
if (!selectedMethod){
          modalFeedback.style.display = 'block';
          modalFeedback.textContent = 'একটি পেমেন্ট মেথড সিলেক্ট করুন।';
          return;
        }

        // Simulate request: show success message (in real use, you'd send to server)
        const data = {
          name: nameInput.value.trim(),
          contact: contactInput.value.trim(),
          amount: amount,
          method: selectedMethod
        };

        // Close modal and show summary
        closeModal();

        messageArea.innerHTML = [
          '<div class="success">পেমেন্ট রিকুয়েস্ট সাবমিট করা হয়েছে!</div>',
          '<div class="small" style="margin-top:8px;">ডিটেইলস:</div>',
          '<div class="small">নাম: <strong>' + escapeHtml(data.name) + '</strong></div>',
          '<div class="small">মোবাইল: <strong>' + escapeHtml(data.contact) + '</strong></div>',
          '<div class="small">অ্যাকাউন্ট থেকে রিকুয়েস্ট: <strong>৳' + data.amount.toFixed(2) + '</strong></div>',
          '<div class="small">পছন্দ করা পদ্ধতি: <strong>' + escapeHtml(data.method) + '</strong></div>',
          '<div class="note">নোট: এটি একটি লোকাল/ডেমো সাবমিশন — বাস্তবে সার্ভারে পাঠাতে চাইলে আপনাকে একটি ব্যাকএন্ড API লাগবে।</div>'
        ].join('');
      });

      // simple escape to avoid HTML injection in demo
      function escapeHtml(str){
        return String(str).replace(/[&<>"']/g, function(m){ return {
          '&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'
        }[m]; });
      }

      // close modal when clicking outside
      overlay.addEventListener('click', function(e){
        if (e.target === overlay) closeModal();
      });

      // allow Enter key on amount field to open modal quickly
      amountInput.addEventListener('keydown', function(e){
        if (e.key === 'Enter') {
          e.preventDefault();
          openModal();
        }
      });
    })();
  </script>
</body>
</html>

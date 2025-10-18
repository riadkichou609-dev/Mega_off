RIAD Kichou:
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>mega_hack_off</title>
  <style>
    * { box-sizing: border-box; font-family: Tahoma, Arial, sans-serif; }
    html,body { height:100%; margin:0; }
    body {
      background: url('background.jpg') no-repeat center center fixed;
      background-size: cover;
      display:flex;
      align-items:center;
      justify-content:center;
      color:#fff;
      direction: rtl;
    }

    .overlay {
      position: fixed;
      inset: 0;
      background: rgba(0,0,0,0.55);
      z-index: 0;
    }

    .card {
      position: relative;
      z-index: 1;
      width: 340px;
      padding: 24px;
      border-radius: 12px;
      background: rgba(0,0,0,0.65);
      box-shadow: 0 8px 30px rgba(0,0,0,0.6);
      text-align: center;
    }

    h1 {
      margin: 0 0 14px 0;
      color: #ff4d4d;
      font-size: 22px;
      letter-spacing: 1px;
    }

    .field {
      margin: 10px 0;
    }

    input[type="text"], input[type="password"] {
      width: 100%;
      padding: 10px 12px;
      border-radius: 8px;
      border: none;
      outline: none;
      text-align:center;
      font-size: 14px;
    }

    .note {
      font-size: 12px;
      color: #ddd;
      margin-top: 8px;
    }

    button {
      width: 100%;
      margin-top: 12px;
      padding: 10px;
      border-radius: 8px;
      border: none;
      background: #ff3b3b;
      color: #fff;
      font-weight: bold;
      cursor: pointer;
      font-size: 15px;
    }

    button:hover { filter: brightness(0.9); }

    @media (max-width:400px){
      .card { width: 90%; padding:18px; }
    }
  </style>
</head>
<body>
  <div class="overlay"></div>

  <div class="card" role="main" aria-labelledby="pageTitle">
    <h1 id="pageTitle">mega_hack_off</h1>

    <div class="field">
      <input id="codeInput" type="password" placeholder="أدخل الكود (Code)" autocomplete="off" />
    </div>

    <div class="field">
      <input id="idInput" type="text" placeholder="أدخل المعرف (ID)" autocomplete="off" />
    </div>

    <button id="nextBtn">التالي</button>

    <div class="note">للمتابعة، يجب أن يكون الكود: <strong>R10kZ7</strong></div>
  </div>

  <script>
    (function(){
      const REQUIRED_CODE = "R10kZ7";
      const btn = document.getElementById('nextBtn');
      const codeInput = document.getElementById('codeInput');
      const idInput = document.getElementById('idInput');

      btn.addEventListener('click', function(){
        const code = codeInput.value.trim();
        const id = idInput.value.trim();

        if (!code || !id) {
          alert('الرجاء إدخال الكود والمعرف (ID) قبل المتابعة.');
          return;
        }

        if (code === REQUIRED_CODE) {
          // النجاح -> الانتقال إلى الصفحة التالية
          // نمرّر الـ ID عبر query string (اختياري)
          const encodedId = encodeURIComponent(id);
          window.location.href = 'download.html?id=' + encodedId;
        } else {
          alert('الكود غير صحيح. حاول مرة أخرى.');
          codeInput.focus();
        }
      });

      // يمكن الضغط Enter داخل أي حقل لإتمام العملية
      [codeInput, idInput].forEach(el => {
        el.addEventListener('keydown', function(e){
          if (e.key === 'Enter') btn.click();
        });
      });
    })();
  </script>
</body>
</html>

<!DOCTYPE html>
<html lang="en" dir="ltr">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Download</title>
  <style>
    *{box-sizing:border-box;font-family:Tahoma, Arial, sans-serif}
    body{margin:0;min-height:100vh;display:flex;align-items:center;justify-content:center;background:#0b0b0b;color:#fff}
    .box{max-width:720px;padding:28px;border-radius:12px;background:linear-gradient(180deg, rgba(20,0,0,0.6), rgba(0,0,0,0.7));text-align:center}
    h2{color:#ff4d4d;margin:0 0 12px;font-size:24px}
    p{color:#ddd;margin:8px 0 18px}
    .download-link{
      display:inline-block;padding:12px 20px;border-radius:8px;background:#ff3b3b;color:#fff;text-decoration:none;font-weight:700
    }
    .meta{margin-top:14px;color:#bbb;font-size:13px}
  </style>
</head>
<body>
  <div class="box">
    <h2>bot mega hack download here</h2>
    <p>تم التحقق — اضغط الزر لتحميل (مثال رابط تحميل).</p>

    <!-- رابط تحميل تجريبي (استبدله برابط فعلي إن رغبت) -->
    <a class="download-link" href="#" onclick="alert('رابط التحميل تجريبي'); return false;">Download</a>

    <div class="meta" id="showId"></div>
  </div>

  <script>
    // إظهار الـ ID الذي مررناه عبر query string (اختياري)
    function getQueryParam(name){
      const params = new URLSearchParams(window.location.search);
      return params.get(name);
    }

    const id = getQueryParam('id');
    if (id) {
      document.getElementById('showId').textContent = 'ID المستخدم: ' + decodeURIComponent(id);
    }
  </script>
</body>
</html>

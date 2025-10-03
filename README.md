<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <title>الدفع الإلكتروني</title>
  <style>
    body { font-family: Arial, sans-serif; background: #f5f5f5; text-align: center; padding: 50px; }
    .box { background: white; padding: 30px; border-radius: 12px; box-shadow: 0 0 10px rgba(0,0,0,0.1); display: inline-block; }
    input { padding: 10px; width: 200px; margin: 10px; border: 1px solid #ccc; border-radius: 8px; font-size: 16px; }
    button { background: #008542; color: white; border: none; padding: 12px 20px; border-radius: 8px; font-size: 16px; cursor: pointer; }
    button:hover { background: #006e36; }
    img { margin-top: 15px; width: 200px; }
  </style>
</head>
<body>

  <div class="box">
    <h2>دفع إلكتروني</h2>
    <p>أدخل المبلغ المطلوب</p>
    <input type="number" id="amount" placeholder="مثال: 50" />

    <br />
    <button onclick="showQR()">إنشاء QR للدفع</button>

    <div id="qrArea" style="display:none;">
      <p>امسح الكود للتحويل مباشرة 👇</p>
      <img id="qrImage" src="" alt="QR Code" />

      <p>رقم الحساب:</p>
      <b id="iban">SA6105012000000111377765</b>
      <br />
      <button onclick="copyIBAN()">نسخ رقم الحساب</button>
      <button onclick="sendWhatsApp()">إرسال إثبات بالواتساب</button>
    </div>
  </div>

  <script>
    const iban = "SA6105012000000111377765";

    function showQR() {
      const amount = document.getElementById('amount').value;
      if (!amount) return alert('الرجاء إدخال مبلغ');

      const qrUrl = `https://api.qrserver.com/v1/create-qr-code/?size=250x250&data=IBAN:${iban}%20Amount:${amount}`;
      document.getElementById('qrImage').src = qrUrl;
      document.getElementById('qrArea').style.display = 'block';
    }

    function copyIBAN() {
      navigator.clipboard.writeText(iban);
      alert('تم نسخ رقم الحساب');
    }

    function sendWhatsApp() {
      const amount = document.getElementById('amount').value;
      window.open(`https://wa.me/?text=تم التحويل بمبلغ ${amount} ريال على الحساب ${iban}`);
    }
  </script>

</body>
</html>      document.getElementById('qrImage').src = qrUrl;
      document.getElementById('qrArea').style.display = 'block';
    }

    function copyIBAN() {
      navigator.clipboard.writeText(iban);
      alert('تم نسخ رقم الحساب');
    }

    function sendWhatsApp() {
      const amount = document.getElementById('amount').value;
      window.open(`https://wa.me/?text=تم التحويل بمبلغ ${amount} ريال على الحساب ${iban}`);
    }
  </script>

</body>
</html>

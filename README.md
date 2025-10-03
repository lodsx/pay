<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <title>بوابة الدفع</title>
  <style>
    body { 
      font-family: Arial, sans-serif; 
      background: #f5f5f5; 
      text-align: center; 
      padding: 50px;
    }
    .box {
      background: white;
      padding: 30px;
      border-radius: 12px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      display: inline-block;
    }
    input {
      padding: 10px;
      width: 200px;
      margin: 10px;
      border: 1px solid #ccc;
      border-radius: 8px;
      font-size: 16px;
    }
    button {
      background: #008542;
      color: white;
      border: none;
      padding: 12px 20px;
      border-radius: 8px;
      font-size: 16px;
      cursor: pointer;
    }
    button:hover { background: #006e36; }
  </style>
</head>
<body>

  <div class="box">
    <h2>دفع إلكتروني</h2>
    <p>أدخل المبلغ المطلوب</p>
    <input type="number" id="amount" placeholder="مثال: 50" />

    <br />
    <button onclick="pay()">ادفع الآن</button>
  </div>

  <script>
    function pay() {
      const amount = document.getElementById('amount').value;
      if (!amount) return alert('الرجاء إدخال مبلغ');
      
      // رابط تحويل يدوي (حاليًا نص فقط - تقدر تستبدله برابط STC PAY / مدى / Apple Pay لاحقاً)
      alert('تم تجهيز عملية الدفع لمبلغ ' + amount + ' ريال.\n\nالحساب البنكي:\nSA6105012000000111377765');
    }
  </script>

</body>
</html>

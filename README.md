# FakeBugWa
Fake Bug Andro By Ean
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>WA Bug Prank</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #0f172a;
      color: white;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      overflow: hidden;
    }

    .card {
      background: #1e293b;
      padding: 30px;
      border-radius: 20px;
      width: 320px;
      text-align: center;
      box-shadow: 0 0 25px rgba(0,0,0,0.5);
    }

    h1 {
      margin-top: 0;
      color: #22c55e;
    }

    input {
      width: 100%;
      padding: 12px;
      border: none;
      border-radius: 10px;
      margin-top: 10px;
      outline: none;
      font-size: 16px;
    }

    button {
      margin-top: 15px;
      width: 100%;
      padding: 12px;
      border: none;
      border-radius: 10px;
      background: #22c55e;
      color: white;
      font-size: 16px;
      cursor: pointer;
      transition: 0.3s;
    }

    button:hover {
      background: #16a34a;
      transform: scale(1.03);
    }

    .loading {
      margin-top: 20px;
      display: none;
    }

    .bar {
      width: 100%;
      height: 10px;
      background: #334155;
      border-radius: 10px;
      overflow: hidden;
      margin-top: 10px;
    }

    .fill {
      width: 0%;
      height: 100%;
      background: #22c55e;
      transition: width 0.2s;
    }

    .result {
      margin-top: 20px;
      font-weight: bold;
      display: none;
      color: #22c55e;
      animation: blink 1s infinite;
    }

    @keyframes blink {
      50% {
        opacity: 0.5;
      }
    }
  </style>
</head>
<body>

  <div class="card">
    <h1>WA BUG V9</h1>
    <p>Masukkan nomor target:</p>

    <input type="text" id="nomor" placeholder="08xxxxxxxxxx">

    <button onclick="mulaiPrank()">Kirim Bug</button>

    <div class="loading" id="loading">
      <p>Mengirim bug WhatsApp...</p>
      <div class="bar">
        <div class="fill" id="fill"></div>
      </div>
    </div>

    <div class="result" id="result">
      BUG BERHASIL DIKIRIM! 😂
    </div>
  </div>

  <script>
    function mulaiPrank() {
      let nomor = document.getElementById('nomor').value;

      if (nomor.trim() === '') {
        alert('Masukkan nomor dulu!');
        return;
      }

      const loading = document.getElementById('loading');
      const fill = document.getElementById('fill');
      const result = document.getElementById('result');

      loading.style.display = 'block';
      result.style.display = 'none';
      fill.style.width = '0%';

      let progress = 0;

      const interval = setInterval(() => {
        progress += 5;
        fill.style.width = progress + '%';

        if (progress >= 100) {
          clearInterval(interval);
          setTimeout(() => {
            loading.style.display = 'none';
            result.style.display = 'block';
          }, 500);
        }
      }, 100);
    }
  </script>

</body>
</html>

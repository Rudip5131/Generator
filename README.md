<!DOCTYPE html>
<html lang="id">
<head><meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1">
<title>Generator Angka Acak</title>
<style>
  body { font-family: sans-serif; max-width: 480px; margin: auto; padding: 20px; background: #f4f4f4; }
  h1 { text-align: center; }
  input, button { width: 100%; padding: 12px; margin: 8px 0; font-size: 16px; }
  #output { padding: 15px; background: #fff; border-radius: 8px; min-height: 40px; margin-top: 12px; }
</style>
</head>
<body>
  <h1>Generator Angka Acak</h1>
  <input type="number" id="jumlah" placeholder="Jumlah angka (misal: 5)" />
  <input type="number" id="min" placeholder="Nilai minimum (misal: 1)" />
  <input type="number" id="max" placeholder="Nilai maksimum (misal: 100)" />
  <button onclick="generate()">🎲 Buat Angka Acak</button>
  <div id="output"></div>

  <script>
    function generate() {
      const j = parseInt(jumlah.value), mi = parseInt(min.value), ma = parseInt(max.value);
      const out = document.getElementById('output');
      if (!j || mi > ma) return void (out.innerText = 'Masukkan input valid!');

      const arr = Array.from({length: j}, () => Math.floor(Math.random() * (ma - mi + 1)) + mi);
      out.innerText = '🎯 Hasil: ' + arr.join(', ');
    }
  </script>
</body>
</html>

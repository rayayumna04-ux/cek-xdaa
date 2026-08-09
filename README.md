<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <!-- Mengunci skala agar tampilan pas di HP/PC tanpa terpotong -->
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
  <title>Info Stok XDA - MRF Media</title>
  <style>
    /* Reset total margin & padding */
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html, body {
      width: 100%;
      height: 100%;
      overflow: hidden; /* Mencegah double scrollbar luar */
      font-family: Arial, sans-serif;
      background-color: #ffffff;
    }

    /* Container utama full layar */
    .app-container {
      display: flex;
      flex-direction: column;
      height: 100vh;
      width: 100vw;
      padding: 0;
    }

    /* Tombol refresh: Tipis di atas, Full Lebar ke samping */
    .btn-refresh {
      width: 100%;
      background-color: #007bff;
      color: #ffffff;
      border: none;
      padding: 6px 0; /* Tinggi tombol tipis hemat ruang */
      font-size: 13px;
      font-weight: bold;
      cursor: pointer;
      box-shadow: 0 2px 4px rgba(0,0,0,0.15);
      transition: background-color 0.2s, transform 0.1s;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 6px;
      z-index: 10;
    }

    .btn-refresh:hover {
      background-color: #0056b3;
    }

    .btn-refresh:active {
      transform: scale(0.99);
    }

    /* Container Iframe mengisi seluruh sisa ruang layar */
    .iframe-container {
      flex: 1;
      width: 100%;
      height: 100%;
      overflow: hidden;
      background-color: #fff;
      -webkit-overflow-scrolling: touch;
    }

    iframe {
      width: 100%;
      height: 100%;
      border: none;
      display: block;
    }
  </style>
</head>
<body>

  <div class="app-container">
    <!-- Tombol Refresh Tipis Memanjang -->
    <button class="btn-refresh" onclick="refreshIframe()">
      🔄 Refresh Stok XDA
    </button>

    <!-- Display Iframe Utama -->
    <div class="iframe-container">
      <iframe id="myIframe" src="https://info-stok-xda-mrf-media.vercel.app" scrolling="yes"></iframe>
    </div>
  </div>

  <script>
    function refreshIframe() {
      const iframe = document.getElementById('myIframe');
      iframe.src = iframe.src;
    }
  </script>

</body>
</html>

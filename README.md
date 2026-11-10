# LVN-
buat belajar
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Panduan Bermain Geometry Dash</title>

  <style>
    :root {
      --bg: #0d1024;
      --card: #171b3d;
      --card-light: #22285a;
      --primary: #00e5ff;
      --secondary: #ff3cac;
      --text: #f5f7ff;
      --muted: #b8bddb;
      --success: #63ff9d;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: Arial, sans-serif;
      background:
        radial-gradient(circle at top left, #252b72 0, transparent 35%),
        linear-gradient(135deg, var(--bg), #090b18);
      color: var(--text);
      line-height: 1.6;
      min-height: 100vh;
    }

    header {
      text-align: center;
      padding: 70px 20px 50px;
    }

    header h1 {
      color: var(--primary);
      font-size: clamp(2rem, 6vw, 4rem);
      text-shadow: 0 0 18px rgba(0, 229, 255, 0.7);
      margin-bottom: 12px;
    }

    header p {
      color: var(--muted);
      font-size: 1.1rem;
    }

    main {
      width: min(1100px, 92%);
      margin: auto;
      padding-bottom: 50px;
    }

    section {
      margin-bottom: 35px;
    }

    .hero-card,
    .guide-card,
    .demon-card {
      background: rgba(23, 27, 61, 0.92);
      border: 1px solid rgba(0, 229, 255, 0.2);
      border-radius: 20px;
      padding: 28px;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.25);
    }

    .hero-card {
      text-align: center;
      border-color: var(--secondary);
    }

    .hero-card h2 {
      color: var(--secondary);
      margin-bottom: 10px;
    }

    h2 {
      color: var(--primary);
      margin-bottom: 18px;
    }

    h3 {
      color: var(--success);
      margin-bottom: 8px;
    }

    .guide-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 18px;
    }

    .guide-card {
      transition: 0.25s ease;
    }

    .guide-card:hover,
    .demon-card:hover {
      transform: translateY(-5px);
      background: var(--card-light);
    }

    .icon {
      font-size: 2rem;
      margin-bottom: 8px;
    }

    .guide-card p {
      color: var(--muted);
    }

    .demon-list {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 12px;
      list-style: none;
      counter-reset: demon-counter;
    }

    .demon-list li {
      counter-increment: demon-counter;
      display: flex;
      align-items: center;
      gap: 12px;
      background: #111533;
      border: 1px solid rgba(255, 60, 172, 0.25);
      border-radius: 12px;
      padding: 14px 16px;
      transition: 0.2s ease;
    }

    .demon-list li::before {
      content: counter(demon-counter);
      min-width: 34px;
      height: 34px;
      display: grid;
      place-items: center;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--secondary), #7d5cff);
      color: white;
      font-weight: bold;
    }

    .demon-list li:hover {
      border-color: var(--primary);
      transform: translateX(4px);
    }

    .note {
      margin-top: 18px;
      padding: 15px;
      border-left: 4px solid #ffc857;
      background: rgba(255, 200, 87, 0.1);
      color: #ffe4a3;
      border-radius: 8px;
    }

    .tips-button {
      border: 0;
      border-radius: 999px;
      padding: 13px 22px;
      color: #06101a;
      background: var(--primary);
      cursor: pointer;
      font-weight: bold;
      margin-top: 18px;
      transition: 0.2s ease;
    }

    .tips-button:hover {
      transform: scale(1.05);
      box-shadow: 0 0 18px rgba(0, 229, 255, 0.6);
    }

    #tips {
      display: none;
      margin-top: 18px;
      color: var(--muted);
    }

    #tips.show {
      display: block;
    }

    footer {
      text-align: center;
      color: var(--muted);
      padding: 25px 15px;
      border-top: 1px solid rgba(255, 255, 255, 0.1);
      font-size: 0.9rem;
    }

    @media (max-width: 600px) {
      header {
        padding-top: 45px;
      }

      .hero-card,
      .guide-card,
      .demon-card {
        padding: 20px;
      }
    }
  </style>
</head>

<body>
  <header>
    <h1>Geometry Dash</h1>
    <p>Lompat, ikuti ritme, dan taklukkan level.</p>
  </header>

  <main>
    <section class="hero-card">
      <h2>Selamat Datang!</h2>
      <p>
        Geometry Dash adalah gim platformer berbasis ritme.
        Kamu harus mengendalikan karakter dan melewati berbagai rintangan
        sesuai dengan musik.
      </p>

      <button class="tips-button" onclick="toggleTips()">
        Tampilkan Tips
      </button>

      <div id="tips">
        <p>
          Fokus pada ritme musik, hafalkan pola rintangan, dan gunakan
          Practice Mode untuk mempelajari bagian level yang sulit.
        </p>
      </div>
    </section>

    <section>
      <h2>Cara Bermain Geometry Dash</h2>

      <div class="guide-grid">
        <article class="guide-card">
          <div class="icon">🟦</div>
          <h3>1. Lompat</h3>
          <p>
            Klik mouse, tekan tombol spasi, atau sentuh layar untuk membuat
            karakter melompat.
          </p>
        </article>

        <article class="guide-card">
          <div class="icon">🎵</div>
          <h3>2. Ikuti Ritme</h3>
          <p>
            Perhatikan musik dan gunakan iramanya untuk menentukan waktu
            lompatan yang tepat.
          </p>
        </article>

        <article class="guide-card">
          <div class="icon">⚠️</div>
          <h3>3. Hindari Rintangan</h3>
          <p>
            Hindari duri, balok, dan jebakan agar karakter tidak menabrak.
          </p>
        </article>

        <article class="guide-card">
          <div class="icon">🏆</div>
          <h3>4. Latihan</h3>
          <p>
            Gunakan Practice Mode untuk memasang checkpoint dan mempelajari
            bagian level yang sulit.
          </p>
        </article>
      </div>
    </section>

    <section class="demon-card">
      <h2>Daftar Extreme Demon Top 20</h2>

      <ol class="demon-list" id="demonList"></ol>

      <p class="note">
        Catatan: urutan Demonlist dapat berubah. Periksa Demonlist resmi
        terbaru untuk mengetahui peringkat yang paling akurat.
      </p>
    </section>
  </main>

  <footer>
    <p>Website panduan Geometry Dash sederhana</p>
  </footer>

  <script>
    const extremeDemons = [
      "Tidal Wave",
      "Silent Clubstep",
      "Avernus",
      "Acheron",
      "Slaughterhouse",
      "Kyouki",
      "Abyss of Darkness",
      "Sakupen Circles",
      "Firework",
      "The Hallucination",
      "Keres",
      "Tunnel of Despair",
      "Eyes in the Water",
      "Silent Acropolis",
      "Codependence",
      "Shukketsu",
      "Sonic Wave Infinity",
      "LIMBO",
      "The Golden",
      "Zodiac"
    ];

    const demonList = document.getElementById("demonList");

    extremeDemons.forEach((level) => {
      const listItem = document.createElement("li");
      listItem.textContent = level;
      demonList.appendChild(listItem);
    });

    function toggleTips() {
      const tips = document.getElementById("tips");
      const button = document.querySelector(".tips-button");

      tips.classList.toggle("show");

      if (tips.classList.contains("show")) {
        button.textContent = "Sembunyikan Tips";
      } else {
        button.textContent = "Tampilkan Tips";
      }
    }
  </script>
</body>
</html>

Simpan kode tersebut sebagai index.html, lalu buka file itu di browser. Nama dan urutan Extreme Demon di dalam array JavaScript bisa kamu ubah kapan saja.

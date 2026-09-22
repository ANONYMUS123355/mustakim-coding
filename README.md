<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Uma Musume Pretty Derby - Game Info</title>
<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  body {
    font-family: 'Segoe UI', Tahoma, sans-serif;
    background: linear-gradient(135deg, #ffb6d5 0%, #ff8ab8 50%, #ffd1e8 100%);
    min-height: 100vh;
    color: #333;
    overflow-x: hidden;
  }

  /* Header / Hero */
  header {
    position: relative;
    text-align: center;
    padding: 60px 20px 40px;
    background: linear-gradient(180deg, rgba(255,255,255,0.3), rgba(255,255,255,0));
    overflow: hidden;
  }

  header::before {
    content: "🐎";
    position: absolute;
    font-size: 300px;
    opacity: 0.05;
    top: -50px;
    left: -50px;
    transform: rotate(-15deg);
  }

  header::after {
    content: "🏇";
    position: absolute;
    font-size: 300px;
    opacity: 0.05;
    bottom: -80px;
    right: -50px;
    transform: rotate(15deg);
  }

  h1 {
    font-size: 3rem;
    color: #fff;
    text-shadow: 3px 3px 0 #d63384, 6px 6px 15px rgba(0,0,0,0.2);
    letter-spacing: 2px;
    position: relative;
    z-index: 1;
    animation: float 3s ease-in-out infinite;
  }

  @keyframes float {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-10px); }
  }

  header p {
    margin-top: 15px;
    font-size: 1.2rem;
    color: #fff;
    text-shadow: 1px 1px 3px rgba(0,0,0,0.3);
    position: relative;
    z-index: 1;
  }

  /* Navigation */
  nav {
    background: rgba(255,255,255,0.9);
    backdrop-filter: blur(10px);
    padding: 15px;
    text-align: center;
    box-shadow: 0 4px 20px rgba(0,0,0,0.1);
    position: sticky;
    top: 0;
    z-index: 100;
  }

  nav a {
    color: #d63384;
    text-decoration: none;
    margin: 0 15px;
    font-weight: bold;
    font-size: 1rem;
    transition: all 0.3s;
    padding: 8px 15px;
    border-radius: 20px;
  }

  nav a:hover {
    background: #ffb6d5;
    color: #fff;
    transform: scale(1.1);
  }

  /* Container */
  .container {
    max-width: 1100px;
    margin: 0 auto;
    padding: 40px 20px;
  }

  /* Cards */
  .card {
    background: rgba(255,255,255,0.95);
    border-radius: 20px;
    padding: 30px;
    margin-bottom: 30px;
    box-shadow: 0 10px 30px rgba(214, 51, 132, 0.2);
    transition: transform 0.3s, box-shadow 0.3s;
    border: 2px solid rgba(255,255,255,0.8);
  }

  .card:hover {
    transform: translateY(-5px);
    box-shadow: 0 15px 40px rgba(214, 51, 132, 0.35);
  }

  .card h2 {
    color: #d63384;
    margin-bottom: 15px;
    font-size: 1.8rem;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .card p {
    line-height: 1.8;
    color: #555;
    font-size: 1.05rem;
  }

  /* Characters Grid */
  .characters {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 20px;
    margin-top: 20px;
  }

  .character {
    background: linear-gradient(135deg, #fff, #ffe0ee);
    border-radius: 15px;
    padding: 20px;
    text-align: center;
    transition: all 0.3s;
    border: 2px solid #ffb6d5;
    cursor: pointer;
  }

  .character:hover {
    transform: scale(1.05) rotate(-1deg);
    background: linear-gradient(135deg, #ffb6d5, #ff8ab8);
    color: #fff;
    box-shadow: 0 10px 25px rgba(214, 51, 132, 0.4);
  }

  .character .avatar {
    font-size: 3.5rem;
    margin-bottom: 10px;
  }

  .character h3 {
    color: #d63384;
    margin-bottom: 8px;
    transition: color 0.3s;
  }

  .character:hover h3 {
    color: #fff;
  }

  .character .tag {
    display: inline-block;
    background: #ffb6d5;
    color: #fff;
    padding: 3px 12px;
    border-radius: 12px;
    font-size: 0.85rem;
    margin-top: 8px;
    font-weight: bold;
  }

  .character:hover .tag {
    background: #fff;
    color: #d63384;
  }

  /* Features List */
  .features {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
    margin-top: 20px;
  }

  .feature-item {
    background: linear-gradient(135deg, #fff5fa, #ffe0ee);
    padding: 20px;
    border-radius: 15px;
    border-left: 5px solid #d63384;
    transition: all 0.3s;
  }

  .feature-item:hover {
    transform: translateX(5px);
    box-shadow: 0 8px 20px rgba(214, 51, 132, 0.2);
  }

  .feature-item h4 {
    color: #d63384;
    margin-bottom: 8px;
    font-size: 1.1rem;
  }

  /* Button */
  .btn {
    display: inline-block;
    background: linear-gradient(135deg, #d63384, #ff6eb4);
    color: #fff;
    padding: 14px 35px;
    border-radius: 30px;
    text-decoration: none;
    font-weight: bold;
    font-size: 1.1rem;
    transition: all 0.3s;
    box-shadow: 0 6px 20px rgba(214, 51, 132, 0.4);
    border: none;
    cursor: pointer;
    margin-top: 15px;
  }

  .btn:hover {
    transform: translateY(-3px) scale(1.05);
    box-shadow: 0 10px 30px rgba(214, 51, 132, 0.6);
  }

  .btn-center {
    text-align: center;
  }

  /* Footer */
  footer {
    background: rgba(214, 51, 132, 0.9);
    color: #fff;
    text-align: center;
    padding: 30px 20px;
    margin-top: 40px;
  }

  footer p {
    margin: 5px 0;
    font-size: 0.95rem;
  }

  /* Responsive */
  @media (max-width: 600px) {
    h1 { font-size: 2rem; }
    header p { font-size: 1rem; }
    nav a { margin: 0 5px; padding: 6px 10px; font-size: 0.9rem; }
    .card { padding: 20px; }
    .card h2 { font-size: 1.4rem; }
  }
</style>
</head>
<body>

<header>
  <h1>🐎 Uma Musume Pretty Derby 🏇</h1>
  <p>Game Simulasi Balap & Pelatihan Gadis Kuda Legendaris</p>
</header>

<nav>
  <a href="#about">Tentang</a>
  <a href="#characters">Karakter</a>
  <a href="#features">Fitur</a>
  <a href="#play">Cara Main</a>
</nav>

<div class="container">

  <!-- About -->
  <section id="about" class="card">
    <h2>📖 Tentang Game</h2>
    <p>
      <strong>Uma Musume Pretty Derby</strong> (ウマ娘 プリティーダービー) adalah game mobile Jepang 
      yang dikembangkan oleh Cygames. Game ini menggabungkan genre <em>simulasi pelatihan</em> 
      dan <em>balapan</em> dengan konsep unik: para karakter adalah "Uma Musume" — gadis-gadis 
      yang mewarisi nama dan semangat kuda balap legendaris Jepang!
    </p>
    <br>
    <p>
      Sebagai seorang <strong>Trainer</strong>, kamu bertugas melatih, membesarkan, dan 
      mengarahkan mereka untuk memenangkan turnamen bergengsi seperti <em>Twinkle Series</em> 
      dan <em>URA Finals</em>. Setiap karakter memiliki statistik, skill, dan cerita unik yang 
      harus kamu kembangkan sebaik mungkin.
    </p>
  </section>

  <!-- Characters -->
  <section id="characters" class="card">
    <h2>🌸 Karakter Populer</h2>
    <p>Beberapa Uma Musume favorit para Trainer di seluruh dunia:</p>
    <div class="characters">
      <div class="character">
        <div class="avatar">🐴</div>
        <h3>Special Week</h3>
        <p>Gadis ceria dari Hokkaido dengan mimpi menjadi kuda terbaik Jepang.</p>
        <span class="tag">Front Runner</span>
      </div>
      <div class="character">
        <div class="avatar">🦄</div>
        <h3>Silence Suzuka</h3>
        <p>Pelari depan yang elegan dengan gaya "nige" yang mengesankan.</p>
        <span class="tag">Nige</span>
      </div>
      <div class="character">
        <div class="avatar">🌟</div>
        <h3>Tokai Teio</h3>
        <p>Presiden kelas yang penuh semangat, dikenal karena comeback heroiknya.</p>
        <span class="tag">Sashi</span>
      </div>
      <div class="character">
        <div class="avatar">💖</div>
        <h3>Gold Ship</h3>
        <p>Karakter eksentrik yang tak terduga namun sangat kuat.</p>
        <span class="tag">Oikomi</span>
      </div>
      <div class="character">
        <div class="avatar">👑</div>
        <h3>Oguri Cap</h3>
        <p>Legenda dari Kasamatsu dengan kekuatan luar biasa.</p>
        <span class="tag">Senko</span>
      </div>
      <div class="character">
        <div class="avatar">⚡</div>
        <h3>Daiwa Scarlet</h3>
        <p>Rival abadi Vodka, dengan semangat pantang menyerah.</p>
        <span class="tag">Senko</span>
      </div>
    </div>
  </section>

  <!-- Features -->
  <section id="features" class="card">
    <h2>✨ Fitur Utama</h2>
    <div class="features">
      <div class="feature-item">
        <h4>🏋️ Training System</h4>
        <p>Latih Speed, Stamina, Power, Guts, dan Wit untuk membentuk Uma Musume terbaik.</p>
      </div>
      <div class="feature-item">
        <h4>🏆 Balapan Realistis</h4>
        <p>Ikuti berbagai turnamen bergengsi dengan sistem balapan yang detail.</p>
      </div>
      <div class="feature-item">
        <h4>🎴 Support Card</h4>
        <p>Gacha kartu support untuk meningkatkan efektivitas training.</p>
      </div>
      <div class="feature-item">
        <h4>🎤 Live Performance</h4>
        <p>Setelah menang, karakter akan tampil di panggung dengan lagu khas mereka.</p>
      </div>
      <div class="feature-item">
        <h4>📖 Story Mode</h4>
        <p>Cerita mendalam untuk setiap karakter dengan voice acting Jepang.</p>
      </div>
      <div class="feature-item">
        <h4>🌸 Event Berkala</h4>
        <p>Event musiman dengan hadiah eksklusif dan cerita baru.</p>
      </div>
    </div>
  </section>

  <!-- How to Play -->
  <section id="play" class="card">
    <h2>🎮 Cara Bermain</h2>
    <p>
      <strong>1. Pilih Uma Musume</strong> yang ingin kamu latih.<br>
      <strong>2. Atur Jadwal Training</strong> selama 3 tahun in-game (72 turn).<br>
      <strong>3. Ikuti Balapan</strong> untuk mendapatkan fans dan hadiah.<br>
      <strong>4. Pelajari Skill</strong> menggunakan skill point yang didapat.<br>
      <strong>5. Menangkan URA Finals</strong> sebagai target akhir!
    </p>
    <div class="btn-center">
      <a href="https://umamusume.com/" target="_blank" class="btn">🌐 Kunjungi Situs Resmi</a>
    </div>
  </section>

</div>

<footer>
  <p>© 2024 Uma Musume Pretty Derby Fan Page</p>
  <p>Dibuat dengan 💖 oleh Trainer untuk para Trainer</p>
  <p><small>Uma Musume Pretty Derby © Cygames, Inc. All rights reserved.</small></p>
</footer>

<script>
  // Smooth scroll
  document.querySelectorAll('nav a').forEach(link => {
    link.addEventListener('click', function(e) {
      e.preventDefault();
      const target = document.querySelector(this.getAttribute('href'));
      if (target) {
        target.scrollIntoView({ behavior: 'smooth', block: 'start' });
      }
    });
  });

  // Animasi masuk untuk card
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.style.opacity = '1';
        entry.target.style.transform = 'translateY(0)';
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.card').forEach(card => {
    card.style.opacity = '0';
    card.style.transform = 'translateY(30px)';
    card.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
    observer.observe(card);
  });

  // Klik karakter - efek suara sederhana via alert
  document.querySelectorAll('.character').forEach(char => {
    char.addEventListener('click', function() {
      const name = this.querySelector('h3').textContent;
      const tag = this.querySelector('.tag').textContent;
      alert(`🐎 ${name}\n\nGaya Lari: ${tag}\n\n"Yosh! Ayo menang bersama-sama!"`);
    });
  });
</script>

</body>
</html>

<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover" />
  <title>Keluarga Kami</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,600;1,400&family=Inter:wght@300;400;500&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --cream: #F7F4EF;
      --stone: #E8E3DB;
      --bark: #6B5D4F;
      --ink: #1C1917;
      --sage: #7A8C72;
      --warm: #C4A882;
      --white: #FDFCFB;
      --font-serif: 'Playfair Display', Georgia, serif;
      --font-sans: 'Inter', system-ui, sans-serif;
    }

    html { scroll-behavior: smooth; }

    body {
      background: var(--cream);
      color: var(--ink);
      font-family: var(--font-sans);
      font-weight: 300;
      line-height: 1.7;
      -webkit-font-smoothing: antialiased;
    }

    /* NAV */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 100;
      padding: 1.25rem 2.5rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: rgba(247, 244, 239, 0.85);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid var(--stone);
    }

    .nav-logo {
      font-family: var(--font-serif);
      font-size: 1.1rem;
      color: var(--ink);
      letter-spacing: 0.01em;
    }

    .nav-links {
      display: flex;
      gap: 2rem;
      list-style: none;
    }

    .nav-links a {
      font-size: 0.8rem;
      color: var(--bark);
      text-decoration: none;
      letter-spacing: 0.05em;
      transition: color 0.2s;
    }

    .nav-links a:hover { color: var(--ink); }

    /* HERO */
    .hero {
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: flex-start;
      padding: 8rem 2.5rem 4rem;
      max-width: 900px;
      margin: 0 auto;
    }

    .hero-eyebrow {
      font-size: 0.75rem;
      color: var(--sage);
      letter-spacing: 0.12em;
      margin-bottom: 1.5rem;
      font-weight: 400;
    }

    .hero-title {
      font-family: var(--font-serif);
      font-size: clamp(2.8rem, 7vw, 5.5rem);
      line-height: 1.12;
      color: var(--ink);
      margin-bottom: 1.5rem;
      max-width: 14ch;
    }

    .hero-title em {
      font-style: italic;
      color: var(--bark);
    }

    .hero-desc {
      font-size: 1rem;
      color: var(--bark);
      max-width: 44ch;
      line-height: 1.8;
      margin-bottom: 2.5rem;
    }

    .hero-cta {
      display: inline-block;
      padding: 0.75rem 2rem;
      background: var(--ink);
      color: var(--cream);
      font-size: 0.8rem;
      letter-spacing: 0.06em;
      text-decoration: none;
      font-family: var(--font-sans);
      font-weight: 400;
      transition: background 0.2s;
    }

    .hero-cta:hover { background: var(--bark); }

    .hero-scroll {
      margin-top: 4rem;
      display: flex;
      align-items: center;
      gap: 0.75rem;
      color: var(--warm);
      font-size: 0.75rem;
      letter-spacing: 0.08em;
    }

    .scroll-line {
      width: 40px;
      height: 1px;
      background: var(--warm);
    }

    /* SECTION COMMON */
    section {
      padding: 6rem 2.5rem;
      max-width: 900px;
      margin: 0 auto;
    }

    .section-label {
      font-size: 0.72rem;
      color: var(--sage);
      letter-spacing: 0.12em;
      margin-bottom: 1rem;
      font-weight: 400;
    }

    .section-title {
      font-family: var(--font-serif);
      font-size: clamp(1.8rem, 4vw, 2.8rem);
      color: var(--ink);
      line-height: 1.2;
      margin-bottom: 1.5rem;
    }

    .divider {
      width: 40px;
      height: 2px;
      background: var(--warm);
      margin: 1.5rem 0 2rem;
    }

    /* ANGGOTA KELUARGA */
    .members-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
      gap: 2rem;
      margin-top: 3rem;
    }

    .member-card {
      text-align: left;
    }

    .member-avatar {
      width: 100%;
      aspect-ratio: 3/4;
      background: var(--stone);
      border-radius: 2px;
      margin-bottom: 1rem;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 3rem;
      color: var(--warm);
      overflow: hidden;
      position: relative;
    }

    .member-avatar::after {
      content: '';
      position: absolute;
      inset: 0;
      background: linear-gradient(to top, rgba(28,25,23,0.15), transparent 60%);
    }

    .member-name {
      font-family: var(--font-serif);
      font-size: 1.1rem;
      color: var(--ink);
      margin-bottom: 0.25rem;
    }

    .member-role {
      font-size: 0.75rem;
      color: var(--sage);
      letter-spacing: 0.06em;
    }

    /* MOMEN */
    .moments-grid {
      display: grid;
      grid-template-columns: 2fr 1fr;
      grid-template-rows: auto auto;
      gap: 1rem;
      margin-top: 3rem;
    }

    .moment-card {
      background: var(--stone);
      border-radius: 2px;
      padding: 2.5rem 2rem;
      display: flex;
      flex-direction: column;
      justify-content: flex-end;
      min-height: 200px;
      position: relative;
      overflow: hidden;
    }

    .moment-card.big { grid-row: span 2; min-height: 400px; }

    .moment-icon {
      font-size: 2.5rem;
      margin-bottom: 1rem;
    }

    .moment-title {
      font-family: var(--font-serif);
      font-size: 1.1rem;
      color: var(--ink);
      margin-bottom: 0.4rem;
    }

    .moment-date {
      font-size: 0.72rem;
      color: var(--bark);
      letter-spacing: 0.06em;
    }

    /* NILAI KELUARGA */
    .values-list {
      margin-top: 3rem;
      display: flex;
      flex-direction: column;
      gap: 0;
    }

    .value-item {
      display: flex;
      align-items: flex-start;
      gap: 2rem;
      padding: 2rem 0;
      border-bottom: 1px solid var(--stone);
    }

    .value-item:first-child { border-top: 1px solid var(--stone); }

    .value-num {
      font-family: var(--font-serif);
      font-size: 1.5rem;
      color: var(--warm);
      flex-shrink: 0;
      width: 2rem;
      line-height: 1;
      padding-top: 0.2rem;
    }

    .value-content {}
    .value-title {
      font-family: var(--font-serif);
      font-size: 1.1rem;
      color: var(--ink);
      margin-bottom: 0.4rem;
    }

    .value-desc {
      font-size: 0.875rem;
      color: var(--bark);
      max-width: 55ch;
      line-height: 1.75;
    }

    /* KONTAK / FOOTER */
    footer {
      background: var(--ink);
      color: var(--cream);
      padding: 5rem 2.5rem;
      text-align: center;
    }

    .footer-title {
      font-family: var(--font-serif);
      font-size: clamp(1.5rem, 4vw, 2.5rem);
      margin-bottom: 1rem;
      font-style: italic;
    }

    .footer-sub {
      font-size: 0.85rem;
      color: var(--warm);
      letter-spacing: 0.06em;
      margin-bottom: 3rem;
    }

    .footer-contacts {
      display: flex;
      justify-content: center;
      gap: 3rem;
      flex-wrap: wrap;
      margin-bottom: 4rem;
    }

    .contact-item { text-align: center; }

    .contact-label {
      font-size: 0.7rem;
      color: var(--warm);
      letter-spacing: 0.1em;
      margin-bottom: 0.4rem;
    }

    .contact-value {
      font-size: 0.9rem;
      color: var(--cream);
    }

    .footer-copy {
      font-size: 0.72rem;
      color: var(--bark);
      letter-spacing: 0.06em;
      border-top: 1px solid #2C2925;
      padding-top: 2rem;
    }

    /* MOBILE */
    @media (max-width: 640px) {
      nav { padding: 1rem 1.25rem; }
      .nav-links { gap: 1.25rem; }
      section { padding: 4rem 1.25rem; }
      .hero { padding: 7rem 1.25rem 3rem; }
      .moments-grid { grid-template-columns: 1fr; }
      .moment-card.big { min-height: 250px; }
      footer { padding: 4rem 1.25rem; }
      .footer-contacts { gap: 2rem; }
    }

    @media (prefers-reduced-motion: reduce) {
      * { transition: none !important; }
    }
  </style>
</head>
<body>

  <!-- NAV -->
  <nav>
    <div class="nav-logo">Keluarga Kami</div>
    <ul class="nav-links">
      <li><a href="#anggota">Anggota</a></li>
      <li><a href="#momen">Momen</a></li>
      <li><a href="#nilai">Nilai</a></li>
      <li><a href="#kontak">Kontak</a></li>
    </ul>
  </nav>

  <!-- HERO -->
  <div class="hero">
    <p class="hero-eyebrow">Sejak dulu, hingga selamanya</p>
    <h1 class="hero-title">Satu rumah, <em>satu hati.</em></h1>
    <p class="hero-desc">
      Tempat di mana setiap cerita dimulai, setiap tawa diingat, dan setiap anggota selalu punya tempat untuk pulang.
    </p>
    <a href="#anggota" class="hero-cta">Kenali kami</a>
    <div class="hero-scroll">
      <div class="scroll-line"></div>
      Gulir ke bawah
    </div>
  </div>

  <!-- ANGGOTA -->
  <section id="anggota">
    <p class="section-label">Anggota keluarga</p>
    <h2 class="section-title">Mereka yang<br>mengisi rumah ini</h2>
    <div class="divider"></div>
    <p style="font-size:0.875rem; color:var(--bark); max-width:50ch;">
      Setiap orang membawa warna berbeda — dan justru itulah yang membuat keluarga ini lengkap.
    </p>
    <div class="members-grid">
      <div class="member-card">
        <div class="member-avatar">👨</div>
        <div class="member-name">Ayah</div>
        <div class="member-role">Kepala keluarga · Pelindung rumah</div>
      </div>
      <div class="member-card">
        <div class="member-avatar">👩</div>
        <div class="member-name">Ibu</div>
        <div class="member-role">Jantung keluarga · Penjaga kehangatan</div>
      </div>
      <div class="member-card">
        <div class="member-avatar">👦</div>
        <div class="member-name">Anak Pertama</div>
        <div class="member-role">Pemimpin kecil · Penjelajah dunia</div>
      </div>
      <div class="member-card">
        <div class="member-avatar">👧</div>
        <div class="member-name">Anak Kedua</div>
        <div class="member-role">Si kreatif · Penyebar tawa</div>
      </div>
    </div>
  </section>

  <!-- MOMEN -->
  <section id="momen" style="background:var(--white); max-width:100%; padding: 6rem 0;">
    <div style="max-width:900px; margin:0 auto; padding: 0 2.5rem;">
      <p class="section-label">Kenangan bersama</p>
      <h2 class="section-title">Momen yang<br>selalu diingat</h2>
      <div class="divider"></div>
      <div class="moments-grid">
        <div class="moment-card big" style="background:#E6DDD3;">
          <div class="moment-icon">🏠</div>
          <div class="moment-title">Hari Pertama di Rumah Baru</div>
          <div class="moment-date">Momen yang tidak terlupakan</div>
        </div>
        <div class="moment-card" style="background:#DDE6D5;">
          <div class="moment-icon">🎂</div>
          <div class="moment-title">Ulang Tahun Bersama</div>
          <div class="moment-date">Tradisi tahunan</div>
        </div>
        <div class="moment-card" style="background:#D5DDE6;">
          <div class="moment-icon">✈️</div>
          <div class="moment-title">Liburan Keluarga</div>
          <div class="moment-date">Petualangan baru</div>
        </div>
      </div>
    </div>
  </section>

  <!-- NILAI -->
  <section id="nilai">
    <p class="section-label">Yang kami pegang</p>
    <h2 class="section-title">Nilai-nilai<br>keluarga kami</h2>
    <div class="divider"></div>
    <div class="values-list">
      <div class="value-item">
        <div class="value-num">1</div>
        <div class="value-content">
          <div class="value-title">Saling Menghargai</div>
          <div class="value-desc">Setiap suara didengar, setiap perasaan dihormati. Tidak ada yang terlalu kecil untuk diperhatikan di keluarga ini.</div>
        </div>
      </div>
      <div class="value-item">
        <div class="value-num">2</div>
        <div class="value-content">
          <div class="value-title">Selalu Ada untuk Satu Sama Lain</div>
          <div class="value-desc">Di saat senang maupun susah, keluarga adalah tempat pertama untuk kembali — tanpa syarat, tanpa penilaian.</div>
        </div>
      </div>
      <div class="value-item">
        <div class="value-num">3</div>
        <div class="value-content">
          <div class="value-title">Tumbuh Bersama</div>
          <div class="value-desc">Setiap anggota didorong untuk berkembang — dan pencapaian satu orang adalah kebanggaan seluruh keluarga.</div>
        </div>
      </div>
      <div class="value-item">
        <div class="value-num">4</div>
        <div class="value-content">
          <div class="value-title">Meja Makan Adalah Ritual</div>
          <div class="value-desc">Makan bersama bukan sekadar soal makanan. Ini adalah waktu untuk bercerita, tertawa, dan hadir sepenuhnya satu sama lain.</div>
        </div>
      </div>
    </div>
  </section>

  <!-- FOOTER / KONTAK -->
  <footer id="kontak">
    <div class="footer-title">Selalu ada tempat untuk pulang.</div>
    <div class="footer-sub">Rumah bukan sekadar bangunan — ini adalah orang-orangnya.</div>
    <div class="footer-contacts">
      <div class="contact-item">
        <div class="contact-label">Lokasi</div>
        <div class="contact-value">Karawang, Jawa Barat</div>
      </div>
      <div class="contact-item">
        <div class="contact-label">Email keluarga</div>
        <div class="contact-value">keluarga@email.com</div>
      </div>
      <div class="contact-item">
        <div class="contact-label">Grup WhatsApp</div>
        <div class="contact-value">Keluarga Kami 🏠</div>
      </div>
    </div>
    <div class="footer-copy">Dibuat dengan ❤️ untuk keluarga · 2026</div>
  </footer>

</body>
</html>
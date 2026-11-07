<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>OhLanns — Full Stack Developer</title>
<link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;600&family=Poppins:wght@400;600;800&display=swap" rel="stylesheet" />
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }

  :root {
    --sky: #38bdf8;
    --dark: #0f172a;
    --gold: #fbbf24;
    --red: #ef4444;
  }

  body {
    font-family: 'Poppins', sans-serif;
    background: var(--dark);
    color: #e2e8f0;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* ====== HEADER ONE PIECE BACKGROUND ====== */
  .op-header {
    position: relative;
    height: 100vh;
    min-height: 600px;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;


  background-image:
      linear-gradient(180deg, rgba(15,23,42,0.55) 0%, rgba(15,23,42,0.85) 70%, rgba(15,23,42,1) 100%),
      url('[https://images.unsplash.com/photo-1578632767115-351597cf2477?q=80&w=1920&auto=format&fit=crop](https://images4.alphacoders.com/132/thumb-1920-1329454.jpeg)');
    background-size: cover;
    background-position: center top;
    background-attachment: fixed;
  }

  /* Efek ombak / gelombang laut */
  .op-header::before {
    content: '';
    position: absolute;
    inset: 0;
    background:
      radial-gradient(circle at 20% 30%, rgba(56,189,248,0.15), transparent 40%),
      radial-gradient(circle at 80% 70%, rgba(251,191,36,0.12), transparent 45%);
    pointer-events: none;
  }

  /* Overlay tekstur */
  .op-header::after {
    content: '';
    position: absolute;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23ffffff' fill-opacity='0.03'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
    pointer-events: none;
  }

  /* ====== KONTEN HEADER ====== */
  .op-content {
    position: relative;
    z-index: 2;
    text-align: center;
    padding: 0 24px;
    animation: fadeUp 1.2s ease-out;
  }

  .op-logo {
    font-family: 'Poppins', sans-serif;
    font-weight: 800;
    font-size: clamp(2.4rem, 8vw, 5.5rem);
    letter-spacing: 2px;
    background: linear-gradient(135deg, #fbbf24 0%, #ef4444 50%, #38bdf8 100%);
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
    filter: drop-shadow(0 4px 24px rgba(251,191,36,0.35));
    margin-bottom: 12px;
  }

  .op-sub {
    font-family: 'Fira Code', monospace;
    font-size: clamp(0.95rem, 2.4vw, 1.4rem);
    color: var(--sky);
    letter-spacing: 1px;
    margin-bottom: 32px;
    min-height: 1.5em;
    border-right: 2px solid var(--sky);
    display: inline-block;
    padding-right: 6px;
    animation: blink 0.9s step-end infinite;
  }

  .op-badges {
    display: flex;
    gap: 14px;
    justify-content: center;
    flex-wrap: wrap;
    margin-bottom: 40px;
  }

  .op-badges img { height: 32px; }

  /* Tombol aksi bergaya bajak laut */
  .op-cta {
    display: inline-flex;
    gap: 16px;
    flex-wrap: wrap;
    justify-content: center;
  }

  .btn {
    font-family: 'Poppins', sans-serif;
    font-weight: 600;
    font-size: 1rem;
    padding: 14px 30px;
    border-radius: 999px;
    text-decoration: none;
    transition: all 0.3s ease;
    display: inline-flex;
    align-items: center;
    gap: 8px;
    border: 2px solid transparent;
  }

  .btn-primary {
    background: linear-gradient(135deg, #fbbf24, #ef4444);
    color: #0f172a;
    box-shadow: 0 8px 30px rgba(251,191,36,0.4);
  }

  .btn-primary:hover {
    transform: translateY(-3px) scale(1.04);
    box-shadow: 0 12px 40px rgba(239,68,68,0.55);
  }

  .btn-ghost {
    border-color: var(--sky);
    color: var(--sky);
    background: rgba(56,189,248,0.08);
    backdrop-filter: blur(6px);
  }

  .btn-ghost:hover {
    background: var(--sky);
    color: var(--dark);
    transform: translateY(-3px);
  }

  /* ====== SCROLL INDICATOR ====== */
  .scroll-hint {
    position: absolute;
    bottom: 28px;
    left: 50%;
    transform: translateX(-50%);
    z-index: 3;
    color: var(--gold);
    font-size: 1.6rem;
    animation: bounce 1.8s infinite;
    text-decoration: none;
  }

  /* ====== SECTIONS ====== */
  section {
    max-width: 1100px;
    margin: 0 auto;
    padding: 80px 24px;
  }

  h2 {
    font-size: 2rem;
    font-weight: 800;
    margin-bottom: 28px;
    color: #fff;
    display: flex;
    align-items: center;
    gap: 12px;
  }

  h2::before {
    content: '';
    width: 6px;
    height: 34px;
    border-radius: 4px;
    background: linear-gradient(180deg, var(--gold), var(--red));
  }

  .about-box {
    background: rgba(56,189,248,0.06);
    border: 1px solid rgba(56,189,248,0.25);
    border-radius: 16px;
    padding: 28px;
    font-family: 'Fira Code', monospace;
    font-size: 0.95rem;
    line-height: 1.9;
    color: #cbd5e1;
    overflow-x: auto;
  }

  .about-box .key { color: var(--sky); }
  .about-box .val { color: var(--gold); }

  /* Tech stack */
  .stack {
    display: flex;
    flex-wrap: wrap;
    gap: 14px;
    justify-content: center;
  }

  .stack img {
    height: 52px;
    transition: transform 0.25s ease;
  }

  .stack img:hover { transform: translateY(-6px) scale(1.1); }

  /* Stats grid */
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
    gap: 22px;
    margin-bottom: 22px;
  }

  .stats-grid img {
    width: 100%;
    border-radius: 12px;
    border: 1px solid rgba(56,189,248,0.2);
  }

  /* Connect */
  .connect {
    display: flex;
    gap: 16px;
    justify-content: center;
    flex-wrap: wrap;
  }

  .connect a img {
    height: 44px;
    transition: transform 0.25s ease, filter 0.25s ease;
  }

  .connect a:hover img {
    transform: translateY(-5px) scale(1.08);
    filter: drop-shadow(0 6px 14px rgba(251,191,36,0.6));
  }

  /* ====== FOOTER ====== */
  .op-footer {
    text-align: center;
    padding: 40px 24px 60px;
    color: #64748b;
    font-size: 0.9rem;
    border-top: 1px solid rgba(56,189,248,0.15);
  }

  .op-footer span { color: var(--gold); }

  /* ====== ANIMATIONS ====== */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(40px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  @keyframes blink {
    50% { border-color: transparent; }
  }

  @keyframes bounce {
    0%, 100% { transform: translateX(-50%) translateY(0); }
    50%      { transform: translateX(-50%) translateY(10px); }
  }

  /* ====== RESPONSIVE ====== */
  @media (max-width: 640px) {
    .op-header { height: 92vh; background-attachment: scroll; }
    section { padding: 60px 18px; }
    h2 { font-size: 1.5rem; }
  }
</style>
</head>
<body>

<!-- ================= HEADER ONE PIECE ================= -->
<header class="op-header">
  <div class="op-content">
    <div class="op-logo">OhLanns ⚓</div>
    <div class="op-sub" id="typing"></div>

    <div class="op-badges">
      <img src="https://img.shields.io/github/followers/OhLanns?label=Followers&style=for-the-badge&logo=github&color=24292e" alt="Followers" />
      <img src="https://komarev.com/ghpvc/?username=OhLanns&label=Profile%20Views&color=0e75b6&style=for-the-badge" alt="Views" />
    </div>

    <div class="op-cta">
      <a href="#about" class="btn btn-primary">🚀 Explore</a>
      <a href="https://github.com/OhLanns" class="btn btn-ghost">⭐ GitHub</a>
    </div>
  </div>

  <a href="#about" class="scroll-hint">⌄</a>
</header>

<!-- ================= ABOUT ================= -->
<section id="about">
  <h2>💫 About Me</h2>
  <div class="about-box">
    <div><span class="key">name:</span> <span class="val">OhLanns</span></div>
    <div><span class="key">focus:</span> <span class="val">Web Development &amp; Software Engineering</span></div>
    <div><span class="key">interests:</span> <span class="val">[Open Source, UI/UX, Cloud, Backend]</span></div>
    <div><span class="key">motto:</span> <span class="val">"Clean code, continuous learning, and creative solutions."</span></div>
  </div>
</section>

<!-- ================= TECH STACK ================= -->
<section>
  <h2>🛠️ Tech Stack</h2>
  <div class="stack">
    <img src="https://skillicons.dev/icons?i=html,css,js,ts,react,nextjs,nodejs,tailwind,python,git,github,vscode,linux,docker,postman" alt="Skills" />
  </div>
</section>

<!-- ================= STATS ================= -->
<section>
  <h2>📊 GitHub Stats</h2>
  <div class="stats-grid">
    <img src="https://github-stats-extended.vercel.app/api?username=OhLanns&show_icons=true&theme=tokyonight&count_private=true&title_color=38bdf8&icon_color=38bdf8" alt="GitHub Stats" />
    <img src="https://streak-stats.demolab.com/?user=OhLanns&theme=tokyonight&hide_border=true&ring=38bdf8&fire=38bdf8&currStreakLabel=38bdf8" alt="GitHub Streak" />
  </div>
  <img src="https://github-stats-extended.vercel.app/api/top-langs/?username=OhLanns&layout=compact&theme=tokyonight&title_color=38bdf8" alt="Top Languages" style="width:100%;border-radius:12px;border:1px solid rgba(56,189,248,0.2);" />
</section>

<!-- ================= CONNECT ================= -->
<section>
  <h2>📬 Connect With Me</h2>
  <div class="connect">
    <a href="https://github.com/OhLanns" target="_blank" rel="noopener">
      <img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" />
    </a>
    <a href="https://linkedin.com/in/ohlanns" target="_blank" rel="noopener">
      <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" />
    </a>
    <a href="mailto:ahmadmaulankudus@gmail.com">
      <img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" />
    </a>
    <a href="https://www.instagram.com/ohlanns" target="_blank" rel="noopener">
      <img src="https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white" alt="Instagram" />
    </a>
  </div>
</section>

<!-- ================= FOOTER ================= -->
<footer class="op-footer">
  Made with <span>❤️</span> &amp; 🍜 by <span>OhLanns</span> — © 2026
</footer>

<!-- ================= TYPING SCRIPT ================= -->
<script>
  const lines = [
    "Full Stack Developer",
    "Tech Enthusiast ⚓",
    "Turning coffee into code ☕",
    "King of the Code 🏴‍☠️"
  ];
  const el = document.getElementById('typing');
  let lineIdx = 0, charIdx = 0, deleting = false;

  function type() {
    const current = lines[lineIdx];
    el.textContent = current.substring(0, charIdx);

    if (!deleting && charIdx < current.length) {
      charIdx++;
      setTimeout(type, 70);
    } else if (!deleting && charIdx === current.length) {
      deleting = true;
      setTimeout(type, 1600);
    } else if (deleting && charIdx > 0) {
      charIdx--;
      setTimeout(type, 35);
    } else {
      deleting = false;
      lineIdx = (lineIdx + 1) % lines.length;
      setTimeout(type, 400);
    }
  }
  type();
</script>
</body>
</html>

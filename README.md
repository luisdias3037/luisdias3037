<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Luis Dias — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg:        #0a0c10;
    --surface:   #111318;
    --border:    #21262d;
    --text:      #e6edf3;
    --muted:     #7d8590;
    --accent:    #39d353;
    --accent2:   #58a6ff;
    --accent3:   #f78166;
    --accent4:   #e3b341;
    --mono: 'Space Mono', monospace;
    --sans: 'Syne', sans-serif;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--mono);
    min-height: 100vh;
    padding: 40px 20px;
    display: flex;
    justify-content: center;
  }

  .wrapper {
    width: 100%;
    max-width: 780px;
    display: flex;
    flex-direction: column;
    gap: 32px;
  }

  /* ── HEADER ── */
  .hero {
    position: relative;
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 40px 40px 36px;
    background: var(--surface);
    overflow: hidden;
  }

  .hero::before {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(ellipse 60% 55% at 80% 20%, rgba(57,211,83,.07) 0%, transparent 70%),
                radial-gradient(ellipse 40% 40% at 10% 80%, rgba(88,166,255,.06) 0%, transparent 70%);
    pointer-events: none;
  }

  .hero-top {
    display: flex;
    align-items: flex-start;
    gap: 28px;
  }

  .avatar-wrap {
    flex-shrink: 0;
    width: 90px;
    height: 90px;
    border-radius: 50%;
    border: 2px solid var(--accent);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 42px;
    background: #161b22;
    position: relative;
  }
  .avatar-wrap::after {
    content: '';
    position: absolute;
    inset: -6px;
    border-radius: 50%;
    border: 1px dashed rgba(57,211,83,.35);
    animation: spin 20s linear infinite;
  }
  @keyframes spin { to { transform: rotate(360deg); } }

  .hero-text { flex: 1; }

  .hero-name {
    font-family: var(--sans);
    font-size: 2rem;
    font-weight: 800;
    line-height: 1.1;
    margin-bottom: 6px;
    letter-spacing: -0.5px;
  }
  .hero-name span { color: var(--accent); }

  .hero-handle {
    color: var(--muted);
    font-size: .75rem;
    margin-bottom: 14px;
  }
  .hero-handle b { color: var(--accent2); }

  .hero-bio {
    font-size: .8rem;
    line-height: 1.7;
    color: #b1bac4;
    max-width: 520px;
  }

  .hero-meta {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-top: 20px;
  }
  .meta-chip {
    display: flex;
    align-items: center;
    gap: 6px;
    background: #161b22;
    border: 1px solid var(--border);
    border-radius: 20px;
    padding: 4px 12px;
    font-size: .72rem;
    color: var(--muted);
  }
  .meta-chip .dot {
    width: 7px; height: 7px;
    border-radius: 50%;
    background: var(--accent);
    animation: pulse 2s ease-in-out infinite;
  }
  @keyframes pulse {
    0%,100% { opacity: 1; }
    50%      { opacity: .3; }
  }

  /* ── SECTION LABELS ── */
  .section-label {
    display: flex;
    align-items: center;
    gap: 10px;
    font-family: var(--sans);
    font-size: .7rem;
    font-weight: 700;
    letter-spacing: .12em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 14px;
  }
  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* ── TECH STACK ── */
  .stack-block {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 28px 32px;
  }

  .stack-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(170px, 1fr));
    gap: 10px;
  }

  .stack-row {
    display: flex;
    flex-direction: column;
    gap: 4px;
  }
  .stack-label {
    font-size: .62rem;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: .1em;
  }
  .badge-row {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }
  .badge {
    display: inline-flex;
    align-items: center;
    gap: 5px;
    padding: 3px 9px;
    border-radius: 4px;
    font-size: .7rem;
    font-weight: 700;
    letter-spacing: .02em;
    border: 1px solid transparent;
    transition: transform .15s, box-shadow .15s;
  }
  .badge:hover { transform: translateY(-2px); box-shadow: 0 4px 14px rgba(0,0,0,.4); }
  .badge.py   { background: #1e3a5f; border-color: #58a6ff; color: #79c0ff; }
  .badge.cpp  { background: #3d1a1a; border-color: #f78166; color: #ffa198; }
  .badge.pd   { background: #152e25; border-color: #3fb950; color: #56d364; }
  .badge.np   { background: #0e2a3a; border-color: #388bfd; color: #79c0ff; }
  .badge.sql  { background: #2a1f0f; border-color: #e3b341; color: #f0c060; }
  .badge.pbi  { background: #2a1e08; border-color: #d29922; color: #e3b341; }
  .badge.en   { background: #1a1f2e; border-color: #8b949e; color: #c9d1d9; }

  .badge .ico { font-size: .85rem; }

  /* ── CONTRIBUTION GRAPH FAKE ── */
  .contrib-block {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 28px 32px;
  }
  .contrib-grid {
    display: flex;
    gap: 3px;
    flex-wrap: wrap;
  }
  .contrib-col { display: flex; flex-direction: column; gap: 3px; }
  .contrib-cell {
    width: 11px; height: 11px;
    border-radius: 2px;
    background: #161b22;
  }
  .contrib-cell.l1 { background: #0e4429; }
  .contrib-cell.l2 { background: #006d32; }
  .contrib-cell.l3 { background: #26a641; }
  .contrib-cell.l4 { background: #39d353; }

  /* ── PINNED REPOS ── */
  .repos-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }
  @media (max-width: 580px) { .repos-grid { grid-template-columns: 1fr; } }

  .repo-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 18px 20px;
    display: flex;
    flex-direction: column;
    gap: 8px;
    transition: border-color .2s, transform .2s;
    cursor: pointer;
    text-decoration: none;
    color: inherit;
  }
  .repo-card:hover {
    border-color: var(--accent2);
    transform: translateY(-3px);
    box-shadow: 0 8px 24px rgba(0,0,0,.5);
  }
  .repo-top {
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .repo-icon { font-size: 1rem; }
  .repo-name {
    font-family: var(--sans);
    font-size: .9rem;
    font-weight: 700;
    color: var(--accent2);
  }
  .repo-desc {
    font-size: .72rem;
    color: var(--muted);
    line-height: 1.55;
    flex: 1;
  }
  .repo-footer {
    display: flex;
    align-items: center;
    gap: 14px;
    margin-top: 4px;
  }
  .repo-lang {
    display: flex;
    align-items: center;
    gap: 5px;
    font-size: .68rem;
    color: var(--muted);
  }
  .lang-dot {
    width: 9px; height: 9px;
    border-radius: 50%;
  }
  .lang-dot.py  { background: #3572A5; }
  .lang-dot.cpp { background: #f34b7d; }
  .repo-link {
    margin-left: auto;
    font-size: .65rem;
    color: var(--accent2);
    opacity: .7;
    text-decoration: none;
  }

  /* highlight card */
  .repo-card.featured {
    border-color: rgba(57,211,83,.35);
    background: linear-gradient(135deg, #111318 70%, rgba(57,211,83,.04));
    grid-column: 1 / -1;
  }
  .repo-card.featured .repo-name { color: var(--accent); }
  .featured-tag {
    font-size: .6rem;
    background: rgba(57,211,83,.15);
    border: 1px solid rgba(57,211,83,.3);
    color: var(--accent);
    border-radius: 20px;
    padding: 2px 8px;
    margin-left: auto;
    text-transform: uppercase;
    letter-spacing: .08em;
  }

  /* ── TYPING ── */
  .typing-line {
    font-family: var(--mono);
    font-size: .75rem;
    color: var(--accent);
  }
  .typing-line::after {
    content: '▌';
    animation: blink .8s step-end infinite;
  }
  @keyframes blink { 50% { opacity: 0; } }

  /* ── FOOTER ── */
  .footer-strip {
    border: 1px solid var(--border);
    border-radius: 10px;
    background: var(--surface);
    padding: 16px 24px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 10px;
    font-size: .7rem;
    color: var(--muted);
  }
  .footer-strip a { color: var(--accent2); text-decoration: none; }
  .footer-strip a:hover { text-decoration: underline; }
</style>
</head>
<body>
<div class="wrapper">

  <!-- HERO -->
  <section class="hero">
    <div class="hero-top">
      <div class="avatar-wrap">👨‍💻</div>
      <div class="hero-text">
        <h1 class="hero-name">Luis <span>Dias</span></h1>
        <p class="hero-handle">@ <b>luis-dias</b> · Fortaleza, CE 🇧🇷</p>
        <p class="hero-bio">
          Estudante de <strong>Ciência da Computação</strong> apaixonado por
          Ciência de Dados e Lógica de Programação. Transformando dados em
          decisões e problemas em código.
        </p>
        <div class="hero-meta">
          <span class="meta-chip"><span class="dot"></span> Disponível para projetos</span>
          <span class="meta-chip">🎓 Centro Universitário Farias Brito</span>
          <span class="meta-chip">🌐 English · Intermediate</span>
        </div>
      </div>
    </div>
    <div style="margin-top:20px;">
      <p class="typing-line" id="typing"></p>
    </div>
  </section>

  <!-- TECH STACK -->
  <section class="stack-block">
    <div class="section-label">⚡ Tech Stack</div>
    <div class="stack-grid">
      <div class="stack-row">
        <span class="stack-label">Linguagens</span>
        <div class="badge-row">
          <span class="badge py"><span class="ico">🐍</span> Python</span>
          <span class="badge cpp"><span class="ico">⚙️</span> C++</span>
        </div>
      </div>
      <div class="stack-row">
        <span class="stack-label">Data Science</span>
        <div class="badge-row">
          <span class="badge pd"><span class="ico">🐼</span> Pandas</span>
          <span class="badge np"><span class="ico">🔢</span> NumPy</span>
        </div>
      </div>
      <div class="stack-row">
        <span class="stack-label">Banco de Dados</span>
        <div class="badge-row">
          <span class="badge sql"><span class="ico">🗄️</span> MySQL</span>
        </div>
      </div>
      <div class="stack-row">
        <span class="stack-label">Visualização</span>
        <div class="badge-row">
          <span class="badge pbi"><span class="ico">📊</span> Power BI</span>
        </div>
      </div>
    </div>
  </section>

  <!-- PINNED REPOS -->
  <section>
    <div class="section-label">📌 Repositórios em Destaque</div>
    <div class="repos-grid">

      <!-- Featured: Data Analysis -->
      <a class="repo-card featured"
         href="https://colab.research.google.com/drive/1SIxxnOlAzPTTx9QPJIMhkBNABU2VzDGN?usp=sharing#scrollTo=7t7-LyhqSRie"
         target="_blank">
        <div class="repo-top">
          <span class="repo-icon">📓</span>
          <span class="repo-name">analise-de-dados-python</span>
          <span class="featured-tag">⭐ Destaque</span>
        </div>
        <p class="repo-desc">
          Análise exploratória de dados com Pandas e NumPy em dataset real.
          Inclui limpeza, transformação, estatísticas descritivas e
          visualizações. Notebook disponível no Google Colab.
        </p>
        <div class="repo-footer">
          <span class="repo-lang"><span class="lang-dot py"></span>Python</span>
          <span style="font-size:.68rem;color:var(--muted)">🔗 Google Colab</span>
        </div>
      </a>

      <!-- C++ Challenges -->
      <div class="repo-card">
        <div class="repo-top">
          <span class="repo-icon">⚙️</span>
          <span class="repo-name">desafios-cpp</span>
        </div>
        <p class="repo-desc">
          Soluções de lógica de programação e algoritmos clássicos
          implementados em C++. Estruturas de dados, ordenação e
          problemas competitivos.
        </p>
        <div class="repo-footer">
          <span class="repo-lang"><span class="lang-dot cpp"></span>C++</span>
        </div>
      </div>

      <!-- DB Modeling -->
      <div class="repo-card">
        <div class="repo-top">
          <span class="repo-icon">🗄️</span>
          <span class="repo-name">modelagem-banco-de-dados</span>
        </div>
        <p class="repo-desc">
          Scripts SQL e diagramas de modelagem física/lógica de um sistema
          completo. Normalização, ERD e boas práticas de BD relacional.
        </p>
        <div class="repo-footer">
          <span class="repo-lang"><span class="lang-dot" style="background:#e38c00"></span>SQL</span>
        </div>
      </div>

      <!-- Power BI Dashboard -->
      <div class="repo-card">
        <div class="repo-top">
          <span class="repo-icon">📊</span>
          <span class="repo-name">dashboard-power-bi</span>
        </div>
        <p class="repo-desc">
          Painel de análise de dados construído no Power BI com KPIs,
          filtros dinâmicos e storytelling visual para tomada de decisão.
        </p>
        <div class="repo-footer">
          <span class="repo-lang"><span class="lang-dot" style="background:#f2c811"></span>Power BI</span>
        </div>
      </div>

    </div>
  </section>

  <!-- CONTRIBUTION HEATMAP (decorative) -->
  <section class="contrib-block">
    <div class="section-label">📅 Contribuições (preview)</div>
    <div class="contrib-grid" id="grid"></div>
    <p style="font-size:.65rem;color:var(--muted);margin-top:10px;">
      Menos &nbsp;
      <span style="display:inline-flex;gap:3px;vertical-align:middle">
        <span style="width:9px;height:9px;border-radius:2px;background:#161b22;display:inline-block"></span>
        <span style="width:9px;height:9px;border-radius:2px;background:#0e4429;display:inline-block"></span>
        <span style="width:9px;height:9px;border-radius:2px;background:#26a641;display:inline-block"></span>
        <span style="width:9px;height:9px;border-radius:2px;background:#39d353;display:inline-block"></span>
      </span>
      &nbsp; Mais
    </p>
  </section>

  <!-- FOOTER -->
  <div class="footer-strip">
    <span>⚡ made with curiosity &amp; caffeine</span>
    <span>
      <a href="mailto:luis@email.com">✉️ Contato</a> &nbsp;·&nbsp;
      <a href="https://linkedin.com" target="_blank">💼 LinkedIn</a>
    </span>
  </div>

</div>

<script>
  // Typing effect
  const phrases = [
    'print("Seja bem-vindo ao meu perfil!")',
    'df = pd.read_csv("meus_dados.csv")',
    '#include <iostream> // Olá, mundo!',
    'SELECT * FROM projetos WHERE status = "ativo";',
  ];
  let pi = 0, ci = 0, del = false;
  const el = document.getElementById('typing');
  function type() {
    const phrase = phrases[pi];
    if (!del) {
      el.textContent = phrase.slice(0, ++ci);
      if (ci === phrase.length) { del = true; setTimeout(type, 1800); return; }
    } else {
      el.textContent = phrase.slice(0, --ci);
      if (ci === 0) { del = false; pi = (pi + 1) % phrases.length; }
    }
    setTimeout(type, del ? 30 : 55);
  }
  type();

  // Contribution grid
  const levels = ['','l1','l2','l3','l4'];
  const grid = document.getElementById('grid');
  const COLS = 52, ROWS = 7;
  for (let c = 0; c < COLS; c++) {
    const col = document.createElement('div');
    col.className = 'contrib-col';
    for (let r = 0; r < ROWS; r++) {
      const cell = document.createElement('div');
      const rand = Math.random();
      const lv = rand < .55 ? '' : rand < .7 ? 'l1' : rand < .82 ? 'l2' : rand < .92 ? 'l3' : 'l4';
      cell.className = `contrib-cell ${lv}`;
      col.appendChild(cell);
    }
    grid.appendChild(col);
  }
</script>
</body>
</html>

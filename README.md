<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>UniPro – Uniformes Profissionais para Empresas</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Barlow:wght@300;400;500;600;700&family=Barlow+Condensed:wght@600;700&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --black: #0d0d0d;
    --blue: #1a6fd8;
    --blue-light: #3b9be8;
    --blue-dark: #0f4fa0;
    --cyan: #29c4e0;
    --cream: #f5f3ee;
    --white: #ffffff;
    --gray: #888;
  }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'Barlow', sans-serif;
    background: var(--black);
    color: var(--white);
    overflow-x: hidden;
  }

  /* ── NAV ── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 18px 6vw;
    background: rgba(13,13,13,0.85);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid rgba(255,255,255,0.06);
  }
  .nav-logo { display: flex; align-items: center; gap: 10px; text-decoration: none; }
  .nav-logo-text {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 2rem;
    letter-spacing: 2px;
    color: var(--white);
  }
  .nav-logo-text span { color: var(--blue-light); }
  nav ul { list-style: none; display: flex; gap: 36px; }
  nav ul a {
    text-decoration: none;
    color: rgba(255,255,255,0.7);
    font-size: .9rem;
    font-weight: 500;
    letter-spacing: .5px;
    text-transform: uppercase;
    transition: color .2s;
  }
  nav ul a:hover { color: var(--cyan); }
  .nav-cta {
    background: var(--blue);
    color: #fff !important;
    padding: 9px 22px;
    border-radius: 4px;
    transition: background .2s !important;
  }
  .nav-cta:hover { background: var(--blue-light) !important; color: #fff !important; }

  /* ── HERO ── */
  .hero {
    min-height: 100vh;
    display: flex; align-items: center;
    padding: 120px 6vw 80px;
    position: relative;
    overflow: hidden;
  }
  .hero-bg {
    position: absolute; inset: 0;
    background: linear-gradient(135deg, #0d0d0d 50%, #0a1a35 100%);
  }
  .hero-grid {
    position: absolute; inset: 0;
    background-image:
      linear-gradient(rgba(26,111,216,0.07) 1px, transparent 1px),
      linear-gradient(90deg, rgba(26,111,216,0.07) 1px, transparent 1px);
    background-size: 60px 60px;
  }
  .hero-shape {
    position: absolute;
    top: -120px; right: -120px;
    width: 600px; height: 600px;
    background: radial-gradient(circle, rgba(26,111,216,0.25) 0%, transparent 70%);
    border-radius: 50%;
    animation: pulse 6s ease-in-out infinite;
  }
  .hero-shape2 {
    position: absolute;
    bottom: -80px; left: 30%;
    width: 400px; height: 400px;
    background: radial-gradient(circle, rgba(41,196,224,0.1) 0%, transparent 70%);
    border-radius: 50%;
    animation: pulse 8s ease-in-out infinite reverse;
  }
  @keyframes pulse { 0%,100%{transform:scale(1);} 50%{transform:scale(1.08);} }

  .hero-content { position: relative; z-index: 2; max-width: 700px; }
  .hero-badge {
    display: inline-flex; align-items: center; gap: 8px;
    background: rgba(26,111,216,0.15);
    border: 1px solid rgba(26,111,216,0.4);
    border-radius: 100px;
    padding: 6px 16px;
    font-size: .75rem;
    text-transform: uppercase;
    letter-spacing: 2px;
    color: var(--cyan);
    margin-bottom: 28px;
    animation: fadeUp .6s ease both;
  }
  .hero-badge::before { content:''; width:6px; height:6px; border-radius:50%; background:var(--cyan); }

  .hero h1 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(3.5rem, 8vw, 7rem);
    line-height: .95;
    letter-spacing: 2px;
    animation: fadeUp .7s .1s ease both;
  }
  .hero h1 em { font-style: normal; color: var(--blue-light); }

  .hero p {
    margin-top: 24px;
    font-size: 1.1rem;
    font-weight: 300;
    color: rgba(255,255,255,0.7);
    line-height: 1.7;
    max-width: 520px;
    animation: fadeUp .7s .2s ease both;
  }

  .hero-actions {
    display: flex; gap: 16px; flex-wrap: wrap;
    margin-top: 40px;
    animation: fadeUp .7s .3s ease both;
  }
  .btn-primary {
    display: inline-flex; align-items: center; gap: 10px;
    background: var(--blue);
    color: #fff;
    padding: 16px 32px;
    border-radius: 6px;
    font-size: 1rem;
    font-weight: 600;
    text-decoration: none;
    letter-spacing: .5px;
    transition: background .2s, transform .2s;
  }
  .btn-primary:hover { background: var(--blue-light); transform: translateY(-2px); }
  .btn-outline {
    display: inline-flex; align-items: center; gap: 10px;
    border: 1px solid rgba(255,255,255,0.25);
    color: #fff;
    padding: 16px 32px;
    border-radius: 6px;
    font-size: 1rem;
    font-weight: 500;
    text-decoration: none;
    transition: border-color .2s, background .2s, transform .2s;
  }
  .btn-outline:hover { border-color: var(--cyan); background: rgba(41,196,224,0.07); transform: translateY(-2px); }

  .hero-stats {
    display: flex; gap: 40px; flex-wrap: wrap;
    margin-top: 60px;
    padding-top: 40px;
    border-top: 1px solid rgba(255,255,255,0.08);
    animation: fadeUp .7s .4s ease both;
  }
  .stat-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 2.4rem;
    color: var(--blue-light);
    line-height: 1;
  }
  .stat-label { font-size: .8rem; color: var(--gray); text-transform: uppercase; letter-spacing: 1px; margin-top: 4px; }

  @keyframes fadeUp { from{opacity:0;transform:translateY(30px);} to{opacity:1;transform:none;} }

  /* ── SOBRE ── */
  section { padding: 100px 6vw; }
  .section-label {
    display: inline-block;
    font-size: .72rem;
    text-transform: uppercase;
    letter-spacing: 3px;
    color: var(--cyan);
    margin-bottom: 16px;
  }
  h2 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(2.5rem, 5vw, 4rem);
    letter-spacing: 1px;
    line-height: 1;
  }
  h2 span { color: var(--blue-light); }

  .sobre { background: #111115; }
  .sobre-inner {
    display: grid; grid-template-columns: 1fr 1fr; gap: 80px; align-items: center;
  }
  .sobre-text p {
    margin-top: 20px;
    color: rgba(255,255,255,0.65);
    font-size: 1.05rem;
    line-height: 1.8;
  }
  .sobre-visual {
    position: relative;
    display: flex; align-items: center; justify-content: center;
  }
  .sobre-card {
    background: linear-gradient(135deg, #1a2540, #0d1628);
    border: 1px solid rgba(26,111,216,0.3);
    border-radius: 16px;
    padding: 40px;
    width: 100%;
    position: relative;
    overflow: hidden;
  }
  .sobre-card::before {
    content:'';
    position: absolute; top: -60px; right: -60px;
    width: 200px; height: 200px;
    background: radial-gradient(circle, rgba(26,111,216,0.3) 0%, transparent 70%);
    border-radius: 50%;
  }
  .sobre-card ul { list-style: none; display: flex; flex-direction: column; gap: 20px; }
  .sobre-card li {
    display: flex; align-items: flex-start; gap: 14px;
    font-size: 1rem; color: rgba(255,255,255,0.85); line-height: 1.5;
  }
  .icon-check {
    width: 24px; height: 24px; min-width: 24px;
    background: rgba(26,111,216,0.2);
    border: 1px solid var(--blue);
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-size: .75rem; color: var(--cyan); margin-top: 2px;
  }

  /* ── PRODUTOS ── */
  .produtos { background: var(--black); }
  .produtos-header { text-align: center; margin-bottom: 60px; }
  .produtos-header p { margin-top: 16px; color: var(--gray); font-size: 1rem; max-width: 500px; margin-inline: auto; }

  .cards-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 24px; }
  .card {
    background: #111115;
    border: 1px solid rgba(255,255,255,0.07);
    border-radius: 12px;
    padding: 36px 30px;
    transition: border-color .3s, transform .3s;
    position: relative; overflow: hidden;
  }
  .card::after {
    content:'';
    position:absolute; bottom:0; left:0; right:0; height:3px;
    background: linear-gradient(90deg, var(--blue), var(--cyan));
    transform: scaleX(0); transform-origin: left;
    transition: transform .3s;
  }
  .card:hover { border-color: rgba(26,111,216,0.5); transform: translateY(-6px); }
  .card:hover::after { transform: scaleX(1); }
  .card-icon {
    font-size: 2.2rem; margin-bottom: 20px;
    width: 60px; height: 60px;
    background: rgba(26,111,216,0.1);
    border-radius: 12px;
    display: flex; align-items: center; justify-content: center;
  }
  .card h3 {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 1.3rem; letter-spacing: .5px;
    margin-bottom: 10px;
  }
  .card p { color: rgba(255,255,255,0.6); font-size: .95rem; line-height: 1.65; }
  .card-tag {
    display: inline-block;
    margin-top: 16px;
    background: rgba(41,196,224,0.1);
    border: 1px solid rgba(41,196,224,0.3);
    color: var(--cyan);
    font-size: .72rem;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    padding: 4px 12px;
    border-radius: 100px;
  }

  /* ── PERSONALIZAÇÃO ── */
  .personalizacao { background: linear-gradient(135deg, #0a1428 0%, #0d0d0d 100%); }
  .pers-inner { display: grid; grid-template-columns: 1.2fr 1fr; gap: 80px; align-items: center; }
  .pers-text p { margin-top: 20px; color: rgba(255,255,255,0.65); font-size: 1.05rem; line-height: 1.8; }
  .pers-highlight {
    display: flex; align-items: center; gap: 20px;
    background: rgba(26,111,216,0.1);
    border: 1px solid rgba(26,111,216,0.3);
    border-radius: 12px;
    padding: 28px;
    margin-top: 32px;
  }
  .pers-highlight .big-icon { font-size: 3rem; }
  .pers-highlight h4 { font-size: 1.1rem; font-weight: 600; margin-bottom: 6px; }
  .pers-highlight p { margin: 0; font-size: .9rem; color: rgba(255,255,255,0.6); }

  .pers-visual {
    display: grid; grid-template-rows: repeat(3, auto); gap: 16px;
  }
  .pers-step {
    display: flex; align-items: center; gap: 20px;
    background: #111115;
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 10px;
    padding: 20px 24px;
    transition: border-color .2s;
  }
  .pers-step:hover { border-color: rgba(26,111,216,0.4); }
  .step-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 2rem; color: rgba(26,111,216,0.5);
    min-width: 40px;
  }
  .pers-step h4 { font-size: 1rem; font-weight: 600; margin-bottom: 4px; }
  .pers-step p { font-size: .875rem; color: var(--gray); margin: 0; }

  /* ── CTA ── */
  .cta-section {
    background: linear-gradient(135deg, var(--blue-dark), #0a3d7a);
    text-align: center;
    padding: 100px 6vw;
    position: relative; overflow: hidden;
  }
  .cta-section::before {
    content:'';
    position: absolute; inset: 0;
    background-image:
      linear-gradient(rgba(255,255,255,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(255,255,255,0.04) 1px, transparent 1px);
    background-size: 40px 40px;
  }
  .cta-section > * { position: relative; z-index: 1; }
  .cta-section h2 { font-size: clamp(2.5rem, 5vw, 4.5rem); margin-bottom: 20px; }
  .cta-section p { color: rgba(255,255,255,0.75); font-size: 1.1rem; max-width: 540px; margin: 0 auto 40px; line-height: 1.7; }
  .btn-white {
    display: inline-flex; align-items: center; gap: 12px;
    background: #fff;
    color: var(--blue-dark);
    padding: 18px 40px;
    border-radius: 6px;
    font-size: 1.05rem;
    font-weight: 700;
    text-decoration: none;
    letter-spacing: .3px;
    transition: transform .2s, box-shadow .2s;
  }
  .btn-white:hover { transform: translateY(-3px); box-shadow: 0 16px 40px rgba(0,0,0,0.3); }
  .whatsapp-icon { width: 24px; height: 24px; }

  /* ── FOOTER ── */
  footer {
    background: #060606;
    border-top: 1px solid rgba(255,255,255,0.06);
    padding: 50px 6vw 30px;
    display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap;
    gap: 20px;
  }
  .footer-logo {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.8rem; letter-spacing: 2px;
  }
  .footer-logo span { color: var(--blue-light); }
  footer p { color: var(--gray); font-size: .85rem; }

  /* ── RESPONSIVE ── */
  @media(max-width: 900px) {
    .sobre-inner, .pers-inner, .cards-grid { grid-template-columns: 1fr; }
    nav ul { display: none; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a class="nav-logo" href="#">
    <span class="nav-logo-text">Uni<span>Pro</span></span>
  </a>
  <ul>
    <li><a href="#sobre">Sobre</a></li>
    <li><a href="#produtos">Produtos</a></li>
    <li><a href="#personalizacao">Personalização</a></li>
    <li><a href="https://wa.me/5511978095516?text=Ol%C3%A1%2C%20vim%20pelo%20link%20da%20UniPro%20e%20gostaria%20de%20um%20or%C3%A7amento%20de%20uniformes%20para%20minha%20empresa" class="nav-cta" target="_blank">Solicitar Orçamento</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-bg"></div>
  <div class="hero-grid"></div>
  <div class="hero-shape"></div>
  <div class="hero-shape2"></div>
  <div class="hero-content">
    <div class="hero-badge">Uniformes B2B para empresas</div>
    <h1>Sua equipe,<br><em>sua identidade.</em></h1>
    <p>A UniPro transforma o visual da sua empresa com uniformes personalizados que unem profissionalismo, conforto e excelente custo-benefício.</p>
    <div class="hero-actions">
      <a href="https://wa.me/5511978095516?text=Ol%C3%A1%2C%20vim%20pelo%20link%20da%20UniPro%20e%20gostaria%20de%20um%20or%C3%A7amento%20de%20uniformes%20para%20minha%20empresa" class="btn-primary" target="_blank">
        <svg class="whatsapp-icon" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347z"/><path d="M12 0C5.373 0 0 5.373 0 12c0 2.124.558 4.122 1.529 5.856L.057 23.43a.75.75 0 0 0 .922.944l5.713-1.493A11.957 11.957 0 0 0 12 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 22a9.958 9.958 0 0 1-5.187-1.448l-.372-.22-3.392.887.902-3.286-.241-.381A9.95 9.95 0 0 1 2 12C2 6.477 6.477 2 12 2s10 4.477 10 10-4.477 10-10 10z"/></svg>
        Solicitar Orçamento
      </a>
      <a href="#sobre" class="btn-outline">Conheça a UniPro</a>
    </div>
    <div class="hero-stats">
      <div>
        <div class="stat-num">3+</div>
        <div class="stat-label">Tipos de Tecido</div>
      </div>
      <div>
        <div class="stat-num">DTF</div>
        <div class="stat-label">Estamparia Premium</div>
      </div>
      <div>
        <div class="stat-num">B2B</div>
        <div class="stat-label">Foco em Empresas</div>
      </div>
    </div>
  </div>
</section>

<!-- SOBRE -->
<section id="sobre" class="sobre">
  <div class="sobre-inner">
    <div class="sobre-text">
      <span class="section-label">Quem somos</span>
      <h2>Especialistas em <span>uniformes</span> corporativos</h2>
      <p>A UniPro é especializada na produção de camisetas e uniformes personalizados para empresas, oferecendo soluções que unem profissionalismo, conforto e excelente custo-benefício.</p>
      <p>Entendemos que cada empresa tem uma identidade única. Por isso, trabalhamos com diferentes materiais e técnicas para entregar uniformes que realmente representam a sua marca.</p>
    </div>
    <div class="sobre-visual">
      <div class="sobre-card">
        <ul>
          <li>
            <div class="icon-check">✓</div>
            <span>Produção dedicada para empresas de todos os portes</span>
          </li>
          <li>
            <div class="icon-check">✓</div>
            <span>Variedade de tecidos para cada necessidade de equipe</span>
          </li>
          <li>
            <div class="icon-check">✓</div>
            <span>Personalização profissional com estamparia DTF</span>
          </li>
          <li>
            <div class="icon-check">✓</div>
            <span>Atendimento B2B com foco em custo-benefício</span>
          </li>
          <li>
            <div class="icon-check">✓</div>
            <span>Solução completa: do pedido à entrega</span>
          </li>
        </ul>
      </div>
    </div>
  </div>
</section>

<!-- PRODUTOS -->
<section id="produtos" class="produtos">
  <div class="produtos-header">
    <span class="section-label">Nossos produtos</span>
    <h2>Tecidos para <span>cada equipe</span></h2>
    <p>Trabalhamos com diferentes tipos de tecido para atender a necessidade de cada empresa.</p>
  </div>
  <div class="cards-grid">
    <div class="card">
      <div class="card-icon">👕</div>
      <h3>100% Algodão</h3>
      <p>Conforto e qualidade para uso diário. O clássico que nunca falha, com toque macio e ótima respirabilidade para equipes que trabalham em ambientes internos.</p>
      <span class="card-tag">Conforto diário</span>
    </div>
    <div class="card">
      <div class="card-icon">🔵</div>
      <h3>Poliéster</h3>
      <p>Maior durabilidade e ótimo custo-benefício. Ideal para equipes que precisam de uniformes resistentes ao uso intenso e lavagens frequentes.</p>
      <span class="card-tag">Alta durabilidade</span>
    </div>
    <div class="card">
      <div class="card-icon">⚡</div>
      <h3>Dri-Fit</h3>
      <p>Tecido leve e respirável, ideal para equipes em movimento ou ambientes quentes. Tecnologia que mantém o corpo seco e confortável durante toda a jornada.</p>
      <span class="card-tag">Alto desempenho</span>
    </div>
  </div>
</section>

<!-- PERSONALIZAÇÃO -->
<section id="personalizacao" class="personalizacao">
  <div class="pers-inner">
    <div class="pers-text">
      <span class="section-label">Personalização</span>
      <h2>Sua marca em cada <span>detalhe</span></h2>
      <p>Oferecemos personalização profissional para garantir que a identidade visual da sua empresa esteja presente em cada peça entregue aos colaboradores.</p>
      <div class="pers-highlight">
        <div class="big-icon">🎨</div>
        <div>
          <h4>Estamparia DTF</h4>
          <p>Tecnologia Direct to Film para impressões vibrantes, detalhadas e duráveis. Perfeita para logotipos complexos e cores vivas.</p>
        </div>
      </div>
    </div>
    <div class="pers-visual">
      <div class="pers-step">
        <div class="step-num">01</div>
        <div>
          <h4>Envie seu logo ou arte</h4>
          <p>Compartilhe o arquivo da sua identidade visual pelo WhatsApp.</p>
        </div>
      </div>
      <div class="pers-step">
        <div class="step-num">02</div>
        <div>
          <h4>Escolha o tecido e modelo</h4>
          <p>Algodão, Poliéster ou Dri-Fit — indicamos o melhor para sua equipe.</p>
        </div>
      </div>
      <div class="pers-step">
        <div class="step-num">03</div>
        <div>
          <h4>Receba o orçamento</h4>
          <p>Proposta rápida, clara e sem surpresas, com prazo de produção.</p>
        </div>
      </div>
      <div class="pers-step">
        <div class="step-num">04</div>
        <div>
          <h4>Produção e entrega</h4>
          <p>Cuidamos de tudo até os uniformes chegarem na sua empresa.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CTA -->
<section class="cta-section">
  <span class="section-label" style="display:block; margin-bottom: 12px;">Pronto para começar?</span>
  <h2>Solicite seu orçamento <br>agora mesmo</h2>
  <p>Atendemos empresas de todos os tamanhos. Entre em contato pelo WhatsApp e receba uma proposta personalizada para a sua equipe.</p>
  <a href="https://wa.me/5511978095516?text=Ol%C3%A1%2C%20vim%20pelo%20link%20da%20UniPro%20e%20gostaria%20de%20um%20or%C3%A7amento%20de%20uniformes%20para%20minha%20empresa" class="btn-white" target="_blank">
    <svg class="whatsapp-icon" viewBox="0 0 24 24" fill="#25D366"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347z"/><path d="M12 0C5.373 0 0 5.373 0 12c0 2.124.558 4.122 1.529 5.856L.057 23.43a.75.75 0 0 0 .922.944l5.713-1.493A11.957 11.957 0 0 0 12 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 22a9.958 9.958 0 0 1-5.187-1.448l-.372-.22-3.392.887.902-3.286-.241-.381A9.95 9.95 0 0 1 2 12C2 6.477 6.477 2 12 2s10 4.477 10 10-4.477 10-10 10z"/></svg>
    Falar no WhatsApp
  </a>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">Uni<span>Pro</span></div>
  <p>Uniformes Profissionais para Empresas</p>
  <p style="color:#444;">© 2025 UniPro. Todos os direitos reservados.<br>CNPJ: 65.161.783/0001-30 · SP – Zona Norte</p>
</footer>

</body>
</html>

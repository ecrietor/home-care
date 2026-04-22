<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Home Care — Serviços Domésticos e para Empresas</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;0,700;1,300;1,400&family=Jost:wght@300;400;500;600&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

   :root {
      /* PALETA DE CORES (Preto e Laranja da sua imagem) */
      --white:       #FFFFFF;
      --bg-light:    #F4F7F9; 
      --bg-mid:      #E1E8ED; 
      --border-color:#CFD9E0; 
      
      /* Textos a Preto */
      --text-dark:   #000000; /* Preto absoluto para os textos gerais */
      --text-mid:    #1A1A1A; /* Quase preto para suavizar subtítulos */
      
      /* Laranja da Paleta */
      --brand-primary: #000000; /* Laranja vibrante principal da sua imagem */
      --brand-hover:   #EB9337; /* Laranja mais escuro para quando passar o rato por cima */
      --brand-accent:  #e8a726; /* Laranja muito claro para fundos de destaque */
      
      --radius:      12px;
      --transition:  0.35s cubic-bezier(0.25, 0.46, 0.45, 0.94);
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'Jost', sans-serif;
      background: var(--white);
      color: var(--text-dark);
      overflow-x: hidden;
      line-height: 1.6;
    }

    /* ─── HEADER ─────────────────────────────── */
    header {
      position: fixed; top: 0; left: 0; right: 0; z-index: 100;
      display: flex; align-items: center; justify-content: space-between;
      padding: 0 5%;
      height: 72px;
      background: rgba(255,255,255,0.92);
      backdrop-filter: blur(14px);
      border-bottom: 1px solid var(--bg-mid);
      transition: box-shadow var(--transition);
    }
    header.scrolled { box-shadow: 0 4px 24px rgba(10, 74, 130, 0.08); }

    .logo {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.65rem;
      font-weight: 600;
      color: var(--brand-primary);
      letter-spacing: 0.04em;
      text-decoration: none;
    }
    .logo span { color: var(--brand-accent); }

    nav { display: flex; align-items: center; gap: 2.4rem; }
    nav a {
      font-size: 0.82rem; font-weight: 500; letter-spacing: 0.06em;
      text-transform: uppercase; color: var(--text-mid);
      text-decoration: none; position: relative; transition: color var(--transition);
    }
    nav a::after {
      content: ''; position: absolute; bottom: -3px; left: 0;
      width: 0; height: 1.5px; background: var(--brand-accent); transition: width var(--transition);
    }
    nav a:hover { color: var(--brand-primary); }
    nav a:hover::after { width: 100%; }

    .btn-nav {
      background: var(--brand-primary); color: var(--white) !important;
      padding: 0.5rem 1.5rem; border-radius: 6px; font-size: 0.82rem !important;
      letter-spacing: 0.08em; transition: background var(--transition), transform 0.2s !important;
      text-decoration: none;
    }
    .btn-nav::after { display: none !important; }
    .btn-nav:hover { background: var(--brand-hover) !important; transform: translateY(-1px); }

    .hamburger {
      display: none; flex-direction: column; gap: 5px; cursor: pointer;
      background: none; border: none; padding: 4px;
    }
    .hamburger span {
      display: block; width: 22px; height: 2px;
      background: var(--brand-primary); border-radius: 2px; transition: var(--transition);
    }

    /* ─── HERO E BUSCA DUPLA ───────────────────────────────── */
    .hero {
      min-height: 100vh; padding: 120px 5% 80px; display: grid;
      grid-template-columns: 1fr 1fr; gap: 4rem; align-items: center;
      background: var(--white); position: relative; overflow: hidden;
    }
    .hero::before {
      content: ''; position: absolute; top: -60px; right: -80px;
      width: 520px; height: 520px; background: radial-gradient(circle, var(--bg-light) 0%, transparent 70%);
      z-index: 0; animation: pulse-bg 8s ease-in-out infinite;
    }
    @keyframes pulse-bg { 0%, 100% { transform: scale(1); opacity: 0.8; } 50% { transform: scale(1.1); opacity: 1; } }

    .hero-text { position: relative; z-index: 1; }
    .hero-badge {
      display: inline-flex; align-items: center; gap: 6px;
      background: var(--bg-light); border: 1px solid var(--border-color);
      color: var(--text-mid); font-size: 0.73rem; font-weight: 500;
      letter-spacing: 0.1em; text-transform: uppercase; padding: 6px 14px;
      border-radius: 100px; margin-bottom: 1.5rem; animation: fadeUp 0.7s ease both;
    }
    .hero-badge::before { content: ''; width: 6px; height: 6px; background: var(--brand-accent); border-radius: 50%; }

    .hero h1 {
      font-family: 'Cormorant Garamond', serif; font-size: clamp(2.4rem, 5vw, 3.8rem);
      font-weight: 600; line-height: 1.18; color: var(--brand-primary); margin-bottom: 1.2rem;
      animation: fadeUp 0.7s 0.15s ease both;
    }
    .hero h1 em { font-style: italic; color: var(--brand-accent); }
    .hero p {
      font-size: 1.05rem; font-weight: 300; color: var(--text-mid);
      max-width: 440px; margin-bottom: 2.5rem; animation: fadeUp 0.7s 0.3s ease both;
    }

    .search-bar {
      display: flex; align-items: center; background: var(--white);
      border: 2px solid var(--border-color); border-radius: 12px; padding: 6px;
      box-shadow: 0 4px 20px rgba(10, 74, 130, 0.07); transition: border-color var(--transition), box-shadow var(--transition);
      animation: fadeUp 0.7s 0.45s ease both; width: 100%; max-width: 600px;
    }
    .search-bar:focus-within { border-color: var(--brand-accent); box-shadow: 0 4px 24px rgba(0, 168, 232, 0.18); }
    .search-field { display: flex; align-items: center; gap: 8px; flex: 1; padding: 0 12px; }
    .search-field svg { color: var(--border-color); flex-shrink: 0; }
    
    .location-select {
      width: 100%; border: none; outline: none; font-family: 'Jost', sans-serif; font-size: 0.95rem;
      color: var(--text-dark); background: transparent; cursor: pointer;
      -webkit-appearance: none; -moz-appearance: none; appearance: none;
      background-image: url("data:image/svg+xml;charset=UTF-8,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='none' stroke='%23CFD9E0' stroke-width='2' stroke-linecap='round' stroke-linejoin='round'%3e%3cpolyline points='6 9 12 15 18 9'%3e%3c/polyline%3e%3c/svg%3e");
      background-repeat: no-repeat; background-position: right center; background-size: 16px; padding-right: 20px;
    }
    .location-select:invalid { color: var(--border-color); }
    .search-field input { width: 100%; border: none; outline: none; font-family: 'Jost', sans-serif; font-size: 0.95rem; color: var(--text-dark); background: transparent; }
    .search-field input::placeholder { color: var(--border-color); }
    .search-divider { width: 1px; height: 24px; background-color: var(--bg-mid); margin: 0 4px; }
    
    .btn-search {
      background: var(--brand-primary); color: var(--white); border: none; cursor: pointer;
      padding: 0.85rem 1.8rem; border-radius: 8px; font-family: 'Jost', sans-serif; font-size: 0.9rem;
      font-weight: 500; letter-spacing: 0.06em; transition: background var(--transition), transform 0.2s; white-space: nowrap;
    }
    .btn-search:hover { background: var(--brand-hover); transform: translateY(-1px); }

    .hero-tags { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 1.2rem; animation: fadeUp 0.7s 0.6s ease both; }
    .hero-tags span {
      font-size: 0.75rem; color: var(--text-mid); background: var(--bg-light); border: 1px solid var(--bg-mid);
      padding: 4px 12px; border-radius: 100px; cursor: pointer; transition: background var(--transition), color var(--transition);
    }
    .hero-tags span:hover { background: var(--bg-mid); color: var(--brand-primary); }

    .hero-image { position: relative; z-index: 1; animation: fadeIn 1s 0.3s ease both; }
    .hero-image-frame {
      position: relative; border-radius: 20px; overflow: hidden; background: var(--bg-light);
      aspect-ratio: 4/4.5; box-shadow: 0 24px 64px rgba(10, 74, 130, 0.14);
    }
    .hero-image-frame img { width: 100%; height: 100%; object-fit: cover; display: block; }
    .hero-illustration {
      width: 100%; height: 100%; display: flex; align-items: center; justify-content: center;
      flex-direction: column; background: linear-gradient(145deg, var(--bg-light) 0%, var(--bg-mid) 100%);
    }
    .hero-illustration svg { opacity: 0.6; color: var(--brand-primary); }
    .hero-illustration p { font-family: 'Cormorant Garamond', serif; font-size: 1rem; color: var(--brand-primary); margin-top: 1rem; letter-spacing: 0.05em; font-weight: 600;}

    .hero-float-card {
      position: absolute; bottom: 32px; left: -28px; background: var(--white); border-radius: var(--radius);
      padding: 14px 18px; box-shadow: 0 8px 32px rgba(10, 74, 130, 0.12); display: flex; align-items: center; gap: 12px;
      min-width: 200px; animation: float 6s ease-in-out infinite;
    }
    .hero-float-card2 {
      position: absolute; top: 36px; right: -20px; background: var(--brand-primary); border-radius: var(--radius);
      padding: 14px 18px; box-shadow: 0 8px 32px rgba(10, 74, 130, 0.25); color: var(--white);
      min-width: 160px; animation: float 6s 3s ease-in-out infinite;
    }
    @keyframes float { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-8px); } }
    .card-icon-wrap { width: 38px; height: 38px; background: var(--bg-light); border-radius: 8px; display: flex; align-items: center; justify-content: center; flex-shrink: 0; }
    .hero-float-card .card-label { font-size: 0.72rem; color: var(--text-mid); }
    .hero-float-card .card-value { font-size: 0.92rem; font-weight: 600; color: var(--brand-primary); }
    .hero-float-card2 .card-label { font-size: 0.72rem; color: rgba(255,255,255,0.7); margin-bottom: 2px; }
    .hero-float-card2 .card-stars { color: #FFD700; font-size: 0.8rem; letter-spacing: 2px; }
    .hero-float-card2 .card-rating { font-size: 1.1rem; font-weight: 600; }

    /* ─── CATEGORIES, HOW IT WORKS & STATS ─────────────────────────── */
    .categories, .how-it-works, .testimonials, .signature-section { padding: 96px 5%; background: var(--white); }
    .categories { background: var(--bg-light); }
    .section-header { text-align: center; margin-bottom: 3.5rem; }
    .section-label {
      display: inline-block; font-size: 0.72rem; font-weight: 600; letter-spacing: 0.14em;
      text-transform: uppercase; color: var(--brand-accent); margin-bottom: 0.8rem;
    }
    .section-title { font-family: 'Cormorant Garamond', serif; font-size: clamp(1.9rem, 3.5vw, 2.8rem); font-weight: 600; color: var(--brand-primary); line-height: 1.2; }
    .section-sub { font-size: 0.95rem; color: var(--text-mid); font-weight: 400; margin-top: 0.6rem; }

    .categories-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 1.5rem; }
    .cat-card {
      background: var(--white); border: 1px solid var(--border-color); border-radius: 16px; padding: 2.2rem 1.8rem;
      cursor: pointer; transition: transform var(--transition), box-shadow var(--transition), border-color var(--transition);
      position: relative; overflow: hidden;
    }
    .cat-card::before {
      content: ''; position: absolute; bottom: 0; left: 0; right: 0; height: 3px;
      background: linear-gradient(90deg, var(--brand-accent), var(--brand-primary)); transform: scaleX(0);
      transform-origin: left; transition: transform var(--transition);
    }
    .cat-card:hover { transform: translateY(-6px); box-shadow: 0 16px 40px rgba(10, 74, 130, 0.1); border-color: var(--border-color); }
    .cat-card:hover::before { transform: scaleX(1); }
    .cat-icon {
      width: 56px; height: 56px; background: var(--bg-light); border-radius: 14px;
      display: flex; align-items: center; justify-content: center; margin-bottom: 1.4rem; transition: background var(--transition);
    }
    .cat-card:hover .cat-icon { background: var(--bg-mid); }
    .cat-icon svg { color: var(--brand-primary); }
    .cat-card h3 { font-family: 'Cormorant Garamond', serif; font-size: 1.2rem; font-weight: 600; color: var(--text-dark); margin-bottom: 0.5rem; }
    .cat-card p { font-size: 0.82rem; color: var(--text-mid); font-weight: 400; line-height: 1.55; }
    .cat-count { display: inline-block; margin-top: 1.2rem; font-size: 0.72rem; font-weight: 600; letter-spacing: 0.06em; color: var(--brand-accent); }

    .steps-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 2rem; margin-top: 3.5rem; position: relative; }
    .steps-grid::before {
      content: ''; position: absolute; top: 52px; left: 16.5%; right: 16.5%; height: 1px;
      background: linear-gradient(90deg, transparent, var(--border-color), var(--border-color), transparent);
    }
    .step { text-align: center; padding: 2.4rem 2rem; background: var(--bg-light); border-radius: 16px; border: 1px solid var(--border-color); transition: transform var(--transition), box-shadow var(--transition); }
    .step:hover { transform: translateY(-4px); box-shadow: 0 12px 32px rgba(10, 74, 130, 0.07); }
    .step-num { font-family: 'Cormorant Garamond', serif; font-size: 4.5rem; font-weight: 300; color: var(--bg-mid); line-height: 1; margin-bottom: 0.8rem; transition: color var(--transition); }
    .step:hover .step-num { color: var(--brand-accent); }
    .step-icon { width: 52px; height: 52px; background: var(--white); border: 1.5px solid var(--border-color); border-radius: 50%; display: flex; align-items: center; justify-content: center; margin: 0 auto 1.2rem; }
    .step h3 { font-family: 'Cormorant Garamond', serif; font-size: 1.25rem; font-weight: 600; color: var(--brand-primary); margin-bottom: 0.6rem; }
    .step p { font-size: 0.85rem; color: var(--text-mid); font-weight: 400; }

    /* ─── FORMULÁRIO DE ORÇAMENTO DETALHADO ──────────────────── */
    .quote-section { padding: 80px 5%; background: var(--bg-mid); }
    .quote-container {
      max-width: 800px; margin: 0 auto; background: var(--white); border-radius: 20px;
      padding: 3rem; box-shadow: 0 16px 48px rgba(10, 74, 130, 0.08); border: 1px solid var(--border-color);
    }
    .quote-container .section-header { margin-bottom: 2rem; }
    .quote-form { display: flex; flex-direction: column; gap: 1.5rem; }
    .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; }
    .form-group { display: flex; flex-direction: column; gap: 6px; }
    .form-group label { font-size: 0.85rem; font-weight: 500; color: var(--brand-primary); }
    .form-control {
      width: 100%; padding: 0.9rem 1rem; border: 1.5px solid var(--border-color); border-radius: 8px;
      font-family: 'Jost', sans-serif; font-size: 0.95rem; color: var(--text-dark); background: var(--bg-light);
      transition: border-color var(--transition), box-shadow var(--transition);
    }
    .form-control:focus { outline: none; border-color: var(--brand-accent); background: var(--white); box-shadow: 0 0 0 3px rgba(0, 168, 232, 0.15); }
    .file-drop-area {
      border: 2px dashed var(--border-color); border-radius: 8px; padding: 2rem; text-align: center;
      background: var(--bg-light); cursor: pointer; transition: background var(--transition), border-color var(--transition);
      display: flex; flex-direction: column; align-items: center; gap: 8px;
    }
    .file-drop-area:hover, .file-drop-area.dragover { background: var(--white); border-color: var(--brand-accent); }
    .file-drop-area svg { color: var(--brand-accent); margin-bottom: 4px; }
    .file-drop-area span { font-size: 0.85rem; color: var(--text-mid); }
    .file-drop-area input[type="file"] { display: none; }
    textarea.form-control { resize: vertical; min-height: 120px; }
    .btn-submit {
      background: var(--brand-primary); color: var(--white); border: none; padding: 1rem; border-radius: 8px;
      font-family: 'Jost', sans-serif; font-size: 1rem; font-weight: 500; letter-spacing: 0.05em;
      cursor: pointer; transition: background var(--transition), transform 0.2s; margin-top: 0.5rem;
    }
    .btn-submit:hover { background: var(--brand-hover); transform: translateY(-2px); }

    /* ─── NOVA SEÇÃO: APROVAÇÃO & ASSINATURAS (ATUALIZADA) ───────────────── */
    .signature-section { background: var(--bg-light); padding-top: 80px; padding-bottom: 100px; }
    .plans-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 1.5rem; margin-bottom: 4rem; }
    
    .plan-card {
      background: var(--white); border: 2px solid var(--border-color); border-radius: 16px;
      padding: 2.5rem 1.5rem 2rem; position: relative; transition: all var(--transition); cursor: pointer;
      display: flex; flex-direction: column;
    }
    .plan-card:hover, .plan-card.active {
      border-color: var(--brand-primary); box-shadow: 0 16px 32px rgba(10, 74, 130, 0.12);
      transform: translateY(-4px);
    }
    
    /* Destaque Plano B */
    .plan-card.popular {
      border-color: var(--brand-accent); box-shadow: 0 8px 24px rgba(0, 168, 232, 0.12);
    }
    .plan-card.popular:hover, .plan-card.popular.active {
      box-shadow: 0 16px 32px rgba(0, 168, 232, 0.2);
    }

    .plan-badge {
      position: absolute; top: -14px; left: 50%; transform: translateX(-50%);
      background: var(--brand-accent); color: var(--white); font-size: 0.75rem; font-weight: 600;
      padding: 6px 16px; border-radius: 100px; white-space: nowrap; letter-spacing: 0.05em; text-transform: uppercase;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
    }
    .plan-badge.premium { background: var(--brand-primary); }

    .plan-card h3 { font-size: 1.2rem; color: var(--text-dark); margin-bottom: 0.5rem; font-weight: 600; text-align: center; }
    .plan-card .price { font-family: 'Cormorant Garamond', serif; font-size: 2.5rem; font-weight: 700; color: var(--brand-primary); text-align: center; line-height: 1; margin-bottom: 1rem; }
    .plan-card .price span { font-size: 1.1rem; color: var(--text-mid); font-weight: 400; font-family: 'Jost', sans-serif;}
    
    .plan-desc { font-size: 0.85rem; color: var(--text-mid); text-align: center; margin-bottom: 1.5rem; line-height: 1.5; padding-bottom: 1.5rem; border-bottom: 1px solid var(--bg-mid); flex-shrink: 0; }
    
    .plan-features { list-style: none; padding: 0; margin: 0; flex-grow: 1; display: flex; flex-direction: column; gap: 0.8rem; }
    .plan-features li { font-size: 0.85rem; color: var(--text-dark); display: flex; align-items: flex-start; gap: 8px; line-height: 1.4; }
    .plan-features li svg { color: var(--brand-accent); flex-shrink: 0; margin-top: 2px; width: 16px; height: 16px; }
    .plan-card.popular .plan-features li svg { color: var(--brand-primary); }

    .signature-blocks { display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; max-width: 800px; margin: 0 auto; }
    .sig-box { text-align: center; }
    .sig-line { width: 100%; height: 2px; background: var(--text-dark); margin-bottom: 1rem; margin-top: 3rem; }
    .sig-box p { font-size: 1rem; font-weight: 600; color: var(--text-dark); text-transform: uppercase; letter-spacing: 0.05em;}
    .sig-box span { font-size: 0.85rem; color: var(--text-mid); }


    /* ─── TESTIMONIALS ───────────────────────── */
    .testimonials-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem; margin-top: 3.5rem; }
    .testi-card { background: var(--white); border-radius: 16px; padding: 2rem; border: 1px solid var(--border-color); transition: transform var(--transition), box-shadow var(--transition); position: relative; }
    .testi-card:hover { transform: translateY(-4px); box-shadow: 0 12px 32px rgba(10, 74, 130, 0.09); }
    .testi-card::before { content: '\201C'; position: absolute; top: 18px; right: 24px; font-family: 'Cormorant Garamond', serif; font-size: 4rem; font-weight: 700; color: var(--bg-mid); line-height: 1; }
    .stars { color: #FFD700; font-size: 0.85rem; letter-spacing: 2px; margin-bottom: 1rem; }
    .testi-text { font-size: 0.9rem; color: var(--text-mid); font-weight: 400; line-height: 1.65; margin-bottom: 1.5rem; font-style: italic; }
    .testi-author { display: flex; align-items: center; gap: 12px; border-top: 1px solid var(--bg-light); padding-top: 1rem; }
    .author-avatar { width: 40px; height: 40px; border-radius: 50%; background: var(--bg-mid); display: flex; align-items: center; justify-content: center; font-family: 'Cormorant Garamond', serif; font-size: 1.1rem; font-weight: 600; color: var(--brand-primary); flex-shrink: 0; }
    .author-name { font-size: 0.88rem; font-weight: 500; color: var(--text-dark); }
    .author-role { font-size: 0.75rem; color: var(--text-mid); }

    /* ─── MURAL DE SERVIÇOS (FREELANCER) ──────────────────── */
    .job-board { padding: 96px 5%; background: var(--bg-light); }
    .job-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 1.5rem; margin-top: 2.5rem; }
    .job-card {
      background: var(--white); border: 1px solid var(--border-color); border-radius: 16px; padding: 1.8rem;
      position: relative; transition: transform var(--transition), box-shadow var(--transition);
      display: flex; flex-direction: column; justify-content: space-between;
    }
    .job-card:hover { transform: translateY(-4px); box-shadow: 0 12px 32px rgba(10, 74, 130, 0.08); border-color: var(--brand-accent); }
    .job-badge {
      position: absolute; top: 1.5rem; right: 1.5rem; background: var(--bg-light); color: var(--brand-accent);
      font-size: 0.7rem; font-weight: 600; letter-spacing: 0.1em; text-transform: uppercase; padding: 4px 10px;
      border-radius: 100px; border: 1px solid var(--border-color);
    }
    .job-card h3 { font-family: 'Cormorant Garamond', serif; font-size: 1.4rem; font-weight: 600; color: var(--brand-primary); margin-bottom: 0.5rem; padding-right: 50px; }
    .job-info { display: flex; flex-direction: column; gap: 8px; margin-bottom: 1.5rem; }
    .job-info span { font-size: 0.85rem; color: var(--text-mid); display: flex; align-items: center; gap: 6px; }
    .job-price { font-size: 1.25rem; font-weight: 600; color: var(--brand-primary); margin-bottom: 1rem; }
    .btn-grab {
      width: 100%; background: var(--white); color: var(--brand-primary); border: 2px solid var(--brand-primary);
      padding: 0.8rem; border-radius: 8px; font-family: 'Jost', sans-serif; font-weight: 500; cursor: pointer; transition: all var(--transition);
    }
    .btn-grab:hover { background: var(--brand-primary); color: var(--white); }

    /* ─── STATS BAR ──────────────────────────── */
    .stats-bar { padding: 60px 5%; background: var(--white); display: grid; grid-template-columns: repeat(4, 1fr); gap: 2rem; border-top: 1px solid var(--border-color); border-bottom: 1px solid var(--border-color); }
    .stat-item { text-align: center; }
    .stat-num { font-family: 'Cormorant Garamond', serif; font-size: 2.8rem; font-weight: 600; color: var(--brand-primary); line-height: 1; }
    .stat-num span { color: var(--brand-accent); }
    .stat-label { font-size: 0.8rem; color: var(--text-mid); font-weight: 400; margin-top: 0.4rem; letter-spacing: 0.04em; }

    /* ─── CTA PROFESSIONALS ──────────────────── */
    .cta-section { padding: 96px 5%; background: var(--brand-primary); position: relative; overflow: hidden; text-align: center; }
    .cta-section::before { content: ''; position: absolute; inset: 0; background: radial-gradient(ellipse at 30% 50%, rgba(0, 168, 232, 0.15) 0%, transparent 60%), radial-gradient(ellipse at 70% 50%, rgba(255,255,255,0.05) 0%, transparent 60%); }
    .cta-section::after { content: 'Home Care'; position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); font-family: 'Cormorant Garamond', serif; font-size: 18rem; font-weight: 700; color: rgba(255,255,255,0.03); white-space: nowrap; pointer-events: none; letter-spacing: -0.02em; }
    .cta-content { position: relative; z-index: 1; max-width: 600px; margin: 0 auto; }
    .cta-badge { display: inline-block; border: 1px solid rgba(0, 168, 232, 0.4); color: var(--brand-accent); font-size: 0.72rem; letter-spacing: 0.12em; text-transform: uppercase; padding: 6px 14px; border-radius: 100px; margin-bottom: 1.5rem; }
    .cta-section h2 { font-family: 'Cormorant Garamond', serif; font-size: clamp(2rem, 4vw, 3rem); font-weight: 600; color: var(--white); line-height: 1.2; margin-bottom: 1rem; }
    .cta-section p { font-size: 0.95rem; color: rgba(255,255,255,0.75); font-weight: 300; margin-bottom: 2.5rem; }
    .btn-cta-white { background: var(--white); color: var(--brand-primary); border: none; cursor: pointer; padding: 0.95rem 2.4rem; border-radius: 8px; font-family: 'Jost', sans-serif; font-size: 0.85rem; font-weight: 500; letter-spacing: 0.08em; transition: transform var(--transition), box-shadow var(--transition); display: inline-flex; align-items: center; gap: 8px; }
    .btn-cta-white:hover { transform: translateY(-2px); box-shadow: 0 8px 28px rgba(0,0,0,0.25); }
    .cta-perks { display: flex; justify-content: center; flex-wrap: wrap; gap: 1.5rem; margin-top: 2.5rem; }
    .perk { display: flex; align-items: center; gap: 8px; color: rgba(255,255,255,0.65); font-size: 0.8rem; }
    .perk svg { color: var(--brand-accent); flex-shrink: 0; }

    /* ─── FOOTER ─────────────────────────────── */
    footer { background: #041B33; padding: 72px 5% 36px; color: rgba(255,255,255,0.6); }
    .footer-grid { display: grid; grid-template-columns: 2fr 1fr 1fr 1fr; gap: 3rem; margin-bottom: 3rem; padding-bottom: 3rem; border-bottom: 1px solid rgba(255,255,255,0.1); }
    .footer-brand .logo { color: var(--white); }
    .footer-brand p { margin-top: 1rem; font-size: 0.85rem; line-height: 1.7; color: rgba(255,255,255,0.5); max-width: 260px; }
    .social-links { display: flex; gap: 10px; margin-top: 1.4rem; }
    .social-link { width: 36px; height: 36px; border: 1px solid rgba(255,255,255,0.15); border-radius: 8px; display: flex; align-items: center; justify-content: center; color: rgba(255,255,255,0.5); cursor: pointer; transition: border-color var(--transition), color var(--transition); }
    .social-link:hover { border-color: var(--brand-accent); color: var(--brand-accent); }
    .footer-col h4 { font-size: 0.75rem; font-weight: 500; letter-spacing: 0.1em; text-transform: uppercase; color: rgba(255,255,255,0.8); margin-bottom: 1.2rem; }
    .footer-col ul { list-style: none; }
    .footer-col ul li { margin-bottom: 0.6rem; }
    .footer-col ul li a { font-size: 0.85rem; color: rgba(255,255,255,0.5); text-decoration: none; transition: color var(--transition); }
    .footer-col ul li a:hover { color: var(--brand-accent); }
    .footer-bottom { display: flex; align-items: center; justify-content: space-between; font-size: 0.78rem; }
    .footer-bottom a { color: var(--brand-accent); text-decoration: none; }

    /* ─── ANIMATIONS ─────────────────────────── */
    @keyframes fadeUp { from { opacity: 0; transform: translateY(24px); } to { opacity: 1; transform: translateY(0); } }
    @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
    .reveal { opacity: 0; transform: translateY(32px); transition: opacity 0.7s ease, transform 0.7s ease; }
    .reveal.visible { opacity: 1; transform: translateY(0); }
    .reveal-delay-1 { transition-delay: 0.1s; }
    .reveal-delay-2 { transition-delay: 0.2s; }
    .reveal-delay-3 { transition-delay: 0.3s; }

    /* ─── MOBILE NAV E RESPONSIVIDADE ─────────────────────────── */
    .mobile-nav {
      display: none; position: fixed; top: 72px; left: 0; right: 0; background: var(--white);
      border-bottom: 1px solid var(--border-color); padding: 1.5rem 5%; flex-direction: column; gap: 1rem;
      z-index: 99; box-shadow: 0 8px 24px rgba(10, 74, 130, 0.08);
    }
    .mobile-nav.open { display: flex; }
    .mobile-nav a {
      font-size: 0.9rem; font-weight: 500; color: var(--text-mid); text-decoration: none;
      padding: 0.5rem 0; border-bottom: 1px solid var(--bg-light); transition: color var(--transition);
    }
    .mobile-nav a:hover { color: var(--brand-primary); }
    .mobile-nav .btn-nav { text-align: center; padding: 0.75rem; border-radius: 8px; border: none; background: var(--brand-primary); color: var(--white) !important; }

    @media (max-width: 1024px) {
      .categories-grid, .plans-grid { grid-template-columns: repeat(2, 1fr); }
      .testimonials-grid { grid-template-columns: repeat(2, 1fr); }
      .footer-grid { grid-template-columns: 1fr 1fr; }
    }

    @media (max-width: 768px) {
      nav { display: none; }
      .hamburger { display: flex; }
      .hero { grid-template-columns: 1fr; padding-top: 100px; text-align: center; }
      .hero p { max-width: 100%; }
      .hero-image { order: -1; max-width: 80%; margin: 0 auto; }
      .hero-float-card, .hero-float-card2 { display: none; }
      .hero::before { width: 300px; height: 300px; }
      
      .search-bar { flex-direction: column; padding: 12px; border-radius: 16px; gap: 12px; }
      .search-divider { width: 100%; height: 1px; margin: 4px 0; }
      .search-field { width: 100%; padding: 8px 4px; }
      .btn-search { width: 100%; padding: 1rem; }

      .form-row, .signature-blocks { grid-template-columns: 1fr; gap: 1rem; }
      .quote-container { padding: 2rem 1.5rem; }

      .categories-grid, .plans-grid { grid-template-columns: repeat(2, 1fr); }
      .steps-grid { grid-template-columns: 1fr; }
      .steps-grid::before { display: none; }
      .testimonials-grid { grid-template-columns: 1fr; }
      .stats-bar { grid-template-columns: repeat(2, 1fr); }
      .footer-grid { grid-template-columns: 1fr; gap: 2rem; }
      .footer-bottom { flex-direction: column; gap: 0.5rem; text-align: center; }
    }

    @media (max-width: 480px) {
      .categories-grid, .plans-grid { grid-template-columns: 1fr; }
      .stats-bar { grid-template-columns: 1fr 1fr; }
    }
  </style>
</head>
<body>

<header id="header">
  <a href="#" class="logo">Home<span>Care</span></a>
  <nav>
    <a href="#how">Como Funciona</a>
    <a href="#categories">Categorias</a>
    <a href="#orcamento">Orçamento</a>
    <a href="#assinaturas">Contrato</a>
    <a href="#mural">Mural de Vagas</a>
    <a href="login.html" class="btn-nav">Entrar</a>
  </nav>
  <button class="hamburger" id="hamburger" aria-label="Menu">
    <span></span><span></span><span></span>
  </button>
</header>

<div class="mobile-nav" id="mobileNav">
  <a href="#how">Como Funciona</a>
  <a href="#categories">Categorias</a>
  <a href="#orcamento">Orçamento</a>
  <a href="#assinaturas">Contrato de Serviço</a>
  <a href="#mural">Mural de Vagas</a>
  <a href="login.html" class="btn-nav">Entrar</a>
</div>

<section class="hero">
  <div class="hero-text">
    <div class="hero-badge">Marketplace de Serviços #1 no Brasil</div>
    <h1>Sua casa ou empresa <em>impecável</em>, sem esforço.</h1>
    <p>Encontre montadores, eletricistas e encanadores de confiança em minutos. Profissionais verificados, orçamentos transparentes.</p>

    <div class="search-bar">
      <div class="search-field location-field">
        <svg width="18" height="18" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
          <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"></path>
          <circle cx="12" cy="10" r="3"></circle>
        </svg>
        <select class="location-select" id="campoLocal" aria-label="Escolha sua localização" required>
          <option value="" disabled selected>Onde você está?</option>
          <option value="São Paulo">São Paulo, SP</option>
          <option value="Rio de Janeiro">Rio de Janeiro, RJ</option>
          <option value="Belo Horizonte">Belo Horizonte, MG</option>
          <option value="Brasília">Brasília, DF</option>
        </select>
      </div>
      
      <div class="search-divider"></div>
      
      <div class="search-field service-field">
        <svg width="18" height="18" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
          <circle cx="11" cy="11" r="8"/><path d="m21 21-4.35-4.35"/>
        </svg>
        <input type="text" id="campoServico" placeholder="Qual conserto você precisa?" />
      </div>
      
      <button class="btn-search" onclick="simularBusca()">Buscar</button>
    </div>

    <div class="hero-tags">
      <span>🔧 Montagem de Móveis</span>
      <span>⚡ Elétrica</span>
      <span>🔩 Encanamento</span>
      <span>🏢 Escritórios</span>
    </div>
  </div>

  <div class="hero-image">
    <div class="hero-image-frame">
      <div class="hero-illustration">
        <svg width="120" height="120" fill="none" viewBox="0 0 120 120">
          <rect x="20" y="60" width="80" height="48" rx="4" fill="currentColor" opacity="0.15"/>
          <rect x="35" y="40" width="50" height="25" rx="3" fill="currentColor" opacity="0.12"/>
          <circle cx="60" cy="28" r="14" fill="currentColor" opacity="0.18"/>
          <rect x="48" y="68" width="10" height="20" rx="2" fill="currentColor" opacity="0.2"/>
          <rect x="62" y="68" width="10" height="20" rx="2" fill="currentColor" opacity="0.2"/>
          <rect x="15" y="75" width="90" height="4" rx="2" fill="var(--brand-accent)" opacity="0.5"/>
          <rect x="68" y="50" width="22" height="16" rx="3" fill="var(--brand-accent)" opacity="0.6"/>
          <rect x="72" y="46" width="14" height="6" rx="2" fill="var(--brand-accent)" opacity="0.4"/>
          <line x1="68" y1="58" x2="90" y2="58" stroke="currentColor" stroke-width="1.5" opacity="0.3"/>
        </svg>
        <p>Profissional verificado</p>
      </div>
    </div>

    <div class="hero-float-card">
      <div class="card-icon-wrap">
        <svg width="20" height="20" fill="none" stroke="currentColor" stroke-width="1.8" viewBox="0 0 24 24"><path d="M22 11.08V12a10 10 0 1 1-5.93-9.14"/><polyline points="22 4 12 14.01 9 11.01"/></svg>
      </div>
      <div>
        <div class="card-label">Serviços concluídos</div>
        <div class="card-value">+12.400 hoje</div>
      </div>
    </div>

    <div class="hero-float-card2">
      <div class="card-label">Avaliação média</div>
      <div class="card-stars">★★★★★</div>
      <div class="card-rating">4.9 / 5.0</div>
    </div>
  </div>
</section>

<div class="stats-bar">
  <div class="stat-item reveal">
    <div class="stat-num">50<span>k+</span></div>
    <div class="stat-label">Profissionais ativos</div>
  </div>
  <div class="stat-item reveal reveal-delay-1">
    <div class="stat-num">98<span>%</span></div>
    <div class="stat-label">Índice de satisfação</div>
  </div>
  <div class="stat-item reveal reveal-delay-2">
    <div class="stat-num">200<span>k+</span></div>
    <div class="stat-label">Serviços realizados</div>
  </div>
  <div class="stat-item reveal reveal-delay-3">
    <div class="stat-num">48<span>h</span></div>
    <div class="stat-label">Atendimento garantido</div>
  </div>
</div>

<section class="categories" id="categories">
  <div class="section-header reveal">
    <div class="section-label">Nossos Serviços</div>
    <h2 class="section-title">Categorias Populares</h2>
    <p class="section-sub">Do reparo emergencial à montagem completa, temos o profissional certo para você.</p>
  </div>

  <div class="categories-grid">
    <div class="cat-card reveal">
      <div class="cat-icon"><svg width="26" height="26" fill="none" stroke="currentColor" stroke-width="1.8" viewBox="0 0 24 24"><rect x="2" y="3" width="7" height="7" rx="1"/><rect x="15" y="3" width="7" height="7" rx="1"/><rect x="2" y="14" width="7" height="7" rx="1"/><rect x="15" y="14" width="7" height="7" rx="1"/></svg></div>
      <h3>Montagem de Móveis</h3>
      <p>Montagem de racks, guarda-roupas, camas e qualquer mobiliário das principais marcas.</p>
      <span class="cat-count">→ 3.200 profissionais</span>
    </div>

    <div class="cat-card reveal reveal-delay-1">
      <div class="cat-icon"><svg width="26" height="26" fill="none" stroke="currentColor" stroke-width="1.8" viewBox="0 0 24 24"><path d="M14.7 6.3a1 1 0 0 0 0 1.4l1.6 1.6a1 1 0 0 0 1.4 0l3.77-3.77a6 6 0 0 1-7.94 7.94l-6.91 6.91a2.12 2.12 0 0 1-3-3l6.91-6.91a6 6 0 0 1 7.94-7.94l-3.76 3.76z"/></svg></div>
      <h3>Pequenos Reparos</h3>
      <p>Instalação de prateleiras, fixação de quadros, reparos em portas e janelas.</p>
      <span class="cat-count">→ 5.800 profissionais</span>
    </div>

    <div class="cat-card reveal reveal-delay-2">
      <div class="cat-icon"><svg width="26" height="26" fill="none" stroke="currentColor" stroke-width="1.8" viewBox="0 0 24 24"><path d="M13 2 3 14h9l-1 8 10-12h-9l1-8z"/></svg></div>
      <h3>Elétrica &amp; Hidráulica</h3>
      <p>Instalações elétricas, substituição de tomadas, reparos em encanamentos e vazamentos.</p>
      <span class="cat-count">→ 4.100 profissionais</span>
    </div>

    <div class="cat-card reveal reveal-delay-3">
      <div class="cat-icon"><svg width="26" height="26" fill="none" stroke="currentColor" stroke-width="1.8" viewBox="0 0 24 24"><rect x="2" y="3" width="20" height="14" rx="2"/><path d="M8 21h8m-4-4v4"/></svg></div>
      <h3>Soluções para Escritórios</h3>
      <p>Montagem de estações de trabalho, organização de cabeamento e setup completo de ambientes corporativos.</p>
      <span class="cat-count">→ 1.900 profissionais</span>
    </div>
  </div>
</section>

<section class="how-it-works" id="how">
  <div class="section-header reveal">
    <div class="section-label">Processo Simples</div>
    <h2 class="section-title">Como Funciona</h2>
    <p class="section-sub">Em três passos, seu serviço está agendado e garantido.</p>
  </div>

  <div class="steps-grid">
    <div class="step reveal">
      <div class="step-num">01</div>
      <div class="step-icon"><svg width="22" height="22" fill="none" stroke="var(--brand-primary)" stroke-width="1.8" viewBox="0 0 24 24"><path d="M11 4H4a2 2 0 0 0-2 2v14a2 2 0 0 0 2 2h14a2 2 0 0 0 2-2v-7"/><path d="M18.5 2.5a2.121 2.121 0 0 1 3 3L12 15l-4 1 1-4 9.5-9.5z"/></svg></div>
      <h3>Faça o Pedido</h3>
      <p>Descreva o que precisa, informe sua localização e escolha a melhor data para o atendimento.</p>
    </div>

    <div class="step reveal reveal-delay-1">
      <div class="step-num">02</div>
      <div class="step-icon"><svg width="22" height="22" fill="none" stroke="var(--brand-primary)" stroke-width="1.8" viewBox="0 0 24 24"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/></svg></div>
      <h3>Receba Orçamentos</h3>
      <p>Profissionais verificados enviam propostas em minutos. Compare preços e avaliações.</p>
    </div>

    <div class="step reveal reveal-delay-2">
      <div class="step-num">03</div>
      <div class="step-icon"><svg width="22" height="22" fill="none" stroke="var(--brand-primary)" stroke-width="1.8" viewBox="0 0 24 24"><path d="M22 11.08V12a10 10 0 1 1-5.93-9.14"/><polyline points="22 4 12 14.01 9 11.01"/></svg></div>
      <h3>Serviço com Garantia</h3>
      <p>O serviço é realizado e você paga somente após aprovar. Garantia de 30 dias em todos os serviços.</p>
    </div>
  </div>
</section>

<section class="quote-section" id="orcamento">
  <div class="quote-container reveal">
    <div class="section-header">
      <div class="section-label">Projetos Complexos</div>
      <h2 class="section-title">Solicite um Orçamento Detalhado</h2>
      <p class="section-sub">Vai reformar, pintar ou precisa de um projeto sob medida para empresa? Envie a planta e receba propostas precisas.</p>
    </div>
    
    <form class="quote-form" onsubmit="enviarOrcamento(event)">
      <div class="form-row">
        <div class="form-group">
          <label for="tipoImovel">Tipo de Imóvel</label>
          <select id="tipoImovel" class="form-control" required>
            <option value="" disabled selected>Selecione uma opção</option>
            <option value="casa">Casa Residencial</option>
            <option value="apartamento">Apartamento</option>
            <option value="sala_comercial">Sala Comercial</option>
            <option value="galpao">Galpão / Empresa</option>
          </select>
        </div>
        <div class="form-group">
          <label for="tamanhoImovel">Metragem do Local</label>
          <input type="number" id="tamanhoImovel" class="form-control" placeholder="Área aprox. em m²" required min="1">
        </div>
      </div>

      <div class="form-group">
        <label>Planta ou Fotos do Ambiente</label>
        <div class="file-drop-area" id="fileDropArea">
          <svg width="32" height="32" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"/><polyline points="17 8 12 3 7 8"/><line x1="12" y1="3" x2="12" y2="15"/></svg>
          <span id="fileMsg">Arraste a planta/fotos aqui ou <strong>clique para anexar</strong> (PDF, JPG, PNG)</span>
          <input type="file" id="fileInput" accept=".pdf, .jpg, .jpeg, .png" multiple>
        </div>
      </div>

      <div class="form-group">
        <label for="descProjeto">O que você deseja fazer?</label>
        <textarea id="descProjeto" class="form-control" placeholder="Descreva em detalhes o seu projeto, materiais necessários ou o problema que precisa ser resolvido..." required></textarea>
      </div>

      <button type="submit" class="btn-submit">Solicitar Orçamento Grátis</button>
    </form>
  </div>
</section>

<section class="signature-section" id="assinaturas">
  <div class="section-header reveal">
    <div class="section-label">Aprovação Final</div>
    <h2 class="section-title">Categorias de Assinatura do Cliente</h2>
    <p class="section-sub">Selecione a categoria acordada para finalização e aceite dos termos.</p>
  </div>

  <div class="plans-grid reveal">
    <div class="plan-card" onclick="selectPlan(this)">
      <div class="plan-badge premium">⭐ Melhor Experiência</div>
      <h3>A - Premium</h3>
      <div class="price"><span>R$</span> 810<span>,00</span></div>
      <p class="plan-desc">Para quem quer máximo conforto, prioridade e zero dor de cabeça.</p>
      <ul class="plan-features">
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Atendimento prioritário (fila VIP)</li>
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Profissionais top avaliados</li>
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Agendamento em até 2h (urgência incluída)</li>
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Suporte dedicado 24/7</li>
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Garantia estendida de 60 dias</li>
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Até 3 revisitas gratuitas por serviço</li>
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Orçamentos ilimitados e instantâneos</li>
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Desconto exclusivo em serviços recorrentes</li>
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Acompanhamento completo (status + suporte ativo)</li>
      </ul>
    </div>
    
    <div class="plan-card popular" onclick="selectPlan(this)">
      <div class="plan-badge">🔥 Mais Popular</div>
      <h3>B - Excelente</h3>
      <div class="price"><span>R$</span> 405<span>,00</span></div>
      <p class="plan-desc">Equilíbrio perfeito entre qualidade premium e excelente custo-benefício.</p>
      <ul class="plan-features">
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Prioridade alta no atendimento</li>
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Profissionais bem avaliados e verificados</li>
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Agendamento rápido (até 12h)</li>
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Garantia de 45 dias</li>
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Até 2 revisitas gratuitas</li>
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Comparação de múltiplos orçamentos</li>
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Suporte ágil durante o serviço</li>
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Descontos em serviços selecionados</li>
      </ul>
    </div>

    <div class="plan-card" onclick="selectPlan(this)">
      <h3>C - Conforto</h3>
      <div class="price"><span>R$</span> 270<span>,00</span></div>
      <p class="plan-desc">Ideal para quem quer praticidade com muita economia.</p>
      <ul class="plan-features">
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Profissionais verificados</li>
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Agendamento em até 24h</li>
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Garantia de 30 dias</li>
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> 1 revisita gratuita</li>
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Até 3 orçamentos por pedido</li>
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Suporte padrão</li>
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Processo simples e rápido</li>
      </ul>
    </div>

    <div class="plan-card" onclick="selectPlan(this)">
      <h3>D - Básico</h3>
      <div class="price"><span>R$</span> 180<span>,00</span></div>
      <p class="plan-desc">A solução acessível perfeita para demandas rápidas e simples.</p>
      <ul class="plan-features">
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Acesso à plataforma de profissionais</li>
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Agendamento conforme disponibilidade</li>
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Garantia padrão de 7 dias</li>
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> 1 orçamento por pedido</li>
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Suporte básico</li>
        <li><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg> Pagamento seguro após aprovação</li>
      </ul>
    </div>
  </div>

  <div class="signature-blocks reveal reveal-delay-1">
    <div class="sig-box">
      <div class="sig-line"></div>
      <p>Assinatura do Trabalhador</p>
      <span>(Profissional Parceiro)</span>
    </div>
    <div class="sig-box">
      <div class="sig-line"></div>
      <p>Assinatura do Cliente</p>
      <span>(Contratante do Serviço)</span>
    </div>
  </div>
</section>

<section class="testimonials">
  <div class="section-header reveal">
    <div class="section-label">Depoimentos</div>
    <h2 class="section-title">O que nossos clientes dizem</h2>
    <p class="section-sub">Mais de 200 mil avaliações verificadas na plataforma.</p>
  </div>

  <div class="testimonials-grid">
    <div class="testi-card reveal">
      <div class="stars">★★★★★</div>
      <p class="testi-text">Contratei um montador para meu guarda-roupa novo e foi perfeito. Em menos de 2 horas estava tudo pronto e organizado. Com certeza vou usar novamente.</p>
      <div class="testi-author">
        <div class="author-avatar">M</div>
        <div><div class="author-name">Mariana Costa</div><div class="author-role">São Paulo, SP</div></div>
      </div>
    </div>

    <div class="testi-card reveal reveal-delay-1">
      <div class="stars">★★★★★</div>
      <p class="testi-text">Resolvi um vazamento urgente num domingo à noite. Em 40 minutos o encanador já estava na minha casa. Serviço impecável e preço justo.</p>
      <div class="testi-author">
        <div class="author-avatar">R</div>
        <div><div class="author-name">Ricardo Almeida</div><div class="author-role">Rio de Janeiro, RJ</div></div>
      </div>
    </div>

    <div class="testi-card reveal reveal-delay-2">
      <div class="stars">★★★★★</div>
      <p class="testi-text">Reformamos o escritório inteiro com profissionais do HomeCare. Montagem, cabeamento e instalações elétricas — tudo coordenado pela plataforma. Incrível!</p>
      <div class="testi-author">
        <div class="author-avatar">A</div>
        <div><div class="author-name">Ana Ferreira</div><div class="author-role">Diretora — TechFlow Ltda.</div></div>
      </div>
    </div>
  </div>
</section>

<section class="job-board" id="mural">
  <div class="section-header reveal">
    <div class="section-label">Mural de Oportunidades</div>
    <h2 class="section-title">Serviços Disponíveis Agora</h2>
    <p class="section-sub">Assine o plano Pro e tenha acesso imediato a clientes esperando por você.</p>
  </div>

  <div class="job-grid">
    <div class="job-card reveal">
      <div class="job-badge">Novo</div>
      <h3>Montagem de Guarda-Roupa Casal</h3>
      <div class="job-info">
        <span>📍 Pinheiros, São Paulo - SP</span>
        <span>📅 Para amanhã de manhã</span>
      </div>
      <div class="job-price">R$ 150,00</div>
      <button class="btn-grab" onclick="alert('Área Exclusiva: Assine o plano Pro de R$ 70/mês para pegar este serviço!')">Pegar Serviço</button>
    </div>

    <div class="job-card reveal reveal-delay-1">
      <div class="job-badge" style="color:#d9534f; border-color:#d9534f; background:#fdf0f0;">Urgente</div>
      <h3>Instalação de Chuveiro Elétrico</h3>
      <div class="job-info">
        <span>📍 Copacabana, Rio de Janeiro - RJ</span>
        <span>📅 Hoje, o mais rápido possível</span>
      </div>
      <div class="job-price">R$ 90,00</div>
      <button class="btn-grab" onclick="alert('Área Exclusiva: Assine o plano Pro de R$ 70/mês para pegar este serviço!')">Pegar Serviço</button>
    </div>

    <div class="job-card reveal reveal-delay-2">
      <div class="job-badge">Agendado</div>
      <h3>Instalação de 2 Prateleiras</h3>
      <div class="job-info">
        <span>📍 Savassi, Belo Horizonte - MG</span>
        <span>📅 Sábado à tarde</span>
      </div>
      <div class="job-price">R$ 120,00</div>
      <button class="btn-grab" onclick="alert('Área Exclusiva: Assine o plano Pro de R$ 70/mês para pegar este serviço!')">Pegar Serviço</button>
    </div>
  </div>
</section>

<section class="cta-section" id="professional">
  <div class="cta-content reveal">
    <div class="cta-badge">Para Profissionais</div>
    <h2>Seja Dono do Seu Lucro</h2>
    <p>Por apenas <strong>R$ 70,00 mensais</strong>, você tem acesso ilimitado ao nosso mural. Pegue quantos freelas quiser e fique com <strong>100% do valor do serviço</strong>. Sem taxas escondidas, sem comissão.</p>
    
    <a href="https://wa.me/5511999999999?text=Olá!%20Quero%20assinar%20o%20plano%20Pro%20de%20R$%2070%20para%20ter%20acesso%20ao%20mural%20de%20serviços." target="_blank" class="btn-cta-white" style="text-decoration: none;">
      <svg width="16" height="16" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
        <path d="M16 21v-2a4 4 0 0 0-4-4H6a4 4 0 0 0-4 4v2"/><circle cx="9" cy="7" r="4"/><line x1="19" y1="8" x2="19" y2="14"/><line x1="22" y1="11" x2="16" y2="11"/>
      </svg>
      Assinar e Acessar o Mural
    </a>

    <div class="cta-perks">
      <div class="perk"><svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><polyline points="20 6 9 17 4 12"/></svg>0% de Comissão</div>
      <div class="perk"><svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><polyline points="20 6 9 17 4 12"/></svg>Lucro todo seu</div>
      <div class="perk"><svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><polyline points="20 6 9 17 4 12"/></svg>Cancele quando quiser</div>
    </div>
  </div>
</section>

<footer>
  <div class="footer-grid">
    <div class="footer-brand">
      <a href="#" class="logo">Home<span style="color:var(--brand-accent)">Care</span></a>
      <p>Conectando clientes a profissionais de confiança para tornar sua casa ou empresa impecável.</p>
      <div class="social-links">
        <div class="social-link" title="Instagram"><svg width="16" height="16" fill="none" stroke="currentColor" stroke-width="1.8" viewBox="0 0 24 24"><rect x="2" y="2" width="20" height="20" rx="5" ry="5"/><circle cx="12" cy="12" r="4"/><circle cx="17.5" cy="6.5" r="1" fill="currentColor"/></svg></div>
        <div class="social-link" title="Facebook"><svg width="16" height="16" fill="none" stroke="currentColor" stroke-width="1.8" viewBox="0 0 24 24"><path d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z"/></svg></div>
        <div class="social-link" title="LinkedIn"><svg width="16" height="16" fill="none" stroke="currentColor" stroke-width="1.8" viewBox="0 0 24 24"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg></div>
        <div class="social-link" title="WhatsApp"><svg width="16" height="16" fill="none" stroke="currentColor" stroke-width="1.8" viewBox="0 0 24 24"><path d="M21 11.5a8.38 8.38 0 0 1-.9 3.8 8.5 8.5 0 0 1-7.6 4.7 8.38 8.38 0 0 1-3.8-.9L3 21l1.9-5.7a8.38 8.38 0 0 1-.9-3.8 8.5 8.5 0 0 1 4.7-7.6 8.38 8.38 0 0 1 3.8-.9h.5a8.48 8.48 0 0 1 8 8v.5z"/></svg></div>
      </div>
    </div>

    <div class="footer-col">
      <h4>Serviços</h4>
      <ul>
        <li><a href="#categories">Montagem de Móveis</a></li>
        <li><a href="#categories">Pequenos Reparos</a></li>
        <li><a href="#categories">Elétrica &amp; Hidráulica</a></li>
        <li><a href="#categories">Escritórios</a></li>
      </ul>
    </div>

    <div class="footer-col">
      <h4>Empresa</h4>
      <ul>
        <li><a href="#">Sobre nós</a></li>
        <li><a href="#how">Como Funciona</a></li>
        <li><a href="#professional">Seja um Profissional</a></li>
      </ul>
    </div>

    <div class="footer-col">
      <h4>Suporte</h4>
      <ul>
        <li><a href="#">Central de Ajuda</a></li>
        <li><a href="#">Privacidade</a></li>
        <li><a href="#">Termos de Uso</a></li>
        <li><a href="#">Contato</a></li>
      </ul>
    </div>
  </div>

  <div class="footer-bottom">
    <span>© 2025 HomeCare. Todos os direitos reservados.</span>
    <span>Feito com ♥ para conectar pessoas</span>
  </div>
</footer>

<script>
  // Efeito de rolagem do Cabeçalho
  const header = document.getElementById('header');
  window.addEventListener('scroll', () => {
    header.classList.toggle('scrolled', window.scrollY > 20);
  });

  // Menu Mobile
  const hamburger = document.getElementById('hamburger');
  const mobileNav = document.getElementById('mobileNav');
  hamburger.addEventListener('click', () => {
    mobileNav.classList.toggle('open');
  });
  mobileNav.querySelectorAll('a').forEach(a => {
    a.addEventListener('click', () => mobileNav.classList.remove('open'));
  });

  // Efeito Reveal ao rolar a página
  const revealEls = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) { e.target.classList.add('visible'); }
    });
  }, { threshold: 0.12 });
  revealEls.forEach(el => observer.observe(el));

  // --- FUNÇÕES INTERATIVAS ---

  // Seleção de Planos/Categorias de Assinatura
  function selectPlan(card) {
    document.querySelectorAll('.plan-card').forEach(el => el.classList.remove('active'));
    card.classList.add('active');
  }

  // Simulação de Busca na Hero Section
  function simularBusca() {
    const local = document.getElementById('campoLocal').value;
    const servico = document.getElementById('campoServico').value;
    
    if(!local && !servico) {
      alert("Por favor, digite o que precisa e escolha sua localização!");
    } else if (!local) {
      alert(`Buscando profissionais para: ${servico}...\n(Dica: Selecione a localização para resultados mais precisos!)`);
    } else if (!servico) {
      alert(`Buscando todos os profissionais em: ${local}...`);
    } else {
      alert(`Buscando os melhores profissionais de '${servico}' na região de '${local}'...`);
    }
  }

  // Comportamento do Formulário de Orçamento (Área de Upload)
  const dropArea = document.getElementById('fileDropArea');
  const fileInput = document.getElementById('fileInput');
  const fileMsg = document.getElementById('fileMsg');

  dropArea.addEventListener('click', () => fileInput.click());

  dropArea.addEventListener('dragover', (e) => {
    e.preventDefault();
    dropArea.classList.add('dragover');
  });
  dropArea.addEventListener('dragleave', () => {
    dropArea.classList.remove('dragover');
  });
  dropArea.addEventListener('drop', (e) => {
    e.preventDefault();
    dropArea.classList.remove('dragover');
    const files = e.dataTransfer.files;
    if(files.length > 0) {
      fileInput.files = files;
      fileMsg.innerHTML = `<strong>${files.length} arquivo(s) selecionado(s)</strong>`;
    }
  });

  fileInput.addEventListener('change', function() {
    if(this.files.length > 0) {
      fileMsg.innerHTML = `<strong>${this.files.length} arquivo(s) anexado(s)</strong>`;
    }
  });

  // Simulação de Envio do Orçamento COM VALIDAÇÃO SEGURA
  function enviarOrcamento(event) {
    event.preventDefault(); 
    
    const selectImovel = document.getElementById('tipoImovel');
    
    if (selectImovel.selectedIndex <= 0) {
      alert("Por favor, selecione o tipo de imóvel.");
      return;
    }
    
    const tipo = selectImovel.options[selectImovel.selectedIndex].text;
    const tamanho = document.getElementById('tamanhoImovel').value;
    
    alert(`Sucesso! Seu pedido de orçamento para o/a ${tipo} (${tamanho}m²) foi recebido.\n\nNossos profissionais analisarão a descrição e os anexos, e você receberá as propostas em breve.`);
    
    event.target.reset();
    fileMsg.innerHTML = `Arraste a planta/fotos aqui ou <strong>clique para anexar</strong> (PDF, JPG, PNG)`;
  }
</script>
</body>
</html>

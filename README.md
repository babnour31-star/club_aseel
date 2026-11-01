
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CLUB_ASEEL — Studio créatif</title>
  <meta name="description" content="CLUB_ASEEL, studio créatif : montage vidéo, design graphique, animation, création de contenu et gestion des réseaux sociaux.">
  <link rel="icon" href="logo.png">

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Instrument+Serif:ital@0;1&display=swap" rel="stylesheet">
  <link href="https://fonts.googleapis.com/css2?family=Cascadia+Code:wght@400;500&display=swap" rel="stylesheet">

  <script>document.documentElement.classList.add('js');</script>

  <style>
    /* ───────── Palette CLUB_ASEEL ───────── */
    :root{
      --noir:   #000000;
      --nuit:   #1d2f33;
      --ardoise:#608793;
      --ciel:   #cdf2fe;
      --blanc:  #ffffff;

      --texte:  #1d2f33;
      --doux:   #5d7076;
      --ligne:  rgba(29,47,51,.10);
      --fond-2: #f6fbfd;

      --sans:  "Inter", system-ui, -apple-system, sans-serif;
      --serif: "Instrument Serif", Georgia, serif;
      --mono:  "Cascadia Mono", "Cascadia Code", ui-monospace, "SF Mono", Menlo, monospace;

      --max: 1120px;
      --ease: cubic-bezier(.22,1,.36,1);
    }

    *,*::before,*::after{ box-sizing:border-box; margin:0; padding:0; }
    html{ scroll-behavior:smooth; scroll-padding-top:110px; }
    body{
      font-family:var(--sans);
      color:var(--texte);
      background:var(--blanc);
      line-height:1.6;
      font-size:16px;
      -webkit-font-smoothing:antialiased;
      overflow-x:hidden;
    }
    a{ color:inherit; text-decoration:none; }
    img{ display:block; max-width:100%; }

    .wrap{ width:100%; max-width:var(--max); margin:0 auto; padding:0 24px; }
    section{ padding:140px 0; }

    /* ───────── Éléments typographiques ───────── */
    .label{
      font-family:var(--mono);
      font-size:12px;
      letter-spacing:.08em;
      text-transform:uppercase;
      color:var(--ardoise);
      display:inline-flex; align-items:center; gap:10px;
    }
    .label::before{
      content:""; width:6px; height:6px; border-radius:50%;
      background:var(--ardoise);
    }
    .titre{
      font-size:clamp(34px, 5vw, 56px);
      font-weight:500;
      letter-spacing:-.035em;
      line-height:1.08;
      margin-top:20px;
    }
    .titre em, .hero h1 em{
      font-family:var(--serif);
      font-style:italic;
      font-weight:400;
      letter-spacing:-.01em;
      color:var(--ardoise);
    }
    .chapo{ color:var(--doux); font-size:18px; max-width:560px; margin-top:20px; }
    .center{ text-align:center; }
    .center .chapo{ margin-left:auto; margin-right:auto; }

    /* ───────── Boutons ───────── */
    .btn{
      display:inline-flex; align-items:center; gap:10px;
      padding:14px 26px; border-radius:999px;
      font-size:15px; font-weight:500;
      transition:transform .4s var(--ease), background .3s, color .3s, box-shadow .4s var(--ease);
    }
    .btn-dark{ background:var(--nuit); color:var(--blanc); }
    .btn-dark:hover{ background:var(--noir); transform:translateY(-2px); box-shadow:0 12px 30px -10px rgba(29,47,51,.5); }
    .btn-ghost{ border:1px solid var(--ligne); color:var(--nuit); background:var(--blanc); }
    .btn-ghost:hover{ border-color:var(--ardoise); transform:translateY(-2px); }
    .btn .fleche{ transition:transform .4s var(--ease); }
    .btn:hover .fleche{ transform:translateX(4px); }

    /* ───────── Navigation ───────── */
    .nav{
      position:fixed; top:18px; left:50%; transform:translateX(-50%);
      z-index:50;
      width:calc(100% - 32px); max-width:var(--max);
      display:flex; align-items:center; justify-content:space-between;
      padding:10px 10px 10px 14px;
      background:rgba(255,255,255,.72);
      backdrop-filter:blur(16px) saturate(1.4);
      -webkit-backdrop-filter:blur(16px) saturate(1.4);
      border:1px solid var(--ligne);
      border-radius:999px;
      transition:box-shadow .4s var(--ease);
    }
    .nav.scrolled{ box-shadow:0 10px 40px -18px rgba(29,47,51,.35); }
    .nav-logo{ display:flex; align-items:center; gap:10px; font-weight:600; font-size:15px; letter-spacing:-.01em; }
    .nav-logo img{ width:36px; height:36px; }
    .nav-links{ display:flex; gap:4px; }
    .nav-links a{
      font-size:14px; color:var(--doux);
      padding:8px 14px; border-radius:999px;
      transition:background .3s, color .3s;
    }
    .nav-links a:hover{ background:var(--fond-2); color:var(--nuit); }
    .nav .btn{ padding:10px 20px; font-size:14px; }

    /* ───────── Hero ───────── */
    .hero{
      position:relative;
      min-height:100vh;
      display:flex; align-items:center;
      padding:170px 0 120px;
    }
    .anneaux{
      position:absolute; inset:0; pointer-events:none; overflow:hidden;
      display:grid; place-items:center;
    }
    .anneaux span{
      position:absolute; border-radius:50%;
      border:1px solid rgba(96,135,147,.14);
      animation:respire 9s ease-in-out infinite;
    }
    .anneaux span:nth-child(1){ width:420px; height:420px; background:radial-gradient(circle, rgba(205,242,254,.55), transparent 70%); }
    .anneaux span:nth-child(2){ width:720px; height:720px; animation-delay:-3s; }
    .anneaux span:nth-child(3){ width:1040px; height:1040px; animation-delay:-6s; }
    .anneaux span:nth-child(4){ width:1400px; height:1400px; animation-delay:-1.5s; }
    @keyframes respire{ 0%,100%{ transform:scale(1); } 50%{ transform:scale(1.03); } }

    .hero-inner{ position:relative; text-align:center; width:100%; }
    .badge{
      display:inline-flex; align-items:center; gap:10px;
      padding:7px 16px 7px 8px;
      border:1px solid var(--ligne); border-radius:999px;
      background:var(--blanc);
      font-family:var(--mono); font-size:12px; color:var(--doux);
    }
    .badge .court{ display:none; }
    .badge b{ white-space:nowrap;
      background:var(--ciel); color:var(--nuit); font-weight:500;
      padding:3px 10px; border-radius:999px;
    }
    .hero h1{
      font-size:clamp(44px, 8.4vw, 104px);
      font-weight:600;
      letter-spacing:-.05em;
      line-height:.98;
      margin:34px auto 0;
      max-width:980px;
    }
    .hero h1 em{ font-size:1.08em; padding-right:.04em; }
    .hero h1 .mot{ display:inline-block; }
    .hero .point{ color:var(--ardoise); }
    .hero p.sous{
      font-size:clamp(17px, 2vw, 20px);
      color:var(--doux);
      max-width:600px; margin:30px auto 0;
    }
    .hero .actions{ display:flex; gap:12px; justify-content:center; flex-wrap:wrap; margin-top:44px; }
    .plateformes{
      margin-top:90px;
      display:flex; justify-content:center; flex-wrap:wrap; gap:14px 40px;
      font-family:var(--mono); font-size:13px; color:rgba(29,47,51,.45);
    }
    .plateformes span:first-child{ width:100%; font-size:11px; letter-spacing:.08em; text-transform:uppercase; color:var(--ardoise); }

    /* Flottants (inspirés des cartes SMMspot) */
    .flottant{
      position:absolute;
      background:var(--blanc);
      border:1px solid var(--ligne);
      border-radius:16px;
      padding:14px 16px;
      box-shadow:0 20px 50px -24px rgba(29,47,51,.35);
      font-size:13px;
      animation:flotte 7s ease-in-out infinite;
    }
    .flottant small{ font-family:var(--mono); font-size:11px; color:var(--ardoise); display:block; margin-bottom:4px; }
    .flottant strong{ font-size:20px; letter-spacing:-.03em; font-weight:600; }
    /* positionnées par rapport au bloc du titre, jamais par-dessus */
    .flottant{ z-index:2; text-align:left; white-space:nowrap; }
    .f1{ right:calc(50% + 450px); top:40%; }
    .f2{ left:calc(50% + 450px); top:12%; animation-delay:-2.5s; }
    .f3{ left:calc(50% + 330px); bottom:-10px; animation-delay:-4.5s; }
    .f1 .barres{ display:flex; align-items:flex-end; gap:4px; height:34px; margin-top:8px; }
    .f1 .barres i{ width:8px; border-radius:3px; background:var(--ciel); }
    .f1 .barres i:last-child{ background:var(--ardoise); }
    .f3{ display:flex; align-items:center; gap:10px; }
    .f3 .pastille{ width:30px; height:30px; border-radius:50%; background:var(--ciel); display:grid; place-items:center; font-size:14px; }
    @keyframes flotte{ 0%,100%{ transform:translateY(0); } 50%{ transform:translateY(-12px); } }

    /* ───────── Vidéo ───────── */
    .showreel{ padding:140px 0 0; }
    .video-cadre{
      position:relative; aspect-ratio:16/9;
      border-radius:32px; overflow:hidden;
      background:var(--nuit);
      border:1px solid var(--ligne);
      box-shadow:0 50px 100px -50px rgba(29,47,51,.55);
    }
    .js .video-cadre.reveal{ transform:translateY(40px) scale(.94); }
    .js .video-cadre.reveal.visible{ transform:none; }
    .video-cadre video{ width:100%; height:100%; object-fit:cover; display:block; }
    .son{
      position:absolute; right:20px; bottom:20px;
      display:inline-flex; align-items:center; gap:8px;
      padding:10px 16px 10px 12px; border:0; border-radius:999px; cursor:pointer;
      background:rgba(255,255,255,.88); color:var(--nuit);
      backdrop-filter:blur(10px); -webkit-backdrop-filter:blur(10px);
      font-family:var(--mono); font-size:12px;
      transition:transform .4s var(--ease), background .3s;
    }
    .son:hover{ transform:translateY(-2px); background:var(--blanc); }
    .son svg{ width:18px; height:18px; }
    .son .on{ display:none; }
    .son.actif .on{ display:block; }
    .son.actif .off{ display:none; }
    @media (max-width:640px){ .video-cadre{ border-radius:20px; } .showreel{ padding-top:96px; } .son{ right:12px; bottom:12px; } }

    /* ───────── Chiffres ───────── */
    .chiffres{ padding:0; }
    .chiffres .wrap{
      display:grid; grid-template-columns:repeat(4,1fr);
      border-top:1px solid var(--ligne); border-bottom:1px solid var(--ligne);
    }
    .chiffre{ padding:48px 28px; }
    .chiffre + .chiffre{ border-left:1px solid var(--ligne); }
    .chiffre strong{ display:block; font-size:44px; font-weight:500; letter-spacing:-.04em; line-height:1; }
    .chiffre span{ font-family:var(--mono); font-size:12px; color:var(--doux); display:block; margin-top:12px; }

    /* ───────── Présentation / Qui suis-je ───────── */
    .duo{ display:grid; grid-template-columns:1fr 1fr; gap:96px; align-items:start; }
    .texte p{ color:var(--doux); font-size:17px; }
    .texte p + p{ margin-top:18px; }
    .texte strong{ color:var(--nuit); font-weight:600; }

    .portrait{
      position:relative;
      aspect-ratio:4/5;
      border-radius:28px;
      background:linear-gradient(160deg, var(--ciel) 0%, #e9f8fd 45%, var(--blanc) 100%);
      border:1px solid var(--ligne);
      display:grid; place-items:center;
      overflow:hidden;
    }
    .portrait{ background:var(--noir); box-shadow:0 40px 80px -40px rgba(29,47,51,.55); }
    .portrait .photo{ position:absolute; inset:0; width:100%; height:100%; object-fit:cover; object-position:center 40%; transition:transform 1.2s var(--ease); }
    .portrait{ position:sticky; top:120px; }
    @media (max-width:1000px){ .portrait{ position:relative; top:auto; max-width:480px; } }
    .portrait:hover .photo{ transform:scale(1.04); }
    .portrait .tag{ z-index:1; backdrop-filter:blur(8px); background:rgba(255,255,255,.88) !important; }
    .portrait .tag{
      position:absolute; left:20px; bottom:20px;
      font-family:var(--mono); font-size:12px;
      background:var(--blanc); border:1px solid var(--ligne);
      padding:8px 14px; border-radius:999px;
    }
    .citation{
      margin-top:44px; padding-top:36px;
      border-top:1px solid var(--ligne);
      font-family:var(--serif);
      font-size:clamp(26px, 3vw, 34px);
      line-height:1.22;
      color:var(--nuit);
      text-align:center;
    }
    .citation em{ color:var(--ardoise); }

    /* ───────── Services ───────── */
    .services{ background:var(--fond-2); border-radius:40px; margin:0 16px; }
    .grille{
      display:grid; grid-template-columns:repeat(3,1fr); gap:16px;
      margin-top:72px;
    }
    .carte{
      background:var(--blanc);
      border:1px solid var(--ligne);
      border-radius:24px;
      padding:36px 32px 34px;
      transition:transform .5s var(--ease), box-shadow .5s var(--ease), border-color .3s;
    }
    .carte:hover{
      transform:translateY(-6px);
      border-color:rgba(96,135,147,.35);
      box-shadow:0 30px 60px -30px rgba(29,47,51,.3);
    }
    .carte .num{ font-family:var(--mono); font-size:12px; color:var(--ardoise); }
    .carte .ico{
      width:48px; height:48px; border-radius:14px;
      background:var(--ciel); color:var(--nuit);
      display:grid; place-items:center;
      margin:28px 0 24px;
      transition:background .4s, color .4s;
    }
    .carte:hover .ico{ background:var(--nuit); color:var(--ciel); }
    .carte .ico svg{ width:22px; height:22px; }
    .carte h3{ font-size:20px; font-weight:600; letter-spacing:-.02em; }
    .carte p{ color:var(--doux); font-size:15px; margin-top:10px; }

    /* ───────── Mission (sombre) ───────── */
    .mission{
      background:var(--nuit); color:var(--blanc);
      border-radius:40px; margin:140px 16px 0;
      position:relative; overflow:hidden;
    }
    .mission::after{
      content:""; position:absolute; right:-240px; top:-240px;
      width:640px; height:640px; border-radius:50%;
      border:1px solid rgba(205,242,254,.10);
      box-shadow:0 0 0 120px rgba(205,242,254,.025), 0 0 0 240px rgba(205,242,254,.02);
    }
    .mission .label{ color:var(--ciel); }
    .mission .label::before{ background:var(--ciel); }
    .mission blockquote{
      font-family:var(--serif);
      font-size:clamp(32px, 4.6vw, 58px);
      line-height:1.1;
      letter-spacing:-.01em;
      margin-top:28px; max-width:920px;
      position:relative; z-index:1;
    }
    .mission blockquote em{ color:var(--ciel); }
    .mission .sous{ color:rgba(255,255,255,.62); font-size:17px; max-width:560px; margin-top:32px; position:relative; z-index:1; }

    .objectifs{
      list-style:none;
      display:grid; grid-template-columns:repeat(5,1fr); gap:1px;
      margin-top:96px;
      background:rgba(205,242,254,.12);
      border:1px solid rgba(205,242,254,.12);
      border-radius:22px; overflow:hidden;
      position:relative; z-index:1;
    }
    .objectifs li{ background:var(--nuit); padding:30px 24px; font-size:15px; color:rgba(255,255,255,.82); }
    .objectifs li span{ display:block; font-family:var(--mono); font-size:12px; color:var(--ciel); margin-bottom:28px; }

    /* ───────── Méthode ───────── */
    .methode .duo{ grid-template-columns:.9fr 1.1fr; }
    .methode .collant{ position:sticky; top:140px; }
    .etapes{ list-style:none; }
    .etape{
      display:grid; grid-template-columns:56px 1fr; gap:20px;
      padding:28px 0;
      border-bottom:1px solid var(--ligne);
    }
    .etape:first-child{ border-top:1px solid var(--ligne); }
    .etape .n{ font-family:var(--mono); font-size:13px; color:var(--ardoise); padding-top:3px; }
    .etape p{ font-size:19px; letter-spacing:-.015em; color:var(--nuit); transition:transform .4s var(--ease); }
    .etape:hover p{ transform:translateX(6px); }
    .encart{
      margin-top:40px;
      padding:26px 28px;
      background:var(--ciel);
      border-radius:20px;
      font-size:15px; color:var(--nuit);
    }
    .encart strong{ font-weight:600; }

    /* ───────── Réalisations ───────── */
    .realisations .entete{ display:flex; justify-content:space-between; align-items:flex-end; gap:24px; flex-wrap:wrap; }
    .projets{ display:grid; grid-template-columns:repeat(3,1fr); gap:20px; margin-top:64px; }
    .projet .visuel{
      aspect-ratio:4/5; border-radius:24px;
      border:1px solid var(--ligne);
      overflow:hidden; position:relative;
      display:grid; place-items:center;
      font-family:var(--mono); font-size:12px; color:var(--ardoise);
    }
    .projet .visuel::before{
      content:""; position:absolute; inset:0;
      transition:transform .8s var(--ease);
    }
    .projet:nth-child(1) .visuel::before{ background:linear-gradient(170deg, var(--ciel), var(--blanc)); }
    .projet:nth-child(2) .visuel::before{ background:linear-gradient(170deg, var(--nuit), var(--ardoise)); }
    .projet:nth-child(3) .visuel::before{ background:linear-gradient(170deg, #e7f1f4, var(--ciel)); }
    .projet:nth-child(2) .visuel{ color:var(--ciel); }
    .projet:hover .visuel::before{ transform:scale(1.06); }
    .projet .visuel span{ position:relative; }
    .projet{ display:block; padding:32px 30px; border:1px solid var(--ligne); border-radius:24px; background:var(--blanc); transition:transform .5s var(--ease), border-color .3s, box-shadow .5s var(--ease); }
    .projet:hover{ transform:translateY(-6px); border-color:rgba(96,135,147,.35); box-shadow:0 30px 60px -30px rgba(29,47,51,.3); }
    .projet .meta{ display:flex; flex-wrap:wrap; justify-content:space-between; align-items:baseline; gap:12px; }
    .projet h3{ font-size:18px; font-weight:600; letter-spacing:-.02em; }
    .projet .type{ font-family:var(--mono); font-size:12px; color:var(--doux); white-space:nowrap; }
    .projet p{ color:var(--doux); font-size:15px; margin-top:4px; }

    /* ───────── Contact ───────── */
    .contact{ padding-bottom:60px; }
    .cta{
      background:var(--fond-2);
      border:1px solid var(--ligne);
      border-radius:40px;
      padding:110px 32px;
      text-align:center;
      position:relative; overflow:hidden;
    }
    .cta .anneaux span{ border-color:rgba(96,135,147,.12); }
    .cta > *{ position:relative; }
    .cta .chapo{ margin-left:auto; margin-right:auto; }
    .cta .titre{ font-size:clamp(38px, 6vw, 72px); }
    .liens{
      display:flex; flex-wrap:wrap; justify-content:center; gap:10px;
      margin-top:48px;
    }
    .liens a{
      display:inline-flex; align-items:center; gap:8px;
      padding:11px 18px; border-radius:999px;
      background:var(--blanc); border:1px solid var(--ligne);
      font-family:var(--mono); font-size:13px;
      transition:border-color .3s, transform .4s var(--ease);
    }
    .liens a:hover{ border-color:var(--ardoise); transform:translateY(-2px); }
    .liens a small{ color:var(--ardoise); font-size:11px; text-transform:uppercase; letter-spacing:.06em; }

    footer{
      padding:40px 0 48px;
      font-family:var(--mono); font-size:12px; color:var(--doux);
    }
    footer .wrap{ display:flex; justify-content:space-between; align-items:center; gap:16px; flex-wrap:wrap; }
    footer .nav-logo{ font-family:var(--sans); font-size:14px; color:var(--nuit); }
    footer .nav-logo img{ width:28px; height:28px; }

    /* ───────── Animations d'apparition ───────── */
    .js .reveal{
      opacity:0;
      transform:translateY(28px);
      filter:blur(6px);
      transition:opacity 1s var(--ease), transform 1s var(--ease), filter 1s var(--ease);
      transition-delay:var(--d, 0s);
    }
    .js .reveal.visible{ opacity:1; transform:none; filter:none; }

    /* Titre du hero : mot par mot */
    .js .hero h1 .mot{
      opacity:0; transform:translateY(60%) rotate(2deg); filter:blur(8px);
      animation:monte 1.1s var(--ease) forwards;
      animation-delay:calc(.25s + var(--i) * .09s);
    }
    @keyframes monte{ to{ opacity:1; transform:none; filter:none; } }

    .js .hero .anneaux span{ opacity:0; animation:respire 9s ease-in-out infinite, apparait 1.6s var(--ease) forwards; }
    .js .hero .anneaux span:nth-child(2){ animation-delay:-3s, .15s; }
    .js .hero .anneaux span:nth-child(3){ animation-delay:-6s, .3s; }
    .js .hero .anneaux span:nth-child(4){ animation-delay:-1.5s, .45s; }
    @keyframes apparait{ from{ opacity:0; } to{ opacity:1; } }

    .js .nav{ opacity:0; animation:descend 1s var(--ease) .1s forwards; }
    @keyframes descend{ from{ opacity:0; transform:translate(-50%,-20px); } to{ opacity:1; transform:translate(-50%,0); } }

    /* ───────── Responsive ───────── */
    @media (max-width: 1439px){ .flottant{ display:none; } }
    @media (max-width: 1000px){
      .nav-links{ display:none; }
      .duo, .methode .duo{ grid-template-columns:1fr; gap:56px; }
      .methode .collant{ position:static; }
      .grille, .projets{ grid-template-columns:repeat(2,1fr); }
      .objectifs{ grid-template-columns:repeat(2,1fr); }
      .chiffres .wrap{ grid-template-columns:repeat(2,1fr); }
      .chiffre:nth-child(3){ border-left:0; }
      .chiffre:nth-child(n+3){ border-top:1px solid var(--ligne); }
    }
    @media (max-width: 640px){
      section{ padding:96px 0; }
      .wrap{ padding:0 16px; }
      .hero{ padding:140px 0 80px; }
      .grille, .projets, .objectifs{ grid-template-columns:1fr; }
      .services, .mission{ border-radius:28px; margin-left:8px; margin-right:8px; }
      .mission{ margin-top:96px; }
      .cta{ border-radius:28px; padding:80px 20px; }
      .chiffre{ padding:32px 16px; }
      .chiffre strong{ font-size:34px; }
      .badge .suite{ display:none; } .badge .court{ display:inline; }
    }

    @media (prefers-reduced-motion: reduce){
      *, *::before, *::after{ animation:none !important; transition:none !important; }
      .js .reveal, .js .hero h1 .mot, .js .nav, .js .hero .anneaux span{ opacity:1; transform:none; filter:none; }
      .js .nav{ transform:translateX(-50%); }
      html{ scroll-behavior:auto; }
    }
  </style>
</head>
<body>

  <!-- ───────── Navigation ───────── -->
  <header class="nav" id="nav">
    <a href="#top" class="nav-logo">
      <img src="logo.png" alt="Logo Club Aseel">
      CLUB_ASEEL
    </a>
    <nav class="nav-links">
      <a href="#apropos">Qui suis-je</a>
      <a href="#services">Services</a>
      <a href="#mission">Mission</a>
      <a href="#methode">Méthode</a>
      <a href="#realisations">Réalisations</a>
    </nav>
    <a href="#contact" class="btn btn-dark">Me contacter <span class="fleche">→</span></a>
  </header>

  <!-- ───────── Hero ───────── -->
  <section class="hero" id="top">
    <div class="anneaux"><span></span><span></span><span></span><span></span></div>

    <div class="wrap hero-inner">
      <div class="flottant f1">
        <small>Engagement</small>
        <strong>+ Visibilité</strong>
        <div class="barres"><i style="height:30%"></i><i style="height:45%"></i><i style="height:40%"></i><i style="height:65%"></i><i style="height:100%"></i></div>
      </div>
      <div class="flottant f2">
        <small>Reels · Stories · Posts</small>
        <strong>Contenu planifié</strong>
      </div>
      <div class="flottant f3">
        <div class="pastille">✦</div>
        <div><small>Nouvelle abonnée</small>Votre communauté grandit</div>
      </div>

      <span class="badge reveal" style="--d:.1s"><b>Studio créatif</b> <span class="suite">Communication digitale · Réseaux sociaux</span><span class="court">Réseaux sociaux</span></span>

      <h1>
        <span class="mot" style="--i:0">Faites</span>
        <span class="mot" style="--i:1">briller</span>
        <span class="mot" style="--i:2">votre</span>
        <span class="mot" style="--i:3"><em>contenu</em><span class="point">.</span></span>
      </h1>

      <p class="sous reveal" style="--d:.75s">CLUB_ASEEL accompagne les entrepreneuses, créatrices et porteuses de projets dans leur présence digitale — de la stratégie à la création, jusqu'à la gestion des comptes.</p>

      <div class="actions reveal" style="--d:.9s">
        <a href="#contact" class="btn btn-dark">Démarrer un projet <span class="fleche">→</span></a>
        <a href="#services" class="btn btn-ghost">Voir les services</a>
      </div>
    </div>
  </section>

  <!-- ───────── Chiffres ───────── -->
  <section class="chiffres">
    <div class="wrap">
      <div class="chiffre reveal"><strong>5+</strong><span>années d'expérience</span></div>
      <div class="chiffre reveal" style="--d:.1s"><strong>6</strong><span>services complets</span></div>
      <div class="chiffre reveal" style="--d:.2s"><strong>7</strong><span>étapes de méthode</span></div>
      <div class="chiffre reveal" style="--d:.3s"><strong>360°</strong><span>stratégie → création → gestion</span></div>
    </div>
  </section>

  <!-- ───────── Présentation ───────── -->
  <section id="presentation">
    <div class="wrap duo">
      <div>
        <span class="label reveal">01 — Présentation</span>
        <h2 class="titre reveal" style="--d:.1s">Un studio pensé pour la <em>présence digitale</em>.</h2>
      </div>
      <div class="texte">
        <p class="reveal" style="--d:.15s">CLUB_ASEEL est un projet spécialisé dans la création de contenu digital, le montage vidéo, le design graphique, l'animation et la gestion des réseaux sociaux.</p>
        <p class="reveal" style="--d:.25s">Nous accompagnons les marques, les entreprises et les créateurs dans le développement de leur présence digitale grâce à une communication <strong>créative, dynamique et adaptée à leur identité</strong>.</p>
      </div>
    </div>
  </section>

  <!-- ───────── Qui suis-je ───────── -->
  <section id="apropos" style="padding-top:0">
    <div class="wrap duo">
      <div class="portrait reveal">
        <img class="photo" src="photo.jpg" alt="Créatrice au travail devant son écran de montage">
        <span class="tag">Créatrice &amp; designer</span>
      </div>
      <div>
        <span class="label reveal">02 — Qui suis-je ?</span>
        <h2 class="titre reveal" style="--d:.1s">Plus de 5 ans à donner vie aux <em>idées</em>.</h2>
        <div class="texte" style="margin-top:32px">
          <p class="reveal" style="--d:.15s">Je suis une créatrice de contenu et designer passionnée, avec plus de <strong>5 ans d'expérience</strong> dans la création de contenu, le design graphique et le montage vidéo.</p>
          <p class="reveal" style="--d:.2s">Au fil des années, j'ai développé mes compétences, affiné mon regard créatif et appris à maîtriser les outils et les stratégies qui permettent de transformer des idées en contenus visuels impactants.</p>
          <p class="reveal" style="--d:.25s">Aujourd'hui, à travers CLUB_ASEEL, je souhaite mettre cette expérience au service d'autres <strong>sœurs entrepreneuses, créatrices et porteuses de projets</strong>, afin de les accompagner dans le développement de leur présence sur les réseaux sociaux.</p>
          <p class="reveal" style="--d:.3s">Mon objectif : les aider à faire briller leur contenu de manière intelligente, créative et stratégique, tout en mettant en valeur leur identité, leur univers et leurs projets.</p>
        </div>
        <p class="citation reveal" style="--d:.2s">« Un beau contenu ne suffit pas : il faut aussi transmettre un message, attirer l'attention et créer une véritable <em>connexion</em> avec son audience. »</p>
      </div>
    </div>
  </section>

  <!-- ───────── Services ───────── -->
  <section class="services" id="services">
    <div class="wrap">
      <div class="center">
        <span class="label reveal">03 — Nos services</span>
        <h2 class="titre reveal" style="--d:.1s">Tout ce dont votre marque a <em>besoin</em>.</h2>
        <p class="chapo reveal" style="--d:.2s">Six expertises complémentaires pour une communication cohérente, du premier visuel à la stratégie globale.</p>
      </div>

      <div class="grille">
        <article class="carte reveal">
          <span class="num">01</span>
          <div class="ico"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="5" width="15" height="14" rx="3"/><path d="m17 10 5-3v10l-5-3"/></svg></div>
          <h3>Montage vidéo</h3>
          <p>Création et montage de vidéos dynamiques et professionnelles.</p>
        </article>
        <article class="carte reveal" style="--d:.08s">
          <span class="num">02</span>
          <div class="ico"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><path d="M12 19l7-7 3 3-7 7-3-3z"/><path d="M18 13l-1.5-7.5L2 2l3.5 14.5L13 18l5-5z"/><path d="M2 2l7.6 7.6"/><circle cx="11" cy="11" r="2"/></svg></div>
          <h3>Design graphique</h3>
          <p>Visuels, affiches, publications et identités visuelles.</p>
        </article>
        <article class="carte reveal" style="--d:.16s">
          <span class="num">03</span>
          <div class="ico"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><path d="M12 3l1.9 5.8L20 10l-5 3.6L16.5 20 12 16.5 7.5 20 9 13.6 4 10l6.1-1.2z"/></svg></div>
          <h3>Création de contenu</h3>
          <p>Contenus originaux et attractifs pour les réseaux sociaux.</p>
        </article>
        <article class="carte reveal">
          <span class="num">04</span>
          <div class="ico"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="9"/><path d="m10 8 6 4-6 4z"/></svg></div>
          <h3>Animation digitale</h3>
          <p>Contenus animés et vidéos engageantes.</p>
        </article>
        <article class="carte reveal" style="--d:.08s">
          <span class="num">05</span>
          <div class="ico"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="3" width="18" height="18" rx="5"/><circle cx="12" cy="12" r="4"/><circle cx="17.5" cy="6.5" r=".6" fill="currentColor"/></svg></div>
          <h3>Gestion des réseaux</h3>
          <p>Gestion et organisation des comptes Instagram, TikTok, Facebook…</p>
        </article>
        <article class="carte reveal" style="--d:.16s">
          <span class="num">06</span>
          <div class="ico"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="4" width="18" height="17" rx="3"/><path d="M3 9h18M8 2v4M16 2v4M8 14h3M8 17h6"/></svg></div>
          <h3>Stratégie de contenu</h3>
          <p>Planification des publications, adaptée à chaque plateforme.</p>
        </article>
      </div>
    </div>
  </section>

  <!-- ───────── Mission & objectifs ───────── -->
  <section class="mission" id="mission">
    <div class="wrap">
      <span class="label reveal">04 — Notre mission</span>
      <blockquote class="reveal" style="--d:.1s">Transformer les idées en contenus visuels attractifs, et créer une véritable <em>connexion</em> entre les marques et leur communauté.</blockquote>
      <p class="sous reveal" style="--d:.2s">Nous aidons les marques et les entreprises à développer leur image et leur visibilité sur les réseaux sociaux, avec une communication digitale créative, cohérente et engageante.</p>

      <ul class="objectifs" id="objectifs">
        <li class="reveal"><span>Objectif 01</span>Améliorer la présence digitale des marques.</li>
        <li class="reveal" style="--d:.08s"><span>Objectif 02</span>Développer leur visibilité et leur notoriété.</li>
        <li class="reveal" style="--d:.16s"><span>Objectif 03</span>Créer du contenu dynamique qui attire l'attention.</li>
        <li class="reveal" style="--d:.24s"><span>Objectif 04</span>Construire et fidéliser une communauté.</li>
        <li class="reveal" style="--d:.32s"><span>Objectif 05</span>Assurer une gestion efficace et stratégique des comptes.</li>
      </ul>
    </div>
  </section>

  <!-- ───────── Vidéo ───────── -->
  <section class="showreel" id="video">
    <div class="wrap">
      <div class="video-cadre reveal">
        <video id="intro" src="club_aseel_intro.mp4" poster="poster.jpg" muted loop playsinline preload="auto" aria-label="Vidéo de présentation CLUB_ASEEL"></video>
        <button class="son" id="son" type="button" aria-label="Activer le son">
          <svg class="off" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M11 5 6 9H3v6h3l5 4z"/><path d="m22 9-6 6M16 9l6 6"/></svg>
          <svg class="on" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M11 5 6 9H3v6h3l5 4z"/><path d="M15.5 8.5a5 5 0 0 1 0 7M19 5a10 10 0 0 1 0 14"/></svg>
          <span>Son</span>
        </button>
      </div>
    </div>
  </section>

  <!-- ───────── Méthode ───────── -->
  <section class="methode" id="methode">
    <div class="wrap duo">
      <div class="collant">
        <span class="label reveal">05 — Notre méthode</span>
        <h2 class="titre reveal" style="--d:.1s">Gérer un compte et créer du contenu <em>dynamique</em>.</h2>
        <p class="chapo reveal" style="--d:.2s">Une démarche claire, en sept étapes, de l'analyse de votre marque jusqu'à l'amélioration continue.</p>
        <div class="encart reveal" style="--d:.3s"><strong>De la stratégie à la gestion des comptes.</strong> CLUB_ASEEL ne fait pas seulement de la création visuelle : nous accompagnons les marques dans toute leur communication sur les réseaux sociaux.</div>
      </div>
      <ol class="etapes">
        <li class="etape reveal"><span class="n">01</span><p>Analyser l'identité de la marque et son public cible.</p></li>
        <li class="etape reveal"><span class="n">02</span><p>Définir une stratégie de communication.</p></li>
        <li class="etape reveal"><span class="n">03</span><p>Élaborer un calendrier éditorial.</p></li>
        <li class="etape reveal"><span class="n">04</span><p>Créer des vidéos courtes, des Reels, des Stories et des publications.</p></li>
        <li class="etape reveal"><span class="n">05</span><p>Publier régulièrement avec une identité visuelle cohérente.</p></li>
        <li class="etape reveal"><span class="n">06</span><p>Interagir avec la communauté.</p></li>
        <li class="etape reveal"><span class="n">07</span><p>Analyser les statistiques pour améliorer les performances.</p></li>
      </ol>
    </div>
  </section>

  <!-- ───────── Réalisations ───────── -->
  <section class="realisations" id="realisations" style="padding-top:40px">
    <div class="wrap">
      <div class="entete">
        <div>
          <span class="label reveal">06 — Réalisations</span>
          <h2 class="titre reveal" style="--d:.1s">Quelques projets <em>récents</em>.</h2>
        </div>
        <a href="#contact" class="btn btn-ghost reveal" style="--d:.2s">Travailler ensemble <span class="fleche">→</span></a>
      </div>

      <div class="projets">
        <a href="#" class="projet reveal">
          <div class="meta"><h3>[Nom du projet 1]</h3><span class="type">[Vidéo]</span></div>
          <p>[Courte description du projet]</p>
        </a>
        <a href="#" class="projet reveal" style="--d:.1s">
          <div class="meta"><h3>[Nom du projet 2]</h3><span class="type">[Design]</span></div>
          <p>[Courte description du projet]</p>
        </a>
        <a href="#" class="projet reveal" style="--d:.2s">
          <div class="meta"><h3>[Nom du projet 3]</h3><span class="type">[Gestion de compte]</span></div>
          <p>[Courte description du projet]</p>
        </a>
      </div>
    </div>
  </section>

  <!-- ───────── Contact ───────── -->
  <section class="contact" id="contact" style="padding-top:40px">
    <div class="wrap">
      <div class="cta reveal">
        <div class="anneaux"><span></span><span></span><span></span></div>
        <span class="label">07 — Contact</span>
        <h2 class="titre">Un projet ? Une marque<br>à faire <em>grandir</em> ?</h2>
        <p class="chapo">Parlons-en. Je vous réponds avec plaisir pour imaginer ensemble votre présence digitale.</p>
        <div class="actions" style="margin-top:40px">
          <a href="mailto:muslimaharabic25@gmail.com" class="btn btn-dark">Écrire un email <span class="fleche">→</span></a>
        </div>
        <div class="liens">
          <a href="mailto:muslimaharabic25@gmail.com"><small>Email</small> muslimaharabic25@gmail.com</a>
          <a href="https://www.instagram.com/aseel_a2e" target="_blank" rel="noopener"><small>Instagram</small> @aseel_a2e</a>
        </div>
      </div>
    </div>
  </section>

  <footer>
    <div class="wrap">
      <a href="#top" class="nav-logo"><img src="logo.png" alt="">CLUB_ASEEL</a>
      <span>© 2026 CLUB_ASEEL — Studio créatif</span>
    </div>
  </footer>

  <script>
    // Apparition des éléments au défilement
    const io = new IntersectionObserver((entrees) => {
      entrees.forEach(e => {
        if (e.isIntersecting) { e.target.classList.add('visible'); io.unobserve(e.target); }
      });
    }, { threshold: 0.15, rootMargin: '0px 0px -40px 0px' });
    document.querySelectorAll('.reveal').forEach(el => io.observe(el));

    // Étapes de la méthode : apparition en cascade
    document.querySelectorAll('.etape').forEach((el, i) => el.style.setProperty('--d', (i % 7) * 0.06 + 's'));

    // Ombre de la navigation au défilement
    const nav = document.getElementById('nav');
    addEventListener('scroll', () => nav.classList.toggle('scrolled', scrollY > 20), { passive: true });

    // Vidéo : lecture quand elle est visible, bouton son
    const vid = document.getElementById('intro'), son = document.getElementById('son');
    new IntersectionObserver(([e]) => { e.isIntersecting ? vid.play().catch(()=>{}) : vid.pause(); }, { threshold: 0.35 }).observe(vid);
    son.addEventListener('click', () => {
      vid.muted = !vid.muted;
      son.classList.toggle('actif', !vid.muted);
      son.setAttribute('aria-label', vid.muted ? 'Activer le son' : 'Couper le son');
      if (!vid.muted) { vid.currentTime = 0; vid.play().catch(()=>{}); }
    });
  </script>
</body>
</html>

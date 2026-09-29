# crathea111.github.io
portfolio page
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Crathea — the works</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,400;0,9..144,600;0,9..144,700;1,9..144,500;1,9..144,600&family=Space+Grotesk:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --paper:#FFFBF3;
    --ink:#16130E;
    --coral:#FF4F6D;
    --lime:#D6FA3C;
    --cobalt:#3654FF;
    --sun:#FFCF3F;
    box-sizing:border-box;
    padding-top:env(safe-area-inset-top,0px);
    padding-bottom:env(safe-area-inset-bottom,0px);
  }
  /* Brand is intentionally bright regardless of system theme */
  @media (prefers-color-scheme: dark){
    :root:not([data-theme="light"]){ --paper:#FFFBF3; --ink:#16130E; }
  }
  :root[data-theme="dark"]{ --paper:#FFFBF3; --ink:#16130E; }

  *{margin:0;padding:0;box-sizing:border-box;}
  html{scroll-behavior:smooth; scroll-padding-top:env(safe-area-inset-top,0px);}
  body{
    background:var(--paper);
    color:var(--ink);
    font-family:'Space Grotesk', ui-sans-serif, system-ui, sans-serif;
    overflow-x:hidden;
    position:relative;
  }
  /* grain texture */
  body::before{
    content:'';
    position:fixed; inset:0; z-index:1; pointer-events:none;
    opacity:.045; mix-blend-mode:multiply;
    background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='140' height='140'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='2' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");
  }

  h1,h2,h3{font-family:'Fraunces', Georgia, serif; letter-spacing:-0.5px; line-height:1.05;}
  a{color:inherit; text-decoration:none;}
  img{max-width:100%; display:block;}

  .wrap{max-width:1180px; margin:0 auto; padding:0 clamp(1.25rem,4vw,2.5rem);}
  section{padding:clamp(3.5rem,9vw,6.5rem) 0; position:relative;}

  /* ---------- Ticker ---------- */
  .ticker{
    background:var(--ink); color:var(--paper);
    padding:0.85rem 0; overflow:hidden; white-space:nowrap;
    position:sticky; top:0; z-index:40;
    padding-top:calc(0.85rem + env(safe-area-inset-top,0px));
  }
  .ticker-track{
    display:inline-flex; gap:2.5rem;
    animation:scroll 22s linear infinite;
    font-family:'Space Grotesk'; font-weight:600; font-size:0.95rem;
  }
  .ticker-track span{display:inline-flex; align-items:center; gap:2.5rem;}
  .ticker-track .dot{color:var(--lime); font-size:1.1rem;}
  @keyframes scroll{ from{transform:translateX(0);} to{transform:translateX(-50%);} }

  /* ---------- Hero ---------- */
  .hero{padding-top:clamp(3rem,8vw,5rem); padding-bottom:2rem;}
  .hero-grid{display:grid; grid-template-columns:1.3fr .7fr; gap:2rem; align-items:end;}
  .hero h1{
    font-size:clamp(3.4rem,11vw,7.5rem); font-weight:700;
    position:relative; z-index:2;
  }
  .hero h1 em{font-style:italic; font-weight:500; color:var(--coral);}
  .hero-sub{
    font-size:clamp(1.05rem,2vw,1.3rem); max-width:34ch; margin-top:1.25rem;
    font-weight:500; color:var(--ink); opacity:.75;
  }
  .blob{
    position:absolute; border-radius:50%; z-index:0; filter:blur(2px);
  }
  .blob-1{ width:280px; height:280px; background:var(--lime); top:-60px; right:-40px; opacity:.55;}
  .blob-2{ width:180px; height:180px; background:var(--cobalt); bottom:20px; right:120px; opacity:.18;}

  .chip-row{display:flex; flex-wrap:wrap; gap:.7rem; margin-top:2.25rem; position:relative; z-index:2;}
  .chip{
    font-family:'Space Grotesk'; font-weight:600; font-size:.92rem;
    padding:.6rem 1.15rem; border:2.25px solid var(--ink); border-radius:999px;
    background:var(--paper); box-shadow:4px 4px 0 var(--ink);
    transition:transform .18s ease, box-shadow .18s ease;
    cursor:pointer;
  }
  .chip:hover{ transform:translate(-2px,-2px); box-shadow:6px 6px 0 var(--ink); }
  .chip.c-lime{background:var(--lime);}
  .chip.c-coral{background:var(--coral); color:var(--paper);}
  .chip.c-cobalt{background:var(--cobalt); color:var(--paper);}

  /* ---------- Section heading ---------- */
  .heading-row{display:flex; align-items:flex-end; justify-content:space-between; gap:1.5rem; margin-bottom:2.5rem; flex-wrap:wrap;}
  .heading-row h2{font-size:clamp(2.1rem,5vw,3.2rem); font-weight:700;}
  .heading-note{font-size:.95rem; max-width:26ch; opacity:.65; font-weight:500; padding-bottom:.4rem;}

  /* ---------- Sticker cards ---------- */
  .stickers{display:grid; grid-template-columns:repeat(3,1fr); gap:2.2rem;}
  .sticker{
    border:2.5px solid var(--ink); border-radius:22px;
    background:var(--paper); padding:1.6rem 1.5rem 1.8rem;
    box-shadow:7px 7px 0 var(--ink);
    transition:transform .22s cubic-bezier(.2,.9,.3,1.2), box-shadow .22s ease;
    position:relative;
  }
  .sticker:hover{ transform:rotate(0deg) translate(-3px,-5px); box-shadow:10px 10px 0 var(--ink); }
  .sticker:nth-child(3n+1){ transform:rotate(-2.2deg); }
  .sticker:nth-child(3n+2){ transform:rotate(1.6deg); }
  .sticker:nth-child(3n+3){ transform:rotate(-1deg); }
  .sticker:nth-child(3n+1):hover{ transform:rotate(0deg) translate(-3px,-5px); }
  .sticker:nth-child(3n+2):hover{ transform:rotate(0deg) translate(-3px,-5px); }
  .sticker:nth-child(3n+3):hover{ transform:rotate(0deg) translate(-3px,-5px); }

  .washi{
    position:absolute; top:-11px; left:26px; width:64px; height:20px;
    border:1px solid rgba(22,19,14,.18); border-radius:2px; opacity:.9;
  }
  .sticker:nth-child(3n+1) .washi{ background:rgba(255,207,63,.85); transform:rotate(-5deg); }
  .sticker:nth-child(3n+2) .washi{ background:rgba(214,250,60,.85); transform:rotate(4deg); }
  .sticker:nth-child(3n+3) .washi{ background:rgba(255,79,109,.55); transform:rotate(-3deg); }

  .edit-me{
    display:block; font-style:italic; font-weight:500; font-size:.88rem;
    color:var(--ink); opacity:.42; margin-bottom:1.2rem;
    border-bottom:1.5px dashed var(--ink); padding-bottom:.3rem; width:fit-content;
  }
  .edit-me.on-dark{ color:var(--paper); opacity:.55; border-bottom-color:var(--paper); }

  .tag{
    display:inline-block; font-size:.78rem; font-weight:700; font-family:'Space Grotesk';
    padding:.3rem .7rem; border-radius:999px; border:2px solid var(--ink);
    margin-bottom:1rem;
  }
  .tag.coral{background:var(--coral); color:var(--paper);}
  .tag.lime{background:var(--lime);}
  .tag.cobalt{background:var(--cobalt); color:var(--paper);}
  .tag.sun{background:var(--sun);}

  .icon-badge{
    width:52px; height:52px; border-radius:50%; border:2.25px solid var(--ink);
    display:flex; align-items:center; justify-content:center; margin-bottom:1.1rem;
  }
  .icon-badge svg{width:24px; height:24px;}

  .sticker h3{font-size:1.28rem; font-weight:600; margin-bottom:.35rem;}
  .sticker p{font-size:.92rem; opacity:.65; margin-bottom:1.2rem; font-weight:500;}
  .go-link{
    display:inline-flex; align-items:center; gap:.4rem;
    font-weight:700; font-size:.92rem; font-family:'Space Grotesk';
    border-bottom:2.5px solid var(--ink); padding-bottom:2px;
  }

  /* ---------- Tinted section bands ---------- */
  .band-lime{ background:#F5FBDD; }
  .band-cobalt{ background:#EDF0FF; }

  .creative-grid, .music-grid{display:grid; grid-template-columns:repeat(2,1fr); gap:2rem;}
  .music-grid{grid-template-columns:repeat(3,1fr);}

  /* ---------- Contact ---------- */
  .contact-panel{
    background:var(--ink); color:var(--paper); border-radius:28px;
    padding:clamp(2.2rem,5vw,3.5rem); display:grid; grid-template-columns:1fr 1fr; gap:3rem;
  }
  .contact-panel h2{color:var(--paper);}
  .contact-panel p{opacity:.7; margin-top:1rem; max-width:34ch; font-weight:500;}
  .email-link{
    display:inline-block; margin-top:1.6rem; font-family:'Fraunces'; font-style:italic;
    font-size:1.4rem; color:var(--lime); border-bottom:2px solid var(--lime); padding-bottom:2px;
  }
  .form-group{margin-bottom:1.15rem;}
  .form-group label{display:block; font-size:.85rem; font-weight:600; margin-bottom:.4rem; opacity:.8;}
  .form-group input, .form-group textarea{
    width:100%; padding:.85rem 1rem; background:#221E17; border:2px solid #3A342A;
    border-radius:12px; color:var(--paper); font-family:'Space Grotesk'; font-size:.98rem;
  }
  .form-group input:focus, .form-group textarea:focus{ outline:none; border-color:var(--lime); }
  .form-group textarea{min-height:110px; resize:vertical;}
  .submit-btn{
    width:100%; padding:.95rem; border-radius:999px; border:none; cursor:pointer;
    background:var(--lime); color:var(--ink); font-weight:700; font-family:'Space Grotesk'; font-size:1rem;
    box-shadow:5px 5px 0 #8FAE1E; transition:transform .18s ease, box-shadow .18s ease;
  }
  .submit-btn:hover{ transform:translate(-2px,-2px); box-shadow:7px 7px 0 #8FAE1E; }

  /* ---------- Footer ---------- */
  footer{padding:2.5rem 0 calc(2.5rem + env(safe-area-inset-bottom,0px));}
  .footer-row{display:flex; justify-content:space-between; align-items:center; flex-wrap:wrap; gap:1.5rem;}
  .footer-row p{font-size:.88rem; opacity:.6; font-weight:500;}
  .social-row{display:flex; gap:.8rem;}
  .social-row a{
    width:42px; height:42px; border-radius:50%; border:2.25px solid var(--ink);
    display:flex; align-items:center; justify-content:center;
    transition:transform .18s ease, background .18s ease;
  }
  .social-row a svg{width:18px; height:18px;}
  .social-row a:hover{ background:var(--ink); }
  .social-row a:hover svg{ stroke:var(--paper); }

  /* ---------- Sign generator ---------- */
  .band-sun{ background:#FFF6DC; }
  .oracle-wrap{ text-align:center; }
  .oracle-intro{
    font-family:'Fraunces', Georgia, serif; font-weight:500;
    font-size:clamp(1.3rem,3.6vw,1.9rem); line-height:1.3;
    max-width:28ch; margin:0 auto 3rem;
  }
  .oracle-intro em{ font-style:italic; font-weight:600; color:var(--coral); }

  .oracle-seal{
    position:relative; width:clamp(190px,42vw,240px); aspect-ratio:1/1;
    border-radius:50%; border:3px solid var(--ink); background:var(--paper);
    display:flex; align-items:center; justify-content:center; margin:0 auto;
    box-shadow:8px 8px 0 var(--ink); cursor:pointer; padding:1.7rem;
    transition:transform .2s ease, box-shadow .2s ease;
  }
  .oracle-seal:hover{ transform:translate(-2px,-3px); box-shadow:10px 10px 0 var(--ink); }
  .oracle-seal:active{ transform:translate(1px,2px); box-shadow:5px 5px 0 var(--ink); }

  .oracle-tape{
    position:absolute; top:-13px; left:50%; transform:translateX(-50%) rotate(-4deg);
    width:72px; height:21px; background:var(--coral); opacity:.88;
    border:1px solid rgba(22,19,14,.18); border-radius:2px;
  }

  .oracle-result{
    font-family:'Fraunces', Georgia, serif; font-weight:600;
    font-size:1.2rem; line-height:1.3; display:inline-block;
  }
  .oracle-seal.spin .oracle-result{ animation:sealFlip .55s ease; }
  .oracle-seal.spin{ animation:sealPulse .55s ease; }

  @keyframes sealFlip{
    0%{ transform:scale(1) rotate(0deg); opacity:1; }
    40%{ transform:scale(.82) rotate(160deg); opacity:0; }
    55%{ transform:scale(.82) rotate(190deg); opacity:0; }
    100%{ transform:scale(1) rotate(360deg); opacity:1; }
  }
  @keyframes sealPulse{
    0%,100%{ box-shadow:8px 8px 0 var(--ink); }
    50%{ box-shadow:11px 11px 0 var(--ink); }
  }

  .oracle-caption{ margin-top:1.7rem; font-size:.92rem; font-weight:500; opacity:.6; }

  :focus-visible{ outline:3px solid var(--cobalt); outline-offset:2px; }

  @media (max-width:880px){
    .hero-grid{grid-template-columns:1fr;}
    .stickers, .creative-grid, .music-grid{grid-template-columns:1fr;}
    .contact-panel{grid-template-columns:1fr;}
    .sticker{transform:none !important;}
    .sticker:hover{transform:translateY(-4px) !important;}
  }
  @media (prefers-reduced-motion: reduce){
    *{animation:none !important; transition:none !important;}
  }
</style>
</head>
<body>

  <div class="ticker">
    <div class="ticker-track">
      <span>Writer <span class="dot">✦</span> Copywriter <span class="dot">✦</span> Screenwriter <span class="dot">✦</span> Lyricist <span class="dot">✦</span></span>
      <span>Writer <span class="dot">✦</span> Copywriter <span class="dot">✦</span> Screenwriter <span class="dot">✦</span> Lyricist <span class="dot">✦</span></span>
    </div>
  </div>

  <!-- HERO -->
  <section class="hero wrap" style="position:relative;">
    <div class="blob blob-1"></div>
    <div class="blob blob-2"></div>
    <div class="hero-grid">
      <div>
        <h1>Crathea</h1>
        <!-- Just trying to tell the stories I would wanna hear -->
        <p class="hero-sub">Just trying to tell the stories I would wanna hear</p>
        <div class="chip-row">
          <a href="#books" class="chip c-coral">Books</a>
          <a href="#music" class="chip c-cobalt">Music</a>
          <a href="#creative" class="chip c-lime">Advertising</a>
          <a href="#sign" class="chip" style="background:var(--sun);">You gotta try this!</a>
          <a href="#contact" class="chip">Contact</a>
        </div>
      </div>
    </div>
  </section>

  <!-- BOOKS -->
  <section id="books" class="wrap">
    <div class="heading-row">
      <h2>Books</h2>
      <p class="heading-note">Three titles, out now on Amazon (leave a review only if you like it!)</p>
    </div>
    <div class="stickers">
      <div class="sticker">
        <div class="washi"></div>
        <span class="tag coral">A novella</span>
        <div class="icon-badge">
          <svg viewBox="0 0 24 24" fill="none" stroke="var(--ink)" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M3 5.5C3 4.7 3.7 4 4.5 4H10a2 2 0 0 1 2 2v14a2 2 0 0 0-2-1.5H3.5A.5.5 0 0 1 3 18V5.5Z"/><path d="M21 5.5c0-.8-.7-1.5-1.5-1.5H14a2 2 0 0 0-2 2v14a2 2 0 0 1 2-1.5h5.5a.5.5 0 0 0 .5-.5V5.5Z"/></svg>
        </div>
        <h3>Harakiri in the Neighnourly Bastions</h3>
        <!-- A novella! -->
        <span class="edit-me">In the parallel world of Felinaz, an ambitious journey has begun. But as its residents discover...</span>
        <a class="go-link" href="https://www.amazon.com/dp/1794591842?lv=shuf&channelId=500&plpRedirect=mhFallback" target="_blank" rel="noopener">Get it on Amazon</a>
      </div>

      <div class="sticker">
        <div class="washi"></div>
        <span class="tag lime">Another novella!</span>
        <div class="icon-badge">
          <svg viewBox="0 0 24 24" fill="none" stroke="var(--ink)" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M3 5.5C3 4.7 3.7 4 4.5 4H10a2 2 0 0 1 2 2v14a2 2 0 0 0-2-1.5H3.5A.5.5 0 0 1 3 18V5.5Z"/><path d="M21 5.5c0-.8-.7-1.5-1.5-1.5H14a2 2 0 0 0-2 2v14a2 2 0 0 1 2-1.5h5.5a.5.5 0 0 0 .5-.5V5.5Z"/></svg>
        </div>
        <h3>Once Upon a Time in Marketing</h3>
        <!-- Another novella! -->
        <span class="edit-me">A shrewd marketer. A desperate activist. A frustrated writer. And a delusional entrepreneur. All striving for a world they want...</span>
        <a class="go-link" href="https://www.amazon.in/Once-Upon-Time-Marketing-Marketing-ebook/dp/B082H29B7Y" target="_blank" rel="noopener">Get it on Amazon</a>
      </div>

      <div class="sticker">
        <div class="washi"></div>
        <span class="tag sun">A survival mystery thriller!</span>
        <div class="icon-badge">
          <svg viewBox="0 0 24 24" fill="none" stroke="var(--ink)" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M3 5.5C3 4.7 3.7 4 4.5 4H10a2 2 0 0 1 2 2v14a2 2 0 0 0-2-1.5H3.5A.5.5 0 0 1 3 18V5.5Z"/><path d="M21 5.5c0-.8-.7-1.5-1.5-1.5H14a2 2 0 0 0-2 2v14a2 2 0 0 1 2-1.5h5.5a.5.5 0 0 0 .5-.5V5.5Z"/></svg>
        </div>
        <h3>Crushland</h3>
        <!-- A novel -->
        <span class="edit-me">When stuck on an island with three ex-crushes, it's far from romantic</span>
        <a class="go-link" href="https://www.amazon.com/Crushland-Crathea-Katariya-ebook/dp/B08QH18L9L?ref_=ast_author_dp&th=1&psc=1" target="_blank" rel="noopener">Get it on Amazon</a>
      </div>
    </div>
  </section>

  <!-- CREATIVE PRACTICE -->
  <section id="creative" class="band-lime">
    <div class="wrap">
      <div class="heading-row">
        <h2>All about insights!</h2>
        <p class="heading-note">Some of my advertising work and other writings</p>
      </div>
      <div class="creative-grid">
        <div class="sticker">
          <div class="washi"></div>
          <span class="tag cobalt">Portfolio</span>
          <div class="icon-badge">
            <svg viewBox="0 0 24 24" fill="none" stroke="var(--ink)" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M12 19l7-7 3 3-7 7-3-3z"/><path d="M18 13l-1.5-7.5L2 2l3.5 14.5L13 18l5-5z"/><path d="M2 2l7.586 7.586"/><circle cx="11" cy="11" r="2"/></svg>
          </div>
          <h3>Advertising portfolio</h3>
          <!-- Some of my work as an advertising writer and Creative Director -->
          <span class="edit-me">Some of my work as an advertising writer and Creative Director</span>
          <a class="go-link" href="https://www.behance.net/crathea" target="_blank" rel="noopener">View on Behance</a>
        </div>
        <div class="sticker">
          <div class="washi"></div>
          <span class="tag coral">Blog</span>
          <div class="icon-badge">
            <svg viewBox="0 0 24 24" fill="none" stroke="var(--ink)" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M12 20h9"/><path d="M16.5 3.5a2.12 2.12 0 0 1 3 3L7 19l-4 1 1-4L16.5 3.5z"/></svg>
          </div>
          <h3>Blog posts</h3>
          <!-- Essays, poems, short-stories and what not! -->
          <span class="edit-me">Essays, poems, short-stories and what not!</span>
          <a class="go-link" href="https://crathea.substack.com/" target="_blank" rel="noopener">Read the blog</a>
        </div>
      </div>
    </div>
  </section>

  <!-- MUSIC -->
  <section id="music" class="band-cobalt">
    <div class="wrap">
      <div class="heading-row">
        <h2>Music</h2>
        <p class="heading-note">My experiments with words in the musical form</p>
      </div>
      <div class="music-grid">
        <div class="sticker">
          <div class="washi"></div>
          <span class="tag lime">Album</span>
          <div class="icon-badge">
            <svg viewBox="0 0 24 24" fill="none" stroke="var(--ink)" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M9 18V5l12-2v13"/><circle cx="6" cy="18" r="3"/><circle cx="18" cy="16" r="3"/></svg>
          </div>
          <h3>Latest album</h3>
          <!-- Koi Aur Chaara Ni -->
          <span class="edit-me">  </span>
          <a class="go-link" href="https://open.spotify.com/album/1r3uPIixkTHcjWEM3QKNqH" target="_blank" rel="noopener">Play on Spotify</a>
        </div>
        <div class="sticker">
          <div class="washi"></div>
          <span class="tag sun">Channel</span>
          <div class="icon-badge">
            <svg viewBox="0 0 24 24" fill="none" stroke="var(--ink)" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><polygon points="10 8 16 12 10 16 10 8"/><rect x="2" y="4" width="20" height="16" rx="4"/></svg>
          </div>
          <h3>Studio Kalyug</h3>
          <!-- Some videos to go with the songs -->
          <span class="edit-me">  </span>
          <a class="go-link" href="https://youtube.com/@studiokalyug" target="_blank" rel="noopener">Watch on YouTube</a>
        </div>
        <div class="sticker">
          <div class="washi"></div>
          <span class="tag coral">Playlist</span>
          <div class="icon-badge">
            <svg viewBox="0 0 24 24" fill="none" stroke="var(--ink)" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M9 18V5l12-2v13"/><circle cx="6" cy="18" r="3"/><circle cx="18" cy="16" r="3"/></svg>
          </div>
          <h3>Full playlist</h3>
          <!-- Explore other albums as well-->
          <span class="edit-me">  </span>
          <a class="go-link" href="https://music.youtube.com/playlist?list=OLAK5uy_nzsobNcbUMKirnGTtMJo35fdupn2NVHbQ" target="_blank" rel="noopener">Stream it</a>
        </div>
      </div>
    </div>
  </section>

  <!-- CONTACT -->
  <!-- SIGN -->
  <section id="sign" class="band-sun">
    <div class="wrap oracle-wrap">
      <p class="oracle-intro">If you're looking for a sign for whatever it is in your life or mind, look no further! <em>In fact, look below:</em></p>

      <div class="oracle-seal" id="oracleSeal" role="button" tabindex="0" aria-label="Tap to draw a sign">
        <div class="oracle-tape"></div>
        <span class="oracle-result" id="signText" aria-live="polite">✦</span>
      </div>
      <p class="oracle-caption" id="oracleCaption">Tap the seal for your sign</p>
    </div>
  </section>

  <section id="contact" class="wrap">
    <div class="contact-panel">
      <div>
        <h2>Just a mail and an exciting opportunity away!</h2>
        <!-- Let's hope the algorithms don't send it to spam -->
        <span class="edit-me on-dark">  </span>
        <a class="email-link" href="mailto:prakashkatariyalight@gmail.com">prakashkatariyalight@gmail.com</a>
      </div>
      <form id="contactForm">
        <div class="form-group">
          <label for="name">Name</label>
          <input type="text" id="name" name="name" required>
        </div>
        <div class="form-group">
          <label for="email">Email</label>
          <input type="email" id="email" name="email" required>
        </div>
        <div class="form-group">
          <label for="message">Message</label>
          <textarea id="message" name="message" required></textarea>
        </div>
        <button type="submit" class="submit-btn">Send message</button>
      </form>
    </div>
  </section>

  <footer class="wrap">
    <div class="footer-row">
      <p>© 2026 Crathea. May you get wise!</p>
      <div class="social-row">
        <a href="https://www.behance.net/crathea" target="_blank" rel="noopener" aria-label="Behance" title="Behance">
          <svg viewBox="0 0 24 24" fill="none" stroke="var(--ink)" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M12 19l7-7 3 3-7 7-3-3z"/><path d="M18 13l-1.5-7.5L2 2l3.5 14.5L13 18l5-5z"/></svg>
        </a>
        <a href="https://crathea.substack.com/" target="_blank" rel="noopener" aria-label="Substack" title="Substack">
          <svg viewBox="0 0 24 24" fill="none" stroke="var(--ink)" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M12 20h9"/><path d="M16.5 3.5a2.12 2.12 0 0 1 3 3L7 19l-4 1 1-4L16.5 3.5z"/></svg>
        </a>
        <a href="https://youtube.com/@studiokalyug" target="_blank" rel="noopener" aria-label="YouTube" title="YouTube">
          <svg viewBox="0 0 24 24" fill="none" stroke="var(--ink)" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><polygon points="10 8 16 12 10 16 10 8"/><rect x="2" y="4" width="20" height="16" rx="4"/></svg>
        </a>
        <a href="https://open.spotify.com/album/1r3uPIixkTHcjWEM3QKNqH" target="_blank" rel="noopener" aria-label="Spotify" title="Spotify">
          <svg viewBox="0 0 24 24" fill="none" stroke="var(--ink)" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M9 18V5l12-2v13"/><circle cx="6" cy="18" r="3"/><circle cx="18" cy="16" r="3"/></svg>
        </a>
      </div>
    </div>
  </footer>

<script>
  (function(){
    // Fragments, not finished lines — the sign is assembled fresh each time,
    // not picked from a fixed list. Deliberately open to interpretation.
    var OPEN = [
      "Not everything needs an answer",
      "The timing knows something you don't",
      "It's already changing shape",
      "Nothing here is as loud as it seems",
      "The middle is longer than it looks",
      "Some doors open by staying shut",
      "You're closer than the noise suggests",
      "The pattern isn't finished with you yet",
      "There's more time than it feels like",
      "It rearranges itself when you're not looking",
      "The quiet is doing something too",
      "Not all signs point forward",
      "What you're circling already knows you",
      "The answer was never the point",
      "Some things arrive sideways",
      "It's smaller than the story you built around it",
      "The version of you that's waiting isn't far",
      "This isn't the whole picture",
      "It's already begun",
      "The weight is doing its own work",
      "Nothing is as finished as it looks",
      "The space between isn't empty",
      "It's asking for less rather than more",
      "You already passed the hard part",
      "The shape of it hasn't settled yet",
      "Some things need to stay unclear a little longer",
      "You're not ready to see it yet",
      "The noise was never the message",
      "There's a slower version of this that's true too",
      "What's underneath is quieter than what's on top"
    ];
    var CLOSE = [
      "and that's not nothing",
      "even if it doesn't feel like it yet",
      "though not in the way you expect",
      "and it already knows the way",
      "but only when you stop pushing",
      "and it's closer than you think",
      "even now",
      "though it won't announce itself",
      "and the timing is doing its part",
      "but not on your schedule",
      "and that's allowed",
      "though you already sense it",
      "even if it takes longer than planned",
      "and it's already in motion",
      "but softer than you expect",
      "and it doesn't need your permission",
      "though it's easy to miss",
      "and that's the quiet part",
      "even when it looks like nothing",
      "but it's not finished yet",
      "and neither are you",
      "though it's not loud about it",
      "and it's been patient",
      "but that's not a bad thing",
      "even if you can't name it yet",
      "and it already made room for you",
      "though the shape is still forming",
      "and it's not asking you to hurry",
      "but it's paying attention",
      "even in the parts you're avoiding"
    ];
    var SHORT = [
      "Soon.", "Not yet.", "Wait.", "Again.", "Maybe.", "Here.",
      "Elsewhere.", "Both.", "Neither.", "Quietly.", "Still.",
      "Already.", "Almost.", "Later.", "Slowly."
    ];
    var SYMBOL = ["✦","✧","☾","◐","◑","∞","❖","⟡","☉","✺","⋆","◈"];

    function pick(arr){ return arr[Math.floor(Math.random() * arr.length)]; }

    function generate(){
      var r = Math.random();
      if (r < 0.12) return pick(SYMBOL);
      if (r < 0.24) return pick(SHORT);
      var a = pick(OPEN);
      if (Math.random() < 0.55) return a + ', ' + pick(CLOSE) + '.';
      return a + '.';
    }

    var seal = document.getElementById('oracleSeal');
    var text = document.getElementById('signText');
    var caption = document.getElementById('oracleCaption');
    var last = null;

    function draw(){
      if(seal.classList.contains('spin')) return;
      seal.classList.add('spin');
      setTimeout(function(){
        var next, attempts = 0;
        do { next = generate(); attempts++; }
        while (next === last && attempts < 5);
        last = next;
        text.textContent = next;
      }, 240);
      setTimeout(function(){
        seal.classList.remove('spin');
        caption.textContent = 'Think of something else, and tap again!';
      }, 560);
    }

    seal.addEventListener('click', draw);
    seal.addEventListener('keydown', function(e){
      if(e.key === 'Enter' || e.key === ' '){ e.preventDefault(); draw(); }
    });
  })();

  document.getElementById('contactForm').addEventListener('submit', function(e){
    e.preventDefault();
    const name = document.getElementById('name').value;
    const email = document.getElementById('email').value;
    const message = document.getElementById('message').value;
    const subject = encodeURIComponent('New message from ' + name);
    const body = encodeURIComponent('Name: ' + name + '\nEmail: ' + email + '\n\n' + message);
    window.location.href = 'mailto:prakashkatariyalight@gmail.com?subject=' + subject + '&body=' + body;
  });
</script>
</body>
</html>

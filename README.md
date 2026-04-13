<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Cult of Ghoul | Dawn Dream House</title>
  <meta name="description" content="Cult of Ghoul, a Dawn Dream House built on loyalty, family, power, and the eternal night." />
  <style>
    :root{
      --bg:#070508;
      --bg2:#120a12;
      --panel:rgba(18,10,20,.88);
      --panel-2:rgba(26,14,28,.92);
      --text:#f4ebf2;
      --muted:#c6b7c7;
      --accent:#b10f3a;
      --accent-dark:#6c0c28;
      --gold:#d7ae63;
      --line:rgba(255,255,255,.08);
      --shadow:0 14px 40px rgba(0,0,0,.45);
      --radius:20px;
      --max:1200px;
    }

    *{box-sizing:border-box;margin:0;padding:0}
    html{scroll-behavior:smooth}
    body{
      font-family: Georgia, "Times New Roman", serif;
      color:var(--text);
      background:
        radial-gradient(circle at top, rgba(177,15,58,.15), transparent 26%),
        linear-gradient(180deg, #050406 0%, #0b070d 50%, #120912 100%);
      overflow-x:hidden;
    }

    body::before{
      content:"";
      position:fixed;
      inset:0;
      pointer-events:none;
      background:
        radial-gradient(circle at 20% 30%, rgba(255,255,255,.03), transparent 20%),
        radial-gradient(circle at 70% 18%, rgba(177,15,58,.08), transparent 18%),
        radial-gradient(circle at 50% 85%, rgba(177,15,58,.12), transparent 22%);
      animation:fogShift 18s ease-in-out infinite alternate;
      z-index:0;
    }

    @keyframes fogShift{
      0%{transform:translateY(0px) scale(1)}
      100%{transform:translateY(-18px) scale(1.03)}
    }

    .blood-drips{
      position:fixed;
      top:0;
      left:0;
      width:100%;
      height:110px;
      pointer-events:none;
      z-index:999;
      opacity:.9;
    }

    .blood-drips span{
      position:absolute;
      top:0;
      width:26px;
      background:linear-gradient(180deg, #7c0d28, #3f0816);
      border-radius:0 0 14px 14px;
      box-shadow:0 0 18px rgba(177,15,58,.22);
      animation:drip 5s ease-in-out infinite;
    }

    .blood-drips span::after{
      content:"";
      position:absolute;
      bottom:-12px;
      left:50%;
      width:18px;
      height:18px;
      transform:translateX(-50%);
      border-radius:50%;
      background:#5a0a20;
    }

    .blood-drips span:nth-child(1){left:4%;height:48px;animation-delay:.2s}
    .blood-drips span:nth-child(2){left:12%;height:66px;animation-delay:1.4s}
    .blood-drips span:nth-child(3){left:23%;height:40px;animation-delay:.7s}
    .blood-drips span:nth-child(4){left:35%;height:72px;animation-delay:2.2s}
    .blood-drips span:nth-child(5){left:51%;height:52px;animation-delay:1.1s}
    .blood-drips span:nth-child(6){left:63%;height:64px;animation-delay:2.8s}
    .blood-drips span:nth-child(7){left:75%;height:44px;animation-delay:.9s}
    .blood-drips span:nth-child(8){left:87%;height:70px;animation-delay:1.9s}
    .blood-drips span:nth-child(9){left:95%;height:38px;animation-delay:3.2s}

    @keyframes drip{
      0%,100%{transform:translateY(0)}
      50%{transform:translateY(10px)}
    }

    a{text-decoration:none;color:inherit}
    img{display:block;max-width:100%}

    .container{
      width:min(92%, var(--max));
      margin:0 auto;
      position:relative;
      z-index:1;
    }

    header{
      position:sticky;
      top:0;
      z-index:100;
      backdrop-filter:blur(10px);
      background:rgba(9,6,10,.72);
      border-bottom:1px solid var(--line);
    }

    .topbar{
      min-height:78px;
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:20px;
      padding:14px 0;
    }

    .brand small{
      display:block;
      color:var(--gold);
      text-transform:uppercase;
      letter-spacing:.2em;
      font-size:.72rem;
      margin-bottom:4px;
    }

    .brand strong{
      display:block;
      text-transform:uppercase;
      letter-spacing:.08em;
      font-size:1.18rem;
    }

    nav{
      display:flex;
      flex-wrap:wrap;
      gap:16px;
    }

    nav a{
      color:var(--muted);
      transition:.25s ease;
      font-size:.96rem;
    }

    nav a:hover{
      color:#fff;
      text-shadow:0 0 10px rgba(177,15,58,.35);
    }

    .hero{
      min-height:100vh;
      display:grid;
      place-items:center;
      position:relative;
      overflow:hidden;
      border-bottom:1px solid var(--line);
      background:
        linear-gradient(rgba(6,4,7,.38), rgba(6,4,7,.78)),
        url("banner-main.jpg") center/cover no-repeat;
    }

    .hero::before{
      content:"";
      position:absolute;
      inset:0;
      background:
        radial-gradient(circle at center, rgba(177,15,58,.14), transparent 35%),
        linear-gradient(180deg, rgba(0,0,0,.15), rgba(0,0,0,.62));
    }

    .hero-overlay{
      position:absolute;
      inset:0;
      background:
        linear-gradient(90deg, rgba(0,0,0,.45), transparent 20%, transparent 80%, rgba(0,0,0,.45)),
        radial-gradient(circle at 50% 75%, rgba(177,15,58,.14), transparent 25%);
      pointer-events:none;
    }

    .hero-content{
      position:relative;
      z-index:2;
      text-align:center;
      max-width:920px;
      padding:110px 0 80px;
    }

    .eyebrow{
      display:inline-block;
      padding:8px 14px;
      border:1px solid rgba(215,174,99,.35);
      border-radius:999px;
      color:var(--gold);
      letter-spacing:.18em;
      text-transform:uppercase;
      font-size:.72rem;
      background:rgba(255,255,255,.04);
      margin-bottom:20px;
    }

    h1{
      font-size:clamp(2.7rem, 8vw, 5.5rem);
      line-height:1.02;
      letter-spacing:.06em;
      text-transform:uppercase;
      text-shadow:0 0 20px rgba(177,15,58,.2);
    }

    .hero p{
      margin:22px auto 30px;
      max-width:720px;
      font-size:clamp(1rem, 2vw, 1.16rem);
      color:var(--muted);
    }

    .hero-cta{
      display:flex;
      flex-wrap:wrap;
      justify-content:center;
      gap:14px;
    }

    .btn{
      display:inline-flex;
      align-items:center;
      justify-content:center;
      padding:14px 22px;
      border-radius:999px;
      font-weight:bold;
      transition:.25s ease;
      border:1px solid transparent;
      box-shadow:var(--shadow);
      min-width:180px;
    }

    .btn-primary{
      background:linear-gradient(135deg, var(--accent), var(--accent-dark));
      color:#fff;
    }

    .btn-primary:hover{
      transform:translateY(-2px);
      box-shadow:0 0 0 1px rgba(255,255,255,.08), 0 12px 28px rgba(177,15,58,.28);
    }

    .btn-secondary{
      background:rgba(255,255,255,.04);
      border-color:var(--line);
      color:var(--text);
    }

    .btn-secondary:hover{
      transform:translateY(-2px);
      background:rgba(255,255,255,.07);
    }

    .hero-gallery{
      margin-top:38px;
      display:grid;
      grid-template-columns:repeat(3, 1fr);
      gap:18px;
    }

    .hero-card{
      background:rgba(12,8,14,.72);
      border:1px solid rgba(255,255,255,.08);
      border-radius:18px;
      overflow:hidden;
      box-shadow:var(--shadow);
      transform:translateY(0);
      transition:.3s ease;
    }

    .hero-card:hover{
      transform:translateY(-4px);
    }

    .hero-card img{
      width:100%;
      height:260px;
      object-fit:cover;
      filter:brightness(.88) contrast(1.04);
    }

    .hero-card .caption{
      padding:14px;
      color:var(--muted);
      font-size:.95rem;
      text-align:center;
    }

    section{
      padding:88px 0;
      position:relative;
      z-index:1;
    }

    .section-title{
      text-align:center;
      font-size:clamp(1.8rem, 4vw, 3rem);
      text-transform:uppercase;
      letter-spacing:.08em;
      margin-bottom:14px;
    }

    .section-intro{
      text-align:center;
      color:var(--muted);
      max-width:760px;
      margin:0 auto 44px;
    }

    .panel{
      background:var(--panel);
      border:1px solid var(--line);
      border-radius:var(--radius);
      box-shadow:var(--shadow);
    }

    .about-grid{
      display:grid;
      grid-template-columns:1.1fr .9fr;
      gap:26px;
      align-items:center;
      padding:28px;
    }

    .crest-box{
      aspect-ratio:1/1;
      width:100%;
      max-width:400px;
      margin:0 auto;
      border-radius:50%;
      display:grid;
      place-items:center;
      background:
        radial-gradient(circle at center, rgba(177,15,58,.25), transparent 40%),
        linear-gradient(180deg, #140c15, #070507);
      border:1px solid rgba(215,174,99,.3);
      box-shadow:inset 0 0 34px rgba(177,15,58,.12), 0 0 30px rgba(0,0,0,.25);
      position:relative;
      overflow:hidden;
    }

    .crest-box::before{
      content:"☾";
      position:absolute;
      top:12%;
      color:rgba(215,174,99,.16);
      font-size:4rem;
    }

    .crest-box::after{
      content:"✦";
      position:absolute;
      bottom:12%;
      color:rgba(215,174,99,.16);
      font-size:2rem;
    }

    .crest-inner{
      text-align:center;
      padding:20px;
    }

    .crest-icon{
      font-size:5rem;
      line-height:1;
      margin-bottom:12px;
      filter:drop-shadow(0 0 14px rgba(177,15,58,.32));
    }

    .crest-title{
      font-size:2rem;
      text-transform:uppercase;
      letter-spacing:.14em;
      margin-bottom:8px;
    }

    .crest-sub{
      color:var(--gold);
      text-transform:uppercase;
      letter-spacing:.13em;
      font-size:.85rem;
    }

    .list{
      display:grid;
      gap:14px;
      margin-top:18px;
    }

    .list-item{
      padding:14px 16px;
      background:rgba(255,255,255,.03);
      border-left:3px solid var(--accent);
      border-radius:10px;
      color:var(--muted);
    }

    .cards{
      display:grid;
      grid-template-columns:repeat(3, 1fr);
      gap:22px;
    }

    .card{
      background:var(--panel-2);
      border:1px solid var(--line);
      border-radius:18px;
      padding:24px;
      box-shadow:var(--shadow);
      transition:.28s ease;
    }

    .card:hover{
      transform:translateY(-4px);
      border-color:rgba(215,174,99,.22);
    }

    .card h3{
      margin-bottom:10px;
      color:var(--gold);
      text-transform:uppercase;
      letter-spacing:.06em;
      font-size:1rem;
    }

    .card p{
      color:var(--muted);
    }

    .quote{
      text-align:center;
      padding:30px;
      border-top:1px solid rgba(215,174,99,.2);
      border-bottom:1px solid rgba(215,174,99,.2);
      font-size:clamp(1.25rem, 3vw, 2rem);
      max-width:850px;
      margin:0 auto;
    }

    .quote span{
      display:block;
      margin-top:12px;
      color:var(--gold);
      text-transform:uppercase;
      letter-spacing:.16em;
      font-size:.88rem;
    }

    .rank-grid{
      display:grid;
      grid-template-columns:repeat(3, 1fr);
      gap:22px;
    }

    .rank-card{
      background:linear-gradient(180deg, rgba(23,12,24,.96), rgba(15,8,16,.96));
      border:1px solid var(--line);
      border-radius:20px;
      padding:28px 22px;
      text-align:center;
      box-shadow:var(--shadow);
      transition:transform .28s ease, box-shadow .28s ease, border-color .28s ease;
    }

    .rank-card h3{
      color:var(--gold);
      text-transform:uppercase;
      letter-spacing:.1em;
      margin-bottom:8px;
      font-size:1rem;
    }

    .rank-card p{
      color:var(--muted);
      font-size:1.02rem;
    }

    .rank-card.high:hover{
      transform:translateY(-6px);
      border-color:rgba(177,15,58,.5);
      box-shadow:0 0 28px rgba(177,15,58,.28), 0 14px 40px rgba(0,0,0,.45);
    }

    .rank-card.grand:hover{
      transform:translateY(-6px);
      border-color:rgba(215,174,99,.5);
      box-shadow:0 0 28px rgba(215,174,99,.24), 0 14px 40px rgba(0,0,0,.45);
    }

    .rank-card.centurion:hover{
      transform:translateY(-6px);
      border-color:rgba(190,190,220,.4);
      box-shadow:0 0 28px rgba(185,185,220,.18), 0 14px 40px rgba(0,0,0,.45);
    }

    .audio-box{
      padding:28px;
      text-align:center;
    }

    .audio-box h3{
      color:var(--gold);
      text-transform:uppercase;
      letter-spacing:.08em;
      margin-bottom:10px;
    }

    .audio-box p{
      color:var(--muted);
      margin-bottom:18px;
    }

    audio{
      width:min(100%, 640px);
      filter:drop-shadow(0 8px 20px rgba(0,0,0,.35));
    }

    footer{
      border-top:1px solid var(--line);
      background:rgba(0,0,0,.18);
      padding:40px 0 56px;
      text-align:center;
      color:var(--muted);
    }

    footer strong{color:var(--text)}

    .reveal{
      opacity:0;
      transform:translateY(26px);
      transition:opacity .7s ease, transform .7s ease;
    }

    .reveal.show{
      opacity:1;
      transform:translateY(0);
    }

    @media (max-width: 980px){
      .about-grid,
      .cards,
      .rank-grid,
      .hero-gallery{
        grid-template-columns:1fr;
      }

      .topbar{
        flex-direction:column;
        align-items:flex-start;
      }
    }

    @media (max-width: 680px){
      .hero{
        min-height:auto;
      }

      .hero-content{
        padding:110px 0 70px;
      }

      .btn{
        width:100%;
      }

      .hero-cta{
        flex-direction:column;
      }
    }
  </style>
</head>
<body>
  <div class="blood-drips">
    <span></span><span></span><span></span><span></span><span></span>
    <span></span><span></span><span></span><span></span>
  </div>

  <header>
    <div class="container topbar">
      <div class="brand">
        <small>Dawn Dream House</small>
        <strong>Cult of Ghoul</strong>
      </div>

      <nav>
        <a href="index.html">Home</a>
        <a href="members.html">Members</a>
        <a href="rules.html">Rules</a>
        <a href="#contact">Leadership</a>
        <a href="#podcast">Podcast</a>
      </nav>
    </div>
  </header>

  <main>
    <section class="hero">
      <div class="hero-overlay"></div>
      <div class="container hero-content reveal">
        <div class="eyebrow">Family Before Fangs • Eternal Night • Dawn Dream</div>
        <h1>The Cult of Ghoul</h1>
        <p>
          A house forged in shadow, loyalty, elegance, and resolve. We stand as one beneath the moon,
          guarding our own and carrying the name of Ghoul with pride.
        </p>

        <div class="hero-cta">
          <a class="btn btn-primary" href="members.html">Meet the House</a>
          <a class="btn btn-secondary" href="rules.html">Read the Code</a>
        </div>

        <div class="hero-gallery">
          <div class="hero-card">
            <img src="character-das.jpg" alt="Das Ghoul banner portrait">
            <div class="caption">High Reagent • Das Ghoul</div>
          </div>

          <div class="hero-card">
            <img src="character-huntrix.jpg" alt="Huntrix Ghoul banner portrait">
            <div class="caption">Grand Consul • Huntrix Ghoul</div>
          </div>

          <div class="hero-card">
            <img src="character-babu.jpg" alt="Babu banner portrait">
            <div class="caption">Centurion • Babu</div>
          </div>
        </div>
      </div>
    </section>

    <section id="about">
      <div class="container">
        <h2 class="section-title reveal">About the House</h2>
        <p class="section-intro reveal">
          The Cult of Ghoul is more than a title. It is a vow. We are a house built on family, discipline,
          presence, and protection. Neutral when peace has purpose. Unyielding when our own are threatened.
        </p>

        <div class="panel about-grid reveal">
          <div class="crest-box">
            <div class="crest-inner">
              <div class="crest-icon">☠</div>
              <div class="crest-title">Ghoul</div>
              <div class="crest-sub">House of the Eternal Night</div>
            </div>
          </div>

          <div>
            <h3 style="margin-bottom:12px;color:var(--gold);text-transform:uppercase;letter-spacing:.08em;">What We Stand For</h3>
            <div class="list">
              <div class="list-item"><strong style="color:var(--text);">Loyalty:</strong> We protect our family and do not abandon our own.</div>
              <div class="list-item"><strong style="color:var(--text);">Respect:</strong> Presence, discipline, and honor matter as much as power.</div>
              <div class="list-item"><strong style="color:var(--text);">Purpose:</strong> We do not lash out without reason. We choose our ground carefully.</div>
              <div class="list-item"><strong style="color:var(--text);">Legacy:</strong> A house is remembered by the strength of its bonds and the names it carries.</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="creed">
      <div class="container">
        <h2 class="section-title reveal">The Creed</h2>
        <p class="section-intro reveal">
          A house is not only walls and banners. It is the heartbeat that answers the dark.
        </p>

        <div class="cards">
          <article class="card reveal">
            <h3>Family Before Fangs</h3>
            <p>We remember who stands beside us. Power fades. Loyalty remains.</p>
          </article>

          <article class="card reveal">
            <h3>Strength With Purpose</h3>
            <p>We are not chaos for applause. When we strike, it is with intent.</p>
          </article>

          <article class="card reveal">
            <h3>Honor the Night</h3>
            <p>The gothic, the fierce, the beautiful, the feared. The night reveals us.</p>
          </article>
        </div>
      </div>
    </section>

    <section>
      <div class="container">
        <div class="quote reveal">
          “In the dark we are not lost. We are revealed.”
          <span>Cult of Ghoul</span>
        </div>
      </div>
    </section>

    <section id="contact">
      <div class="container">
        <h2 class="section-title reveal">Leadership</h2>
        <p class="section-intro reveal">
          The guiding ranks of the house. The voices that hold the line, shape the legacy, and guard the family.
        </p>

        <div class="rank-grid">
          <article class="rank-card high reveal">
            <h3>High Reagent</h3>
            <p>Das Ghoul</p>
          </article>

          <article class="rank-card grand reveal">
            <h3>Grand Consul</h3>
            <p>Huntrix Ghoul</p>
          </article>

          <article class="rank-card centurion reveal">
            <h3>Centurion</h3>
            <p>Babu</p>
          </article>
        </div>
      </div>
    </section>

    <section id="podcast">
      <div class="container">
        <h2 class="section-title reveal">The Dark Hour</h2>
        <p class="section-intro reveal">
          Add your podcast or background music below. Just replace the file name with your actual audio file.
        </p>

        <div class="panel audio-box reveal">
          <h3>Podcast Player</h3>
          <p>Replace <strong>dark-hour-episode.mp3</strong> with your real file name.</p>
          <audio controls>
            <source src="dark-hour-episode.mp3" type="audio/mpeg">
            Your browser does not support the audio player.
          </audio>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div class="container">
      <p><strong>Cult of Ghoul • Dawn Dream House</strong></p>
      <p style="margin-top:10px;">Built for the night. Bound by loyalty. Remembered by name.</p>
    </div>
  </footer>

  <script>
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('show');
        }
      });
    }, { threshold: 0.14 });

    document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
  </script>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Dawn Dream House | Cult of Ghoul</title>
  <meta
    name="description"
    content="Welcome to the Cult of Ghoul, a Dawn Dream House built on loyalty, family, and the eternal night."
  />
  <style>
    :root {
      --bg: #09070b;
      --bg-alt: #120d14;
      --panel: rgba(20, 12, 22, 0.9);
      --panel-border: rgba(163, 98, 135, 0.35);
      --text: #f3eaf2;
      --muted: #c6b3c0;
      --accent: #b10f3a;
      --accent-2: #7d1835;
      --accent-glow: rgba(177, 15, 58, 0.35);
      --gold: #d1a95a;
      --shadow: 0 10px 30px rgba(0, 0, 0, 0.45);
      --radius: 18px;
      --max-width: 1200px;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: Georgia, "Times New Roman", serif;
      background:
        radial-gradient(circle at top, rgba(110, 17, 41, 0.22), transparent 35%),
        linear-gradient(180deg, #060507 0%, #0b070d 45%, #120b12 100%);
      color: var(--text);
      line-height: 1.6;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    img {
      max-width: 100%;
      display: block;
    }

    .container {
      width: min(92%, var(--max-width));
      margin: 0 auto;
    }

    .topbar {
      position: sticky;
      top: 0;
      z-index: 1000;
      backdrop-filter: blur(10px);
      background: rgba(8, 5, 9, 0.8);
      border-bottom: 1px solid rgba(255, 255, 255, 0.08);
    }

    .topbar-inner {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 20px;
      padding: 16px 0;
    }

    .brand {
      display: flex;
      flex-direction: column;
      gap: 2px;
    }

    .brand small {
      color: var(--gold);
      letter-spacing: 0.18em;
      text-transform: uppercase;
      font-size: 0.72rem;
    }

    .brand strong {
      font-size: 1.2rem;
      letter-spacing: 0.06em;
      text-transform: uppercase;
    }

    .nav {
      display: flex;
      flex-wrap: wrap;
      gap: 16px;
      align-items: center;
    }

    .nav a {
      color: var(--muted);
      transition: 0.25s ease;
      font-size: 0.95rem;
    }

    .nav a:hover {
      color: var(--text);
    }

    .hero {
      min-height: 92vh;
      display: grid;
      place-items: center;
      position: relative;
      overflow: hidden;
      border-bottom: 1px solid rgba(255, 255, 255, 0.08);
    }

    .hero::before,
    .hero::after {
      content: "";
      position: absolute;
      inset: 0;
      pointer-events: none;
    }

    .hero::before {
      background:
        linear-gradient(rgba(0, 0, 0, 0.15), rgba(0, 0, 0, 0.6)),
        radial-gradient(circle at center, rgba(177, 15, 58, 0.12), transparent 38%);
    }

    .hero::after {
      background:
        repeating-linear-gradient(
          90deg,
          transparent 0 120px,
          rgba(255, 255, 255, 0.02) 121px 122px
        );
      opacity: 0.25;
    }

    .hero-content {
      position: relative;
      z-index: 1;
      text-align: center;
      padding: 80px 0;
      max-width: 900px;
    }

    .eyebrow {
      display: inline-block;
      margin-bottom: 18px;
      padding: 8px 14px;
      border: 1px solid rgba(209, 169, 90, 0.3);
      border-radius: 999px;
      color: var(--gold);
      text-transform: uppercase;
      letter-spacing: 0.2em;
      font-size: 0.72rem;
      background: rgba(255, 255, 255, 0.03);
    }

    h1 {
      font-size: clamp(2.5rem, 7vw, 5.2rem);
      line-height: 1.02;
      letter-spacing: 0.04em;
      text-transform: uppercase;
      text-shadow: 0 0 18px rgba(177, 15, 58, 0.2);
    }

    .hero p {
      color: var(--muted);
      font-size: clamp(1rem, 1.8vw, 1.2rem);
      max-width: 700px;
      margin: 22px auto 32px;
    }

    .cta-row {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 14px;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      padding: 14px 22px;
      border-radius: 999px;
      font-weight: bold;
      transition: 0.25s ease;
      border: 1px solid transparent;
      box-shadow: var(--shadow);
    }

    .btn-primary {
      background: linear-gradient(135deg, var(--accent), var(--accent-2));
      color: white;
    }

    .btn-primary:hover {
      transform: translateY(-2px);
      box-shadow: 0 0 0 1px rgba(255,255,255,0.08), 0 10px 28px var(--accent-glow);
    }

    .btn-secondary {
      background: rgba(255,255,255,0.04);
      border-color: rgba(255,255,255,0.1);
      color: var(--text);
    }

    .btn-secondary:hover {
      transform: translateY(-2px);
      background: rgba(255,255,255,0.07);
    }

    section {
      padding: 90px 0;
    }

    .section-title {
      text-align: center;
      margin-bottom: 18px;
      font-size: clamp(1.8rem, 4vw, 3rem);
      text-transform: uppercase;
      letter-spacing: 0.06em;
    }

    .section-intro {
      text-align: center;
      color: var(--muted);
      max-width: 760px;
      margin: 0 auto 50px;
    }

    .cards {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 22px;
    }

    .card {
      background: var(--panel);
      border: 1px solid var(--panel-border);
      border-radius: var(--radius);
      padding: 26px;
      box-shadow: var(--shadow);
    }

    .card h3 {
      margin-bottom: 10px;
      color: var(--gold);
      text-transform: uppercase;
      letter-spacing: 0.06em;
      font-size: 1rem;
    }

    .card p {
      color: var(--muted);
    }

    .crest-box {
      display: grid;
      grid-template-columns: 1.1fr 0.9fr;
      gap: 30px;
      align-items: center;
      background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border: 1px solid rgba(255,255,255,0.08);
      border-radius: var(--radius);
      padding: 30px;
      box-shadow: var(--shadow);
    }

    .crest {
      aspect-ratio: 1 / 1;
      max-width: 420px;
      width: 100%;
      margin: 0 auto;
      border-radius: 50%;
      border: 1px solid rgba(209, 169, 90, 0.35);
      display: grid;
      place-items: center;
      background:
        radial-gradient(circle at center, rgba(177, 15, 58, 0.28), transparent 48%),
        linear-gradient(180deg, #130d14, #080609);
      box-shadow:
        inset 0 0 40px rgba(177, 15, 58, 0.15),
        0 0 30px rgba(0,0,0,0.35);
      position: relative;
      overflow: hidden;
    }

    .crest::before {
      content: "☾";
      position: absolute;
      top: 12%;
      font-size: 4.2rem;
      color: rgba(209, 169, 90, 0.18);
    }

    .crest::after {
      content: "✦";
      position: absolute;
      bottom: 10%;
      font-size: 2rem;
      color: rgba(209, 169, 90, 0.18);
    }

    .crest-inner {
      text-align: center;
      padding: 20px;
    }

    .crest-skull {
      font-size: clamp(4rem, 10vw, 6rem);
      line-height: 1;
      margin-bottom: 12px;
      filter: drop-shadow(0 0 14px rgba(177, 15, 58, 0.35));
    }

    .crest-title {
      font-size: clamp(1.6rem, 4vw, 2.3rem);
      text-transform: uppercase;
      letter-spacing: 0.14em;
      margin-bottom: 8px;
    }

    .crest-sub {
      color: var(--gold);
      letter-spacing: 0.12em;
      text-transform: uppercase;
      font-size: 0.85rem;
    }

    .list {
      display: grid;
      gap: 14px;
      margin-top: 20px;
    }

    .list-item {
      padding: 14px 16px;
      border-left: 3px solid var(--accent);
      background: rgba(255,255,255,0.03);
      border-radius: 10px;
      color: var(--muted);
    }

    .quote-block {
      text-align: center;
      font-size: clamp(1.3rem, 3.2vw, 2rem);
      color: var(--text);
      max-width: 850px;
      margin: 0 auto;
      padding: 30px;
      border-top: 1px solid rgba(209, 169, 90, 0.2);
      border-bottom: 1px solid rgba(209, 169, 90, 0.2);
    }

    .quote-block span {
      display: block;
      margin-top: 12px;
      color: var(--gold);
      font-size: 0.9rem;
      text-transform: uppercase;
      letter-spacing: 0.16em;
    }

    .footer {
      padding: 40px 0 60px;
      text-align: center;
      color: var(--muted);
      border-top: 1px solid rgba(255,255,255,0.08);
      background: rgba(0,0,0,0.16);
    }

    .footer strong {
      color: var(--text);
    }

    .small-note {
      margin-top: 12px;
      font-size: 0.92rem;
    }

    @media (max-width: 900px) {
      .cards,
      .crest-box {
        grid-template-columns: 1fr;
      }

      .topbar-inner {
        flex-direction: column;
        align-items: flex-start;
      }

      .nav {
        gap: 12px;
      }
    }

    @media (max-width: 640px) {
      .hero {
        min-height: auto;
      }

      .card,
      .crest-box {
        padding: 22px;
      }

      .btn {
        width: 100%;
      }

      .cta-row {
        flex-direction: column;
      }
    }
  </style>
</head>
<body>
  <header class="topbar">
    <div class="container topbar-inner">
      <div class="brand">
        <small>Dawn Dream House</small>
        <strong>Cult of Ghoul</strong>
      </div>

      <nav class="nav">
        <a href="#about">About</a>
        <a href="#creed">Creed</a>
        <a href="#join">Join</a>
        <a href="#contact">Contact</a>
      </nav>
    </div>
  </header>

  <main>
    <section class="hero">
      <div class="container hero-content">
        <div class="eyebrow">Eternal Night • Family Before Fangs</div>
        <h1>The Cult of Ghoul</h1>
        <p>
          A house within Dawn Dream built on loyalty, protection, style, and shadow.
          We do not kneel without reason. We do not break without consequence.
          We stand for our own, and we move as one beneath the moon.
        </p>
        <div class="cta-row">
          <a class="btn btn-primary" href="#join">Enter the House</a>
          <a class="btn btn-secondary" href="#about">Read Our Lore</a>
        </div>
      </div>
    </section>

    <section id="about">
      <div class="container">
        <h2 class="section-title">About the House</h2>
        <p class="section-intro">
          The Cult of Ghoul is more than a name. It is a vow. A gathering of those
          who value family, presence, and power tempered by purpose. We are a neutral
          force when peace is possible, and an iron wall when our own are threatened.
        </p>

        <div class="crest-box">
          <div class="crest">
            <div class="crest-inner">
              <div class="crest-skull">☠</div>
              <div class="crest-title">Ghoul</div>
              <div class="crest-sub">House of the Eternal Night</div>
            </div>
          </div>

          <div>
            <h3 style="margin-bottom: 12px; color: var(--gold); text-transform: uppercase; letter-spacing: 0.08em;">
              What We Stand For
            </h3>
            <div class="list">
              <div class="list-item"><strong style="color: var(--text);">Loyalty:</strong> We protect our family and those under our wing.</div>
              <div class="list-item"><strong style="color: var(--text);">Respect:</strong> Power means nothing without discipline and restraint.</div>
              <div class="list-item"><strong style="color: var(--text);">Presence:</strong> We carry ourselves with style, intent, and legacy.</div>
              <div class="list-item"><strong style="color: var(--text);">Resolve:</strong> When the dark tests us, we answer with teeth bared and heads high.</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="creed">
      <div class="container">
        <h2 class="section-title">The Creed</h2>
        <p class="section-intro">
          A house is not stone and banners. A house is the heartbeat inside the dark.
        </p>

        <div class="cards">
          <article class="card">
            <h3>Family Before Fangs</h3>
            <p>
              We remember who stands beside us. Titles fade, status turns to dust,
              but the bond of true kin remains.
            </p>
          </article>

          <article class="card">
            <h3>Strength With Purpose</h3>
            <p>
              We are not chaos for the sake of noise. We choose our battles, and when
              we strike, we do so with intent.
            </p>
          </article>

          <article class="card">
            <h3>Honor the Night</h3>
            <p>
              We embrace the gothic, the beautiful, and the feared. The night is not
              emptiness. It is where we become ourselves.
            </p>
          </article>
        </div>
      </div>
    </section>

    <section>
      <div class="container">
        <div class="quote-block">
          “In the dark we are not lost. We are revealed.”
          <span>Cult of Ghoul</span>
        </div>
      </div>
    </section>

    <section id="join">
      <div class="container">
        <h2 class="section-title">Join the Cult</h2>
        <p class="section-intro">
          Seekers of the moonlit path, the gates are open to those who carry loyalty,
          style, and hunger for something greater than themselves.
        </p>

        <div class="cards">
          <article class="card">
            <h3>Who We Welcome</h3>
            <p>
              Members who value house loyalty, respect for others, and a strong gothic
              identity within the Dawn Dream world.
            </p>
          </article>

          <article class="card">
            <h3>What We Offer</h3>
            <p>
              Community, protection, shared presence, house identity, and a place
              where your character and story can grow.
            </p>
          </article>

          <article class="card">
            <h3>How to Join</h3>
            <p>
              Contact the house leadership in-world or through your listed socials,
              then step forward and prove your place among the Ghouls.
            </p>
          </article>
        </div>
      </div>
    </section>

    <section id="contact">
      <div class="container">
        <h2 class="section-title">Contact</h2>
        <p class="section-intro">
          Replace the text below with your actual names, Discord, Second Life contact,
          or any links you want visitors to use.
        </p>

        <div class="cards">
          <article class="card">
            <h3>House Leader</h3>
            <p>Das Ghoul</p>
          </article>

          <article class="card">
            <h3>Co-Lead / Host</h3>
            <p>Huntrix Ghoul</p>
          </article>

          <article class="card">
            <h3>Discord / In-World</h3>
            <p>Add your invite link, profile link, or contact details here.</p>
          </article>
        </div>
      </div>
    </section>
  </main>

  <footer class="footer">
    <div class="container">
      <p><strong>Dawn Dream House • Cult of Ghoul</strong></p>
      <p class="small-note">
        Built for the night, bound by loyalty, remembered by name.
      </p>
    </div>
  </footer>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Cult of Ghoul | Members</title>
  <style>
    :root{
      --bg:#070508;
      --bg2:#120a12;
      --panel:rgba(18,10,20,.9);
      --text:#f4ebf2;
      --muted:#c6b7c7;
      --accent:#b10f3a;
      --gold:#d7ae63;
      --line:rgba(255,255,255,.08);
      --shadow:0 14px 40px rgba(0,0,0,.45);
      --radius:20px;
      --max:1200px;
    }

    *{box-sizing:border-box;margin:0;padding:0}
    body{
      font-family:Georgia,"Times New Roman",serif;
      color:var(--text);
      background:
        radial-gradient(circle at top, rgba(177,15,58,.15), transparent 26%),
        linear-gradient(180deg, #050406 0%, #0b070d 50%, #120912 100%);
      overflow-x:hidden;
    }

    a{text-decoration:none;color:inherit}
    .container{width:min(92%, var(--max));margin:0 auto}
    header{
      position:sticky;top:0;z-index:10;
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
      display:block;color:var(--gold);text-transform:uppercase;letter-spacing:.2em;font-size:.72rem;margin-bottom:4px;
    }

    .brand strong{
      display:block;text-transform:uppercase;letter-spacing:.08em;font-size:1.18rem;
    }

    nav{display:flex;flex-wrap:wrap;gap:16px}
    nav a{color:var(--muted);transition:.25s ease}
    nav a:hover{color:#fff}

    .hero{
      padding:110px 0 50px;
      text-align:center;
    }

    .hero h1{
      font-size:clamp(2.4rem, 6vw, 4.4rem);
      text-transform:uppercase;
      letter-spacing:.08em;
      margin-bottom:16px;
    }

    .hero p{
      max-width:760px;
      margin:0 auto;
      color:var(--muted);
    }

    .member-grid{
      display:grid;
      grid-template-columns:repeat(3,1fr);
      gap:22px;
      padding:20px 0 80px;
    }

    .member-card{
      background:var(--panel);
      border:1px solid var(--line);
      border-radius:18px;
      overflow:hidden;
      box-shadow:var(--shadow);
      transition:.28s ease;
    }

    .member-card:hover{
      transform:translateY(-5px);
      border-color:rgba(215,174,99,.22);
      box-shadow:0 0 24px rgba(177,15,58,.18), var(--shadow);
    }

    .member-card img{
      width:100%;
      height:320px;
      object-fit:cover;
      background:#120a12;
    }

    .member-body{
      padding:20px;
      text-align:center;
    }

    .member-body h3{
      color:var(--gold);
      text-transform:uppercase;
      letter-spacing:.08em;
      margin-bottom:8px;
      font-size:1rem;
    }

    .member-name{
      font-size:1.2rem;
      margin-bottom:10px;
    }

    .member-body p{
      color:var(--muted);
      font-size:.97rem;
    }

    footer{
      border-top:1px solid var(--line);
      background:rgba(0,0,0,.18);
      padding:40px 0 56px;
      text-align:center;
      color:var(--muted);
    }

    @media (max-width:980px){
      .member-grid{grid-template-columns:1fr}
      .topbar{flex-direction:column;align-items:flex-start}
    }
  </style>
</head>
<body>
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
      </nav>
    </div>
  </header>

  <section class="hero">
    <div class="container">
      <h1>Members of the House</h1>
      <p>
        The names, faces, and roles that shape the Cult of Ghoul. Replace the placeholder text below
        with your real member list and biographies as your house grows.
      </p>
    </div>
  </section>

  <main class="container">
    <section class="member-grid">
      <article class="member-card">
        <img src="character-das.jpg" alt="Das Ghoul">
        <div class="member-body">
          <h3>High Reagent</h3>
          <div class="member-name">Das Ghoul</div>
          <p>Leader of the house. Keeper of its vision, presence, and will.</p>
        </div>
      </article>

      <article class="member-card">
        <img src="character-huntrix.jpg" alt="Huntrix Ghoul">
        <div class="member-body">
          <h3>Grand Consul</h3>
          <div class="member-name">Huntrix Ghoul</div>
          <p>Second voice of the house. Advisor, protector, and pillar of the family.</p>
        </div>
      </article>

      <article class="member-card">
        <img src="character-babu.jpg" alt="Babu">
        <div class="member-body">
          <h3>Centurion</h3>
          <div class="member-name">Babu</div>
          <p>Trusted blade of the house. Presence, duty, and strength in action.</p>
        </div>
      </article>

      <article class="member-card">
        <img src="member-placeholder-1.jpg" alt="Open rank member">
        <div class="member-body">
          <h3>House Member</h3>
          <div class="member-name">Add Name Here</div>
          <p>Add another member, rank, and short description here.</p>
        </div>
      </article>

      <article class="member-card">
        <img src="member-placeholder-2.jpg" alt="Open rank member">
        <div class="member-body">
          <h3>House Member</h3>
          <div class="member-name">Add Name Here</div>
          <p>Add another member, rank, and short description here.</p>
        </div>
      </article>

      <article class="member-card">
        <img src="member-placeholder-3.jpg" alt="Open rank member">
        <div class="member-body">
          <h3>House Member</h3>
          <div class="member-name">Add Name Here</div>
          <p>Add another member, rank, and short description here.</p>
        </div>
      </article>
    </section>
  </main>

  <footer>
    <div class="container">
      <p>Cult of Ghoul • Members of the Night</p>
    </div>
  </footer>
</body>
</html>

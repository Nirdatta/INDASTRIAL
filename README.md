<!DOCTYPE html>
<html lang="it">
<head>
  <meta charset="UTF-8">
  <title>INDASTRIAL</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background-color: #f0f4f8;
      color: #1a1a1a;
      scroll-behavior: smooth;
      line-height: 1.6;
    }

    .version-label {
      position: fixed;
      top: 10px;
      left: 20px;
      background-color: #0055cc;
      color: white;
      padding: 6px 12px;
      font-size: 0.85em;
      font-weight: bold;
      border-radius: 6px;
      z-index: 1000;
      box-shadow: 0 2px 6px rgba(0,0,0,0.15);
    }

    header {
      text-align: center;
      padding: 100px 20px 60px;
      background: linear-gradient(135deg, #00aaff, #0055cc);
      color: white;
    }

    h1 {
      font-size: 3.5em;
      margin: 0;
      letter-spacing: 2px;
    }

    h2 {
      font-size: 1.8em;
      color: #0055cc;
      margin-top: 0;
    }

    .buttons {
      margin-top: 40px;
    }

    .buttons button {
      background: linear-gradient(135deg, #ffffff, #e0f0ff);
      color: #0055cc;
      border: 2px solid #0055cc;
      padding: 12px 25px;
      font-size: 1em;
      margin: 10px;
      border-radius: 30px;
      cursor: pointer;
      transition: all 0.3s ease;
      font-weight: bold;
    }

    .buttons button:hover {
      background: #0055cc;
      color: white;
    }

    section {
      padding: 80px 20px;
      max-width: 900px;
      margin: auto;
    }

    .section-card {
      background-color: #ffffff;
      border-radius: 12px;
      box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
      padding: 40px;
      margin-bottom: 40px;
      animation: fadeIn 0.6s ease forwards;
    }

    #scopri, #contatti, #social {
      display: none;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    form {
      display: flex;
      flex-direction: column;
      gap: 20px;
    }

    input, textarea {
      padding: 15px;
      font-size: 1em;
      border: 1px solid #ccc;
      border-radius: 8px;
      background-color: #fdfdfd;
      color: #121212;
    }

    textarea {
      resize: vertical;
      min-height: 120px;
    }

    button[type="submit"] {
      background: linear-gradient(135deg, #00aaff, #0055cc);
      color: white;
      border: none;
      font-weight: bold;
      padding: 12px;
      border-radius: 30px;
      cursor: pointer;
      transition: background 0.3s ease;
    }

    button[type="submit"]:hover {
      background: #0048a3;
    }

    a.social-link {
      display: inline-block;
      color: #0055cc;
      font-weight: bold;
      margin: 10px 15px 0 0;
      text-decoration: none;
      padding: 10px 15px;
      border: 1px solid #0055cc;
      border-radius: 20px;
      transition: all 0.3s ease;
    }

    a.social-link:hover {
      background-color: #0055cc;
      color: white;
    }
  </style>
</head>
<body>

  <!-- Etichetta versione -->
  <div class="version-label">sito web indastrial 2.0</div>

  <!-- HEADER -->
  <header>
    <h1>INDASTRIAL</h1>
    <h2>top città di Minecraft</h2>
    <div class="buttons">
      <button onclick="showSection('scopri')" aria-label="Scopri di più su Indastrial">Scopri di più</button>
      <button onclick="showSection('contatti')" aria-label="Contattaci tramite il modulo">Contattaci</button>
      <button onclick="showSection('social')" aria-label="Visita i nostri social network">Social</button>
    </div>
  </header>

  <!-- SEZIONE SCOPRI -->
  <section id="scopri" class="section-card">
    <h2>Chi siamo</h2>
    <p>
      Ciao, siamo tre ragazzi che costruiamo INDASTRIAL, un mondo unico e un server di Minecraft.<br>
      La nostra città è piena di edifici, case, strutture reali come la Casa Bianca e le TORRI GEMELLE, oltre a monumenti originali creati da noi!
    </p>
  </section>

  <!-- SEZIONE CONTATTACI -->
  <section id="contatti" class="section-card">
    <h2>Contattaci</h2>
    <form action="mailto:indastrialstaff@gmail.com" method="POST" enctype="text/plain">
      <input type="text" name="Nome" placeholder="Nome Utente" required>
      <input type="email" name="Email" placeholder="Email" required>
      <textarea name="Messaggio" placeholder="Scrivi il tuo messaggio..." required></textarea>
      <button type="submit">Invia</button>
    </form>
  </section>

  <!-- SEZIONE SOCIAL -->
  <section id="social" class="section-card">
    <h2>Seguici sui social</h2>
    <a class="social-link" href="https://youtube.com/@indastrialofficial-u9m?si=rtqZpgclGmGtp1Z7" target="_blank">YouTube</a>
    <a class="social-link" href="https://whatsapp.com/channel/0029Vb6tN94J3jv2rC9Gvz1V" target="_blank">WhatsApp</a>
    <a class="social-link" href="https://www.tiktok.com/@indastrial_minecraft?_t=ZN-8yTzPH7el2E&_r=1" target="_blank">TikTok</a>
    <a class="social-link" href="https://www.instagram.com/indastrial_minecraft?utm_source=qr&igsh=MTd5MHBwanlqODI5NQ==" target="_blank">Instagram</a>
  </section>

  <!-- JAVASCRIPT -->
  <script>
    function showSection(sectionId) {
      const sections = ['scopri', 'contatti', 'social'];
      sections.forEach(id => {
        document.getElementById(id).style.display = (id === sectionId) ? 'block' : 'none';
      });

      const section = document.getElementById(sectionId);
      if (section) {
        section.scrollIntoView({ behavior: 'smooth' });
      }
    }
  </script>

</body>
</html>


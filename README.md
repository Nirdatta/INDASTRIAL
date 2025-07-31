<!DOCTYPE html>
<html lang="it">
<head>
  <meta charset="UTF-8">
  <title>INDASTRIAL</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <style>
    /* Stile base */
    body {
      margin: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background-color: #121212;
      color: #f0f0f0;
      scroll-behavior: smooth;
    }

    header {
      text-align: center;
      padding: 100px 20px 50px;
      background: linear-gradient(135deg, #00ffcc, #0077b6);
    }

    h1 {
      font-size: 4em;
      margin: 0;
      letter-spacing: 2px;
      color: #121212;
    }

    h2 {
      font-size: 1.6em;
      color: #121212;
      margin-top: 10px;
    }

    .buttons {
      margin-top: 40px;
    }

    .buttons button {
      background-color: #121212;
      color: #00ffcc;
      border: 2px solid #00ffcc;
      padding: 12px 25px;
      font-size: 1em;
      margin: 10px;
      border-radius: 8px;
      cursor: pointer;
      transition: all 0.3s ease;
    }

    .buttons button:hover {
      background-color: #00ffcc;
      color: #121212;
    }

    section {
      padding: 80px 20px;
      max-width: 800px;
      margin: auto;
    }

    #scopri, #contatti, #social {
      display: none;
      animation: fadeIn 0.6s ease forwards;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    /* Form di contatto */
    form {
      display: flex;
      flex-direction: column;
      gap: 15px;
    }

    input, textarea {
      padding: 10px;
      font-size: 1em;
      border: none;
      border-radius: 5px;
    }

    textarea {
      resize: vertical;
      min-height: 100px;
    }

    button[type="submit"] {
      background-color: #00ffcc;
      color: #121212;
      border: none;
      font-weight: bold;
    }

    button[type="submit"]:hover {
      background-color: #00ccb3;
    }

    a.social-link {
      display: block;
      color: #00ffcc;
      font-weight: bold;
      margin: 10px 0;
      text-decoration: none;
    }

    a.social-link:hover {
      text-decoration: underline;
    }
  </style>
</head>
<body>

  <!-- HEADER -->
  <header>
    <h1>INDASTRIAL</h1>
    <h2>top citta di minecraft</h2>
    <div class="buttons">
      <button onclick="showSection('scopri')">scopri di più</button>
      <button onclick="showSection('contatti')">contattaci</button>
      <button onclick="showSection('social')">social</button>
    </div>
  </header>

  <!-- SEZIONE SCOPRI -->
  <section id="scopri">
    <h2>Chi siamo</h2>
    <p>
      Ciao, noi siamo tre ragazzi che costruiamo INDASTRIAL.  
      INDASTRIAL è un mondo e server di Minecraft, in cui ci sono case, edifici e importanti monumenti di una città inventata da noi.  
      Però ci sono anche monumenti della vita reale, tipo la Casa Bianca e le TORRI GEMELLE!!
    </p>
  </section>

  <!-- SEZIONE CONTATTACI -->
  <section id="contatti">
    <h2>Contattaci</h2>
    <form action="mailto:indastrialstaff@gmail.com" method="POST" enctype="text/plain">
      <input type="text" name="Nome" placeholder="Nome Utente" required>
      <input type="email" name="Email" placeholder="Email" required>
      <textarea name="Messaggio" placeholder="Scrivi il tuo messaggio..." required></textarea>
      <button type="submit">Invia</button>
    </form>
  </section>

  <!-- SEZIONE SOCIAL -->
  <section id="social">
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

      // Scroll to section
      const section = document.getElementById(sectionId);
      if (section) {
        section.scrollIntoView({ behavior: 'smooth' });
      }
    }
  </script>

</body>
</html>

<!DOCTYPE html>
<html lang="it">
<head>
  <meta charset="UTF-8">
  <title>INDASTRIAL</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <style>
    /* Tema bianco e animazioni */
    body {
      margin: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: #fff;
      min-height: 100vh;
      overflow-x: hidden;
      position: relative;
    }

    /* Animazioni "play" */
    .play-shape {
      position: absolute;
      width: 80px;
      height: 80px;
      background: linear-gradient(135deg, #3ab1edff 60%, #4285f4 100%);
      clip-path: polygon(0 0, 100% 50%, 0 100%);
      opacity: 0.13;
      animation: floatPlay 6s infinite alternate;
      z-index: 0;
    }
    .play-shape.one { top: 10%; left: 5%; animation-delay: 0s;}
    .play-shape.two { top: 60%; left: 80%; animation-delay: 2s;}
    .play-shape.three { top: 80%; left: 20%; animation-delay: 1s;}
    .play-shape.four { top: 30%; left: 60%; animation-delay: 3s;}
    @keyframes floatPlay {
      0% { transform: translateY(0) scale(1);}
      100% { transform: translateY(-30px) scale(1.2);}
    }

    header {
      text-align: center;
      padding: 80px 20px 40px;
      background: rgba(255,255,255,0.92);
      border-bottom: 2px solid #7c3aed;
      box-shadow: 0 8px 32px 0 rgba(130,130,255,0.10);
      border-radius: 0 0 32px 32px;
      position: relative;
      z-index: 2;
    }

    h1 {
      font-size: 4em;
      margin: 0;
      letter-spacing: 2px;
      color: #2196f3;
      font-weight: 900;
      text-shadow: 0 2px 12px #80deea, 0 0 18px #4285f4, 0 0 32px #80deea;
      background: none;
      -webkit-background-clip: unset;
      -webkit-text-fill-color: unset;
      background-clip: unset;
    }

    h2 {
      font-size: 1.7em;
      color: #4285f4;
      margin-top: 10px;
      text-shadow: 0 1px 8px #80deea, 0 0 12px #fff;
      font-weight: 700;
    }

    section {
      padding: 60px 20px;
      max-width: 800px;
      margin: 40px auto;
      background: rgba(255,255,255,0.92);
      border-radius: 24px;
      box-shadow: 0 8px 32px 0 rgba(130,130,255,0.10);
      border: 1.5px solid #e0e0e0;
      position: relative;
      z-index: 1;
      animation: fadeInGlass 1.2s cubic-bezier(.77,0,.18,1) forwards;
      opacity: 0;
    }
    @keyframes fadeInGlass {
      from { opacity: 0; transform: scale(0.98) translateY(30px);}
      to { opacity: 1; transform: scale(1) translateY(0);}
    }

    .buttons {
      margin-top: 36px;
    }
    .buttons button {
      background: #fff;
      color: #7c3aed;
      border: 2px solid #4285f4;
      padding: 14px 32px;
      font-size: 1.2em;
      margin: 10px;
      border-radius: 16px;
      cursor: pointer;
      transition: all 0.3s cubic-bezier(.77,0,.18,1);
      box-shadow: 0 2px 8px rgba(130,130,255,0.10);
      font-weight: 700;
    }
    .buttons button:hover {
      background: #7c3aed;
      color: #fff;
      border-color: #ff80ab;
      transform: scale(1.09);
      box-shadow: 0 4px 24px #4285f4;
    }

    /* Social con icone */
    .social-list {
      display: flex;
      flex-direction: column;
      gap: 18px;
      margin-top: 30px;
    }
    .social-link {
      display: flex;
      align-items: center;
      gap: 16px;
      font-size: 1.25em;
      color: #4285f4;
      font-weight: bold;
      text-decoration: none;
      background: #fff;
      border-radius: 12px;
      box-shadow: 0 2px 8px rgba(130,130,255,0.10);
      padding: 12px 18px;
      transition: background 0.2s, color 0.2s;
    }
    .social-link:hover {
      background: #7c3aed;
      color: #fff;
    }
    .social-link img {
      width: 32px;
      height: 32px;
      border-radius: 8px;
      box-shadow: 0 2px 8px #80deea44;
      background: #fff;
    }

    /* Responsive */
    @media (max-width: 700px) {
      header {
        padding: 40px 10px 20px;
      }
      h1 {
        font-size: 2.2em;
      }
      h2 {
        font-size: 1.15em;
      }
      section {
        padding: 30px 5px;
        max-width: 100%;
        border-radius: 12px;
      }
      .buttons button {
        font-size: 1em;
        padding: 10px 10px;
        margin: 6px 0;
        border-radius: 8px;
      }
      .social-link {
        font-size: 1em;
        padding: 10px 10px;
      }
      .social-link img {
        width: 24px;
        height: 24px;
      }
    }

    /* Sostituisci la parte CSS del popup bot con questa */
    #botPopup {
      background: rgba(255,255,255,0.85);
      border: 2px solid #4285f4;
      box-shadow: 0 8px 32px 0 #80deea55;
      border-radius: 24px;
      animation: fadeInGlass 1.2s cubic-bezier(.77,0,.18,1) forwards;
      opacity: 0;
      backdrop-filter: blur(16px) saturate(180%);
      -webkit-backdrop-filter: blur(16px) saturate(180%);
    }

    #botPopup .bot-header {
      background: #4285f4;
      color: #fff;
      border-radius: 24px 24px 0 0;
      padding: 18px 18px 10px 18px;
      border-bottom: 1px solid #80deea;
      font-size: 1.1em;
      font-weight: bold;
      letter-spacing: 1px;
    }

    #botPopup .bot-answer {
      animation: fadeInGlass 0.8s cubic-bezier(.77,0,.18,1) forwards;
      color: #4285f4;
      font-weight: 500;
    }

    /* Cambia anche il bordo input del popup */
    #userQuestion {
      border: 1.5px solid #80deea !important;
    }

    /* Animazione sfondo per la sezione contatti */
    .contact-bg-anim {
      position: absolute;
      top: -40px; left: -40px; right: -40px; bottom: -40px;
      z-index: 1;
      pointer-events: none;
      background: radial-gradient(circle at 20% 30%, #80deea55 0%, transparent 60%),
                  radial-gradient(circle at 80% 70%, #4285f455 0%, transparent 60%),
                  radial-gradient(circle at 60% 10%, #7c3aed33 0%, transparent 70%);
      animation: contactBgMove 8s infinite alternate;
    }
    @keyframes contactBgMove {
      0% { background-position: 20% 30%, 80% 70%, 60% 10%; }
      100% { background-position: 30% 40%, 70% 60%, 50% 20%; }
    }

    /* Form stile vetro e animazioni */
    .contact-form {
      position: relative;
      z-index: 2;
      display: flex;
      flex-direction: column;
      gap: 28px;
      padding: 36px 28px 28px 28px;
      background: rgba(255,255,255,0.85);
      border-radius: 24px;
      box-shadow: 0 8px 32px 0 #80deea33;
      border: 1.5px solid #80deea;
      backdrop-filter: blur(12px) saturate(180%);
      -webkit-backdrop-filter: blur(12px) saturate(180%);
      animation: fadeInGlass 1.2s cubic-bezier(.77,0,.18,1) forwards;
      opacity: 0;
    }

    .contact-form .input-group {
      position: relative;
      display: flex;
      flex-direction: column;
      margin-bottom: 8px;
    }
    .contact-form input,
    .contact-form textarea {
      padding: 14px 12px 14px 12px;
      font-size: 1.1em;
      border: 1.5px solid #80deea;
      border-radius: 10px;
      background: rgba(255,255,255,0.7);
      color: #222;
      box-shadow: 0 2px 8px #80deea22;
      transition: border-color 0.3s, box-shadow 0.3s;
      outline: none;
      resize: none;
    }
    .contact-form input:focus,
    .contact-form textarea:focus {
      border-color: #4285f4;
      box-shadow: 0 4px 16px #80deea55;
    }
    .contact-form label {
      position: absolute;
      left: 16px;
      top: 8px;
      font-size: 0.95em;
      color: #80deea;
      pointer-events: none;
      opacity: 0.8;
      transition: all 0.2s;
      z-index: 3;
    }
    .contact-form input:focus + label,
    .contact-form input:not(:placeholder-shown) + label,
    .contact-form textarea:focus + label,
    .contact-form textarea:not(:placeholder-shown) + label {
      top: -18px;
      left: 8px;
      font-size: 0.85em;
      color: #4285f4;
      opacity: 1;
      background: #fff;
      padding: 0 6px;
      border-radius: 6px;
      box-shadow: 0 2px 8px #80deea22;
    }

    .contact-btn {
      background: linear-gradient(90deg, #80deea 0%, #4285f4 100%);
      color: #fff;
      border: none;
      font-weight: bold;
      border-radius: 12px;
      padding: 14px 0;
      font-size: 1.2em;
      cursor: pointer;
      box-shadow: 0 2px 8px #80deea55;
      transition: background 0.2s, transform 0.2s;
      margin-top: 10px;
      letter-spacing: 1px;
    }
    .contact-btn:hover {
      background: linear-gradient(90deg, #4285f4 0%, #80deea 100%);
      color: #fff;
      transform: scale(1.04);
      box-shadow: 0 4px 16px #80deea99;
    }

    /* Pulsanti principali - nuova stilizzazione */
    .buttons button,
    .contact-btn,
    #addNewsBtn,
    #submitNews,
    #cancelNews,
    footer button,
    section button[type="submit"] {
      background: linear-gradient(90deg, #80deea 0%, #4285f4 100%);
      color: #fff;
      border: none;
      font-weight: bold;
      border-radius: 32px;
      padding: 18px 40px;
      font-size: 1.4em;
      cursor: pointer;
      box-shadow: 0 4px 24px #80deea55;
      transition: background 0.2s, transform 0.2s, box-shadow 0.2s;
      margin: 12px 8px;
      letter-spacing: 1px;
      outline: none;
    }

    .buttons button:hover,
    .contact-btn:hover,
    #addNewsBtn:hover,
    #submitNews:hover,
    #cancelNews:hover,
    footer button:hover,
    section button[type="submit"]:hover {
      background: linear-gradient(90deg, #4285f4 0%, #80deea 100%);
      color: #fff;
      transform: scale(1.07);
      box-shadow: 0 8px 32px #80deea99;
    }

    /* Responsive migliorato */
    @media (max-width: 700px) {
      .contact-form {
        padding: 18px 6px 18px 6px;
        border-radius: 12px;
      }
    }
  </style>
</head>
<body>
  <!-- Animazioni play -->
  <div class="play-shape one"></div>
  <div class="play-shape two"></div>
  <div class="play-shape three"></div>
  <div class="play-shape four"></div>

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
      Ciao, noi siamo tre ragazzi che costruiamo INDASTRIAL.<br>
      INDASTRIAL è un mondo e server di Minecraft, in cui ci sono case, edifici e importanti monumenti di una città inventata da noi.<br>
      Però ci sono anche monumenti della vita reale, tipo la Casa Bianca e le TORRI GEMELLE!!
    </p>
  </section>

  <!-- SEZIONE CONTATTACI -->
  <section id="contatti" style="overflow:hidden; position:relative;">
    <div class="contact-bg-anim"></div>
    <h2 style="position:relative; z-index:2;">Contattaci</h2>
    <form class="contact-form" action="mailto:indastrialstaff@gmail.com" method="POST" enctype="text/plain" autocomplete="off">
      <div class="input-group">
        <input type="text" name="Nome" placeholder="Nome Utente" required>
        <label>Nome Utente</label>
      </div>
      <div class="input-group">
        <input type="email" name="Email" placeholder="Email" required>
        <label>Email</label>
      </div>
      <div class="input-group">
        <textarea name="Messaggio" placeholder="Scrivi il tuo messaggio..." required></textarea>
        <label>Messaggio</label>
      </div>
      <button type="submit" class="contact-btn">Invia</button>
    </form>
  </section>

  <!-- SEZIONE SOCIAL -->
  <section id="social">
    <h2>Seguici sui social</h2>
    <div class="social-list">
      <a class="social-link" href="https://youtube.com/@indastrialofficial-u9m?si=rtqZpgclGmGtp1Z7" target="_blank">
        <img src="https://upload.wikimedia.org/wikipedia/commons/9/9f/Youtube%28amin%29.png" alt="YouTube">
        YouTube
      </a>
      <a class="social-link" href="https://whatsapp.com/channel/0029Vb6tN94J3jv2rC9Gvz1V" target="_blank">
        <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" alt="WhatsApp">
        WhatsApp
      </a>
      <a class="social-link" href="https://www.tiktok.com/@indastrial_minecraft?_t=ZN-8yTzPH7el2E&_r=1" target="_blank">
        <img src="https://upload.wikimedia.org/wikipedia/commons/6/6f/Tiktok-logo.png" alt="TikTok">
        TikTok
      </a>
      <a class="social-link" href="https://www.instagram.com/indastrial_minecraft?utm_source=qr&igsh=MTd5MHBwanlqODI5NQ==" target="_blank">
        <img src="https://upload.wikimedia.org/wikipedia/commons/a/a5/Instagram_icon.png" alt="Instagram">
        Instagram
      </a>
    </div>
  </section>

  <!-- SEZIONE NOTIZIE -->
  <section id="notizie">
    <h2>Notizie</h2>
    <div id="notizie-list">
      <!-- Spazio per contenuti futuri -->
    </div>
    <button id="addNewsBtn" style="display:none; margin-top:20px;">
      AGGIUNGI NUOVA NOTIZIA
    </button>
    <form id="newsForm" style="display:none; margin-top:20px; flex-direction:column; gap:15px;">
      <input type="text" id="newsTitle" placeholder="Titolo della notizia" required>
      <input type="file" id="newsImage" accept="image/*">
      <textarea id="newsText" placeholder="Testo della notizia" required></textarea>
      <div style="display:flex; gap:10px;">
        <button type="button" id="submitNews">
          CARICA NOTIZIA
        </button>
        <button type="button" id="cancelNews">
          ANNULLA
        </button>
      </div>
    </form>
  </section>

  <!-- SEZIONE PASSWORD -->
  <section id="password">
    <h2>Codice Creatore</h2>
    <input type="password" id="creatorPassword" placeholder="Inserisci la password">
    <button onclick="checkCreatorCode()">
      Verifica
    </button>
  </section>

  <!-- Pulsante CODICE CREATORE -->
  <footer style="text-align: center; padding: 20px; margin-top: 50px; background: var(--glass-bg); border-radius: 0 0 24px 24px;">
    <button onclick="showSection('password')">
      CODICE CREATORE
    </button>
    <div id="version" style="margin-top:18px; color:#2196f3; font-weight:bold; font-size:1.1em;">
      Versione: <span id="versionNumber">1.0</span>
    </div>
  </footer>

  <!-- INDASTRIAL BOT POPUP -->
  <div id="botPopup" style="display:none; position:fixed; bottom:30px; right:30px; z-index:9999; width:320px; max-width:90vw;">
    <div class="bot-header">
      INDASTRIAL BOT
      <button onclick="closeBot()" style="float:right; background:none; border:none; color:#fff; font-size:1.2em; cursor:pointer;">&times;</button>
    </div>
    <div style="padding:18px;">
      <p>Hai una domanda?</p>
      <input type="text" id="userQuestion" placeholder="Scrivi qui..." style="width:100%; padding:8px; border-radius:6px; border:1px solid var(--gemini-blue);">
      <button onclick="sendQuestion()" style="margin-top:10px;">Invia</button>
      <div id="botAnswer" class="bot-answer" style="margin-top:12px;"></div>
    </div>
  </div>

  <!-- JAVASCRIPT -->
  <script>
    function showSection(sectionId) {
      const sections = ['scopri', 'contatti', 'social', 'notizie', 'password'];
      sections.forEach(id => {
        document.getElementById(id).style.display = (id === sectionId || id === 'notizie') ? 'block' : 'none';
      });

      // Scroll to section
      const section = document.getElementById(sectionId);
      if (section) {
        section.scrollIntoView({ behavior: 'smooth' });
      }
    }

    let isCreator = false;

    // Carica le notizie salvate all'avvio
    window.addEventListener('DOMContentLoaded', function() {
      loadNews();
    });

    function loadNews() {
      const newsList = document.getElementById('notizie-list');
      newsList.innerHTML = '';
      const savedNews = JSON.parse(localStorage.getItem('newsList') || '[]');
      savedNews.forEach(news => {
        // Se c'è un'immagine valida (base64), mostra l'immagine, altrimenti niente
        let imageTag = '';
        if (news.image && news.image.startsWith('data:image')) {
          imageTag = `<img src="${news.image}" alt="Immagine notizia" style="max-width:100%;margin-bottom:10px;border-radius:8px;">`;
        }
        newsList.innerHTML += `
          <div class="news-item" style="position:relative; margin-bottom:32px; padding:18px 12px 12px 12px; background:#f9f9ff; border-radius:16px; box-shadow:0 2px 8px #80deea22;">
            <h3>${news.title}</h3>
            ${imageTag}
            <p>${news.text}</p>
            <button class="deleteNewsBtn" style="position:absolute; top:10px; right:10px; background-color:var(--gemini-pink); color:#fff; border:none; padding:5px 12px; border-radius:6px; cursor:pointer;">Elimina</button>
          </div>
        `;
      });
      addDeleteListeners();
    }

    function saveNewsList(newsArray) {
      localStorage.setItem('newsList', JSON.stringify(newsArray));
    }

    // Mostra il pulsante GALLERIA CREATORI solo se sei creatore
    function checkCreatorCode() {
      const password = document.getElementById("creatorPassword").value;
      if (password === "12345") {
        alert("Sei un creatore!!");
        isCreator = true;
        showSection('notizie');
        document.getElementById('addNewsBtn').style.display = 'inline-block';
      } else {
        alert("Accesso negato.");
      }
    }

    // Mostra il form per aggiungere una notizia
    document.getElementById('addNewsBtn').addEventListener('click', function() {
      document.getElementById('newsForm').style.display = 'flex';
    });

    // Annulla la creazione della notizia
    document.getElementById('cancelNews').addEventListener('click', function() {
      document.getElementById('newsForm').reset();
      document.getElementById('newsForm').style.display = 'none';
    });

    // Carica la notizia nella lista e salva
    document.getElementById('submitNews').addEventListener('click', function() {
      const title = document.getElementById('newsTitle').value;
      const text = document.getElementById('newsText').value;
      const imageInput = document.getElementById('newsImage');
      let savedNews = JSON.parse(localStorage.getItem('newsList') || '[]');

      // Solo i creatori possono aggiungere notizie con foto
      if (isCreator && imageInput.files && imageInput.files[0]) {
        const reader = new FileReader();
        reader.onload = function(e) {
          const newsObj = { title, text, image: e.target.result };
          savedNews.push(newsObj);
          saveNewsList(savedNews);
          loadNews();
          // Aggiorna versione
          let version = parseFloat(getVersion());
          version = Math.round((version + 0.1) * 10) / 10;
          setVersion(version.toFixed(1));
        };
        reader.readAsDataURL(imageInput.files[0]);
      } else {
        const newsObj = { title, text, image: '' };
        savedNews.push(newsObj);
        saveNewsList(savedNews);
        loadNews();
        // Aggiorna versione
        let version = parseFloat(getVersion());
        version = Math.round((version + 0.1) * 10) / 10;
        setVersion(version.toFixed(1));
      }

      // Reset form e nascondi
      document.getElementById('newsForm').reset();
      document.getElementById('newsForm').style.display = 'none';
    });

    // ANTEPRIMA IMMAGINE
    document.getElementById('newsImage').addEventListener('change', function(e) {
      const previewId = 'newsImagePreview';
      let preview = document.getElementById(previewId);
      if (!preview) {
        preview = document.createElement('img');
        preview.id = previewId;
        preview.style.maxWidth = '180px';
        preview.style.margin = '10px 0';
        preview.style.borderRadius = '12px';
        document.getElementById('newsForm').insertBefore(preview, document.getElementById('newsText'));
      }
      const file = e.target.files[0];
      if (file) {
        const reader = new FileReader();
        reader.onload = function(ev) {
          preview.src = ev.target.result;
          preview.style.display = 'block';
        };
        reader.readAsDataURL(file);
      } else {
        preview.style.display = 'none';
      }
    });

    // Funzione per aggiungere listener ai bottoni elimina
    function addDeleteListeners() {
      document.querySelectorAll('.deleteNewsBtn').forEach((btn, idx) => {
        btn.onclick = function() {
          if (confirm("Sei sicuro di voler eliminare questa notizia? L'azione è permanente!")) {
            let savedNews = JSON.parse(localStorage.getItem('newsList') || '[]');
            savedNews.splice(idx, 1);
            saveNewsList(savedNews);
            loadNews();
          }
        };
      });
    }

    // Facoltativo: nascondi il pulsante se si cambia sezione
    document.querySelectorAll('.buttons button, footer button').forEach(btn => {
      btn.addEventListener('click', () => {
        if (!isCreator) {
          document.getElementById('addNewsBtn').style.display = 'none';
          document.getElementById('newsForm').style.display = 'none';
        }
      });
    });

    // Mostra il bot automaticamente dopo 2 secondi
    window.addEventListener('load', () => {
      setTimeout(() => {
        document.getElementById('botPopup').style.display = 'block';
        document.getElementById('botPopup').style.opacity = '1';
      }, 2000);
    });

    // Chiudi il bot
    function closeBot() {
      document.getElementById('botPopup').style.display = 'none';
      document.getElementById('userQuestion').value = '';
      document.getElementById('botAnswer').innerText = '';
    }

    // Risposta finta del bot
    function sendQuestion() {
      const question = document.getElementById('userQuestion').value.trim().toLowerCase();
      const answerDiv = document.getElementById('botAnswer');
      if (!question) {
        answerDiv.innerText = "Scrivi la tua domanda!";
        return;
      }

      // Risposte automatiche base
      if (question.includes("minecraft")) {
        answerDiv.innerText = "INDASTRIAL è un server Minecraft creativo, puoi unirti chiedendo su Instagram!";
      } else if (question.includes("come entrare") || question.includes("join")) {
        answerDiv.innerText = "Per entrare nel server INDASTRIAL, contattaci su Instagram o WhatsApp!";
      } else if (question.includes("costruzioni") || question.includes("monumenti")) {
        answerDiv.innerText = "Abbiamo costruito la Casa Bianca, le Torri Gemelle e tanti altri monumenti!";
      } else if (question.includes("staff") || question.includes("chi siete")) {
        answerDiv.innerText = "Siamo tre ragazzi appassionati di Minecraft e costruzioni!";
      } else if (question.includes("ciao") || question.includes("salve")) {
        answerDiv.innerText = "Ciao! Come posso aiutarti?";
      } else {
        answerDiv.innerText = "Grazie per la domanda! Ti risponderemo presto via email oppure sui nostri social.";
      }
    }

    // VERSIONE
    function getVersion() {
      let version = localStorage.getItem('indastrialVersion');
      if (!version) {
        version = "1.0";
        localStorage.setItem('indastrialVersion', version);
      }
      return version;
    }

    function setVersion(version) {
      localStorage.setItem('indastrialVersion', version);
      document.getElementById('versionNumber').innerText = version;
    }

    // Aggiorna la versione in pagina
    document.addEventListener('DOMContentLoaded', function() {
      document.getElementById('versionNumber').innerText = getVersion();
    });

    // Quando si aggiunge una notizia, aumenta la versione di 0.1
    document.getElementById('submitNews').addEventListener('click', function() {
      // Aggiorna versione
      let version = parseFloat(getVersion());
      version = Math.round((version + 0.1) * 10) / 10;
      setVersion(version.toFixed(1));
    });
  </script>
</body>
</html>
<!-- END OF HTML DOCUMENT -->

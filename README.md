<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Willkommen in meiner Welt</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Orbitron&display=swap');

    body {
      margin: 0;
      font-family: 'Orbitron', sans-serif;
      background: linear-gradient(135deg, #111, #222);
      color: #00ffcc;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
      overflow-x: hidden;
    }

    h1 {
      font-size: 3em;
      text-shadow: 0 0 20px #00ffcc;
      animation: pulse 2s infinite;
    }

    @keyframes pulse {
      0% { text-shadow: 0 0 10px #00ffcc; }
      50% { text-shadow: 0 0 25px #00ffcc; }
      100% { text-shadow: 0 0 10px #00ffcc; }
    }

    .button {
      background: #00ffcc;
      color: #000;
      padding: 15px 30px;
      border: none;
      border-radius: 20px;
      cursor: pointer;
      font-size: 1.2em;
      margin-top: 20px;
      transition: 0.3s;
    }

    .button:hover {
      background: #00cccc;
      transform: scale(1.1);
    }

    .games {
      margin-top: 40px;
      display: flex;
      gap: 30px;
      flex-wrap: wrap;
      justify-content: center;
    }

    .game {
      background: #222;
      padding: 20px;
      border-radius: 15px;
      box-shadow: 0 0 15px #00ffcc66;
      text-align: center;
      max-width: 200px;
    }

    .game img {
      max-width: 100%;
      border-radius: 10px;
    }

    #chatbot {
      margin-top: 40px;
      background: #111;
      border: 2px solid #00ffcc;
      border-radius: 10px;
      padding: 20px;
      width: 300px;
    }

    #chatlog {
      height: 150px;
      overflow-y: auto;
      background: #000;
      padding: 10px;
      margin-bottom: 10px;
      border-radius: 5px;
      color: #00ffcc;
      font-size: 0.9em;
    }

    #chatinput {
      width: calc(100% - 20px);
      padding: 10px;
      border-radius: 5px;
      border: none;
    }
  </style>
</head>
<body>

  <h1>Willkommen in meiner Welt 🌌</h1>
  <button class="button" onclick="alert('Du bist jetzt offiziell cool 😎')">Drück mich!</button>

  <div class="games">
    <div class="game">
      <img src="https://upload.wikimedia.org/wikipedia/en/b/bb/Elden_Ring_Box_art.jpg" alt="Elden Ring" />
      <p><strong>Elden Ring</strong><br/>Düster & Episch</p>
    </div>
    <div class="game">
      <img src="https://cdn-products.eneba.com/resized-products/xdeuRSv7N7bsQowPLKycHTFCTItiPENRSpCOZ7s9RQA_350x200_1x-0.jpeg" alt="Landwirtschafts-Simulator" />
      <p><strong>LS 22</strong><br/>Traktoren und Felder 🚜</p>
    </div>
  </div>

  <div id="chatbot">
    <div id="chatlog">🤖 Chatbot: Hey! Wie geht’s dir?</div>
    <input type="text" id="chatinput" placeholder="Schreib etwas..." onkeydown="if(event.key === 'Enter') sendChat()" />
  </div>

  <audio autoplay loop>
    <source src="https://www.bensound.com/bensound-music/bensound-creativeminds.mp3" type="audio/mpeg">
    Dein Browser unterstützt kein Audio.
  </audio>

  <script>
    function sendChat() {
      const input = document.getElementById("chatinput");
      const log = document.getElementById("chatlog");
      const text = input.value.trim();
      if (text !== "") {
        log.innerHTML += `<br/>🧑 Du: ${text}`;
        setTimeout(() => {
          const reply = getBotReply(text);
          log.innerHTML += `<br/>🤖 Chatbot: ${reply}`;
          log.scrollTop = log.scrollHeight;
        }, 500);
        input.value = "";
      }
    }

    function getBotReply(text) {
      text = text.toLowerCase();
      if (text.includes("wie geht")) return "Mir geht’s super – danke der Nachfrage!";
      if (text.includes("was machst du")) return "Ich chatte mit dir 😁";
      if (text.includes("spiel")) return "Elden Ring ist mein Lieblingsspiel!";
      return "Cool 😎";
    }
  </script>

</body>
</html>

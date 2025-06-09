
<html lang="tr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Beni Affet...</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background: url('bg.jpg') no-repeat center center fixed;
      background-size: cover;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      margin: 0;
      overflow: hidden;
      text-align: center;
    }

    h1 {
      font-size: 2.2rem;
      margin-bottom: 20px;
      color: white;
      text-shadow: 1px 1px 3px #000;
    }

    .btn {
      font-size: 1.2rem;
      padding: 12px 28px;
      margin: 10px;
      border: none;
      border-radius: 30px;
      cursor: pointer;
      transition: all 0.3s ease;
      position: relative;
      z-index: 2;
    }

    #yesBtn {
      background-color: #e6005c;
      color: white;
    }

    #noBtn {
      background-color: #fff;
      color: #e6005c;
      border: 2px solid #e6005c;
      position: absolute;
    }

    .heart {
      font-size: 2rem;
      margin-top: 20px;
      display: none;
      animation: pop 0.5s ease forwards;
      color: white;
      text-shadow: 1px 1px 3px #000;
    }

    @keyframes pop {
      0% { transform: scale(0); opacity: 0; }
      100% { transform: scale(1.2); opacity: 1; }
    }

    audio {
      display: none;
    }
  </style>
</head>
<body>

  <h1>Beni affeder misin? 🥺</h1>
  <button id="yesBtn" class="btn" onclick="affet()">Affet</button>
  <button id="noBtn" class="btn" onclick="kac()">Hayır</button>

  <div class="heart" id="heart">❤️ Seni Seviyorum ❤️</div>

  <audio id="music" autoplay loop>
    <source src="https://example.com/gazapizm.mp3" type="audio/mpeg" />
  </audio>

  <script>
    const noBtn = document.getElementById("noBtn");
    const music = document.getElementById("music");

    function resetNoBtn() {
      noBtn.style.top = "50%";
      noBtn.style.left = "50%";
    }

    resetNoBtn();

    function kac() {
      const x = Math.random() * (window.innerWidth - 100);
      const y = Math.random() * (window.innerHeight - 100);
      noBtn.style.left = `${x}px`;
      noBtn.style.top = `${y}px`;

      kac.sayac = (kac.sayac || 0) + 1;
      if (kac.sayac > 7) {
        noBtn.innerText = "Peki... Affettim 😭";
        noBtn.style.backgroundColor = "#e6005c";
        noBtn.style.color = "white";
        noBtn.style.border = "none";
        noBtn.style.cursor = "default";
        noBtn.onclick = null;
      }
    }

    function affet() {
      document.getElementById("heart").style.display = "block";
      music.play();
    }
  </script>
</body>
</html>

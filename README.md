[ucapan.html](https://github.com/user-attachments/files/22102088/ucapan.html)
<!doctype html>
<html lang="id">
<head>
  <meta charset="utf-8">
  <title>Dear Kinaa 🧸</title>
  <style>
    body {
      margin:0;
      height:100vh;
      display:flex;
      justify-content:center;
      align-items:center;
      flex-direction:column;
      font-family: "Comic Sans MS", cursive, sans-serif;
      background: linear-gradient(135deg, #ffb6c1, #ff69b4, #ffc0cb);
      background-size: 400% 400%;
      animation: gradientBG 10s ease infinite;
      overflow:hidden;
    }
    @keyframes gradientBG {
      0% {background-position: 0% 50%;}
      50% {background-position: 100% 50%;}
      100% {background-position: 0% 50%;}
    }
    h1 {
      color:white;
      text-shadow:2px 2px 6px rgba(0,0,0,0.3);
      font-size:2em;
      margin-bottom:20px;
      text-align:center;
      animation: pulse 2s infinite;
    }
    button {
      border:none;
      padding:14px 22px;
      border-radius:25px;
      font-size:16px;
      font-weight:bold;
      cursor:pointer;
      background:#ff69b4;
      color:white;
      box-shadow:0 4px 10px rgba(0,0,0,0.3);
      transition:all 0.3s ease;
    }
    button:hover {
      transform: scale(1.1);
      background:#ff1493;
    }
    button:disabled {
      background: gray;
      cursor: not-allowed;
      transform: none;
    }
    .popup {
      position:fixed;
      top:50%;
      left:50%;
      transform:translate(-50%,-50%);
      background:white;
      padding:20px 30px;
      border-radius:20px;
      box-shadow:0 6px 18px rgba(0,0,0,0.4);
      display:none;
      text-align:center;
      color:#ff1493;
      font-size:22px;
      animation: fadeInScale 0.7s ease;
    }
    @keyframes fadeInScale {
      from {opacity:0; transform:translate(-50%,-50%) scale(0.8);}
      to {opacity:1; transform:translate(-50%,-50%) scale(1);}
    }
    @keyframes pulse {
      0% {transform:scale(1);}
      50% {transform:scale(1.05);}
      100% {transform:scale(1);}
    }
    .star {
      position: fixed;
      top: -20px;
      color: gold;
      font-size: 20px;
      animation: fall 4s linear forwards;
    }
    @keyframes fall {
      to {transform: translateY(110vh);}
    }
    .teddy {
      position: fixed;
      font-size: 30px;
      animation: floatUp 3s ease forwards;
    }
    @keyframes floatUp {
      0% {opacity:0; transform: translateY(20px) scale(0.8);}
      30% {opacity:1;}
      70% {opacity:1;}
      100% {opacity:0; transform: translateY(-80px) scale(1);}
    }
    .confetti {
      position: fixed;
      width: 10px;
      height: 10px;
      background: red;
      top: -10px;
      animation: drop 3s linear forwards;
      opacity: 0.8;
    }
    @keyframes drop {
      to { transform: translateY(110vh) rotate(720deg); }
    }
  </style>
</head>
<body>
  <h1>✨ Ucapan Spesial Buat Kinaa ✨</h1>
  <h3>*kalau mau di ulang tinggal refres*</h3>

  <button id="main-btn" onclick="startMessages()">Klik Aku 💌</button>

  <div class="popup" id="popup"></div>

  <!-- Suara klik -->
  <audio id="click-sound">
    <source src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_cfb3f2e9f7.mp3?filename=click-pop-2-189831.mp3" type="audio/mpeg">
  </audio>

  <!-- Musik romantis -->
  <audio id="bg-music" loop>
    <source src="https://cdn.pixabay.com/download/audio/2022/03/09/audio_6e4f72b78e.mp3?filename=romantic-piano-ambient-110624.mp3" type="audio/mpeg">
  </audio>

  <script>
    const messages = [
      "💖 Hai Kinaa, Maa syaa Allah cakep banget yang lagi baca ini 💖",
      "✨ kalau ada masalah ceritaa yaa",
      "🌸 aku insyaAllah ada kok🌸",
      "😍 Jangan terlalu capee (nanti nge drop)😍",
      "💌 Tubuh kina juga ada batasan 💌",
      "🌈 BTW kapan bisa ngobrol/ chat sama azmi lagi? 🌈"
    ];

    function startMessages() {
      playSound();
      playMusic();

      const popup = document.getElementById("popup");
      popup.style.display = "block";
      let msgIndex = 0;

      const intervalId = setInterval(() => {
        popup.textContent = messages[msgIndex];
        popup.style.animation = "none";
        popup.offsetHeight;
        popup.style.animation = "fadeInScale 0.7s ease";

        msgIndex++;
        if (msgIndex >= messages.length) {
          clearInterval(intervalId);
          setTimeout(() => { 
            popup.style.display = "none"; 
            const btn = document.getElementById("main-btn");
            btn.textContent = "Sudah Dibaca ";
            btn.disabled = true;
            launchConfetti(); // 🎉 confetti keluar
          }, 2500);
        }
      }, 2500);
    }

    function playSound() {
      const click = document.getElementById("click-sound");
      click.currentTime = 0;
      click.play();
    }

    function playMusic() {
      const music = document.getElementById("bg-music");
      music.volume = 0.5;
      music.play();
    }

    function createStar() {
      const star = document.createElement("div");
      star.classList.add("star");
      star.innerHTML = "⭐";
      star.style.left = Math.random() * 100 + "vw";
      star.style.fontSize = Math.random() * 15 + 10 + "px";
      document.body.appendChild(star);
      setTimeout(() => { star.remove(); }, 4000);
    }

    function createTeddy() {
      const teddy = document.createElement("div");
      teddy.classList.add("teddy");
      teddy.innerHTML = "🧸";
      teddy.style.left = Math.random() * 90 + "vw";
      teddy.style.top = Math.random() * 80 + "vh";
      teddy.style.fontSize = Math.random() * 20 + 25 + "px";
      document.body.appendChild(teddy);
      setTimeout(() => { teddy.remove(); }, 3000);
    }

    function launchConfetti() {
      for (let i = 0; i < 100; i++) {
        const conf = document.createElement("div");
        conf.classList.add("confetti");
        conf.style.left = Math.random() * 100 + "vw";
        conf.style.backgroundColor = randomColor();
        conf.style.animationDuration = (Math.random() * 2 + 2) + "s";
        conf.style.transform = `rotate(${Math.random()*360}deg)`;
        document.body.appendChild(conf);
        setTimeout(() => conf.remove(), 4000);
      }
    }

    function randomColor() {
      const colors = ["#ff69b4","#ff1493","#ffb6c1","#fffacd","#87cefa","#98fb98","#ffa07a"];
      return colors[Math.floor(Math.random()*colors.length)];
    }

    setInterval(createStar, 500);
    setInterval(createTeddy, 3000);
  </script>
</body>
</html>

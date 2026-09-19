<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Happy Birthday!</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Great+Vibes&family=Poppins:wght@400;600&display=swap');

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      background: radial-gradient(circle at center, #0a192f 0%, #020c1b 100%);
      height: 100vh;
      overflow: hidden;
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: 'Great Vibes', cursive;
    }

    .scene {
      position: relative;
      width: 100%;
      height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      gap: 20px;
    }

    /* Glowing Cursive Text - Blue Theme */
    .title {
      font-size: 4.5rem;
      color: #fff;
      text-shadow: 
        0 0 10px #80d4ff,
        0 0 20px #00bfff,
        0 0 40px #0077ff,
        0 0 80px #0044ff;
      z-index: 10;
      animation: fadeInText 3s ease-in-out forwards, pulseGlow 2s infinite alternate;
      opacity: 0;
      text-align: center;
    }

    .instruction {
      font-family: 'Poppins', sans-serif;
      font-size: 0.85rem;
      color: #80d4ff;
      text-transform: uppercase;
      letter-spacing: 2px;
      z-index: 10;
      margin-top: -10px;
      opacity: 0.8;
      cursor: pointer;
      text-align: center;
    }

    @keyframes fadeInText {
      0% { opacity: 0; transform: translateY(-20px) scale(0.9); }
      100% { opacity: 1; transform: translateY(0) scale(1); }
    }

    @keyframes pulseGlow {
      from {
        text-shadow: 0 0 10px #80d4ff, 0 0 20px #00bfff, 0 0 40px #0077ff;
      }
      to {
        text-shadow: 0 0 15px #ffffff, 0 0 30px #00bfff, 0 0 60px #0055ff, 0 0 90px #0033ff;
      }
    }

    /* 3D Cake Position - Blue Theme */
    .cake-container {
      position: relative;
      width: 200px;
      height: 150px;
      z-index: 5;
      display: flex;
      justify-content: center;
      align-items: flex-end;
      animation: fadeInCake 2s 1s forwards;
      opacity: 0;
    }

    @keyframes fadeInCake {
      to { opacity: 1; }
    }

    .cake {
      position: relative;
      width: 160px;
      height: 100px;
    }

    .plate {
      width: 200px;
      height: 100px;
      background: radial-gradient(ellipse at center, #e0f7fa 0%, #80deea 70%, #00838f 100%);
      border-radius: 50%;
      position: absolute;
      bottom: -15px;
      left: 50%;
      transform: translateX(-50%);
      box-shadow: 0 10px 25px rgba(0,0,0,0.6);
    }

    .layer {
      position: absolute;
      display: block;
      width: 160px;
      height: 50px;
      border-radius: 50%;
      background-color: #80d4ff;
    }

    .layer-bottom {
      bottom: 0;
      background: linear-gradient(to bottom, #33b5e5, #0073e6);
      box-shadow: 0 4px 0 #0052a5;
    }

    .layer-middle {
      bottom: 25px;
      background: linear-gradient(to bottom, #ffffff, #e0f2fe);
      height: 45px;
    }

    .layer-top {
      bottom: 50px;
      background: linear-gradient(to bottom, #33b5e5, #0099ff);
    }

    .icing {
      position: absolute;
      top: 0;
      width: 160px;
      height: 30px;
      border-radius: 50%;
      background: #ffffff;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }

    /* Candle & Flame */
    .candle {
      background: repeating-linear-gradient(45deg, #fff, #fff 5px, #0099ff 5px, #0099ff 10px);
      width: 10px;
      height: 35px;
      position: absolute;
      top: -20px;
      left: 50%;
      transform: translateX(-50%);
      border-radius: 3px;
      z-index: 6;
      cursor: pointer;
    }

    .flame {
      position: absolute;
      top: -15px;
      left: 50%;
      transform: translateX(-50%);
      width: 12px;
      height: 18px;
      background: #ffaa00;
      border-radius: 50% 50% 20% 20%;
      box-shadow: 0 0 10px #ffaa00, 0 0 20px #ffdd00;
      animation: flicker 0.2s infinite alternate;
      transition: opacity 0.5s ease-out, transform 0.5s ease-out;
    }

    .flame.out {
      opacity: 0;
      transform: translateX(-50%) scale(0);
      animation: none;
    }

    /* Smoke animation */
    .smoke {
      position: absolute;
      top: -25px;
      left: 50%;
      transform: translateX(-50%);
      width: 6px;
      height: 6px;
      background: rgba(200, 230, 255, 0.6);
      border-radius: 50%;
      opacity: 0;
      pointer-events: none;
    }

    .smoke.active {
      animation: riseSmoke 2s ease-out forwards;
    }

    @keyframes riseSmoke {
      0% { opacity: 0.8; transform: translateX(-50%) translateY(0) scale(1); }
      100% { opacity: 0; transform: translateX(-80%) translateY(-40px) scale(3); }
    }

    @keyframes flicker {
      0% { transform: translateX(-50%) scale(1); opacity: 0.9; }
      100% { transform: translateX(-50%) scale(1.15); opacity: 1; }
    }

    /* Message Card Popup - Blue Glassmorphism */
    .message-card {
      position: absolute;
      top: 52%;
      left: 50%;
      transform: translate(-50%, -50%) scale(0.7);
      background: rgba(10, 25, 47, 0.45);
      backdrop-filter: blur(14px);
      border: 1px solid rgba(128, 212, 255, 0.4);
      border-radius: 16px;
      padding: 24px 30px;
      text-align: center;
      width: 85%;
      max-width: 380px;
      box-shadow: 0 15px 35px rgba(0, 0, 0, 0.7), 0 0 20px rgba(0, 191, 255, 0.3);
      z-index: 20;
      opacity: 0;
      visibility: hidden;
      transition: all 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    }

    .message-card.show {
      opacity: 1;
      visibility: visible;
      transform: translate(-50%, -50%) scale(1);
    }

    .message-card h2 {
      font-family: 'Great Vibes', cursive;
      font-size: 2.5rem;
      color: #80d4ff;
      margin-bottom: 10px;
      text-shadow: 0 0 8px #0088ff;
    }

    .message-card p {
      font-family: 'Poppins', sans-serif;
      font-size: 0.95rem;
      line-height: 1.6;
      color: #ffffff;
      opacity: 0.95;
    }

    /* Floating Particles Container - Blue Theme */
    .particles {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      overflow: hidden;
    }

    .heart, .balloon {
      position: absolute;
      bottom: -100px;
      animation: floatUp linear infinite;
    }

    .heart::before, .heart::after {
      content: "";
      position: absolute;
      left: 10px;
      top: 0;
      width: 10px;
      height: 16px;
      background: #00aaff;
      border-radius: 10px 10px 0 0;
      transform: rotate(-45deg);
      transform-origin: 0 100%;
    }

    .heart::after {
      left: 0;
      transform: rotate(45deg);
      transform-origin: 100% 100%;
    }

    .balloon {
      width: 30px;
      height: 40px;
      background: rgba(128, 212, 255, 0.7);
      border-radius: 50% 50% 50% 50% / 40% 40% 60% 60%;
      box-shadow: inset -5px -5px 10px rgba(0,0,0,0.15), 0 0 15px rgba(128, 212, 255, 0.6);
    }

    .balloon::after {
      content: "";
      position: absolute;
      bottom: -12px;
      left: 14px;
      width: 2px;
      height: 15px;
      background: rgba(255,255,255,0.6);
    }

    @keyframes floatUp {
      0% {
        transform: translateY(0) rotate(0deg);
        opacity: 0;
      }
      10% {
        opacity: 0.8;
      }
      100% {
        transform: translateY(-110vh) rotate(360deg);
        opacity: 0;
      }
    }
  </style>
</head>
<body>

  <div class="scene">
    <div class="particles" id="particles"></div>

    <!-- Title -->
    <h1 class="title">Happy Birthday Intal</h1>
    <p class="instruction" id="instruction">Click candle or blow into mic to extinguish!</p>

    <!-- 3D Cake Container -->
    <div class="cake-container" id="cake">
      <div class="plate"></div>
      <div class="cake">
        <div class="layer layer-bottom"></div>
        <div class="layer layer-middle"></div>
        <div class="layer layer-top">
          <div class="icing"></div>
        </div>
        <div class="candle" id="candle">
          <div class="flame" id="flame"></div>
          <div class="smoke" id="smoke"></div>
        </div>
      </div>
    </div>

    <!-- Birthday Message Popup Card -->
    <div class="message-card" id="messageCard">
      <h2>Make a Wish! 🎉</h2>
      <p>May your day be filled with endless joy Intal, unforgettable moments, laughter, and all the love you deserve. Here’s to an amazing year ahead! God bless you always.💙💙💙💙💙</p>
    </div>
  </div>

  <script>
    const flame = document.getElementById('flame');
    const smoke = document.getElementById('smoke');
    const candle = document.getElementById('candle');
    const instruction = document.getElementById('instruction');
    const messageCard = document.getElementById('messageCard');
    let isBlownOut = false;

    // Trigger birthday message display
    function blowOutCandle() {
      if (isBlownOut) return;
      isBlownOut = true;
      
      flame.classList.add('out');
      smoke.classList.add('active');
      instruction.innerText = "✨ Wish Granted! ✨";

      // Show birthday card after a slight delay
      setTimeout(() => {
        messageCard.classList.add('show');
      }, 700);
    }

    // Event listeners
    candle.addEventListener('click', blowOutCandle);
    instruction.addEventListener('click', blowOutCandle);

    // Microphone blow detection
    async function initMicrophone() {
      try {
        const stream = await navigator.mediaDevices.getUserMedia({ audio: true });
        const audioContext = new (window.AudioContext || window.webkitAudioContext)();
        const analyser = audioContext.createAnalyser();
        const microphone = audioContext.createMediaStreamSource(stream);
        
        analyser.fftSize = 256;
        microphone.connect(analyser);

        const dataArray = new Uint8Array(analyser.frequencyBinCount);

        function checkVolume() {
          if (isBlownOut) return;

          analyser.getByteFrequencyData(dataArray);
          let sum = 0;
          for (let i = 0; i < dataArray.length; i++) {
            sum += dataArray[i];
          }
          let average = sum / dataArray.length;

          if (average > 45) {
            blowOutCandle();
          } else {
            requestAnimationFrame(checkVolume);
          }
        }

        checkVolume();
      } catch (err) {
        console.log("Microphone access denied or not supported.");
      }
    }

    document.body.addEventListener('click', () => {
      initMicrophone();
    }, { once: true });

    // Background floating elements generator
    const particlesContainer = document.getElementById('particles');
    const totalParticles = 40;

    for (let i = 0; i < totalParticles; i++) {
      const particle = document.createElement('div');
      const isHeart = Math.random() > 0.4;
      
      particle.className = isHeart ? 'heart' : 'balloon';
      
      const left = Math.random() * 100;
      const duration = 6 + Math.random() * 8;
      const delay = Math.random() * 5;
      const scale = 0.5 + Math.random() * 0.8;

      particle.style.left = `${left}%`;
      particle.style.animationDuration = `${duration}s`;
      particle.style.animationDelay = `${delay}s`;
      particle.style.transform = `scale(${scale})`;

      particlesContainer.appendChild(particle);
    }
  </script>
</body>
</html>


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
    <h1 class="title">Happy Birthday Intal!</h1>
    <p class="instruction" id="instruction"> Click na ang candle tal then wish HAHAHA</p>
    <p class="status" id="status">Click na dayun kay wala ka naman choice HAHAHAHA.</p>

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
      <p>May your day be filled with endless joy, unforgettable moments, laughter, and all the love you deserve. Here’s to an amazing year ahead, God bless you always Intal💙☺️!</p>
    </div>
  </div>

  <style>
    .status {
      font-family: 'Poppins', sans-serif;
      font-size: 0.72rem;
      color: rgba(255,255,255,0.75);
      margin-top: -12px;
      z-index: 10;
      text-align: center;
      min-height: 20px;
    }

    .candle.ready {
      filter: drop-shadow(0 0 8px rgba(128, 212, 255, 0.7));
    }
  </style>
  <script>
    const flame = document.getElementById('flame');
    const smoke = document.getElementById('smoke');
    const candle = document.getElementById('candle');
    const instruction = document.getElementById('instruction');
    const status = document.getElementById('status');
    const messageCard = document.getElementById('messageCard');

    let isBlownOut = false;
    let audioCtx = null;
    let musicLooping = true;
    let microphoneStarted = false;
    let blowFrames = 0;

    // Cute, gentle Happy Birthday arrangement.
    const NOTE = {
      C4: 261.63, D4: 293.66, E4: 329.63, F4: 349.23,
      G4: 392.00, A4: 440.00, B4: 493.88,
      C5: 523.25, D5: 587.33, E5: 659.25, G5: 783.99
    };

    // Recognizable melody with a softer, lullaby-like rhythm.
    const happyBirthday = [
      ['G4', .42], ['G4', .42], ['A4', .78], ['G4', .78], ['C5', .78], ['B4', 1.15],
      ['G4', .42], ['G4', .42], ['A4', .78], ['G4', .78], ['D5', .78], ['C5', 1.15],
      ['G4', .42], ['G4', .42], ['G5', .78], ['E5', .78], ['C5', .78], ['B4', .78], ['A4', 1.15],
      ['F4', .42], ['F4', .42], ['E4', .78], ['C5', .78], ['D5', .78], ['C5', 1.35]
    ];

    function getSongLength() {
      return happyBirthday.reduce((total, [, duration]) => total + duration + 0.075, 0);
    }

    async function initAudio() {
      if (!audioCtx) {
        audioCtx = new (window.AudioContext || window.webkitAudioContext)();
      }

      if (audioCtx.state === 'suspended') {
        await audioCtx.resume();
      }

      if (musicLooping && !isBlownOut) {
        playHappyBirthday();
      }
    }

    function playCuteNote(freq, duration, delay = 0) {
      if (!audioCtx || isBlownOut) return;

      const start = audioCtx.currentTime + delay;

      // Main soft tone.
      const osc = audioCtx.createOscillator();
      const gain = audioCtx.createGain();

      osc.type = 'sine';
      osc.frequency.setValueAtTime(freq, start);

      gain.gain.setValueAtTime(0.0001, start);
      gain.gain.exponentialRampToValueAtTime(0.065, start + 0.055);
      gain.gain.exponentialRampToValueAtTime(0.0001, start + duration + 0.12);

      osc.connect(gain);
      gain.connect(audioCtx.destination);

      osc.start(start);
      osc.stop(start + duration + 0.16);

      // Very quiet higher "sparkle" makes the melody feel cute.
      const sparkle = audioCtx.createOscillator();
      const sparkleGain = audioCtx.createGain();

      sparkle.type = 'triangle';
      sparkle.frequency.setValueAtTime(freq * 2, start);

      sparkleGain.gain.setValueAtTime(0.0001, start);
      sparkleGain.gain.exponentialRampToValueAtTime(0.018, start + 0.04);
      sparkleGain.gain.exponentialRampToValueAtTime(0.0001, start + duration * 0.7);

      sparkle.connect(sparkleGain);
      sparkleGain.connect(audioCtx.destination);

      sparkle.start(start);
      sparkle.stop(start + duration);
    }

    function playHappyBirthday() {
      if (!audioCtx || isBlownOut || !musicLooping) return;

      let delay = 0;

      happyBirthday.forEach(([name, duration]) => {
        playCuteNote(NOTE[name], duration, delay);
        delay += duration + 0.075;
      });

      // Tiny "music-box" ending sparkle.
      const sparkleDelay = delay - 0.45;
      playCuteNote(NOTE.E5, 0.25, sparkleDelay);
      playCuteNote(NOTE.G5, 0.30, sparkleDelay + 0.16);

      setTimeout(() => {
        if (!isBlownOut && musicLooping) {
          playHappyBirthday();
        }
      }, (getSongLength() + 0.5) * 1000);
    }

    function blowOutCandle() {
      if (isBlownOut) return;

      isBlownOut = true;
      musicLooping = false;

      flame.classList.add('out');
      smoke.classList.remove('active');
      void smoke.offsetWidth; // Restart smoke animation if needed.
      smoke.classList.add('active');

      candle.classList.remove('ready');
      instruction.innerText = '✨ Wish Granted! Happy Birthday! ✨';
      status.innerText = '🕯️ The candle is out! Make a wish!';

      // Soft celebratory chord.
      if (audioCtx) {
        playCuteNote(NOTE.C5, 1.1, 0.05);
        playCuteNote(NOTE.E5, 1.1, 0.12);
        playCuteNote(NOTE.G5, 1.4, 0.20);
      }

      setTimeout(() => {
        messageCard.classList.add('show');
      }, 700);
    }

    // Manual fallback: clicking the candle also extinguishes it.
    candle.addEventListener('click', async (event) => {
      event.stopPropagation();
      await initAudio();
      blowOutCandle();
    });

    // Start music + microphone after the user's first tap/click.
    async function startExperience() {
      if (isBlownOut) return;

      try {
        await initAudio();
        await initMicrophone();

        candle.classList.add('ready');
        instruction.innerText = '🎤 Now blow toward your microphone to put out the candle!';
        status.innerText = 'Listening for a strong breath…';
      } catch (err) {
        status.innerText = 'If Microphone unavailable — click the candle to blow it out.';
        instruction.innerText = 'Click the candle if your microphone is unavailable';
      }
    }

    instruction.addEventListener('click', startExperience);

    // Also allow any first tap on the page to start the experience.
    document.body.addEventListener('click', startExperience, { once: true });

    async function initMicrophone() {
      if (microphoneStarted || !navigator.mediaDevices?.getUserMedia || !audioCtx) {
        return;
      }

      microphoneStarted = true;

      const stream = await navigator.mediaDevices.getUserMedia({
        audio: {
          echoCancellation: false,
          noiseSuppression: false,
          autoGainControl: false
        }
      });

      const analyser = audioCtx.createAnalyser();
      analyser.fftSize = 512;
      analyser.smoothingTimeConstant = 0.25;

      const microphone = audioCtx.createMediaStreamSource(stream);
      microphone.connect(analyser);

      const dataArray = new Uint8Array(analyser.fftSize);

      function checkForBlow() {
        if (isBlownOut) {
          stream.getTracks().forEach(track => track.stop());
          return;
        }

        analyser.getByteTimeDomainData(dataArray);

        // RMS measures actual microphone loudness more reliably than
        // averaging frequency bins, so normal speech is less likely
        // to trigger the candle accidentally.
        let sumSquares = 0;
        for (let i = 0; i < dataArray.length; i++) {
          const normalized = (dataArray[i] - 128) / 128;
          sumSquares += normalized * normalized;
        }

        const rms = Math.sqrt(sumSquares / dataArray.length);

        // Require a loud breath for several animation frames.
        if (rms > 0.085) {
          blowFrames++;
        } else {
          blowFrames = Math.max(0, blowFrames - 2);
        }

        if (blowFrames >= 5) {
          blowOutCandle();
          return;
        }

        requestAnimationFrame(checkForBlow);
      }

      checkForBlow();
    }

    // Background floating elements generator.
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

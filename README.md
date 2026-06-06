[tannu_birthday.html](https://github.com/user-attachments/files/28662011/tannu_birthday.html)# birthday[Uploading intex.html…]()
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Birthday Tannu 🎂</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Quicksand:wght@300;400;600&display=swap" rel="stylesheet">
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; scroll-snap-type: y mandatory; }

  body {
    font-family: 'Quicksand', sans-serif;
    overflow-x: hidden;
  }

  .slide {
    min-height: 100vh;
    width: 100%;
    scroll-snap-align: start;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    position: relative;
    overflow: hidden;
    padding: 40px 20px;
  }

  /* Slide 1 — Soft Rose Pink */
  .slide-1 {
    background: linear-gradient(135deg, #fce4ec 0%, #f8bbd0 40%, #ffd6e0 100%);
  }

  /* Slide 2 — Dreamy Lavender */
  .slide-2 {
    background: linear-gradient(135deg, #ede7f6 0%, #d1c4e9 40%, #e8d5f5 100%);
  }

  /* Slide 3 — Peachy Gold */
  .slide-3 {
    background: linear-gradient(135deg, #fff8e1 0%, #ffecb3 40%, #ffe0b2 100%);
  }

  /* Slide 4 — Mint Sky */
  .slide-4 {
    background: linear-gradient(135deg, #e0f7fa 0%, #b2ebf2 40%, #dcedc8 100%);
  }

  /* Floating circles background decoration */
  .bubble {
    position: absolute;
    border-radius: 50%;
    opacity: 0.18;
    animation: float 6s ease-in-out infinite;
  }

  @keyframes float {
    0%, 100% { transform: translateY(0px) scale(1); }
    50% { transform: translateY(-22px) scale(1.04); }
  }

  /* Nav dots */
  .nav-dots {
    position: fixed;
    right: 24px;
    top: 50%;
    transform: translateY(-50%);
    display: flex;
    flex-direction: column;
    gap: 10px;
    z-index: 100;
  }

  .dot {
    width: 10px;
    height: 10px;
    border-radius: 50%;
    background: rgba(0,0,0,0.2);
    cursor: pointer;
    transition: background 0.3s, transform 0.3s;
    border: none;
    outline: none;
  }

  .dot.active { background: rgba(0,0,0,0.55); transform: scale(1.3); }

  /* Photo frame */
  .photo-frame {
    width: 220px;
    height: 260px;
    border-radius: 120px 120px 80px 80px;
    overflow: hidden;
    box-shadow: 0 12px 40px rgba(0,0,0,0.15);
    position: relative;
    margin-bottom: 28px;
    transition: transform 0.4s ease;
    border: 4px solid rgba(255,255,255,0.7);
    background: rgba(255,255,255,0.35);
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .photo-frame:hover { transform: scale(1.04) rotate(-1deg); }

  .photo-frame img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .photo-placeholder {
    font-size: 42px;
    opacity: 0.5;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
  }

  .photo-placeholder span {
    font-size: 13px;
    font-family: 'Quicksand', sans-serif;
    font-weight: 400;
    color: rgba(0,0,0,0.4);
    letter-spacing: 0.5px;
  }

  /* Gallery grid (slide 3) */
  .photo-grid {
    display: grid;
    grid-template-columns: repeat(2, 150px);
    grid-template-rows: repeat(2, 150px);
    gap: 12px;
    margin-bottom: 28px;
  }

  .photo-grid .photo-frame {
    width: 150px;
    height: 150px;
    border-radius: 20px;
    margin-bottom: 0;
  }

  /* Text styles */
  .slide-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(38px, 8vw, 62px);
    font-weight: 700;
    color: #3a2a2a;
    text-align: center;
    line-height: 1.1;
    margin-bottom: 14px;
    animation: fadeUp 0.9s ease both;
  }

  .slide-sub {
    font-family: 'Quicksand', sans-serif;
    font-size: clamp(14px, 3vw, 18px);
    font-weight: 400;
    color: rgba(50, 30, 30, 0.65);
    text-align: center;
    max-width: 420px;
    line-height: 1.7;
    animation: fadeUp 0.9s 0.15s ease both;
  }

  .badge {
    display: inline-block;
    font-family: 'Quicksand', sans-serif;
    font-size: 13px;
    font-weight: 600;
    letter-spacing: 2px;
    text-transform: uppercase;
    padding: 6px 18px;
    border-radius: 30px;
    background: rgba(255,255,255,0.55);
    color: rgba(80,40,40,0.7);
    margin-bottom: 18px;
    border: 1px solid rgba(255,255,255,0.8);
    animation: fadeUp 0.9s 0s ease both;
  }

  /* Confetti bits */
  .confetti-wrap {
    position: absolute;
    top: 0; left: 0; right: 0; bottom: 0;
    pointer-events: none;
    overflow: hidden;
  }

  .conf {
    position: absolute;
    width: 8px;
    height: 8px;
    border-radius: 2px;
    opacity: 0.55;
    animation: fallDown linear infinite;
  }

  @keyframes fallDown {
    0% { transform: translateY(-40px) rotate(0deg); opacity: 0.7; }
    100% { transform: translateY(110vh) rotate(720deg); opacity: 0; }
  }

  /* Heart row */
  .hearts {
    display: flex;
    gap: 8px;
    margin-top: 22px;
    font-size: 20px;
    animation: fadeUp 0.9s 0.3s ease both;
  }

  .heart {
    animation: pulse 1.4s ease-in-out infinite;
  }

  .heart:nth-child(2) { animation-delay: 0.2s; }
  .heart:nth-child(3) { animation-delay: 0.4s; }

  @keyframes pulse {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.3); }
  }

  /* Scroll cue */
  .scroll-cue {
    position: absolute;
    bottom: 28px;
    left: 50%;
    transform: translateX(-50%);
    font-size: 11px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: rgba(0,0,0,0.3);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 6px;
  }

  .scroll-arrow {
    width: 18px;
    height: 18px;
    border-right: 2px solid rgba(0,0,0,0.25);
    border-bottom: 2px solid rgba(0,0,0,0.25);
    transform: rotate(45deg);
    animation: bounce 1.4s infinite;
  }

  @keyframes bounce {
    0%, 100% { transform: rotate(45deg) translateY(0); }
    50% { transform: rotate(45deg) translateY(5px); }
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(28px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .ribbon {
    font-size: 28px;
    animation: spin 6s linear infinite;
    display: inline-block;
  }

  @keyframes spin {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
  }
</style>
</head>
<body>

<!-- Nav dots -->
<nav class="nav-dots" aria-label="Slide navigation">
  <button class="dot active" onclick="goTo(0)" aria-label="Slide 1"></button>
  <button class="dot" onclick="goTo(1)" aria-label="Slide 2"></button>
  <button class="dot" onclick="goTo(2)" aria-label="Slide 3"></button>
  <button class="dot" onclick="goTo(3)" aria-label="Slide 4"></button>
</nav>

<!-- ─── SLIDE 1 — Hero ─── -->
<section class="slide slide-1" id="s0">
  <div class="confetti-wrap" id="cf0"></div>

  <!-- Bubbles -->
  <div class="bubble" style="width:180px;height:180px;background:#f48fb1;top:-40px;left:-50px;animation-delay:0s;"></div>
  <div class="bubble" style="width:120px;height:120px;background:#f06292;bottom:80px;right:-30px;animation-delay:1.5s;"></div>
  <div class="bubble" style="width:70px;height:70px;background:#e91e63;top:30%;left:8%;animation-delay:3s;"></div>

  <div class="badge">✨ Special Day ✨</div>

  <div class="photo-frame">
    <!-- Replace src with your image: <img src="YOUR_IMAGE.jpg" alt="Tannu"> -->
    <div class="photo-placeholder">📷<span>Your Photo</span></div>
  </div>

  <div class="slide-title">Happy Birthday<br><em>Tannu!</em></div>
  <div class="slide-sub">Today is all about you — your smile, your laughter, your beautiful heart. Wishing you the most magical birthday ever! 🎂</div>

  <div class="hearts">
    <span class="heart">🌸</span>
    <span class="heart">💖</span>
    <span class="heart">🌸</span>
  </div>

  <div class="scroll-cue">scroll <div class="scroll-arrow"></div></div>
</section>

<!-- ─── SLIDE 2 — Wishes ─── -->
<section class="slide slide-2" id="s1">
  <div class="confetti-wrap" id="cf1"></div>

  <div class="bubble" style="width:200px;height:200px;background:#ce93d8;top:-60px;right:-60px;animation-delay:0.5s;"></div>
  <div class="bubble" style="width:90px;height:90px;background:#ab47bc;bottom:60px;left:-20px;animation-delay:2s;"></div>

  <div class="badge">💜 With Love 💜</div>

  <div class="photo-frame">
    <!-- Replace src with your image: <img src="YOUR_IMAGE.jpg" alt="Tannu"> -->
    <div class="photo-placeholder">📷<span>Your Photo</span></div>
  </div>

  <div class="slide-title">A Wish<br><em>for You</em></div>
  <div class="slide-sub">May every dream you've ever whispered come true. May joy follow you everywhere you go, and may love always find you. 🌷</div>

  <div class="hearts">
    <span class="heart">🦋</span>
    <span class="heart">💜</span>
    <span class="heart">🦋</span>
  </div>

  <div class="scroll-cue">scroll <div class="scroll-arrow"></div></div>
</section>

<!-- ─── SLIDE 3 — Gallery ─── -->
<section class="slide slide-3" id="s2">
  <div class="confetti-wrap" id="cf2"></div>

  <div class="bubble" style="width:160px;height:160px;background:#ffcc02;top:-50px;left:-40px;animation-delay:1s;"></div>
  <div class="bubble" style="width:100px;height:100px;background:#ff9800;bottom:40px;right:-20px;animation-delay:2.5s;"></div>

  <div class="badge">🌼 Sweet Memories 🌼</div>

  <!-- 4-photo grid -->
  <div class="photo-grid">
    <div class="photo-frame">
      <div class="photo-placeholder" style="font-size:28px;">📷<span>Photo</span></div>
    </div>
    <div class="photo-frame">
      <div class="photo-placeholder" style="font-size:28px;">📷<span>Photo</span></div>
    </div>
    <div class="photo-frame">
      <div class="photo-placeholder" style="font-size:28px;">📷<span>Photo</span></div>
    </div>
    <div class="photo-frame">
      <div class="photo-placeholder" style="font-size:28px;">📷<span>Photo</span></div>
    </div>
  </div>

  <div class="slide-title">Golden<br><em>Moments</em></div>
  <div class="slide-sub">Every picture tells a story. Every moment with you is a treasure worth keeping forever. 🌟</div>

  <div class="scroll-cue">scroll <div class="scroll-arrow"></div></div>
</section>

<!-- ─── SLIDE 4 — Finale ─── -->
<section class="slide slide-4" id="s3">
  <div class="confetti-wrap" id="cf3"></div>

  <div class="bubble" style="width:150px;height:150px;background:#80deea;top:-40px;right:-40px;animation-delay:0.8s;"></div>
  <div class="bubble" style="width:110px;height:110px;background:#a5d6a7;bottom:50px;left:-20px;animation-delay:2.2s;"></div>

  <div class="badge">🎉 Celebrate! 🎉</div>

  <div style="font-size: 70px; margin-bottom: 16px; animation: fadeUp 0.8s ease both;">
    🎂
  </div>

  <div class="slide-title">Here's to<br><em>You, Tannu!</em></div>
  <div class="slide-sub">Another year of adventures, laughter, and beautiful memories ahead. You deserve all the happiness in the world. Stay blessed, stay shining! ✨</div>

  <div class="hearts" style="margin-top: 24px; gap: 12px;">
    <span class="heart" style="font-size: 26px;">🌿</span>
    <span class="heart" style="font-size: 26px;">💚</span>
    <span class="heart" style="font-size: 26px;">🌿</span>
  </div>

  <div style="margin-top: 32px; font-family: 'Playfair Display', serif; font-style: italic; font-size: 13px; color: rgba(0,0,0,0.35); letter-spacing: 1px;">
    Made with 💖 just for you
  </div>
</section>

<script>
  const slides = document.querySelectorAll('.slide');
  const dots = document.querySelectorAll('.dot');

  function goTo(i) {
    slides[i].scrollIntoView({ behavior: 'smooth' });
  }

  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        const i = [...slides].indexOf(e.target);
        dots.forEach(d => d.classList.remove('active'));
        dots[i].classList.add('active');
      }
    });
  }, { threshold: 0.5 });

  slides.forEach(s => observer.observe(s));

  // Confetti generator
  const confColors = ['#f48fb1','#ce93d8','#ffcc02','#80deea','#a5d6a7','#f06292','#ab47bc','#ff9800'];

  function makeConfetti(containerId, count = 22) {
    const container = document.getElementById(containerId);
    for (let i = 0; i < count; i++) {
      const c = document.createElement('div');
      c.className = 'conf';
      c.style.cssText = `
        left: ${Math.random()*100}%;
        top: ${Math.random()*30 - 20}%;
        background: ${confColors[Math.floor(Math.random()*confColors.length)]};
        width: ${5 + Math.random()*8}px;
        height: ${5 + Math.random()*8}px;
        border-radius: ${Math.random() > 0.5 ? '50%' : '2px'};
        animation-duration: ${3 + Math.random()*5}s;
        animation-delay: ${Math.random()*4}s;
      `;
      container.appendChild(c);
    }
  }

  ['cf0','cf1','cf2','cf3'].forEach(id => makeConfetti(id, 20));
</script>
</body>
</html>

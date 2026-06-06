[intex.html](https://github.com/user-attachments/files/28662264/tannu_birthday.1.html)
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
  body { font-family: 'Quicksand', sans-serif; overflow-x: hidden; }

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

  /* ── Slide colours ── */
  .slide-1 { background: linear-gradient(135deg, #fce4ec 0%, #f8bbd0 40%, #ffd6e0 100%); }
  .slide-2 { background: linear-gradient(135deg, #ede7f6 0%, #d1c4e9 40%, #e8d5f5 100%); }
  .slide-3 { background: linear-gradient(135deg, #fff8e1 0%, #ffecb3 40%, #ffe0b2 100%); }
  .slide-4 { background: linear-gradient(135deg, #e0f7fa 0%, #b2ebf2 40%, #dcedc8 100%); }

  /* ── Bubbles ── */
  .bubble {
    position: absolute;
    border-radius: 50%;
    opacity: 0.18;
    animation: float 6s ease-in-out infinite;
  }
  @keyframes float {
    0%,100% { transform: translateY(0) scale(1); }
    50%      { transform: translateY(-22px) scale(1.04); }
  }

  /* ── Nav dots ── */
  .nav-dots {
    position: fixed; right: 24px; top: 50%;
    transform: translateY(-50%);
    display: flex; flex-direction: column; gap: 10px; z-index: 100;
  }
  .dot {
    width: 10px; height: 10px; border-radius: 50%;
    background: rgba(0,0,0,0.2); cursor: pointer;
    transition: background .3s, transform .3s; border: none; outline: none;
  }
  .dot.active { background: rgba(0,0,0,0.55); transform: scale(1.3); }

  /* ── SLIDE 1: Enter button ── */
  #enter-screen {
    position: fixed; inset: 0;
    background: linear-gradient(135deg,#fce4ec,#f8bbd0,#ffd6e0);
    display: flex; flex-direction: column;
    align-items: center; justify-content: center;
    z-index: 999;
    transition: opacity 0.8s ease;
  }
  #enter-screen h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(32px,8vw,58px);
    color: #5a2a2a;
    margin-bottom: 12px;
    text-align: center;
  }
  #enter-screen p {
    font-size: 16px; color: rgba(90,40,40,0.6);
    margin-bottom: 40px; letter-spacing: 1px;
  }

  #ready-btn {
    font-family: 'Quicksand', sans-serif;
    font-size: 20px; font-weight: 600;
    padding: 16px 48px;
    border-radius: 50px;
    border: none; cursor: pointer;
    background: linear-gradient(135deg,#f48fb1,#e91e63);
    color: #fff;
    box-shadow: 0 8px 30px rgba(233,30,99,0.35);
    animation: shake 0.6s ease-in-out infinite, glow 1.5s ease-in-out infinite alternate;
    letter-spacing: 1px;
    transition: transform 0.1s;
  }
  #ready-btn:active { transform: scale(0.95); }

  @keyframes shake {
    0%,100% { transform: rotate(-3deg) scale(1.05); }
    25%      { transform: rotate(3deg)  scale(1.08); }
    50%      { transform: rotate(-2deg) scale(1.05); }
    75%      { transform: rotate(2deg)  scale(1.08); }
  }
  @keyframes glow {
    from { box-shadow: 0 8px 30px rgba(233,30,99,0.35); }
    to   { box-shadow: 0 8px 50px rgba(233,30,99,0.7), 0 0 20px rgba(233,30,99,0.4); }
  }

  /* ── Photo frame (single) ── */
  .photo-frame {
    width: 220px; height: 260px;
    border-radius: 120px 120px 80px 80px;
    overflow: hidden;
    box-shadow: 0 12px 40px rgba(0,0,0,0.15);
    margin-bottom: 28px;
    border: 4px solid rgba(255,255,255,0.7);
    background: rgba(255,255,255,0.35);
    display: flex; align-items: center; justify-content: center;
    transition: transform 0.4s;
  }
  .photo-frame:hover { transform: scale(1.04) rotate(-1deg); }
  .photo-frame img { width:100%; height:100%; object-fit:cover; }

  /* ── Slide 2 layout: 2 corners + center text + bottom ── */
  .slide2-layout {
    width: 100%; max-width: 600px;
    position: relative;
    min-height: 85vh;
    display: flex; flex-direction: column;
    align-items: center; justify-content: center;
  }

  .corner-photo {
    position: absolute;
    width: 130px; height: 155px;
    border-radius: 70px 70px 50px 50px;
    overflow: hidden;
    border: 3px solid rgba(255,255,255,0.75);
    box-shadow: 0 8px 24px rgba(0,0,0,0.12);
  }
  .corner-photo img { width:100%; height:100%; object-fit:cover; }
  .corner-tl { top: 10px;  left: 10px; }
  .corner-tr { top: 10px;  right: 10px; }

  .bottom-photo {
    width: 150px; height: 150px;
    border-radius: 50%;
    overflow: hidden;
    border: 4px solid rgba(255,255,255,0.8);
    box-shadow: 0 10px 30px rgba(0,0,0,0.15);
    margin-top: 28px;
  }
  .bottom-photo img { width:100%; height:100%; object-fit:cover; }

  .center-msg {
    text-align: center;
    padding: 0 20px;
    animation: fadeUp 1s ease both;
  }
  .center-msg .msg-text {
    font-family: 'Playfair Display', serif;
    font-size: clamp(22px,5vw,36px);
    font-style: italic;
    color: #3a1a5a;
    line-height: 1.4;
    text-shadow: 0 2px 8px rgba(180,100,220,0.15);
  }
  .center-msg .hearts { font-size: 22px; margin-top: 12px; }

  /* ── Slide 3: 4-photo grid ── */
  .photo-grid {
    display: grid;
    grid-template-columns: repeat(2, 145px);
    grid-template-rows: repeat(2, 145px);
    gap: 12px;
    margin-bottom: 24px;
  }
  .photo-grid .gframe {
    width:145px; height:145px;
    border-radius: 18px;
    overflow: hidden;
    border: 3px solid rgba(255,255,255,0.7);
    box-shadow: 0 6px 20px rgba(0,0,0,0.12);
  }
  .photo-grid .gframe img { width:100%; height:100%; object-fit:cover; }

  /* ── Common text ── */
  .slide-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(36px,7vw,58px);
    font-weight: 700;
    color: #3a2a2a;
    text-align: center;
    line-height: 1.1;
    margin-bottom: 14px;
    animation: fadeUp 0.9s ease both;
  }
  .slide-sub {
    font-size: clamp(14px,3vw,17px);
    font-weight: 400;
    color: rgba(50,30,30,0.65);
    text-align: center;
    max-width: 400px;
    line-height: 1.7;
    animation: fadeUp 0.9s 0.15s ease both;
  }
  .badge {
    display: inline-block;
    font-size: 13px; font-weight: 600;
    letter-spacing: 2px; text-transform: uppercase;
    padding: 6px 18px; border-radius: 30px;
    background: rgba(255,255,255,0.55);
    color: rgba(80,40,40,0.7);
    margin-bottom: 18px;
    border: 1px solid rgba(255,255,255,0.8);
    animation: fadeUp 0.9s ease both;
  }
  .hearts { display:flex; gap:8px; margin-top:22px; font-size:20px; animation: fadeUp 0.9s 0.3s ease both; }
  .heart { animation: pulse 1.4s ease-in-out infinite; }
  .heart:nth-child(2) { animation-delay:.2s; }
  .heart:nth-child(3) { animation-delay:.4s; }
  @keyframes pulse { 0%,100%{transform:scale(1);} 50%{transform:scale(1.3);} }

  /* ── Confetti ── */
  .confetti-wrap { position:absolute; top:0;left:0;right:0;bottom:0; pointer-events:none; overflow:hidden; }
  .conf { position:absolute; width:8px; height:8px; border-radius:2px; opacity:.55; animation:fallDown linear infinite; }
  @keyframes fallDown { 0%{transform:translateY(-40px) rotate(0deg);opacity:.7;} 100%{transform:translateY(110vh) rotate(720deg);opacity:0;} }

  /* ── Scroll cue ── */
  .scroll-cue { position:absolute; bottom:28px; left:50%; transform:translateX(-50%); font-size:11px; letter-spacing:2px; text-transform:uppercase; color:rgba(0,0,0,0.3); display:flex; flex-direction:column; align-items:center; gap:6px; }
  .scroll-arrow { width:18px;height:18px; border-right:2px solid rgba(0,0,0,0.25); border-bottom:2px solid rgba(0,0,0,0.25); transform:rotate(45deg); animation:bounce 1.4s infinite; }
  @keyframes bounce { 0%,100%{transform:rotate(45deg) translateY(0);} 50%{transform:rotate(45deg) translateY(5px);} }
  @keyframes fadeUp { from{opacity:0;transform:translateY(28px);} to{opacity:1;transform:translateY(0);} }
</style>
</head>
<body>

<!-- ══ ENTER SCREEN ══ -->
<div id="enter-screen">
  <h1>🎂 Tannu's<br>Birthday!</h1>
  <p>A special surprise is waiting…</p>
  <button id="ready-btn" onclick="enterSite()">🎉 Ready!</button>
</div>

<!-- Nav dots -->
<nav class="nav-dots">
  <button class="dot active" onclick="goTo(0)"></button>
  <button class="dot" onclick="goTo(1)"></button>
  <button class="dot" onclick="goTo(2)"></button>
  <button class="dot" onclick="goTo(3)"></button>
</nav>

<!-- ══ SLIDE 1 — Hero with img4 ══ -->
<section class="slide slide-1" id="s0">
  <div class="confetti-wrap" id="cf0"></div>
  <div class="bubble" style="width:180px;height:180px;background:#f48fb1;top:-40px;left:-50px;animation-delay:0s;"></div>
  <div class="bubble" style="width:120px;height:120px;background:#f06292;bottom:80px;right:-30px;animation-delay:1.5s;"></div>

  <div class="badge">✨ Special Day ✨</div>

  <div class="photo-frame">
    <img src="img4.jpg" alt="Tannu">
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

<!-- ══ SLIDE 2 — 3 photos + center message ══ -->
<section class="slide slide-2" id="s1">
  <div class="confetti-wrap" id="cf1"></div>
  <div class="bubble" style="width:200px;height:200px;background:#ce93d8;top:-60px;right:-60px;animation-delay:0.5s;"></div>
  <div class="bubble" style="width:90px;height:90px;background:#ab47bc;bottom:60px;left:-20px;animation-delay:2s;"></div>

  <div class="slide2-layout">
    <!-- top left -->
    <div class="corner-photo corner-tl">
      <img src="img2.jpg" alt="Tannu">
    </div>
    <!-- top right -->
    <div class="corner-photo corner-tr">
      <img src="img3.jpg" alt="Tannu">
    </div>

    <!-- center message -->
    <div class="center-msg" style="margin-top:170px;">
      <div class="msg-text">"Happy Birthday to my<br>precious beautiful girl"</div>
      <div class="hearts" style="justify-content:center;">
        <span class="heart">💜</span>
        <span class="heart">🦋</span>
        <span class="heart">💜</span>
      </div>
    </div>

    <!-- bottom center -->
    <div class="bottom-photo">
      <img src="img1.jpg" alt="Tannu">
    </div>
  </div>

  <div class="scroll-cue">scroll <div class="scroll-arrow"></div></div>
</section>

<!-- ══ SLIDE 3 — 4-photo grid ══ -->
<section class="slide slide-3" id="s2">
  <div class="confetti-wrap" id="cf2"></div>
  <div class="bubble" style="width:160px;height:160px;background:#ffcc02;top:-50px;left:-40px;animation-delay:1s;"></div>
  <div class="bubble" style="width:100px;height:100px;background:#ff9800;bottom:40px;right:-20px;animation-delay:2.5s;"></div>

  <div class="badge">🌼 Sweet Memories 🌼</div>

  <div class="photo-grid">
    <div class="gframe"><img src="img1.jpg" alt="Tannu"></div>
    <div class="gframe"><img src="img2.jpg" alt="Tannu"></div>
    <div class="gframe"><img src="img3.jpg" alt="Tannu"></div>
    <div class="gframe"><img src="img4.jpg" alt="Tannu"></div>
  </div>

  <div class="slide-title">Golden<br><em>Moments</em></div>
  <div class="slide-sub">Every picture tells a story. Every moment with you is a treasure worth keeping forever. 🌟</div>
  <div class="scroll-cue">scroll <div class="scroll-arrow"></div></div>
</section>

<!-- ══ SLIDE 4 — Finale ══ -->
<section class="slide slide-4" id="s3">
  <div class="confetti-wrap" id="cf3"></div>
  <div class="bubble" style="width:150px;height:150px;background:#80deea;top:-40px;right:-40px;animation-delay:0.8s;"></div>
  <div class="bubble" style="width:110px;height:110px;background:#a5d6a7;bottom:50px;left:-20px;animation-delay:2.2s;"></div>

  <div class="badge">🎉 Celebrate! 🎉</div>

  <div style="font-size:70px;margin-bottom:16px;animation:fadeUp 0.8s ease both;">🎂</div>

  <div class="slide-title">Here's to<br><em>You, Tannu!</em></div>
  <div class="slide-sub">Another year of adventures, laughter, and beautiful memories ahead. You deserve all the happiness in the world. Stay blessed, stay shining! ✨</div>

  <div class="hearts" style="margin-top:24px;gap:12px;">
    <span class="heart" style="font-size:26px;">🌿</span>
    <span class="heart" style="font-size:26px;">💚</span>
    <span class="heart" style="font-size:26px;">🌿</span>
  </div>

  <div style="margin-top:32px;font-family:'Playfair Display',serif;font-style:italic;font-size:13px;color:rgba(0,0,0,0.35);letter-spacing:1px;">
    Made with 💖 just for you
  </div>
</section>

<script>
  function enterSite() {
    const s = document.getElementById('enter-screen');
    s.style.opacity = '0';
    setTimeout(() => s.style.display = 'none', 800);
  }

  const slides = document.querySelectorAll('.slide');
  const dots   = document.querySelectorAll('.dot');

  function goTo(i) { slides[i].scrollIntoView({ behavior:'smooth' }); }

  const observer = new IntersectionObserver(entries => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        const i = [...slides].indexOf(e.target);
        dots.forEach(d => d.classList.remove('active'));
        dots[i].classList.add('active');
      }
    });
  }, { threshold: 0.5 });
  slides.forEach(s => observer.observe(s));

  const colors = ['#f48fb1','#ce93d8','#ffcc02','#80deea','#a5d6a7','#f06292','#ab47bc','#ff9800'];
  function makeConfetti(id, n=20) {
    const c = document.getElementById(id);
    for (let i=0;i<n;i++) {
      const d = document.createElement('div');
      d.className = 'conf';
      d.style.cssText = `left:${Math.random()*100}%;top:${Math.random()*30-20}%;background:${colors[Math.floor(Math.random()*colors.length)]};width:${5+Math.random()*8}px;height:${5+Math.random()*8}px;border-radius:${Math.random()>.5?'50%':'2px'};animation-duration:${3+Math.random()*5}s;animation-delay:${Math.random()*4}s;`;
      c.appendChild(d);
    }
  }
  ['cf0','cf1','cf2','cf3'].forEach(id => makeConfetti(id));
</script>
</body>
</html>

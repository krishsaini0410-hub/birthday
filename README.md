<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday Tannu!</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body, html {
            height: 100%;
            scroll-behavior: smooth;
            overflow: hidden;
            background-color: #fff5f5;
        }

        /* Intro Screen with Burst Effect */
        #intro-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle, #ffe3e3, #ffd1d1);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            transition: opacity 0.8s ease-out, visibility 0.8s;
        }

        @keyframes shake {
            0% { transform: translate(1px, 1px) rotate(0deg); }
            10% { transform: translate(-1px, -2px) rotate(-1deg); }
            20% { transform: translate(-3px, 0px) rotate(1deg); }
            30% { transform: translate(0px, 2px) rotate(0deg); }
            40% { transform: translate(1px, -1px) rotate(1deg); }
            50% { transform: translate(-1px, 2px) rotate(-1deg); }
            60% { transform: translate(-3px, 1px) rotate(0deg); }
            70% { transform: translate(2px, 1px) rotate(-1deg); }
            80% { transform: translate(-1px, -1px) rotate(1deg); }
            90% { transform: translate(2px, 2px) rotate(0deg); }
            100% { transform: translate(1px, -2px) rotate(0deg); }
        }

        .ready-btn {
            padding: 20px 50px;
            font-size: 2rem;
            font-weight: bold;
            color: white;
            background: linear-gradient(45deg, #ff4b5c, #ff6b8b);
            border: none;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 10px 25px rgba(255, 75, 92, 0.4);
            animation: shake 0.5s infinite;
            transition: transform 0.2s;
        }

        .ready-btn:hover {
            animation-play-state: paused;
            transform: scale(1.1);
        }

        /* Particle / Sparkle Styles */
        .particle {
            position: fixed;
            pointer-events: none;
            z-index: 10000;
            border-radius: 50%;
            animation: explode 1.2s forwards ease-out;
        }

        @keyframes explode {
            0% {
                transform: translate(-50%, -50%) scale(1);
                opacity: 1;
            }
            100% {
                transform: translate(var(--mx), var(--my)) scale(0);
                opacity: 0;
            }
        }

        /* Main Container setup */
        .main-wrapper {
            height: 100%;
            overflow-y: scroll;
            snap-type: y mandatory;
        }

        .slide {
            height: 100vh;
            width: 100%;
            display: flex;
            justify-content: center;
            align-items: center;
            snap-align: start;
            position: relative;
            padding: 40px;
        }

        /* Slide 1 Layout: Left Photo (Full length), Right Text */
        #slide1 {
            background-color: #fff0f5; /* Light Rose Pink */
            display: flex;
            flex-direction: row;
            align-items: center;
            justify-content: space-between;
            gap: 50px;
            max-width: 1400px;
            margin: 0 auto;
        }

        .s1-photo-container {
            flex: 1;
            height: 85vh;
            max-width: 700px;
            max-height: 1300px;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .s1-photo-container img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 24px;
            box-shadow: 0 15px 35px rgba(0,0,0,0.15);
        }

        .s1-text-container {
            flex: 1;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: flex-start;
            text-align: left;
        }

        .s1-text-container h1 {
            font-size: 3.5rem;
            color: #d63384;
            margin-bottom: 20px;
            line-height: 1.2;
        }

        .s1-text-container p {
            font-size: 1.5rem;
            color: #6c757d;
        }

        /* Slide 2 Layout: Corners and center text */
        #slide2 {
            background-color: #f3e5f5; /* Dreamy Lavender */
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .s2-top-row {
            display: flex;
            justify-content: space-between;
            width: 100%;
            padding: 20px;
        }

        .s2-center-content {
            text-align: center;
            max-width: 600px;
            margin: auto;
        }

        .s2-center-content h2 {
            font-size: 2.8rem;
            color: #6a1b9a;
            line-height: 1.4;
        }

        .s2-bottom-row {
            display: flex;
            justify-content: center;
            width: 100%;
            padding: 20px;
        }

        .s2-card {
            width: 200px;
            height: 240px;
            object-fit: cover;
            border-radius: 16px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        }

        .s2-card-square {
            width: 200px;
            height: 200px;
            object-fit: cover;
            border-radius: 16px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        }

        /* Slide 3 Layout: 2 Horizontal Pictures */
        #slide3 {
            background-color: #fff3e0; /* Peachy Gold */
            flex-direction: column;
            gap: 30px;
        }

        .horizontal-gallery {
            display: flex;
            gap: 40px;
            justify-content: center;
            align-items: center;
            width: 100%;
            max-width: 1000px;
        }

        .horizontal-gallery img {
            width: 45%;
            height: 450px;
            object-fit: cover;
            border-radius: 20px;
            box-shadow: 0 12px 28px rgba(0,0,0,0.12);
        }

        /* Slide 4 Layout: Finale */
        #slide4 {
            background-color: #e8f5e9; /* Mint Green */
            flex-direction: column;
            text-align: center;
            gap: 20px;
        }

        #slide4 h2 {
            font-size: 4rem;
            color: #2e7d32;
        }

        #slide4 p {
            font-size: 1.8rem;
            color: #4caf50;
        }

        /* Confetti elements for Slide 4 */
        .confetti-dummy {
            font-size: 4rem;
            animation: bounce 2s infinite alternate;
        }

        @keyframes bounce {
            0% { transform: translateY(0); }
            100% { transform: translateY(-20px); }
        }

        /* Mobile Adjustments */
        @media (max-width: 768px) {
            #slide1 {
                flex-direction: column;
                gap: 20px;
                padding: 20px;
            }
            .s1-photo-container {
                height: 50vh;
                width: 100%;
            }
            .s1-text-container h1 {
                font-size: 2.2rem;
            }
            .horizontal-gallery {
                flex-direction: column;
                gap: 20px;
            }
            .horizontal-gallery img {
                width: 90%;
                height: 250px;
            }
            .s2-card, .s2-card-square {
                width: 100px;
                height: 120px;
            }
            .s2-card-square {
                height: 100px;
            }
            .s2-center-content h2 {
                font-size: 1.6rem;
            }
        }
    </style>
</head>
<body>

    <!-- Ready Button Overlay Screen -->
    <div id="intro-overlay">
        <button class="ready-btn" onclick="triggerBurst(event)">Ready!</button>
    </div>

    <!-- Main Website Scroll Wrapper -->
    <div class="main-wrapper">

        <!-- Slide 1: Side-by-Side Full Length Hero Presentation -->
        <section class="slide" id="slide1">
            <div class="s1-photo-container">
                <!-- Left Full Length Picture (img4.jpg) -->
                <img src="img4.jpg" alt="Tannu Portrait">
            </div>
            <div class="s1-text-container">
                <h1>Happy Birthday,<br>Tannu! ✨</h1>
                <p>Welcome to your special day web corner. Scroll down to see your memories...</p>
            </div>
        </section>

        <!-- Slide 2: Corners Configuration & Perfect Message -->
        <section class="slide" id="slide2">
            <div class="s2-top-row">
                <img src="img2.jpg" alt="Tannu Left Top" class="s2-card">
                <img src="img3.jpg" alt="Tannu Right Top" class="s2-card">
            </div>
            
            <div class="s2-center-content">
                <h2>"Happy Birthday to my precious beautiful girl"</h2>
            </div>
            
            <div class="s2-bottom-row">
                <img src="img1.jpg" alt="Tannu Bottom" class="s2-card-square">
            </div>
        </section>

        <!-- Slide 3: Two Horizontal Hoodie Pictures Side by Side -->
        <section class="slide" id="slide3">
            <h2 style="color: #e65100; font-size: 2.5rem;">Memories Together 🎯</h2>
            <div class="horizontal-gallery">
                <img src="img5.jpg" alt="Hoodie Photo 1">
                <img src="img6.jpg" alt="Hoodie Photo 2">
            </div>
        </section>

        <!-- Slide 4: Celebration Finale -->
        <section class="slide" id="slide4">
            <div class="confetti-dummy">🎉 🎂 🥳 🎈</div>
            <h2>Let's Celebrate!</h2>
            <p>Wishing you a year filled with endless laughter, success, and beautiful moments.</p>
        </section>

    </div>

    <script>
        function triggerBurst(event) {
            const btn = event.target;
            const rect = btn.getBoundingClientRect();
            const centerX = rect.left + rect.width / 2;
            const centerY = rect.top + rect.height / 2;
            
            const particleCount = 60;
            const colors = ['#ff4b5c', '#ff6b8b', '#ffeb3b', '#4caf50', '#00bcd4', '#9c27b0'];
            const emojis = ['✨', '💖', '🎉', '🌸', '🎂'];

            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.classList.add('particle');
                
                // Determine whether to spawn a colorful dot or an emoji
                if (Math.random() > 0.4) {
                    particle.style.background = colors[Math.floor(Math.random() * colors.length)];
                    const size = Math.random() * 12 + 6;
                    particle.style.width = `${size}px`;
                    particle.style.height = `${size}px`;
                } else {
                    particle.innerText = emojis[Math.floor(Math.random() * emojis.length)];
                    particle.style.fontSize = `${Math.random() * 15 + 15}px`;
                }

                // Random angle and distance for explosion motion path
                const angle = Math.random() * Math.PI * 2;
                const distance = Math.random() * 250 + 100;
                const moveX = Math.cos(angle) * distance;
                const moveY = Math.sin(angle) * distance;

                particle.style.setProperty('--mx', `${moveX}px`);
                particle.style.setProperty('--my', `${moveY}px`);
                
                particle.style.left = `${centerX}px`;
                particle.style.top = `${centerY}px`;

                document.body.appendChild(particle);

                // Cleanup particles after animation runs out
                setTimeout(() => {
                    particle.remove();
                }, 1200);
            }

            // Hide overlay smoothly right after the explosion sparks fly
            setTimeout(() => {
                const overlay = document.getElementById('intro-overlay');
                overlay.style.opacity = '0';
                overlay.style.visibility = 'hidden';
                // Unlock slide viewport scrolling interaction 
                document.body.style.overflow = 'auto';
                document.documentElement.style.overflow = 'auto';
            }, 400);
        }
    </script>
</body>
</html>

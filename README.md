<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Happy Father's Day 💙</title>
    <style>
        /* ── Reset & Base ── */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(145deg, #0b1a2e, #1a2f44);
            font-family: 'Segoe UI', 'Poppins', system-ui, sans-serif;
            padding: 20px;
            overflow-x: hidden;
        }

        /* ── Floating particles (stars) ── */
        .particles {
            position: fixed;
            inset: 0;
            pointer-events: none;
            z-index: 0;
            overflow: hidden;
        }
        .particle {
            position: absolute;
            width: 6px;
            height: 6px;
            background: rgba(255, 215, 100, 0.5);
            border-radius: 50%;
            box-shadow: 0 0 12px rgba(255, 215, 100, 0.3);
            animation: floatParticle linear infinite;
        }
        @keyframes floatParticle {
            0% {
                transform: translateY(100vh) scale(0.2);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                transform: translateY(-10vh) scale(1.2);
                opacity: 0;
            }
        }

        /* ── Card Container ── */
        .card-wrapper {
            perspective: 1500px;
            width: 100%;
            max-width: 520px;
            position: relative;
            z-index: 1;
        }

        /* ── The Card ── */
        .card {
            position: relative;
            width: 100%;
            padding-bottom: 130%;
            /* aspect ratio ~ 3:4 */
            transition: transform 1.2s cubic-bezier(0.23, 1, 0.32, 1);
            transform-style: preserve-3d;
            cursor: pointer;
        }
        .card.flipped {
            transform: rotateY(180deg);
        }

        /* ── Faces ── */
        .card-face {
            position: absolute;
            inset: 0;
            border-radius: 32px;
            backface-visibility: hidden;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 30px 28px;
            box-shadow: 0 30px 60px rgba(0, 0, 0, 0.6), 0 0 0 2px rgba(255, 215, 100, 0.15);
            overflow: hidden;
            transition: box-shadow 0.4s;
        }
        .card-face:hover {
            box-shadow: 0 40px 80px rgba(0, 0, 0, 0.7), 0 0 0 3px rgba(255, 215, 100, 0.25);
        }

        /* ── Front ── */
        .card-front {
            background: linear-gradient(160deg, #1e3a5f, #0f2440);
            color: #f5e7c8;
            border: 1px solid rgba(255, 215, 100, 0.2);
            transform: rotateY(0deg);
        }
        .card-front::before {
            content: '';
            position: absolute;
            inset: 0;
            background: radial-gradient(circle at 20% 30%, rgba(255, 215, 100, 0.06), transparent 70%);
            pointer-events: none;
        }
        .card-front .gold {
            color: #f6c96e;
            text-shadow: 0 0 20px rgba(246, 201, 110, 0.25);
        }

        .front-icon {
            font-size: 70px;
            margin-bottom: 16px;
            animation: pulseGlow 2.4s ease-in-out infinite;
            filter: drop-shadow(0 0 18px rgba(255, 215, 100, 0.3));
        }
        @keyframes pulseGlow {
            0%,
            100% {
                transform: scale(1);
                filter: drop-shadow(0 0 18px rgba(255, 215, 100, 0.25));
            }
            50% {
                transform: scale(1.08);
                filter: drop-shadow(0 0 34px rgba(255, 215, 100, 0.5));
            }
        }

        .front-title {
            font-size: clamp(2rem, 8vw, 3.2rem);
            font-weight: 700;
            letter-spacing: 2px;
            text-align: center;
            line-height: 1.2;
            margin-bottom: 6px;
        }
        .front-sub {
            font-size: clamp(1rem, 3vw, 1.3rem);
            color: #b8d0e8;
            letter-spacing: 4px;
            text-transform: uppercase;
            font-weight: 300;
            margin-bottom: 20px;
            border-bottom: 2px solid rgba(246, 201, 110, 0.25);
            padding-bottom: 14px;
        }
        .front-names {
            font-size: clamp(1.3rem, 4vw, 1.9rem);
            font-weight: 300;
            color: #f0e0c0;
            letter-spacing: 3px;
        }
        .front-names strong {
            font-weight: 600;
            color: #f6c96e;
        }

        .front-hint {
            margin-top: 28px;
            font-size: 0.9rem;
            color: rgba(255, 255, 255, 0.35);
            letter-spacing: 2px;
            border: 1px solid rgba(255, 215, 100, 0.12);
            padding: 8px 22px;
            border-radius: 40px;
            background: rgba(255, 255, 255, 0.03);
            backdrop-filter: blur(2px);
            transition: all 0.3s;
        }
        .card-front:hover .front-hint {
            color: rgba(255, 255, 255, 0.6);
            border-color: rgba(255, 215, 100, 0.25);
        }

        /* ── Back ── */
        .card-back {
            background: linear-gradient(160deg, #faf3e8, #f0e3d0);
            color: #1e2f44;
            transform: rotateY(180deg);
            border: 1px solid rgba(246, 201, 110, 0.3);
            justify-content: flex-start;
            padding-top: 40px;
        }
        .card-back::before {
            content: '';
            position: absolute;
            inset: 0;
            background: radial-gradient(circle at 80% 10%, rgba(246, 201, 110, 0.10), transparent 60%);
            pointer-events: none;
        }

        .back-header {
            display: flex;
            align-items: center;
            gap: 12px;
            margin-bottom: 18px;
            width: 100%;
            border-bottom: 2px solid rgba(246, 201, 110, 0.3);
            padding-bottom: 14px;
        }
        .back-header .heart-icon {
            font-size: 32px;
            color: #d44a5a;
            animation: heartBeat 1.6s ease-in-out infinite;
        }
        @keyframes heartBeat {
            0%,
            100% {
                transform: scale(1);
            }
            15% {
                transform: scale(1.25);
            }
            30% {
                transform: scale(1);
            }
            45% {
                transform: scale(1.15);
            }
            60% {
                transform: scale(1);
            }
        }
        .back-header h2 {
            font-size: clamp(1.2rem, 4vw, 1.8rem);
            font-weight: 600;
            color: #1a2f44;
            letter-spacing: 1px;
        }
        .back-header h2 span {
            color: #d44a5a;
        }

        .message {
            font-size: clamp(1rem, 2.8vw, 1.25rem);
            line-height: 1.8;
            color: #2a3f54;
            text-align: left;
            width: 100%;
            margin: 6px 0 12px;
            font-weight: 400;
        }
        .message p {
            margin-bottom: 14px;
        }
        .message .signature {
            text-align: right;
            font-style: italic;
            font-size: clamp(1.1rem, 3vw, 1.4rem);
            color: #1a2f44;
            margin-top: 8px;
            border-top: 1px solid rgba(246, 201, 110, 0.25);
            padding-top: 14px;
        }
        .message .signature strong {
            font-weight: 600;
            color: #c47a3a;
        }

        .back-deco {
            display: flex;
            gap: 10px;
            margin-top: 8px;
            font-size: 26px;
            letter-spacing: 6px;
            color: #c47a3a;
            opacity: 0.4;
            width: 100%;
            justify-content: center;
        }

        .back-hint {
            margin-top: auto;
            font-size: 0.75rem;
            color: rgba(26, 47, 68, 0.3);
            letter-spacing: 2px;
            text-transform: uppercase;
            border-top: 1px solid rgba(26, 47, 68, 0.08);
            padding-top: 16px;
            width: 100%;
            text-align: center;
        }

        /* ── Responsive tweaks ── */
        @media (max-width: 480px) {
            .card-face {
                padding: 24px 18px;
                border-radius: 24px;
            }
            .front-icon {
                font-size: 50px;
            }
            .message {
                font-size: 0.95rem;
                line-height: 1.7;
            }
            .back-header .heart-icon {
                font-size: 26px;
            }
        }

        @media (min-width: 768px) {
            .card-wrapper {
                max-width: 580px;
            }
        }

        /* ── Confetti overlay (on flip) ── */
        .confetti-container {
            position: fixed;
            inset: 0;
            pointer-events: none;
            z-index: 10;
            overflow: hidden;
        }
        .confetti-piece {
            position: absolute;
            width: 10px;
            height: 10px;
            opacity: 0;
            animation: confettiFall linear forwards;
        }
        @keyframes confettiFall {
            0% {
                transform: translateY(-20px) rotate(0deg) scale(0.5);
                opacity: 1;
            }
            100% {
                transform: translateY(110vh) rotate(720deg) scale(1.2);
                opacity: 0;
            }
        }
    </style>
</head>
<body>

    <!-- ─── Floating Particles ─── -->
    <div class="particles" id="particles"></div>

    <!-- ─── Confetti Container ─── -->
    <div class="confetti-container" id="confettiContainer"></div>

    <!-- ─── Card ─── -->
    <div class="card-wrapper">
        <div class="card" id="card">

            <!-- FRONT -->
            <div class="card-face card-front">
                <div class="front-icon">👔</div>
                <div class="front-title gold">Happy Father's Day</div>
                <div class="front-sub">with love</div>
                <div class="front-names">
                    from <strong>Wan</strong> &amp; <strong>Senette</strong>
                </div>
                <div class="front-hint">✨ tap to open ✨</div>
            </div>

            <!-- BACK -->
            <div class="card-face card-back">
                <div class="back-header">
                    <span class="heart-icon">❤️</span>
                    <h2>For <span>Dad</span></h2>
                </div>

                <div class="message">
                    <p>
                        Thank you for being our rock, our guide, and our greatest
                        cheerleader. Your strength, kindness, and wisdom inspire us
                        every single day.
                    </p>
                    <p>
                        We're so grateful for all the little moments — the laughs,
                        the talks, and the way you always make us feel loved.
                    </p>
                    <p>
                        You are our hero, today and always.
                    </p>
                    <div class="signature">
                        with all our love,<br />
                        <strong>Wan</strong> &amp; <strong>Senette</strong> 💙
                    </div>
                </div>

                <div class="back-deco">✦ ✧ ✦ ✧ ✦</div>
                <div class="back-hint">♡ forever &amp; always ♡</div>
            </div>

        </div>
    </div>

    <script>
        // ─── Particles ───
        (function createParticles() {
            const container = document.getElementById('particles');
            const count = 50;
            for (let i = 0; i < count; i++) {
                const p = document.createElement('div');
                p.className = 'particle';
                const size = 3 + Math.random() * 8;
                p.style.width = size + 'px';
                p.style.height = size + 'px';
                p.style.left = Math.random() * 100 + '%';
                p.style.animationDuration = 12 + Math.random() * 20 + 's';
                p.style.animationDelay = Math.random() * 20 + 's';
                p.style.background = `rgba(255, 215, 100, ${0.2 + Math.random() * 0.4})`;
                p.style.boxShadow = `0 0 ${size * 2}px rgba(255, 215, 100, ${0.1 + Math.random() * 0.2})`;
                container.appendChild(p);
            }
        })();

        // ─── Card Flip ───
        const card = document.getElementById('card');
        let isFlipped = false;

        card.addEventListener('click', function(e) {
            // Ignore clicks on interactive elements inside the card if needed
            isFlipped = !isFlipped;
            card.classList.toggle('flipped', isFlipped);

            // Trigger confetti when opening (back face becomes visible)
            if (isFlipped) {
                launchConfetti();
            }
        });

        // ─── Confetti ───
        function launchConfetti() {
            const container = document.getElementById('confettiContainer');
            const colors = ['#f6c96e', '#d44a5a', '#4a8db7', '#f0e3d0', '#c47a3a', '#8ab3cf', '#ffb07c'];
            const count = 70;

            for (let i = 0; i < count; i++) {
                const piece = document.createElement('div');
                piece.className = 'confetti-piece';
                const size = 6 + Math.random() * 10;
                const isCircle = Math.random() > 0.5;
                piece.style.width = isCircle ? size + 'px' : size * 0.4 + 'px';
                piece.style.height = isCircle ? size + 'px' : size * 1.6 + 'px';
                piece.style.borderRadius = isCircle ? '50%' : '2px';
                piece.style.background = colors[Math.floor(Math.random() * colors.length)];
                piece.style.left = Math.random() * 100 + '%';
                piece.style.top = '-10px';
                piece.style.transform = `rotate(${Math.random() * 360}deg)`;
                const duration = 2 + Math.random() * 3;
                piece.style.animationDuration = duration + 's';
                piece.style.animationDelay = Math.random() * 1.2 + 's';
                piece.style.opacity = '1';
                piece.style.boxShadow = '0 2px 8px rgba(0,0,0,0.15)';
                container.appendChild(piece);

                // Remove after animation ends
                setTimeout(() => {
                    if (piece.parentNode) piece.remove();
                }, (duration + 1.5) * 1000);
            }

            // Clean up any leftovers after a while
            setTimeout(() => {
                const remain = container.querySelectorAll('.confetti-piece');
                remain.forEach(el => el.remove());
            }, 6000);
        }

        // ─── Keyboard support (Enter / Space) ───
        card.setAttribute('tabindex', '0');
        card.setAttribute('role', 'button');
        card.addEventListener('keydown', function(e) {
            if (e.key === 'Enter' || e.key === ' ') {
                e.preventDefault();
                card.click();
            }
        });

        // ─── Small initial hint: auto-flip after 4s? No – let user discover ───
        // But we can add a tiny pulse to the hint
        console.log('💙 Happy Father\'s Day from Wan & Senette!');
    </script>

</body>
</html>
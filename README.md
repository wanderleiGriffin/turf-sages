<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes" />
    <title>Happy Father's Day 💙</title>
    <style>
        /* ── Reset & Base ── */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            min-height: 100dvh;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(145deg, #0b1a2e, #1a2f44);
            font-family: 'Segoe UI', 'Poppins', system-ui, -apple-system, sans-serif;
            padding: 16px;
            touch-action: manipulation;
        }

        /* ── Card Container ── */
        .card-wrapper {
            perspective: 1500px;
            width: 100%;
            max-width: 460px;
            /* slightly narrower for phone comfort */
            position: relative;
            z-index: 1;
        }

        /* ── The Card ── */
        .card {
            position: relative;
            width: 100%;
            padding-bottom: 135%;
            /* taller ratio for portrait phones */
            transition: transform 1.2s cubic-bezier(0.23, 1, 0.32, 1);
            transform-style: preserve-3d;
            cursor: pointer;
            -webkit-tap-highlight-color: transparent;
        }
        .card.flipped {
            transform: rotateY(180deg);
        }

        /* ── Faces ── */
        .card-face {
            position: absolute;
            inset: 0;
            border-radius: 28px;
            backface-visibility: hidden;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 28px 22px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.6), 0 0 0 2px rgba(255, 215, 100, 0.12);
            overflow: hidden;
            transition: box-shadow 0.3s;
        }

        /* ── Front ── */
        .card-front {
            background: linear-gradient(160deg, #1e3a5f, #0f2440);
            color: #f5e7c8;
            border: 1px solid rgba(255, 215, 100, 0.15);
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
            text-shadow: 0 0 24px rgba(246, 201, 110, 0.2);
        }

        .front-icon {
            font-size: 60px;
            margin-bottom: 12px;
            animation: pulseGlow 2.6s ease-in-out infinite;
            filter: drop-shadow(0 0 16px rgba(255, 215, 100, 0.2));
        }
        @keyframes pulseGlow {
            0%,
            100% {
                transform: scale(1);
                filter: drop-shadow(0 0 16px rgba(255, 215, 100, 0.2));
            }
            50% {
                transform: scale(1.06);
                filter: drop-shadow(0 0 30px rgba(255, 215, 100, 0.4));
            }
        }

        .front-title {
            font-size: clamp(2.2rem, 10vw, 3.4rem);
            font-weight: 700;
            letter-spacing: 1px;
            text-align: center;
            line-height: 1.2;
            margin-bottom: 4px;
        }
        .front-sub {
            font-size: clamp(0.85rem, 3vw, 1.2rem);
            color: #b8d0e8;
            letter-spacing: 3px;
            text-transform: uppercase;
            font-weight: 300;
            margin-bottom: 14px;
            border-bottom: 2px solid rgba(246, 201, 110, 0.2);
            padding-bottom: 12px;
        }
        .front-names {
            font-size: clamp(1.1rem, 4.5vw, 1.9rem);
            font-weight: 300;
            color: #f0e0c0;
            letter-spacing: 2px;
            text-align: center;
        }
        .front-names strong {
            font-weight: 600;
            color: #f6c96e;
        }

        .front-hint {
            margin-top: 24px;
            font-size: 0.8rem;
            color: rgba(255, 255, 255, 0.3);
            letter-spacing: 2px;
            border: 1px solid rgba(255, 215, 100, 0.1);
            padding: 6px 20px;
            border-radius: 40px;
            background: rgba(255, 255, 255, 0.02);
            transition: all 0.3s;
            touch-action: none;
        }

        /* ── Back ── */
        .card-back {
            background: linear-gradient(160deg, #faf3e8, #f0e3d0);
            color: #1e2f44;
            transform: rotateY(180deg);
            border: 1px solid rgba(246, 201, 110, 0.25);
            justify-content: flex-start;
            padding-top: 32px;
        }
        .card-back::before {
            content: '';
            position: absolute;
            inset: 0;
            background: radial-gradient(circle at 80% 10%, rgba(246, 201, 110, 0.08), transparent 60%);
            pointer-events: none;
        }

        .back-header {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 14px;
            width: 100%;
            border-bottom: 2px solid rgba(246, 201, 110, 0.3);
            padding-bottom: 12px;
        }
        .back-header .heart-icon {
            font-size: 28px;
            color: #d44a5a;
            animation: heartBeat 1.8s ease-in-out infinite;
        }
        @keyframes heartBeat {
            0%,
            100% {
                transform: scale(1);
            }
            15% {
                transform: scale(1.2);
            }
            30% {
                transform: scale(1);
            }
            45% {
                transform: scale(1.1);
            }
            60% {
                transform: scale(1);
            }
        }
        .back-header h2 {
            font-size: clamp(1.1rem, 4.5vw, 1.8rem);
            font-weight: 600;
            color: #1a2f44;
            letter-spacing: 0.5px;
        }
        .back-header h2 span {
            color: #d44a5a;
        }

        .message {
            font-size: clamp(0.95rem, 3vw, 1.2rem);
            line-height: 1.7;
            color: #2a3f54;
            text-align: left;
            width: 100%;
            margin: 4px 0 10px;
            font-weight: 400;
        }
        .message p {
            margin-bottom: 12px;
        }
        .message .signature {
            text-align: right;
            font-style: italic;
            font-size: clamp(1rem, 3.2vw, 1.4rem);
            color: #1a2f44;
            margin-top: 6px;
            border-top: 1px solid rgba(246, 201, 110, 0.25);
            padding-top: 12px;
        }
        .message .signature strong {
            font-weight: 600;
            color: #c47a3a;
        }

        .back-deco {
            display: flex;
            gap: 8px;
            margin-top: 6px;
            font-size: 22px;
            letter-spacing: 4px;
            color: #c47a3a;
            opacity: 0.35;
            width: 100%;
            justify-content: center;
        }

        .back-hint {
            margin-top: auto;
            font-size: 0.7rem;
            color: rgba(26, 47, 68, 0.25);
            letter-spacing: 2px;
            text-transform: uppercase;
            border-top: 1px solid rgba(26, 47, 68, 0.06);
            padding-top: 14px;
            width: 100%;
            text-align: center;
            padding-bottom: 4px;
        }

        /* ── Responsive phone tweaks ── */
        @media (max-width: 480px) {
            .card-face {
                padding: 22px 16px;
                border-radius: 24px;
            }
            .front-icon {
                font-size: 48px;
            }
            .message p {
                margin-bottom: 10px;
            }
            .back-header {
                margin-bottom: 10px;
                padding-bottom: 10px;
            }
        }

        @media (max-width: 380px) {
            .card-face {
                padding: 18px 14px;
                border-radius: 20px;
            }
            .front-title {
                font-size: 1.8rem;
            }
            .front-icon {
                font-size: 40px;
            }
            .message {
                font-size: 0.85rem;
            }
        }

        /* ── Confetti overlay ── */
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
                transform: translateY(-20px) rotate(0deg) scale(0.4);
                opacity: 1;
            }
            100% {
                transform: translateY(110vh) rotate(720deg) scale(1.1);
                opacity: 0;
            }
        }
    </style>
</head>
<body>

    <!-- ─── Confetti Container ─── -->
    <div class="confetti-container" id="confettiContainer"></div>

    <!-- ─── Card ─── -->
    <div class="card-wrapper">
        <div class="card" id="card" role="button" tabindex="0" aria-label="Father's Day card from Wan and Senette">

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
        // ─── Card Flip ───
        const card = document.getElementById('card');
        let isFlipped = false;

        function handleFlip(e) {
            // Prevent double-tap zoom on mobile
            if (e) e.preventDefault();
            isFlipped = !isFlipped;
            card.classList.toggle('flipped', isFlipped);

            if (isFlipped) {
                launchConfetti();
            }
        }

        // Click / touch
        card.addEventListener('click', handleFlip);
        // Keyboard support
        card.addEventListener('keydown', function(e) {
            if (e.key === 'Enter' || e.key === ' ') {
                e.preventDefault();
                handleFlip(e);
            }
        });

        // ─── Confetti (lighter for mobile) ───
        function launchConfetti() {
            const container = document.getElementById('confettiContainer');
            const colors = ['#f6c96e', '#d44a5a', '#4a8db7', '#f0e3d0', '#c47a3a', '#8ab3cf', '#ffb07c'];
            const count = 50; // fewer pieces for performance on phones

            for (let i = 0; i < count; i++) {
                const piece = document.createElement('div');
                piece.className = 'confetti-piece';
                const size = 5 + Math.random() * 8;
                const isCircle = Math.random() > 0.5;
                piece.style.width = isCircle ? size + 'px' : size * 0.4 + 'px';
                piece.style.height = isCircle ? size + 'px' : size * 1.5 + 'px';
                piece.style.borderRadius = isCircle ? '50%' : '2px';
                piece.style.background = colors[Math.floor(Math.random() * colors.length)];
                piece.style.left = Math.random() * 100 + '%';
                piece.style.top = '-10px';
                piece.style.transform = `rotate(${Math.random() * 360}deg)`;
                const duration = 2 + Math.random() * 2.5;
                piece.style.animationDuration = duration + 's';
                piece.style.animationDelay = Math.random() * 1.0 + 's';
                piece.style.boxShadow = '0 2px 6px rgba(0,0,0,0.12)';
                container.appendChild(piece);

                setTimeout(() => {
                    if (piece.parentNode) piece.remove();
                }, (duration + 1.5) * 1000);
            }

            setTimeout(() => {
                const remain = container.querySelectorAll('.confetti-piece');
                remain.forEach(el => el.remove());
            }, 5000);
        }

        // ─── Prevent zoom on double-tap (iOS) ───
        let lastTouchEnd = 0;
        document.addEventListener('touchend', function(e) {
            const now = Date.now();
            if (now - lastTouchEnd <= 300) {
                e.preventDefault();
            }
            lastTouchEnd = now;
        }, { passive: false });

        console.log('💙 Happy Father\'s Day from Wan & Senette!');
    </script>

</body>
</html>
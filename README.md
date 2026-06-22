<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes" />
  <title>Father's Day ✦ Wan & Senette</title>
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
      background: linear-gradient(135deg, #f9f3e8 0%, #f0e6d8 100%);
      font-family: 'Georgia', 'Times New Roman', serif;
      padding: 16px;
      touch-action: manipulation;
    }

    /* ── Main card container ── */
    .card {
      width: 100%;
      max-width: 440px;
      background: #ffffff;
      border-radius: 36px;
      box-shadow: 0 30px 60px rgba(0, 0, 0, 0.10), 0 10px 25px rgba(0, 0, 0, 0.06);
      overflow: hidden;
      position: relative;
      transition: box-shadow 0.3s;
      border: 1px solid rgba(200, 170, 130, 0.2);
    }

    /* ── Panels ── */
    .panel {
      padding: 40px 28px 32px;
      transition: transform 0.7s cubic-bezier(0.23, 1, 0.32, 1), opacity 0.5s ease;
      will-change: transform, opacity;
      background: #ffffff;
      min-height: 480px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      text-align: center;
    }

    /* Front panel */
    .panel-front {
      transform: translateY(0);
      opacity: 1;
      position: relative;
      z-index: 2;
      background: linear-gradient(150deg, #fcf8f2 0%, #f5ede2 100%);
      border-bottom: 1px solid rgba(200, 170, 130, 0.1);
    }

    .panel-front .deco-line {
      width: 60px;
      height: 3px;
      background: #c9a87c;
      margin: 12px auto 16px;
      border-radius: 4px;
      opacity: 0.5;
    }

    .panel-front .icon-big {
      font-size: 68px;
      margin-bottom: 8px;
      filter: drop-shadow(0 4px 12px rgba(0,0,0,0.06));
    }

    .panel-front h1 {
      font-size: clamp(2.2rem, 10vw, 3.2rem);
      font-weight: 700;
      color: #2d3e4b;
      letter-spacing: 1px;
      line-height: 1.2;
      margin-bottom: 2px;
    }
    .panel-front .gold {
      color: #b8895c;
    }
    .panel-front .sub {
      font-size: clamp(0.9rem, 2.5vw, 1.1rem);
      color: #7a8d9b;
      letter-spacing: 4px;
      text-transform: uppercase;
      font-weight: 400;
      margin-top: -2px;
    }
    .panel-front .names {
      font-size: clamp(1.2rem, 4vw, 1.8rem);
      color: #2d3e4b;
      margin-top: 10px;
      font-weight: 300;
      letter-spacing: 1px;
    }
    .panel-front .names strong {
      color: #b8895c;
      font-weight: 600;
    }

    .panel-front .tap-hint {
      margin-top: 28px;
      font-size: 0.8rem;
      color: #a0b2be;
      letter-spacing: 2px;
      background: rgba(200, 170, 130, 0.08);
      padding: 6px 24px;
      border-radius: 40px;
      border: 1px solid rgba(200, 170, 130, 0.12);
      transition: all 0.3s;
      cursor: default;
    }

    /* ── Back panel (message) ── */
    .panel-back {
      transform: translateY(20px) scale(0.97);
      opacity: 0;
      pointer-events: none;
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      z-index: 1;
      background: #fcf9f5;
      padding: 36px 28px 30px;
      justify-content: flex-start;
      text-align: left;
      border-radius: 36px;
      box-shadow: inset 0 0 0 1px rgba(200, 170, 130, 0.08);
    }

    .panel-back.open {
      transform: translateY(0) scale(1);
      opacity: 1;
      pointer-events: auto;
      z-index: 3;
    }

    /* when back is open, front slides up and fades */
    .panel-front.slide-up {
      transform: translateY(-30px) scale(0.96);
      opacity: 0;
      pointer-events: none;
      transition: transform 0.6s cubic-bezier(0.23, 1, 0.32, 1), opacity 0.5s ease;
    }

    .panel-back .header {
      display: flex;
      align-items: center;
      gap: 10px;
      margin-bottom: 18px;
      border-bottom: 2px solid rgba(200, 170, 130, 0.2);
      padding-bottom: 14px;
      width: 100%;
    }
    .panel-back .header .heart {
      font-size: 28px;
      color: #c47a6a;
      animation: heartbeat 1.8s ease-in-out infinite;
    }
    @keyframes heartbeat {
      0%, 100% { transform: scale(1); }
      14% { transform: scale(1.25); }
      28% { transform: scale(1); }
      42% { transform: scale(1.15); }
      56% { transform: scale(1); }
    }
    .panel-back .header h2 {
      font-size: clamp(1.2rem, 4.5vw, 1.8rem);
      font-weight: 600;
      color: #2d3e4b;
    }
    .panel-back .header h2 span {
      color: #c47a6a;
    }

    .panel-back .message {
      font-size: clamp(0.95rem, 3vw, 1.15rem);
      line-height: 1.8;
      color: #3e4f5c;
      font-weight: 400;
      width: 100%;
    }
    .panel-back .message p {
      margin-bottom: 14px;
    }
    .panel-back .message .signature {
      text-align: right;
      font-style: italic;
      font-size: clamp(1rem, 3.2vw, 1.3rem);
      color: #2d3e4b;
      margin-top: 8px;
      border-top: 1px solid rgba(200, 170, 130, 0.2);
      padding-top: 16px;
    }
    .panel-back .message .signature strong {
      color: #b8895c;
      font-weight: 600;
    }

    .panel-back .deco-footer {
      margin-top: 18px;
      font-size: 18px;
      letter-spacing: 6px;
      color: #c9a87c;
      opacity: 0.3;
      width: 100%;
      text-align: center;
    }

    .panel-back .close-btn {
      position: absolute;
      top: 18px;
      right: 22px;
      font-size: 24px;
      color: #b0a28b;
      cursor: pointer;
      transition: color 0.2s;
      background: none;
      border: none;
      padding: 8px;
      line-height: 1;
      touch-action: manipulation;
    }
    .panel-back .close-btn:hover {
      color: #7a6b5a;
    }

    /* ── Confetti overlay ── */
    .confetti-container {
      position: fixed;
      inset: 0;
      pointer-events: none;
      z-index: 20;
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

    /* ── Responsive ── */
    @media (max-width: 480px) {
      .panel {
        padding: 32px 20px 28px;
        min-height: 420px;
      }
      .panel-back {
        padding: 28px 18px 24px;
      }
      .panel-front .icon-big {
        font-size: 52px;
      }
      .panel-back .header .heart {
        font-size: 24px;
      }
    }
    @media (max-width: 380px) {
      .panel {
        padding: 24px 16px 20px;
        min-height: 380px;
      }
      .panel-front .icon-big {
        font-size: 44px;
      }
      .panel-front h1 {
        font-size: 1.8rem;
      }
    }
  </style>
</head>
<body>

  <!-- ─── Confetti Container ─── -->
  <div class="confetti-container" id="confettiContainer"></div>

  <!-- ─── The Card ─── -->
  <div class="card" id="card">

    <!-- FRONT PANEL -->
    <div class="panel panel-front" id="panelFront">
      <div class="icon-big">👔</div>
      <h1>Happy <span class="gold">Father's</span> Day</h1>
      <div class="deco-line"></div>
      <div class="sub">with love</div>
      <div class="names">from <strong>Wan</strong> &amp; <strong>Senette</strong></div>
      <div class="tap-hint">✧ tap to open ✧</div>
    </div>

    <!-- BACK PANEL (message) -->
    <div class="panel panel-back" id="panelBack">
      <button class="close-btn" id="closeBtn" aria-label="Close card">✕</button>

      <div class="header">
        <span class="heart">❤️</span>
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

      <div class="deco-footer">✦ ✧ ✦ ✧ ✦</div>
    </div>

  </div>

  <script>
    (function() {
      const front = document.getElementById('panelFront');
      const back = document.getElementById('panelBack');
      const closeBtn = document.getElementById('closeBtn');
      const card = document.getElementById('card');
      let isOpen = false;

      // ─── Open card ───
      function openCard(e) {
        if (e) e.preventDefault();
        if (isOpen) return;
        isOpen = true;

        front.classList.add('slide-up');
        back.classList.add('open');
        launchConfetti();
      }

      // ─── Close card ───
      function closeCard(e) {
        if (e) e.preventDefault();
        if (!isOpen) return;
        isOpen = false;

        front.classList.remove('slide-up');
        back.classList.remove('open');
      }

      // ─── Event listeners ───
      // Tap front to open
      front.addEventListener('click', openCard);
      // Tap close button
      closeBtn.addEventListener('click', closeCard);
      // Also tap on back panel background (but not on close button) – we'll let the close button handle it, but we can also close on click outside the message? Not necessary.

      // Keyboard support
      card.setAttribute('tabindex', '0');
      card.addEventListener('keydown', function(e) {
        if (e.key === 'Enter' || e.key === ' ') {
          e.preventDefault();
          if (!isOpen) {
            openCard(e);
          } else {
            closeCard(e);
          }
        }
        if (e.key === 'Escape' && isOpen) {
          closeCard(e);
        }
      });

      // ─── Confetti (light) ───
      function launchConfetti() {
        const container = document.getElementById('confettiContainer');
        const colors = ['#f6c96e', '#d44a5a', '#4a8db7', '#f0e3d0', '#c47a3a', '#8ab3cf', '#ffb07c'];
        const count = 50;

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
          piece.style.boxShadow = '0 2px 6px rgba(0,0,0,0.10)';
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

      // ─── Prevent double-tap zoom on iOS ───
      let lastTouchEnd = 0;
      document.addEventListener('touchend', function(e) {
        const now = Date.now();
        if (now - lastTouchEnd <= 300) {
          e.preventDefault();
        }
        lastTouchEnd = now;
      }, { passive: false });

      console.log('💙 Father\'s Day card from Wan & Senette');
    })();
  </script>

</body>
</html>
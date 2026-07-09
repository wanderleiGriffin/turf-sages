<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Turf Sages · lawn mowing Hockley TX</title>
  <!-- Google Fonts & modern reset -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,400;14..32,500;14..32,600;14..32,700&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
      background: #f6f9f5;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 1.5rem;
      background-image: radial-gradient(circle at 10% 30%, rgba(60, 130, 70, 0.03) 0%, transparent 30%),
                        radial-gradient(circle at 90% 70%, rgba(40, 100, 50, 0.04) 0%, transparent 40%);
    }

    .card {
      max-width: 720px;
      width: 100%;
      background: rgba(255, 255, 255, 0.75);
      backdrop-filter: blur(12px);
      -webkit-backdrop-filter: blur(12px);
      border-radius: 48px;
      padding: 2.8rem 2.8rem 3.2rem;
      box-shadow: 0 30px 60px -20px rgba(20, 50, 30, 0.25),
                  0 8px 24px rgba(0, 0, 0, 0.02);
      border: 1px solid rgba(255, 255, 255, 0.5);
      transition: all 0.2s ease;
    }

    /* header */
    .logo {
      display: flex;
      align-items: center;
      gap: 0.5rem;
      margin-bottom: 0.6rem;
    }

    .logo-icon {
      background: #1e3d2b;
      color: #e2f0e0;
      width: 44px;
      height: 44px;
      border-radius: 16px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.6rem;
      font-weight: 500;
      box-shadow: 0 6px 12px rgba(30, 61, 43, 0.15);
    }

    .logo h1 {
      font-size: 2.1rem;
      font-weight: 700;
      letter-spacing: -0.02em;
      color: #1a2e20;
      margin-left: 4px;
    }

    .logo h1 span {
      font-weight: 400;
      color: #3f6b4c;
    }

    .tagline {
      font-size: 1rem;
      font-weight: 500;
      color: #3d5e48;
      background: rgba(60, 120, 70, 0.08);
      padding: 0.3rem 1rem;
      border-radius: 40px;
      display: inline-block;
      margin-top: 0.2rem;
      letter-spacing: 0.01em;
      border: 1px solid rgba(60, 120, 70, 0.08);
      backdrop-filter: blur(4px);
    }

    .divider {
      height: 2px;
      background: linear-gradient(90deg, rgba(50, 110, 60, 0.12), rgba(50, 110, 60, 0.02));
      margin: 1.8rem 0 2.2rem;
      width: 100%;
    }

    /* main form */
    .form-group {
      margin-bottom: 2.4rem;
    }

    .form-label {
      display: block;
      font-weight: 600;
      font-size: 1.1rem;
      color: #1c2f22;
      letter-spacing: -0.01em;
      margin-bottom: 0.6rem;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .form-label i {
      font-style: normal;
      background: #d9e8db;
      width: 24px;
      height: 24px;
      border-radius: 30px;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      font-size: 0.8rem;
      color: #1f402b;
    }

    .address-input-wrapper {
      position: relative;
      display: flex;
      align-items: center;
      background: white;
      border-radius: 60px;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.02), 0 0 0 1px rgba(40, 80, 50, 0.08);
      transition: box-shadow 0.25s, border-color 0.2s;
      border: 1px solid rgba(60, 110, 70, 0.10);
    }

    .address-input-wrapper:focus-within {
      box-shadow: 0 8px 20px rgba(40, 90, 50, 0.10), 0 0 0 3px rgba(50, 120, 70, 0.15);
      border-color: #2c7a3e;
    }

    .address-input-wrapper input {
      width: 100%;
      padding: 1.1rem 1.6rem;
      border: none;
      background: transparent;
      font-size: 1.05rem;
      font-weight: 500;
      color: #142018;
      outline: none;
      font-family: 'Inter', sans-serif;
      letter-spacing: -0.01em;
    }

    .address-input-wrapper input::placeholder {
      color: #8aa392;
      font-weight: 400;
      opacity: 0.7;
    }

    .address-input-wrapper .submit-btn {
      background: #1e3d2b;
      color: white;
      border: none;
      font-weight: 600;
      font-size: 0.95rem;
      padding: 0.7rem 1.8rem;
      border-radius: 60px;
      margin-right: 0.5rem;
      cursor: pointer;
      transition: all 0.15s ease;
      display: flex;
      align-items: center;
      gap: 0.5rem;
      white-space: nowrap;
      font-family: 'Inter', sans-serif;
      letter-spacing: 0.3px;
      box-shadow: 0 4px 10px rgba(30, 61, 43, 0.2);
    }

    .address-input-wrapper .submit-btn:hover {
      background: #14331f;
      transform: scale(0.96);
      box-shadow: 0 6px 14px rgba(20, 50, 30, 0.25);
    }

    .address-input-wrapper .submit-btn:active {
      transform: scale(0.94);
    }

    /* call manager */
    .call-section {
      margin: 1.6rem 0 0.2rem;
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: space-between;
      gap: 1rem;
      background: rgba(240, 248, 240, 0.5);
      padding: 0.9rem 1.6rem;
      border-radius: 60px;
      backdrop-filter: blur(4px);
      border: 1px solid rgba(60, 120, 70, 0.08);
    }

    .call-label {
      display: flex;
      align-items: center;
      gap: 0.6rem;
      font-weight: 500;
      color: #1d3a26;
      font-size: 0.98rem;
    }

    .call-label .phone-icon {
      background: #1e3d2b;
      color: white;
      width: 32px;
      height: 32px;
      border-radius: 40px;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      font-size: 1.1rem;
    }

    .call-btn {
      background: transparent;
      border: 1.5px solid #1e3d2b;
      color: #1e3d2b;
      font-weight: 600;
      padding: 0.5rem 1.8rem;
      border-radius: 60px;
      text-decoration: none;
      font-size: 0.95rem;
      transition: all 0.2s;
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      font-family: 'Inter', sans-serif;
      letter-spacing: 0.2px;
      background: rgba(255, 255, 255, 0.2);
      backdrop-filter: blur(4px);
    }

    .call-btn:hover {
      background: #1e3d2b;
      color: white;
      box-shadow: 0 8px 18px rgba(30, 61, 43, 0.2);
      border-color: #1e3d2b;
      transform: scale(1.01);
    }

    .call-btn:active {
      transform: scale(0.96);
    }

    .footnote {
      margin-top: 2.2rem;
      font-size: 0.8rem;
      color: #5a7a64;
      text-align: center;
      border-top: 1px solid rgba(60, 110, 70, 0.06);
      padding-top: 1.6rem;
      letter-spacing: 0.2px;
      display: flex;
      justify-content: center;
      gap: 1.6rem;
      flex-wrap: wrap;
    }

    .footnote span {
      opacity: 0.7;
    }

    /* toast / status + confirmation overlay */
    .status-message {
      margin-top: 1.2rem;
      padding: 0.6rem 1.2rem;
      border-radius: 60px;
      font-weight: 500;
      font-size: 0.9rem;
      text-align: center;
      background: rgba(40, 80, 50, 0.03);
      color: #1a3a22;
      border: 1px solid rgba(40, 80, 50, 0.02);
      transition: all 0.2s;
      min-height: 2.8rem;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 0.5rem;
    }

    .status-message.success {
      background: rgba(40, 130, 60, 0.06);
      border-color: rgba(40, 130, 60, 0.10);
      color: #124d20;
    }

    .status-message.error {
      background: rgba(180, 70, 50, 0.04);
      border-color: rgba(180, 70, 50, 0.08);
      color: #762f1f;
    }

    /* confirmation overlay (modal) */
    .confirmation-overlay {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(20, 40, 28, 0.45);
      backdrop-filter: blur(8px);
      -webkit-backdrop-filter: blur(8px);
      align-items: center;
      justify-content: center;
      z-index: 1000;
      padding: 1.5rem;
    }

    .confirmation-overlay.active {
      display: flex;
    }

    .confirmation-modal {
      background: #ffffff;
      max-width: 480px;
      width: 100%;
      border-radius: 48px;
      padding: 2.8rem 2.2rem 2.8rem;
      box-shadow: 0 40px 80px rgba(0, 0, 0, 0.15), 0 10px 30px rgba(0, 0, 0, 0.05);
      text-align: center;
      border: 1px solid rgba(255, 255, 255, 0.3);
      animation: modalFadeIn 0.3s ease;
    }

    @keyframes modalFadeIn {
      0% { opacity: 0; transform: scale(0.94) translateY(12px); }
      100% { opacity: 1; transform: scale(1) translateY(0); }
    }

    .confirmation-modal .check-icon {
      background: #1e3d2b;
      color: white;
      width: 72px;
      height: 72px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 2.6rem;
      margin: 0 auto 1.2rem;
      box-shadow: 0 8px 20px rgba(30, 61, 43, 0.15);
    }

    .confirmation-modal h2 {
      font-size: 1.7rem;
      font-weight: 700;
      color: #1a2e20;
      letter-spacing: -0.02em;
      margin-bottom: 0.4rem;
    }

    .confirmation-modal .subhead {
      color: #3f5f49;
      font-weight: 500;
      font-size: 1rem;
      margin-bottom: 1.2rem;
      border-bottom: 1px solid rgba(60, 110, 70, 0.06);
      padding-bottom: 1.2rem;
    }

    .confirmation-modal .address-display {
      background: #f2f8f2;
      padding: 0.9rem 1.2rem;
      border-radius: 60px;
      font-weight: 600;
      color: #1a3a22;
      margin-bottom: 1.6rem;
      font-size: 1rem;
      word-break: break-word;
      border: 1px solid rgba(40, 80, 50, 0.05);
    }

    .confirmation-modal .call-encouragement {
      background: #f1f7f0;
      padding: 1.2rem 1.2rem;
      border-radius: 30px;
      margin-bottom: 1.8rem;
      border: 1px solid rgba(60, 120, 70, 0.06);
    }

    .confirmation-modal .call-encouragement p {
      font-size: 0.95rem;
      color: #1d3a26;
      font-weight: 500;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 0.5rem;
      flex-wrap: wrap;
    }

    .confirmation-modal .call-encouragement .big-phone {
      font-size: 1.3rem;
      font-weight: 700;
      color: #1e3d2b;
      letter-spacing: 0.5px;
    }

    .confirmation-modal .modal-actions {
      display: flex;
      flex-wrap: wrap;
      gap: 0.8rem;
      justify-content: center;
      margin-top: 0.2rem;
    }

    .confirmation-modal .modal-btn {
      padding: 0.8rem 2rem;
      border-radius: 60px;
      font-weight: 600;
      font-size: 0.95rem;
      border: none;
      cursor: pointer;
      transition: all 0.15s ease;
      font-family: 'Inter', sans-serif;
      background: #eef3ee;
      color: #1f3d2a;
      border: 1px solid rgba(40, 80, 50, 0.06);
      flex: 1 1 auto;
      min-width: 120px;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 0.4rem;
    }

    .confirmation-modal .modal-btn.primary {
      background: #1e3d2b;
      color: white;
      box-shadow: 0 4px 12px rgba(30, 61, 43, 0.15);
      border-color: #1e3d2b;
    }

    .confirmation-modal .modal-btn.primary:hover {
      background: #14331f;
      transform: scale(0.97);
    }

    .confirmation-modal .modal-btn.secondary:hover {
      background: #dce6dc;
    }

    .confirmation-modal .modal-btn .phone-icon-sm {
      font-size: 1.1rem;
    }

    /* responsive */
    @media (max-width: 580px) {
      .card {
        padding: 2rem 1.5rem;
        border-radius: 32px;
      }
      .logo h1 {
        font-size: 1.6rem;
      }
      .address-input-wrapper {
        flex-direction: column;
        background: transparent;
        box-shadow: none;
        border: none;
        gap: 0.8rem;
        align-items: stretch;
      }
      .address-input-wrapper input {
        background: white;
        border-radius: 60px;
        padding: 1rem 1.4rem;
        border: 1px solid rgba(40, 80, 50, 0.08);
        box-shadow: 0 4px 12px rgba(0, 0, 0, 0.02);
      }
      .address-input-wrapper .submit-btn {
        margin-right: 0;
        justify-content: center;
        padding: 0.9rem;
      }
      .call-section {
        flex-direction: column;
        align-items: stretch;
        text-align: center;
        padding: 1.2rem 1.2rem;
      }
      .call-btn {
        justify-content: center;
      }
      .footnote {
        flex-direction: column;
        gap: 0.2rem;
      }
      .confirmation-modal {
        padding: 2rem 1.5rem;
      }
      .confirmation-modal .modal-actions {
        flex-direction: column;
      }
      .confirmation-modal .modal-btn {
        width: 100%;
      }
    }
  </style>
</head>
<body>
  <div class="card">
    <!-- header -->
    <div class="logo">
      <div class="logo-icon">🌿</div>
      <h1>Turf <span>Sages</span></h1>
    </div>
    <div class="tagline">✧ precision mowing · Hockley, TX</div>

    <div class="divider"></div>

    <!-- main address form -->
    <form id="addressForm" action="#" method="POST">
      <div class="form-group">
        <span class="form-label">
          <i>📍</i> service address
        </span>
        <div class="address-input-wrapper">
          <input 
            type="text" 
            id="addressInput" 
            placeholder="e.g. 123 Main St, Hockley, TX" 
            required
            autocomplete="street-address"
            aria-label="Your street address"
          >
          <button type="submit" class="submit-btn" id="submitBtn">
            <span>send</span>
            <span style="font-size: 1.2rem; line-height: 1;">→</span>
          </button>
        </div>
      </div>
    </form>

    <!-- status message (feedback) -->
    <div id="statusMessage" class="status-message">
      <span>🌱 enter your address &amp; we’ll reach out</span>
    </div>

    <!-- call manager -->
    <div class="call-section">
      <span class="call-label">
        <span class="phone-icon">📞</span> 
        <span>manager on duty</span>
      </span>
      <a href="tel:+16015978142" class="call-btn">
        <span>📱</span> 601-597-8142
      </a>
    </div>

    <div class="footnote">
      <span>🌾 same-day service</span>
      <span>✧ 5-star care</span>
      <span>📍 Hockley &amp; surrounding</span>
    </div>
  </div>

  <!-- CONFIRMATION OVERLAY (modal) -->
  <div id="confirmationOverlay" class="confirmation-overlay">
    <div class="confirmation-modal">
      <div class="check-icon">✓</div>
      <h2>address received</h2>
      <div class="subhead">we'll reach out shortly</div>
      <div class="address-display" id="confirmAddressDisplay">123 Main St, Hockley, TX</div>

      <!-- encouragement to call -->
      <div class="call-encouragement">
        <p>
          📞 <span>Prefer faster service? <br class="mobile-break" style="display: none;"> Call the manager directly:</span>
        </p>
        <p style="margin-top: 0.2rem; font-size: 1.2rem; font-weight: 700; color: #1e3d2b;">
          <a href="tel:+16015978142" style="text-decoration: none; color: #1e3d2b; display: inline-flex; align-items: center; gap: 0.4rem;">
            <span>📱</span> 601-597-8142
          </a>
        </p>
        <p style="font-size: 0.8rem; opacity: 0.7; margin-top: 0.2rem;">available now – same-day service</p>
      </div>

      <div class="modal-actions">
        <button class="modal-btn secondary" id="closeConfirmBtn">close</button>
        <a href="tel:+16015978142" class="modal-btn primary" style="text-decoration: none;">
          <span class="phone-icon-sm">📞</span> call manager
        </a>
      </div>
    </div>
  </div>

  <script>
    (function() {
      const form = document.getElementById('addressForm');
      const addressInput = document.getElementById('addressInput');
      const statusMessage = document.getElementById('statusMessage');
      const submitBtn = document.getElementById('submitBtn');

      // confirmation elements
      const overlay = document.getElementById('confirmationOverlay');
      const confirmAddressDisplay = document.getElementById('confirmAddressDisplay');
      const closeConfirmBtn = document.getElementById('closeConfirmBtn');

      // Target email
      const TARGET_EMAIL = 'wanderlei.griffin11@gmail.com';

      // Helper: show status message (inline, but we'll use modal on success)
      function setStatus(text, type = 'info') {
        statusMessage.innerHTML = text;
        statusMessage.className = 'status-message';
        if (type === 'success') {
          statusMessage.classList.add('success');
        } else if (type === 'error') {
          statusMessage.classList.add('error');
        }
      }

      // Show confirmation modal with address
      function showConfirmation(address) {
        confirmAddressDisplay.textContent = address;
        overlay.classList.add('active');
        document.body.style.overflow = 'hidden'; // prevent scroll
      }

      // Hide confirmation modal
      function hideConfirmation() {
        overlay.classList.remove('active');
        document.body.style.overflow = '';
      }

      // close via button
      closeConfirmBtn.addEventListener('click', hideConfirmation);

      // close if user clicks outside the modal content (on overlay)
      overlay.addEventListener('click', function(e) {
        if (e.target === overlay) {
          hideConfirmation();
        }
      });

      // Handle form submit
      function handleFormSubmit(e) {
        e.preventDefault();

        const address = addressInput.value.trim();
        if (!address) {
          setStatus('⚠️ please enter your address', 'error');
          addressInput.focus();
          return;
        }

        // Build the email content
        const subject = encodeURIComponent('New lawn mowing request – Turf Sages (Hockley, TX)');
        const body = encodeURIComponent(
          `Address: ${address}\n\n` +
          `---\n` +
          `Sent from Turf Sages website (direct request).\n` +
          `Manager contact: 601-597-8142\n` +
          `Service area: Hockley, TX`
        );

        const mailtoLink = `mailto:${TARGET_EMAIL}?subject=${subject}&body=${body}`;

        // 1) Open mail client (Gmail, etc.)
        try {
          window.open(mailtoLink, '_blank');
          // also try anchor fallback
          const anchor = document.createElement('a');
          anchor.href = mailtoLink;
          anchor.target = '_blank';
          anchor.style.display = 'none';
          document.body.appendChild(anchor);
          setTimeout(() => {
            if (!document.hidden) {
              anchor.click();
            }
            document.body.removeChild(anchor);
          }, 300);
        } catch (err) {
          // fallback: copy address
          navigator.clipboard?.writeText(address).catch(() => {});
        }

        // Show confirmation modal (with address and call encouragement)
        showConfirmation(address);

        // Update inline status (but modal is primary)
        setStatus(`✅ address recorded — check your mail client`, 'success');

        // Clear error state if any
        if (statusMessage.classList.contains('error')) {
          setStatus(`✅ address recorded`, 'success');
        }

        // Reset status after a while (but modal stays until dismissed)
        setTimeout(() => {
          if (!overlay.classList.contains('active')) {
            // only reset if modal is not active (user closed it)
            setStatus('🌱 enter your address &amp; we’ll reach out', 'info');
          }
        }, 8000);

        console.log(`🌿 Turf Sages address (Hockley, TX): ${address}`);
        console.log(`📧 sent to ${TARGET_EMAIL}`);
      }

      form.addEventListener('submit', handleFormSubmit);

      // Clear error state when user types
      addressInput.addEventListener('input', function() {
        if (statusMessage.classList.contains('error')) {
          setStatus('🌱 enter your address &amp; we’ll reach out', 'info');
        }
      });

      // Also if user closes modal, we reset status after a moment
      // but we keep the status as success.
      // We also ensure that when modal is closed, we don't override status
      // but we set a small timeout to reset after a while.
      // The hideConfirmation will be called by close or overlay click.
      // We'll keep status as success and later reset.

      // Additional: if modal is closed, we keep success message for a while.
      // We already have a timeout above.

      console.log('Turf Sages – modern lawn mowing, Hockley TX with confirmation & call encouragement');
    })();
  </script>
</body>
</html>

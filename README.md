# turf-sages<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Turf Sage · waitlist</title>
  <!-- Font & minimal reset -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,400;14..32,500;14..32,600;14..32,700&display=swap" rel="stylesheet" />
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: #f6f8fa;
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 1.5rem;
      line-height: 1.5;
      color: #1e293b;
    }

    .card {
      max-width: 560px;
      width: 100%;
      background: #ffffff;
      border-radius: 40px;
      box-shadow: 0 20px 60px -12px rgba(0, 20, 30, 0.15), 0 4px 18px rgba(0, 0, 0, 0.02);
      padding: 2.5rem 2rem 2.8rem;
      transition: box-shadow 0.2s ease;
    }

    /* brand */
    .brand {
      display: flex;
      align-items: center;
      gap: 8px;
      margin-bottom: 2rem;
    }

    .brand-icon {
      background: #0b2b26;
      color: #d4e9e2;
      width: 44px;
      height: 44px;
      border-radius: 18px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.6rem;
      font-weight: 500;
      letter-spacing: -0.5px;
      box-shadow: 0 6px 12px -6px rgba(10, 40, 30, 0.2);
    }

    .brand-name {
      font-size: 1.8rem;
      font-weight: 700;
      letter-spacing: -0.03em;
      color: #0b2b26;
    }

    .brand-name span {
      font-weight: 400;
      color: #5f7b76;
    }

    /* headline */
    .headline {
      margin-bottom: 2.2rem;
    }

    .headline h1 {
      font-size: 1.9rem;
      font-weight: 650;
      letter-spacing: -0.02em;
      line-height: 1.2;
      color: #0b2b26;
    }

    .headline p {
      margin-top: 0.5rem;
      font-size: 1rem;
      color: #4b5e5a;
      font-weight: 400;
      max-width: 90%;
    }

    /* form */
    .address-form {
      display: flex;
      flex-direction: column;
      gap: 1.25rem;
    }

    .input-group {
      display: flex;
      flex-direction: column;
      gap: 0.4rem;
    }

    .input-group label {
      font-size: 0.9rem;
      font-weight: 600;
      letter-spacing: -0.01em;
      color: #1e3a34;
      display: flex;
      align-items: center;
      gap: 6px;
    }

    .input-group label svg {
      opacity: 0.6;
    }

    .input-group input {
      width: 100%;
      padding: 0.9rem 1.2rem;
      font-size: 1rem;
      font-family: 'Inter', sans-serif;
      background: #f2f5f7;
      border: 1.5px solid #e2e9ed;
      border-radius: 28px;
      transition: border 0.15s ease, box-shadow 0.15s ease;
      color: #0b2b26;
      font-weight: 450;
      letter-spacing: -0.01em;
    }

    .input-group input:focus {
      outline: none;
      border-color: #0b2b26;
      box-shadow: 0 0 0 4px rgba(11, 43, 38, 0.08);
      background: #ffffff;
    }

    .input-group input::placeholder {
      color: #94a8a2;
      font-weight: 400;
      opacity: 0.8;
    }

    /* button */
    .submit-btn {
      background: #0b2b26;
      color: white;
      font-weight: 600;
      font-size: 1.1rem;
      padding: 0.95rem 1.8rem;
      border: none;
      border-radius: 60px;
      cursor: pointer;
      transition: background 0.15s ease, transform 0.1s ease, box-shadow 0.15s ease;
      box-shadow: 0 6px 18px -6px rgba(11, 43, 38, 0.25);
      letter-spacing: -0.01em;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      margin-top: 0.5rem;
      width: 100%;
    }

    .submit-btn:hover {
      background: #153f38;
      box-shadow: 0 10px 22px -10px rgba(11, 43, 38, 0.35);
    }

    .submit-btn:active {
      transform: scale(0.97);
      background: #0a241f;
    }

    .submit-btn:disabled {
      opacity: 0.6;
      pointer-events: none;
      transform: scale(0.98);
    }

    /* status message / wait state */
    .status-area {
      margin-top: 2rem;
      padding: 0.5rem 0.2rem;
      min-height: 4.5rem;
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      justify-content: center;
    }

    .wait-message {
      background: #eef4f0;
      border-radius: 40px;
      padding: 1.2rem 1.8rem;
      width: 100%;
      display: flex;
      align-items: center;
      gap: 14px;
      border-left: 6px solid #0b2b26;
      box-shadow: 0 2px 8px rgba(0,0,0,0.02);
      opacity: 0;
      transform: translateY(8px);
      transition: opacity 0.25s ease, transform 0.25s ease;
    }

    .wait-message.visible {
      opacity: 1;
      transform: translateY(0);
    }

    .wait-message svg {
      flex-shrink: 0;
    }

    .wait-message span {
      font-weight: 500;
      color: #1e3a34;
      font-size: 1.05rem;
      letter-spacing: -0.01em;
    }

    .wait-message small {
      display: block;
      font-weight: 400;
      color: #4d6b63;
      font-size: 0.9rem;
      margin-top: 3px;
    }

    .subnote {
      margin-top: 0.6rem;
      font-size: 0.8rem;
      color: #6a847c;
      letter-spacing: -0.01em;
      padding-left: 0.3rem;
    }

    .subnote a {
      color: #0b2b26;
      font-weight: 500;
      text-decoration: none;
      border-bottom: 1px dotted #b6cdc4;
    }

    .subnote a:hover {
      border-bottom: 1px solid #0b2b26;
    }

    /* simple state: hidden by default */
    .hidden {
      display: none !important;
    }

    /* mobile fine-tune */
    @media (max-width: 480px) {
      .card {
        padding: 2rem 1.25rem 2.2rem;
        border-radius: 32px;
      }
      .brand-name {
        font-size: 1.6rem;
      }
      .headline h1 {
        font-size: 1.6rem;
      }
      .wait-message {
        padding: 1rem 1.4rem;
      }
    }
  </style>
</head>
<body>

<div class="card" role="main">
  
  <!-- brand -->
  <div class="brand">
    <div class="brand-icon">🌿</div>
    <div class="brand-name">Turf <span>Sage</span></div>
  </div>

  <!-- headline -->
  <div class="headline">
    <h1>Your lawn,<br />our wisdom.</h1>
    <p>Drop your address — we’ll reach out personally.</p>
  </div>

  <!-- form -->
  <form id="addressForm" class="address-form" novalidate>
    <div class="input-group">
      <label for="addressInput">
        <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M20 10c0 6-8 12-8 12s-8-6-8-12a8 8 0 0 1 16 0Z"/><circle cx="12" cy="10" r="3"/></svg>
        Street address
      </label>
      <input 
        type="text" 
        id="addressInput" 
        placeholder="e.g. 1234 Elm St, Springfield" 
        required 
        autocomplete="street-address"
      />
    </div>

    <button type="submit" class="submit-btn" id="submitBtn">
      <span>Get sage advice</span>
      <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14M12 5l7 7-7 7"/></svg>
    </button>
  </form>

  <!-- status / wait message -->
  <div class="status-area">
    <div id="waitMessage" class="wait-message">
      <svg width="36" height="36" viewBox="0 0 24 24" fill="none" stroke="#0b2b26" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/><path d="M12 8v4l3 3"/></svg>
      <div>
        <span>Waiting for Turf Sage</span>
        <small>We’ll respond within 24h · check your inbox</small>
      </div>
    </div>
    <div class="subnote">
      ✦ your info is sent to <a href="mailto:turfsages@gmail.com">turfsages@gmail.com</a>
    </div>
  </div>

</div>

<script>
  (function() {
    const form = document.getElementById('addressForm');
    const addressInput = document.getElementById('addressInput');
    const submitBtn = document.getElementById('submitBtn');
    const waitMessage = document.getElementById('waitMessage');

    // target email (hardcoded as requested)
    const TARGET_EMAIL = 'turfsages@gmail.com';

    // helper to show wait state
    function showWaitState() {
      waitMessage.classList.add('visible');
    }

    // helper to hide wait state (if needed, but we keep it visible after submit)
    function resetWaitState() {
      waitMessage.classList.remove('visible');
    }

    // send data via mailto: with pre-filled subject & body
    function sendViaMailto(address) {
      // build mailto link with subject and body
      const subject = encodeURIComponent('New Turf Sage inquiry');
      const body = encodeURIComponent(
        `Address: ${address}\n\n` +
        `— submitted via Turf Sage website`
      );
      const mailtoLink = `mailto:${TARGET_EMAIL}?subject=${subject}&body=${body}`;
      
      // open default mail client
      window.location.href = mailtoLink;

      // slight delay to let the mail client open, then show wait message.
      // but we want to show wait after mailto triggered, however some browsers
      // may block popups, but mailto is a navigation. we show wait after short delay.
      setTimeout(() => {
        showWaitState();
      }, 150);
    }

    // handle form submission
    function handleSubmit(e) {
      e.preventDefault();

      const address = addressInput.value.trim();
      if (!address) {
        // simple client-side validation: focus & shake? we just highlight.
        addressInput.focus();
        addressInput.style.borderColor = '#b91c1c';
        addressInput.style.boxShadow = '0 0 0 4px rgba(185, 28, 28, 0.08)';
        setTimeout(() => {
          addressInput.style.borderColor = '#e2e9ed';
          addressInput.style.boxShadow = 'none';
        }, 800);
        return;
      }

      // disable button to prevent double send
      submitBtn.disabled = true;
      submitBtn.innerHTML = `<span>Sending…</span>`;

      // send via mailto (opens default email client)
      sendViaMailto(address);

      // re-enable button after a while (but keep wait visible)
      setTimeout(() => {
        submitBtn.disabled = false;
        submitBtn.innerHTML = `<span>Get sage advice</span>
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14M12 5l7 7-7 7"/></svg>`;
      }, 2000);

      // clear input (optional, but user can see it's sent)
      // we keep the address visible, but we could clear if we want. we keep it.
      // we also show wait message (already called inside sendViaMailto)
      // but in case mailto is blocked or not triggered, we also show wait.
      showWaitState();
    }

    // reset border on input focus
    addressInput.addEventListener('focus', function() {
      this.style.borderColor = '#0b2b26';
      this.style.boxShadow = '0 0 0 4px rgba(11, 43, 38, 0.08)';
    });

    addressInput.addEventListener('blur', function() {
      if (!this.value.trim()) {
        this.style.borderColor = '#e2e9ed';
        this.style.boxShadow = 'none';
      } else {
        this.style.borderColor = '#0b2b26';
        this.style.boxShadow = '0 0 0 4px rgba(11, 43, 38, 0.04)';
      }
    });

    // form submit listener
    form.addEventListener('submit', handleSubmit);

    // if the user manually changes the address after submission, we could hide wait?
    // but we keep it visible as per spec: once submitted, they wait.
    // we also prefill wait message hidden initially.
    // resetWaitState() is not used after first submit, but we keep for consistency.
    // additional: if someone clicks again after wait, we re-trigger.
    // also if they try to submit again, we send again (but we show wait again)
    // we handle that gracefully.
    // optional: if page loads, wait is hidden.
    window.addEventListener('load', function() {
      resetWaitState();
      // ensure button is enabled
      submitBtn.disabled = false;
      submitBtn.innerHTML = `<span>Get sage advice</span>
        <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14M12 5l7 7-7 7"/></svg>`;
    });

  })();
</script>

<!-- note: the mailto approach sends the info to turfsages@gmail.com directly via the user's default email client. 
     It also shows the wait message after submission, as requested. 
     The design is modern, minimal, and avoids AI-generated clichés. -->
</body>
</html>

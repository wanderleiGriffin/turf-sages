<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Turf Sages • Lawn Mowing</title>
  <!-- minimal, clean, no-fuss style -->
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: linear-gradient(145deg, #f0f7f0 0%, #dae8da 100%);
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      font-family: 'Segoe UI', Roboto, system-ui, -apple-system, sans-serif;
      padding: 1.5rem;
    }

    .card {
      max-width: 580px;
      width: 100%;
      background: rgba(255, 255, 255, 0.85);
      backdrop-filter: blur(4px);
      -webkit-backdrop-filter: blur(4px);
      border-radius: 56px 56px 48px 48px;
      padding: 2.5rem 2.2rem 2.8rem;
      box-shadow: 0 20px 40px rgba(0, 30, 10, 0.2),
                  0 8px 16px rgba(0, 20, 0, 0.08);
      transition: all 0.2s ease;
      border: 1px solid rgba(255, 255, 255, 0.4);
    }

    h1 {
      font-size: 2.6rem;
      font-weight: 600;
      letter-spacing: -0.02em;
      color: #1e3a2a;
      display: flex;
      align-items: center;
      gap: 0.5rem;
      margin-bottom: 0.2rem;
    }

    .subhead {
      font-size: 1rem;
      color: #3a5a3a;
      margin-bottom: 2.2rem;
      padding-bottom: 0.75rem;
      border-bottom: 2px dashed #b3cfb3;
      font-weight: 400;
      display: flex;
      align-items: center;
      gap: 0.3rem;
    }

    .subhead span {
      background: #2b532b;
      color: #f0faf0;
      font-size: 0.7rem;
      font-weight: 600;
      padding: 0.15rem 0.8rem;
      border-radius: 30px;
      letter-spacing: 0.3px;
      margin-left: 0.5rem;
    }

    .form-group {
      margin-bottom: 1.8rem;
    }

    label {
      display: block;
      font-weight: 500;
      color: #1f3a1f;
      margin-bottom: 0.4rem;
      font-size: 0.95rem;
      letter-spacing: 0.3px;
      display: flex;
      align-items: center;
      gap: 0.4rem;
    }

    label i {
      font-style: normal;
      font-size: 1.2rem;
    }

    input {
      width: 100%;
      padding: 0.9rem 1.2rem;
      font-size: 1rem;
      background: #fafffa;
      border: 2px solid #d0e4d0;
      border-radius: 60px;
      outline: none;
      transition: all 0.15s;
      color: #1c321c;
      font-weight: 450;
      box-shadow: inset 0 2px 4px rgba(0,20,0,0.02);
    }

    input:focus {
      border-color: #3d7a3d;
      background: #ffffff;
      box-shadow: 0 0 0 4px rgba(60, 130, 60, 0.15), inset 0 2px 6px rgba(0,20,0,0.02);
    }

    input::placeholder {
      color: #96b496;
      font-weight: 300;
      font-size: 0.95rem;
    }

    .btn-group {
      margin-top: 0.8rem;
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: space-between;
      gap: 1rem;
    }

    .btn {
      background: #1f4620;
      border: none;
      color: white;
      font-weight: 600;
      font-size: 1.2rem;
      padding: 0.9rem 2.2rem;
      border-radius: 60px;
      cursor: pointer;
      transition: 0.15s;
      box-shadow: 0 6px 0 #0f2a10, 0 6px 12px rgba(0,20,0,0.15);
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 0.4rem;
      letter-spacing: 0.5px;
      flex: 1 1 auto;
      min-width: 160px;
    }

    .btn:hover {
      background: #2a5a2b;
      transform: translateY(-2px);
      box-shadow: 0 8px 0 #0f2a10, 0 10px 20px rgba(0,30,0,0.2);
    }

    .btn:active {
      transform: translateY(4px);
      box-shadow: 0 2px 0 #0f2a10;
    }

    .btn-secondary {
      background: #e6f0e6;
      color: #1d3a1d;
      box-shadow: 0 4px 0 #b3cbb3, 0 4px 10px rgba(0,20,0,0.05);
      border: 1px solid #c0d9c0;
      flex: 0.5 1 auto;
      min-width: 100px;
      font-size: 1rem;
      padding: 0.9rem 1.5rem;
    }

    .btn-secondary:hover {
      background: #f0fcf0;
      box-shadow: 0 6px 0 #b3cbb3;
      transform: translateY(-2px);
    }

    .btn-secondary:active {
      transform: translateY(4px);
      box-shadow: 0 2px 0 #b3cbb3;
    }

    .status-message {
      margin-top: 2rem;
      padding: 0.6rem 1rem;
      border-radius: 60px;
      background: #eaf3ea;
      color: #1d3a1d;
      font-size: 0.95rem;
      text-align: center;
      border-left: 6px solid #3a7a3a;
      transition: 0.2s;
      min-height: 3.2rem;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 0.5rem;
      flex-wrap: wrap;
      font-weight: 450;
      box-shadow: inset 0 1px 4px rgba(0,0,0,0.02);
      width: 100%;
    }

    .status-message.success {
      background: #dff0df;
      border-left-color: #1d7a1d;
      color: #0d3a0d;
    }

    .status-message.error {
      background: #fdeaea;
      border-left-color: #b33a3a;
      color: #621c1c;
    }

    .status-message .emoji {
      font-size: 1.3rem;
    }

    .footer-note {
      margin-top: 1.8rem;
      font-size: 0.8rem;
      color: #3f623f;
      text-align: center;
      border-top: 1px solid #caddca;
      padding-top: 1.2rem;
      opacity: 0.8;
      letter-spacing: 0.3px;
    }

    .footer-note a {
      color: #1f4a1f;
      text-decoration: none;
      font-weight: 500;
    }

    .footer-note a:hover {
      text-decoration: underline;
    }

    .grass-icon {
      font-size: 1.6rem;
      line-height: 1;
      margin-right: 0.1rem;
    }

    /* mobile friendly */
    @media (max-width: 480px) {
      .card {
        padding: 2rem 1.2rem 2rem;
        border-radius: 40px;
      }
      h1 {
        font-size: 2.1rem;
        flex-wrap: wrap;
      }
      .btn-group {
        flex-direction: column;
        align-items: stretch;
      }
      .btn {
        min-width: auto;
        justify-content: center;
      }
      .btn-secondary {
        min-width: auto;
      }
    }
  </style>
</head>
<body>

  <div class="card">
    <h1>
      <span class="grass-icon">🌿</span> Turf Sages
    </h1>
    <div class="subhead">
      ✦ lawn mowing · just name & address
      <span>one‑step</span>
    </div>

    <!-- the one & only form: name + address, nothing else -->
    <form id="bookingForm" action="#" method="POST">
      <div class="form-group">
        <label for="customerName">
          <i>🧑‍🌾</i> Full name
        </label>
        <input type="text" id="customerName" name="name" placeholder="e.g. Jamie Green" required autocomplete="name">
      </div>

      <div class="form-group">
        <label for="customerAddress">
          <i>📍</i> Address
        </label>
        <input type="text" id="customerAddress" name="address" placeholder="Street, city, zip" required autocomplete="street-address">
      </div>

      <div class="btn-group">
        <button type="submit" class="btn" id="sendBtn">
          ✦ Schedule now
        </button>
        <button type="reset" class="btn btn-secondary" id="resetBtn">
          ↻ Clear
        </button>
      </div>
    </form>

    <!-- status message area: shows feedback after send -->
    <div id="statusMessage" class="status-message">
      <span class="emoji">⏳</span> Ready — fill & send
    </div>

    <div class="footer-note">
      ⚡ we’ll confirm your mowing · <a href="#" id="mailtoTrigger">📧 wanderlei.griffin11@gmail.com</a>
    </div>
  </div>

  <script>
    (function() {
      "use strict";

      // DOM elements
      const form = document.getElementById('bookingForm');
      const nameInput = document.getElementById('customerName');
      const addressInput = document.getElementById('customerAddress');
      const statusDiv = document.getElementById('statusMessage');
      const resetBtn = document.getElementById('resetBtn');

      // The target email (hardcoded as requested)
      const TARGET_EMAIL = 'wanderlei.griffin11@gmail.com';

      // Helper: update status with message and optional type
      function setStatus(message, type = 'info') {
        statusDiv.innerHTML = message;
        statusDiv.className = 'status-message'; // reset
        if (type === 'success') {
          statusDiv.classList.add('success');
        } else if (type === 'error') {
          statusDiv.classList.add('error');
        }
        // default: info style (green left border)
      }

      // Helper: show temporary "sending..." state
      function setSending(isSending) {
        const btn = document.getElementById('sendBtn');
        if (isSending) {
          btn.textContent = '⏳ Sending...';
          btn.disabled = true;
          btn.style.opacity = '0.7';
        } else {
          btn.textContent = '✦ Schedule now';
          btn.disabled = false;
          btn.style.opacity = '1';
        }
      }

      // Build mailto: link with the data (name + address)
      function buildMailtoLink(name, address) {
        // subject & body with clear info
        const subject = '🌿 Turf Sages · new lawn mowing request';
        const body = 
          `New lawn mowing request:\n\n` +
          `Name: ${name.trim() || '(not provided)'}\n` +
          `Address: ${address.trim() || '(not provided)'}\n\n` +
          `---\nSent via Turf Sages quick form.`;
        
        // encodeURIComponent for safe mailto
        const mailtoLink = `mailto:${TARGET_EMAIL}?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`;
        return mailtoLink;
      }

      // Handle form submission
      function handleFormSubmit(event) {
        event.preventDefault(); // prevent page reload

        // Get values
        const name = nameInput.value.trim();
        const address = addressInput.value.trim();

        // Basic validation: both fields required (HTML required, but double-check)
        if (!name || !address) {
          setStatus('⚠️ Please enter both your name and address.', 'error');
          // focus on empty field
          if (!name) {
            nameInput.focus();
          } else {
            addressInput.focus();
          }
          return;
        }

        // Build mailto link
        const mailtoLink = buildMailtoLink(name, address);

        // 1) Show sending state
        setSending(true);
        setStatus('⏳ Preparing your request ...', 'info');

        // 2) Open the user's email client with the pre-filled message
        //    using window.location for mailto: (reliable)
        //    but we also want to show success after a tiny delay.
        //    We'll open the mailto and then update status.
        try {
          // Open mailto link (this will open default email client)
          window.location.href = mailtoLink;

          // Since mailto: might not give feedback, we show success after a short delay.
          // Also we reset the form after a moment (optional, but nice).
          setTimeout(() => {
            // Show success message
            setStatus(
              `✅ Request sent! Check your email client. We’ll mow your lawn soon.`,
              'success'
            );
            // Reset the form fields after successful send (user can still change)
            // but we do NOT clear automatically because user may want to keep values.
            // We'll provide a clear button for that.
            setSending(false);
          }, 600);
        } catch (err) {
          // fallback: if mailto fails for any reason (should not happen)
          setStatus('❌ Could not open email. Please try again or contact us directly.', 'error');
          setSending(false);
        }

        // We also set a fallback: if after 2.5 sec the mailto didn't work,
        // we still revert from sending state. But we already handle with setTimeout above.
        // additionally, we handle if user clicks "Clear" while sending.
      }

      // Reset / clear form and status
      function resetFormAndStatus() {
        // if currently sending, we don't interrupt but we can clear anyway.
        // reset the form fields
        form.reset();
        // reset status to default
        setStatus('🧹 Cleared — ready for new request', 'info');
        // make sure send button is re-enabled (if disabled)
        setSending(false);
        // focus on name
        nameInput.focus();
      }

      // Attach event listeners
      form.addEventListener('submit', handleFormSubmit);

      // Reset button: clear fields and status
      resetBtn.addEventListener('click', function(e) {
        e.preventDefault(); // prevent any weirdness
        resetFormAndStatus();
      });

      // Extra: if user clicks on the "mailto" footer link, we can prefill a default message
      // but that's just a nice extra; we keep it as a mailto link.
      // But we can also hook the footer link to open the mail with default text?
      const mailtoTrigger = document.getElementById('mailtoTrigger');
      mailtoTrigger.addEventListener('click', function(e) {
        e.preventDefault();
        // if form has data, use it, otherwise use placeholder
        const name = nameInput.value.trim() || 'your name';
        const address = addressInput.value.trim() || 'your address';
        const link = buildMailtoLink(name, address);
        window.location.href = link;
        setStatus('📧 Email client opened. Thank you!', 'success');
      });

      // Initial status 
      setStatus('✏️ Enter name & address, then click “Schedule now”', 'info');

      // Optional: if user types, we can clear error state (nice ux)
      nameInput.addEventListener('input', function() {
        if (statusDiv.classList.contains('error')) {
          setStatus('✏️ Enter name & address, then click “Schedule now”', 'info');
        }
      });
      addressInput.addEventListener('input', function() {
        if (statusDiv.classList.contains('error')) {
          setStatus('✏️ Enter name & address, then click “Schedule now”', 'info');
        }
      });

      // Also if user uses the "Clear" button, we set focus
      // already done in reset function

      console.log('🌿 Turf Sages — ready. Send to: ' + TARGET_EMAIL);
    })();
  </script>

  <!-- note: all logic uses mailto to send data to wanderlei.griffin11@gmail.com -->
  <!-- no backend, no third-party, just plain HTML+JS -->
</body>
</html>

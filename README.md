<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TurfSage | Expert Lawn Care</title>

    <!-- Font Awesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">

    <style>
        /* ----- RESET & BASE ----- */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Roboto, system-ui, -apple-system, sans-serif;
            background: #f4f7f2;
            color: #1e2f23;
            line-height: 1.6;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 2rem 1.5rem;
        }

        /* ----- MAIN CARD (Glassmorphism / Secure feel) ----- */
        .container {
            max-width: 680px;
            width: 100%;
            background: rgba(255, 255, 255, 0.92);
            backdrop-filter: blur(6px);
            -webkit-backdrop-filter: blur(6px);
            border-radius: 2.5rem;
            padding: 2.8rem 2.5rem;
            box-shadow: 
                0 20px 60px rgba(30, 47, 35, 0.12),
                0 8px 24px rgba(0, 0, 0, 0.04),
                inset 0 1px 0 rgba(255, 255, 255, 0.7);
            border: 1px solid rgba(255, 255, 255, 0.3);
            transition: all 0.2s ease;
        }

        /* ----- HEADER / LOGO ----- */
        .logo {
            display: flex;
            align-items: center;
            gap: 0.6rem;
            margin-bottom: 0.3rem;
        }

        .logo i {
            font-size: 2.4rem;
            color: #2b5e3b;
            background: #e8f3e4;
            padding: 0.5rem;
            border-radius: 16px;
            box-shadow: inset 0 0 0 1px rgba(43, 94, 59, 0.15);
        }

        .logo h1 {
            font-size: 2rem;
            font-weight: 700;
            letter-spacing: -0.5px;
            color: #1a3a24;
        }

        .logo h1 span {
            color: #4a7c5c;
            font-weight: 300;
        }

        .tagline {
            font-size: 1rem;
            color: #426b4f;
            font-weight: 400;
            margin-top: -0.2rem;
            margin-bottom: 1.8rem;
            border-left: 4px solid #7faF8a;
            padding-left: 1rem;
            background: #f0f7ee;
            border-radius: 0 12px 12px 0;
            padding: 0.6rem 1rem;
        }

        .tagline i {
            margin-right: 0.5rem;
            color: #3d6b4a;
        }

        /* ----- SECURITY BADGE ----- */
        .trust-badge {
            display: flex;
            flex-wrap: wrap;
            gap: 1.2rem 1.8rem;
            background: #eaf3e7;
            padding: 0.8rem 1.4rem;
            border-radius: 60px;
            margin-bottom: 2rem;
            justify-content: center;
            border: 1px solid #cde0d0;
        }

        .trust-badge span {
            font-size: 0.85rem;
            font-weight: 500;
            color: #1f3f28;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .trust-badge i {
            color: #2b6e3b;
            font-size: 1rem;
        }

        /* ----- FORM ELEMENTS ----- */
        form {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }

        .form-group {
            display: flex;
            flex-direction: column;
            gap: 0.4rem;
        }

        .form-group label {
            font-weight: 600;
            font-size: 0.95rem;
            color: #1f3a27;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .form-group label i {
            color: #3d7a4e;
            width: 1.2rem;
            font-size: 1rem;
        }

        .form-group input {
            padding: 0.9rem 1.2rem;
            border: 1.5px solid #d6e4d4;
            border-radius: 16px;
            font-size: 1rem;
            transition: all 0.2s ease;
            background: white;
            color: #1a2f1f;
            font-family: inherit;
        }

        .form-group input:focus {
            outline: none;
            border-color: #2b6e3b;
            box-shadow: 0 0 0 4px rgba(43, 110, 59, 0.15);
        }

        .form-group input::placeholder {
            color: #a3bca5;
            font-weight: 300;
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1rem;
        }

        /* ----- ACTION BUTTONS ROW (Call + Submit side by side) ----- */
        .action-row {
            display: grid;
            grid-template-columns: 1fr 1.2fr;
            gap: 1rem;
            margin-top: 0.3rem;
            align-items: stretch;
        }

        /* Call Button (Phone) */
        .call-btn {
            background: #ffffff;
            color: #1f452b;
            border: 2px solid #1f452b;
            padding: 1.1rem 1.2rem;
            border-radius: 60px;
            font-weight: 700;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.2s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.7rem;
            text-decoration: none;
            font-family: inherit;
            box-shadow: 0 4px 12px rgba(31, 69, 43, 0.08);
        }

        .call-btn:hover {
            background: #1f452b;
            color: white;
            transform: translateY(-2px);
            box-shadow: 0 8px 24px rgba(31, 69, 43, 0.20);
        }

        .call-btn:active {
            transform: translateY(0px);
        }

        .call-btn i {
            font-size: 1.2rem;
        }

        /* Submit Button */
        .submit-btn {
            background: #1f452b;
            color: white;
            border: none;
            padding: 1.1rem 1.5rem;
            border-radius: 60px;
            font-weight: 700;
            font-size: 1.1rem;
            letter-spacing: 0.3px;
            cursor: pointer;
            transition: all 0.2s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.8rem;
            box-shadow: 0 8px 24px rgba(31, 69, 43, 0.25);
            border: 1px solid rgba(255, 255, 255, 0.1);
            font-family: inherit;
        }

        .submit-btn:hover {
            background: #14361e;
            transform: translateY(-2px);
            box-shadow: 0 12px 32px rgba(31, 69, 43, 0.35);
        }

        .submit-btn:active {
            transform: translateY(0px);
            box-shadow: 0 4px 12px rgba(31, 69, 43, 0.2);
        }

        .submit-btn i {
            font-size: 1.1rem;
        }

        /* Disabled state */
        .submit-btn:disabled {
            opacity: 0.7;
            cursor: not-allowed;
            transform: none;
        }

        /* ----- SUCCESS MESSAGE (hidden by default) ----- */
        #success-message {
            display: none;
            background: #e6f5e6;
            border: 1px solid #8fbf8f;
            border-radius: 18px;
            padding: 1.5rem 1.8rem;
            margin-top: 1.5rem;
            text-align: center;
            color: #1d4a27;
            font-weight: 500;
        }

        #success-message i {
            font-size: 2.2rem;
            color: #2b7a3b;
            display: block;
            margin-bottom: 0.5rem;
        }

        /* ----- FOOTER NOTE ----- */
        .secure-note {
            margin-top: 1.8rem;
            font-size: 0.85rem;
            color: #5c7a62;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.6rem;
            flex-wrap: wrap;
            border-top: 1px solid #dde8db;
            padding-top: 1.5rem;
        }

        .secure-note i {
            color: #3d7a4e;
        }

        /* ----- RESPONSIVE ----- */
        @media (max-width: 600px) {
            .container {
                padding: 1.8rem 1.2rem;
                border-radius: 1.8rem;
            }

            .logo h1 {
                font-size: 1.6rem;
            }

            .form-row {
                grid-template-columns: 1fr;
                gap: 0.8rem;
            }

            /* Stack buttons vertically on mobile */
            .action-row {
                grid-template-columns: 1fr;
                gap: 0.8rem;
            }

            .call-btn {
                padding: 0.9rem 1rem;
                font-size: 1rem;
            }

            .submit-btn {
                padding: 0.9rem 1rem;
                font-size: 1rem;
            }

            .trust-badge {
                border-radius: 28px;
                padding: 0.6rem 1rem;
                gap: 0.8rem;
            }

            .trust-badge span {
                font-size: 0.75rem;
            }
        }

        /* small extra touch */
        .highlight {
            background: #d8edda;
            border-radius: 8px;
            padding: 0.1rem 0.4rem;
            color: #1f4a28;
        }
    </style>
</head>
<body>

    <div class="container">

        <!-- Logo & Brand -->
        <div class="logo">
            <i class="fas fa-seedling"></i>
            <h1>Turf<span>Sage</span></h1>
        </div>
        <div class="tagline">
            <i class="fas fa-quote-left"></i> Wisdom grows here — expert care for living landscapes.
        </div>

        <!-- Trust / Security Badges -->
        <div class="trust-badge">
            <span><i class="fas fa-lock"></i> 256-bit encrypted</span>
            <span><i class="fas fa-shield-alt"></i> Your data is private</span>
            <span><i class="fas fa-check-circle"></i> Licensed & insured</span>
        </div>

        <!-- 
            ⚡ Form: Sends to wanderlei.griffin11@gmail.com via Formspree
        -->
        <form id="turf-form" action="https://formspree.io/f/xqakvwzr" method="POST">

            <!-- Honeypot: helps block spam -->
            <input type="text" name="_gotcha" style="display:none" />

            <!-- Customer Address -->
            <div class="form-group">
                <label for="address"><i class="fas fa-map-pin"></i> Your full street address</label>
                <input 
                    type="text" 
                    id="address" 
                    name="address" 
                    placeholder="e.g. 1234 Maple Drive, Springfield, IL 62701"
                    required
                >
            </div>

            <!-- Name & Phone -->
            <div class="form-row">
                <div class="form-group">
                    <label for="name"><i class="fas fa-user"></i> Your name</label>
                    <input 
                        type="text" 
                        id="name" 
                        name="name" 
                        placeholder="John Doe"
                    >
                </div>
                <div class="form-group">
                    <label for="phone"><i class="fas fa-phone-alt"></i> Phone number</label>
                    <input 
                        type="tel" 
                        id="phone" 
                        name="phone" 
                        placeholder="(555) 123-4567"
                    >
                </div>
            </div>

            <!-- Extra note -->
            <div class="form-group">
                <label for="note"><i class="fas fa-pencil-alt"></i> Anything else?</label>
                <input 
                    type="text" 
                    id="note" 
                    name="message" 
                    placeholder="e.g. Backyard needs extra attention, or best time to call..."
                >
            </div>

            <!-- ACTION ROW: Call + Submit side by side -->
            <div class="action-row">
                <!-- CALL BUTTON — your phone number -->
                <a href="tel:+16015978142" class="call-btn">
                    <i class="fas fa-phone"></i> Call Us
                </a>

                <!-- SUBMIT BUTTON -->
                <button type="submit" class="submit-btn" id="submitBtn">
                    <i class="fas fa-paper-plane"></i> Get Estimate
                </button>
            </div>

            <!-- Success message (shows after form submission) -->
            <div id="success-message">
                <i class="fas fa-check-circle"></i>
                <strong>You're all set, neighbor!</strong><br>
                Your address has been sent securely to TurfSage. 
                We'll reach out within 24 hours with your custom plan.
            </div>

        </form>

        <!-- Footer security reassurance + phone number visible -->
        <div class="secure-note">
            <i class="fas fa-lock"></i> 
            SSL-secured &bull; 
            <i class="fas fa-phone" style="margin-left:0.3rem;"></i> 
            <strong>601-597-8142</strong> &bull; 
            <i class="fas fa-tree" style="margin-left:0.3rem;"></i>
        </div>

    </div>

    <!-- ----- JAVASCRIPT: handle form submit via fetch (no redirect) ----- -->
    <script>
        (function() {
            const form = document.getElementById('turf-form');
            const successDiv = document.getElementById('success-message');
            const submitBtn = document.getElementById('submitBtn');

            form.addEventListener('submit', function(e) {
                e.preventDefault(); // prevent page reload

                const formData = new FormData(form);

                // Show loading state
                submitBtn.disabled = true;
                submitBtn.innerHTML = '<i class="fas fa-spinner fa-spin"></i> Sending...';

                fetch(form.action, {
                    method: 'POST',
                    body: formData,
                    headers: {
                        'Accept': 'application/json'
                    }
                })
                .then(response => {
                    if (response.ok) {
                        // Show success
                        successDiv.style.display = 'block';
                        submitBtn.innerHTML = '<i class="fas fa-check"></i> Sent!';
                        form.reset(); // clear all fields
                    } else {
                        alert('Oops! Something went wrong. Please try again or call us directly.');
                        submitBtn.innerHTML = '<i class="fas fa-paper-plane"></i> Get Estimate';
                        submitBtn.disabled = false;
                        successDiv.style.display = 'none';
                    }
                })
                .catch(error => {
                    alert('Network error. Please check your connection and try again.');
                    submitBtn.innerHTML = '<i class="fas fa-paper-plane"></i> Get Estimate';
                    submitBtn.disabled = false;
                    successDiv.style.display = 'none';
                });
            });

        })();
    </script>

    <!-- 
        🔐 NOTES:
        - Phone number: 601-597-8142 appears in the Call button AND in the footer.
        - The "Call Us" button uses tel: protocol — on mobile it opens the dialer.
        - Form submissions go to wanderlei.griffin11@gmail.com via Formspree.
        - All data is sent over HTTPS.
    -->

</body>
</html>
